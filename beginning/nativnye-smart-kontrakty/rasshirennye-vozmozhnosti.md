---
description: Ещё немного интересной инфы про KLYNTAR VM
cover: ../../.gitbook/assets/4439981.jpg
coverY: -260.62833432128036
---

# 💪 Расширенные возможности

### <mark style="color:red;">**Как KLYNTAR рассчитывает энергию для выполнения смарт-контрактов**</mark>

Выполнение смарт-контрактов должно быть контролируемым - нам ведь не нужно чтоб наш процессор сгорел и нода остановилась. Нужно учитывать тот факт, что внутри байт-кода злоумышленник попытается спрятать бесконечный цикл или ещё каким-то образом повлиять на нормальный поток работы.

Кроме того, надо контролировать и то, сколько ресурсов будет потрачено при работе ноды. Ведь запуск функции которая просто возвращает сумму a+b явно требует меньше, чем цикл с 10 000 итераций.

В KLYNTAR VM мы будем использовать проект от EWASM для измерения работы смарт-контрактов. Вот их GitHub

![](<../../.gitbook/assets/image (1) (2).png>)

{% embed url="https://github.com/ewasm" %}

Нам необходим репозиторий _<mark style="color:red;">**wasm-metering**</mark>_ который предоставляет функцию, которую необходимо инжектировать внутрь байт-кода для измерения его выполнения

![](<../../.gitbook/assets/image (1) (1) (1).png>)

На выходе мы получим  аналогичный по функционалу байт-код, но теперь выполнение операций контролируемо и идёт расчёт затрачиваемых ресурсов. Проведём небольшое исследование

### <mark style="color:red;">**Разбираемся детальней**</mark>

Для этого, в README проекта представлен пример:

```javascript
const fs = require('fs')
const metering = require('wasm-metering')

const wasm = fs.readFileSync('fac.wasm')
const meteredWasm = metering.meterWASM(wasm, {
  meterType: 'i32'
})

const limit = 90000000
let gasUsed = 0

const mod = WebAssembly.Module(meteredWasm.module)
const instance = WebAssembly.Instance(mod, {
  'metering': {
    'usegas': (gas) => {
      gasUsed += gas
      if (gasUsed > limit) {
        throw new Error('out of gas!')
      }
    }
  }
})

const result = instance.exports.fac(6)
console.log(`result:${result}, gas used ${gasUsed * 1e-4}`) // result:720, gas used 0.4177
```

Здесь определяется глобальная переменная gasUsed и лимит газа. Как видно из этих строчек, модуль берёт голый байт-код и возвращает изменённый байт-код куда инжектит ссылку на функцию извне(в данном случае это функция _<mark style="color:purple;">**usegas**</mark>_ из импортируемого объекта _<mark style="color:red;">**metering**</mark>_).

При превышении лимита - работа останавливается и мы ловим исключения. Хоть документация EWASM и описывает принцип работы, мы всё же не просто услышим, но и увидим как это работает.

Кстати, вот детальное и хорошее описание на GitHub

![](<../../.gitbook/assets/image (52).png>)

{% embed url="https://github.com/ewasm/design/blob/master/metering.md" %}

### <mark style="color:red;">Смотрим на видоизменённый WASM модуль</mark>

После того, как произойдут изменения над нашим модулем, давайте запишем этот набор байт в .wasm файл, а затем декомпилируем в .wat откуда можно будет посмотреть на внутренности

Изначальный AssemblyScript модуль. Выберем что-то более сложное, например цикл

```typescript
export function testAdding(a: i32, b: i32 ): i32 {

    let sum:i32 = 0;

    for(let i:i32=0;i<a;i++){

        sum+=b

    }

    return sum;
   
}
```

Хоть это можно было сделать через умножение, всё же сделаем так.

Получаем .wasm код

```
asc test.ts -o test.wasm -O3z
```

Запись в .wasm

```javascript
import metering from 'wasm-metering'
import fs from 'fs'

const wasm = fs.readFileSync('test.wasm')

const meteredWasm = metering.meterWASM(wasm,{
    meterType: 'i32'
})

fs.writeFileSync('metered.wasm',meteredWasm)

console.log('Default module => ',wasm)
console.log('After injection => ',meteredWasm)
```

