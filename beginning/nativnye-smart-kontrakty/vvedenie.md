---
description: Пару слов о KLYNTAR VM
cover: >-
  ../../.gitbook/assets/vaporwave_artwork_science_fiction_concept_art_original_4k_hd.jpg
coverY: -300.46235921754595
---

# ℹ Введение

### <mark style="color:red;">**Начало**</mark>

![](../../.gitbook/assets/661117a8aa30d80eb2d4e156fe6ad384.png)

Сегодня необходимость смарт-контрактов в блокчейнах фактически обязательная, ведь позволяет писать кастомную логику в виде контрактов которые потом живут и выполняются в децентрализованной среде.

В KLYNTAR мы старались быть максимально универсальными для того, чтоб позволить вам легко и быстро начать писать что-либо для KLYNTAR. Вы сможете писать на любом языке который вы хорошо знаете и который компилируется в WASM модули, а так же использовать расширенные возможности такие как запросы в сеть или хранения больших данных "вне блокчейна" симбиота которые могут быть запрошены для выполнения некоторой функции и многое другое.

В основе KLYNTAR VM - WebAssembly который позволяет вам писать на любом языке, затем скомпилировать его в .wasm байткод и запускать в безопасной среде.

WebAssembly безопасный благодаря

* Отсутствию доступа к сети
* Отсутствию доступа к файловой системе
* Отсутствию доступа к генератору рандомных чисел

Таким образом, можно локально(у вас в среде разработки, если вы разработчик) создавать сжатые и скомпилированные .wasm файлы, а затем публиковать их в сети KLYNTAR для выполнения.

![](<../../.gitbook/assets/image (24).png>)

### <mark style="color:red;">**Больше про WebAssembly**</mark>

Сегодня WebAssembly становится популярным по всему миру и в разных сферах - от небольших модулей для работы в браузере до облачных FaaS сервисов и блокчейнов(Cosmos,Near и т.д.).&#x20;

Ниже представлен список языков которые уже можно использовать для компиляции в WASM и безопасно выполнять их работу на симбиотах KLYNTAR

![](<../../.gitbook/assets/image (37).png>)

{% embed url="https://github.com/appcypher/awesome-wasm-langs" %}

WebAssembly - это не совсем язык, это скорее низкоуровневый байт-код который выполняется быстро и безопасно. Для наглядного примера, можно рассмотреть формат .wat файла - это файлы так называемого WebAssemblyText. Его тоже можно компилировать в wasm и обратно. Так к примеру вы можете повторить эту процедуру используя инструменты wat2wasm(очевидно что _<mark style="color:purple;">**.wat**</mark>_ => _<mark style="color:purple;">**.wasm**</mark>_) и wasm2wat(наоборот). Как раз таки .wat файлы и позволяют нам увидеть опкоды WASM, понять что тут идёт работа со стеком подобно низкоуровневым языкам и так далее. Вот к примеру реализация простой функции которая принимает 2 параметра и возвращает их сумму

Файл _<mark style="color:red;">**add.wat**</mark>_

```wasm
(module
 (func (export "calculate")
 (param $value_1 i32) (param $value_2 i32)
 (result i32)
    local.get $value_1
    local.get $value_2
    i32.add
    )
)
```

Затем, мы используем инструмент _<mark style="color:purple;">**wat2wasm**</mark>_ который идёт в пакете _<mark style="color:red;">**wat-wasm**</mark>_

![](<../../.gitbook/assets/image (67).png>)

{% embed url="https://github.com/battlelinegames/wat-wasm" %}

Компилируем(с помощью флагов -O3z максимально сжимаем и проводим оптимизацию)

```bash
wat2wasm add.wat -o add.wasm -O3z
```

И используем в JavaScript(Node.js)

```javascript
import fs from 'fs';
const bytes = fs.readFileSync (__dirname+'/add.wasm');

let value_1 = parseInt (process.argv[2]);
let value_2 = parseInt (process.argv[3]);

let obj = await WebAssembly.instantiate(new Uint8Array(bytes));

let add_value = obj.instance.exports.calculate(value_1,value_2);

console.log(`${value_1}+${value_2}=${add_value}`);
```

```bash
node test.js 11 33
```

```bash
11+33=44
```

Это был простой пример использования и вы просматривая код .wat файла немножко больше узнали про его формат.

Конечно, на чистом WAT писать сложно и поэтому вы, скорее всего будете использовать высокоуровневые языки типа AssemblyScript(надстройка над TypeScript), Rust, C++, Python и прочие.

Мы как раз таки и начнём использовать AssemblyScript в качестве первой точки входа для .wasm смарт-контрактов на KLYNTAR.

![](<../../.gitbook/assets/image (123) (1).png>)

