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

![](<../../.gitbook/assets/image (1).png>)

{% embed url="https://github.com/ewasm" %}

Нам необходим репозиторий _<mark style="color:red;">**wasm-metering**</mark>_ который предоставляет функцию, которую необходимо инжектировать внутрь байт-кода для измерения его выполнения

![](../../.gitbook/assets/image.png)

На выходе мы получим  аналогичный по функционалу байт-код, но теперь выполнение операций контролируемо и идёт расчёт затрачиваемых ресурсов. Для этого, в README проекта представлен пример:

### <mark style="color:red;">**Разбираемся детальней**</mark>

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

Здесь определяется глобальная переменная gasUsed и лимит газа. Как видно из этих строчек, модуль берёт голый байт-код и возвращает изменённый байт-код куда инжектит&#x20;



![](<../../.gitbook/assets/image (52).png>)

{% embed url="https://github.com/ewasm/design/blob/master/metering.md" %}

\*сюда картинку с .wat файлом с инжектнутым измерением



### <mark style="color:red;">**Ссылки**</mark>

{% embed url="https://ewasm.readthedocs.io/en/mkdocs/" %}