Получим такой вывод

```
Default module =>  <Buffer 00 61 73 6d 01 00 00 00 01 07 01 60 02 7f 7f 01 7f 03 02 01 00 05 03 01 00 00 07 17 02 0a 74 65 73 74 41 64 64 69 6e 67 00 00 06 6d 65 6d 6f 72 79 02 ... 38 more bytes>
After injection =>  <Buffer 00 61 73 6d 01 00 00 00 01 0b 02 60 02 7f 7f 01 7f 60 01 7f 00 02 13 01 08 6d 65 74 65 72 69 6e 67 06 75 73 65 67 61 73 00 01 03 02 01 00 05 03 01 00 ... 83 more bytes>
```

Видно что размер увеличился и сейчас будет видно почему. Прежде, протестируем работу

```javascript
import loader from '@assemblyscript/loader'
import metering from 'wasm-metering'
import fs from 'fs'

const wasm = fs.readFileSync('test.wasm')

const meteredWasm = metering.meterWASM(wasm,{
    meterType: 'i32'
})

const energyLimit = 2000000
let energyUsed = 0

let wasmMetered = await loader.instantiate(meteredWasm,{
    'metering': {
      'usegas': (energy) => {
        energyUsed += energy
        if (energyUsed > energyLimit) {
          throw new Error('No more energy!')
        }
      }
    }
});

const result = wasmMetered.exports.testAdding(8,20);

console.log(`Result:${result}, energy used ${energyUsed * 1e-4}`);
```

```
Result:160, energy used 1.0672000000000001
```

Декомпиляция в .wat

```
wasm2wat metered.wasm
```

И смотрим на файл

```wasm
(module
 (type $i32_=>_none (func (param i32)))
 (type $i32_i32_=>_i32 (func (param i32 i32) (result i32)))
 (import "metering" "usegas" (func $fimport$0 (param i32)))
 (memory $0 0)
 (export "testAdding" (func $0))
 (export "memory" (memory $0))
 (func $0 (param $0 i32) (param $1 i32) (result i32)
  (local $2 i32)
  (local $3 i32)
  (call $fimport$0
   (i32.const 92)
  )
  (loop $label$1
   (call $fimport$0
    (i32.const 377)
   )
   (if
    (i32.gt_s
     (local.get $0)
     (local.get $2)
    )
    (block
     (call $fimport$0
      (i32.const 872)
     )
     (local.set $3
      (i32.add
       (local.get $1)
       (local.get $3)
      )
     )
     (local.set $2
      (i32.add
       (local.get $2)
       (i32.const 1)
      )
     )
     (br $label$1)
    )
   )
  )
  (call $fimport$0
   (i32.const 211)
  )
  (local.get $3)
 )
)

```

Видим нашу функцию

```wasm
 (import "metering" "usegas" (func $fimport$0 (param i32)))
```

Таким образом везде в коде где будет встречаться вызов этой функции, мы будем понимать что идёт счёт газа(энергии). Так можно заметить, что функция вызывается при входе в главную функцию _<mark style="color:purple;">**testAdding**</mark>_, в начале цикла, при возврате из функции и так далее.

С помощью этих инструментов можете сами поиграть и протестировать механику работы

### <mark style="color:red;">**Зачем всё это**</mark>

На основании этих и представленных ранее механизмов мы и предоставим мощность и силу возможностей KLYNTAR.

Вы сможете с помощью расчётных таблиц назначать цену опкодам за выполнение, предоставлять доступ к импортируемым объектам, предоставлять разные API для контрактов и многое другое. Каждый симбиот может самостоятельно конфигурировать свою виртуальную машину.

{% hint style="info" %}
Следите за обновлениями на этой странице чтобы не пропускать ничего важного
{% endhint %}

### <mark style="color:red;">**Ссылки**</mark>

{% embed url="https://ewasm.readthedocs.io/en/mkdocs/" %}