{% embed url="https://github.com/AssemblyScript/assemblyscript" %}

Позднее, добавятся и другие. Вот несколько интересных тематических репозиториев

![](<../../.gitbook/assets/image (120) (1).png>)

![](<../../.gitbook/assets/image (121).png>)

![](<../../.gitbook/assets/image (122) (1).png>)

### <mark style="color:red;">**KLYNTAR VM и симбиоты**</mark>

Виртуальная машина KLYNTAR индивидуальная для каждого симбиота в плане возможностей и таблицы затрат. Для своей работы она использует такой ресурс который называется _<mark style="color:red;">**энергия**</mark>_**.** Мы решили так назвать аналогию с газом на Ethereum, но с тем лишь отличием, что понятие энергии является более глобальным.

Как мы знаем из физики

> Энергия ниоткуда не берётся и никуда не девается, а лишь переходит из одного состояния в другое

С этой мыслю мы и продолжаем работать над KLYNTAR VM. Вы сможете запускать виртуальную машину за токены, за уровень полезности вашего сервиса, за количество унобтаниума и многое другое.

Тем не менее, в целом, суть энергии как ресурса на KLYNTAR будет аналогична сути газа в EVM машинах - обеспечить расчёт стоимости затраченных ресурсов для выполнения смарт-контракта(его функций).

Благодаря принципу мутаций, каждый симбиот индивидуально назначает себе возможности KLYNTAR VM и расчётную таблицу. Вы сможете даже сделать бесплатным выполнения смарт-контрактов, построить собственное дерево кому разрешено запускать какой-смарт контракт бесплатно и так далее. Это дарит гибкость и позволяет равномерно распределять нагрузку между симбиотами.

### <mark style="color:red;">**Расчётная таблица**</mark>

Ранее мы показали вам простую функцию в файле _<mark style="color:red;">**add.wat**</mark>_ и там вы могли наблюдать, что в WebAssembly используются байт-коды. Для симбиота можно будет настроить конфигурацию виртуальной машины так, чтоб самостоятельно настраивать сколько энергии будет потреблять каждый опкод.

Вот пример **vmEnergyTable.json из** dev\_controller workflow.

{% embed url="https://github.com/KLYN74R/KlyntarCore/blob/main/KLY_Workflows/dev_controller/vmEnergyTable.json" %}

```json
{
    "start": 0,
    "type": {
      "params": {
        "DEFAULT": 0
      },
      "return_type": {
        "DEFAULT": 0
      }
    },
    "import": 0,
    "code": {
      "locals": {
        "DEFAULT": 1
      },
      "code": {
        "get_local": 120,
        "set_local": 120,
        "tee_local": 120,
        "get_global": 120,
        "set_global": 120,
  
        "load8_s": 120,
        "load8_u": 120,
        "load16_s": 120,
        "load16_u": 120,
        "load32_s": 120,
        "load32_u": 120,
        "load": 120,
  
        "store8": 120,
        "store16": 120,
        "store32": 120,
        "store": 120,
  
        "grow_memory": 10000,
        "current_memory": 100,
  
        "nop": 1,
        "block": 1,
        "loop": 1,
        "if": 1,
        "then": 90,
        "else": 90,
        "br": 90,
        "br_if": 90,
        "br_table": 120,
        "return": 90,
  
        "call": 90,
        "call_indirect": 10000,
  
        "const": 1,
  
        "add": 90,
        "sub": 45,
        "mul": 45,
        "div_s": 36000,
        "div_u": 36000,
        "rem_s": 36000,
        "rem_u": 36000,
        "and": 45,
        "or": 45,
        "xor": 45,
        "shl": 67,
        "shr_u": 67,
        "shr_s": 67,
        "rotl": 90,
        "rotr": 90,
        "eq": 45,
        "eqz": 45,
        "ne": 45,
        "lt_s": 45,
        "lt_u": 45,
        "le_s": 45,
        "le_u": 45,
        "gt_s": 45,
        "gt_u": 45,
        "ge_s": 45,
        "ge_u": 45,
        "clz": 45,
        "ctz": 45,
        "popcnt": 45,
  
        "drop": 120,
        "select": 120,
  
        "unreachable": 1
      }
    },
    "data": 0
  }
```

{% hint style="info" %}
Более детально о принципах измерения и таких таблицах мы рассказываем в разделе [_<mark style="color:purple;">**Расширенные возможности**</mark>_](rasshirennye-vozmozhnosti.md)_<mark style="color:purple;">****</mark>_
{% endhint %}

### <mark style="color:red;">**Ссылки**</mark>

{% embed url="https://www.rust-lang.org/fr/what/wasm" %}

{% embed url="https://wasmbook.com/" %}

{% embed url="https://habr.com/ru/post/475778/" %}

