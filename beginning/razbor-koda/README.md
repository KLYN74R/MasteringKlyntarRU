---
description: То чего все так ждали от других
cover: ../../.gitbook/assets/223e6792880429.5e569ff84ebef.gif
coverY: -118.71469095096039
---

# 🧑💻 Разбор кода

### <mark style="color:red;">**Что это?!**</mark>

Сфера крипто-проектов - это зачастую open source решения. Поскольку предполагается что над ядром и его компонентами, а так же другими проектами экосистемы будет работать большое количество разработчиков то хорошей практикой было бы дать понять из чего состоит ядро, как проиходит запуск демона пошагово, разъяснить структуру директорий.

Ввиду того, что проект большой и сложный это будет крайне полезно как для людей которые просто хотят глубже узнать о проекте, так и для разработчиков.

Поскольку сейчас мы только начинаем, то предоставим лишь что-то типа демоверсии того как это будет выглядеть. Вскоре, мы создадим отдельную книгу(документацию) которая будет посвящена именно этому

### <mark style="color:red;">**Обещанная демо-версия**</mark>

{% hint style="info" %}
Ниже будет представлена небольшая "демо-версия" введения в код для того, чтоб вы представляли как мы планируем предоставлять разработчикам информацию. Так же обратите внимание, что последующие разделы ([_<mark style="color:red;">**Аддоны**</mark>_](addony.md), [_<mark style="color:red;">**Блоки**</mark>_](bloki.md) ...) имеют плашку _<mark style="color:purple;">**Coming soon**</mark>_. Мы будем заполнять это по мере роста интереса к проекту
{% endhint %}

{% hint style="warning" %}
Для разработок и внесения изменений в код мы рекомендуем ещё раз клонировать репозиторий в отдельную директорию вместо изменений в том, который запускает рабочую версию ядра.
{% endhint %}

### <mark style="color:red;">**Подготовка к разбору**</mark>

Для дальнейшего чтения и разбора рекомендуем открыть репозиторий ядра KLYNTAR и вместе с этим руководством постепенно разбираться что к чему

{% embed url="https://github.com/KLYN74R/KlyntarCore" %}

### <mark style="color:yellow;">**Дерево директорий**</mark>

Прежде чем начинать разбираться с кодом, стоит обратить внимание на структуру директорий ядра. Она имеет следующий вид

{% hint style="info" %}
Использовано ограничение глубины равное 1
{% endhint %}

```
|-- ANTIVENOM
|
|-- KLY_Addons
|
|-- KLY_Doppelgangers
|
|-- KLY_ExternalServices
|
|-- KLY_Hostchains
|
|-- KLY_Plugins
|
|-- KLY_Runners
|
|-- KLY_Services
|
|-- KLY_Tests
|
|-- KLY_Utils
|
|-- KLY_WASM
|
|-- KLY_Workflows
|
|-- MAINNET
```

<mark style="color:yellow;">**AntiVenom**</mark>

Дефолтная директория для данных тестнета. Используется если не указана переменная среды <mark style="color:red;">**SYMBIOTE\_DIR**</mark>** ** и установлен режим тестнета <mark style="color:red;">**KLY\_MODE=test**</mark>. Имеет следующую структуру

```
ANTIVENOM
|
|-- CHAINDATA
|   `-- FASj1powx5qF1J6MRmx1PB7NQp5mENYEukhyfaWoqzL9
|       |-- CANDIDATES
|       |-- CONTROLLER_BLOCKS
|       |-- HOSTCHAINS_DATA
|       |-- INSTANT_BLOCKS
|       |-- METADATA
|       `-- STATE
|
|-- CONFIGS
|   |-- network.json
|   |-- node.json
|   |-- services.json
|   `-- symbiotes.json
|
|-- GENESIS
|   `-- FASj1powx5qF1J6MRmx1PB7NQp5mENYEukhyfaWoqzL9
|       `-- 0.json
|
|-- LOGS
|   `-- FASj1powx5qF1J6MRmx1PB7NQp5mENYEukhyfaWoqzL9.txt
|
`-- SNAPSHOTS
    `-- FASj1powx5qF1J6MRmx1PB7NQp5mENYEukhyfaWoqzL9
        |-- METADATA
        `-- STATE
```

<mark style="color:purple;">**CHAINDATA**</mark> - хранит данные состояния, блоки и метаданные(ссылки на коммиты в хостчейнах и другие данные)

<mark style="color:purple;">**CONFIGS**</mark> - директория с настройками для данного симбиота. Мы разделили на несколько файлов ввиду большого размера конфигурации + для лёгкости редактирования

<mark style="color:purple;">**GENESIS**</mark> <mark style="color:purple;"></mark><mark style="color:purple;"></mark> - директория с генезис-состоянием для симбиота. Может включать в себя несколько JSON файлов

<mark style="color:purple;">**LOGS**</mark> - директория с логами событий\
\
<mark style="color:purple;">**SNAPSHOTS**</mark> - содержит поддиректории METADATA и STATE. METADATA хранит указатели на текущий блок снепшота(высоту), его хэш, канарейку и другие данные. STATE представляет собой данные состояния в чистом виде

{% hint style="info" %}
Вы могли заметить промежуточную директорию \
\
<mark style="color:orange;">**FASj1powx5qF1J6MRmx1PB7NQp5mENYEukhyfaWoqzL9**</mark>\ <mark style="color:orange;">****</mark>\ <mark style="color:orange;">****</mark>Это адрес который создал данного симбиота и ID симбиота(подобно адресу смарт-контракта в EVM-совместимых цепях). При работе с другими цепочками у вас будут другие адреса. Так же это "ненужная" директория ввиду того, что сначала планировался другой дизайн и размещение директорий. В будущем мы исправим это
{% endhint %}

<mark style="color:yellow;">**KLY\_Addons**</mark>

Директория с разного рода кодом на других языках. Тут лежат исходники на Go, Rust и C++ которые требуют определённых манипуляций таких как компиляция в библиотеку и преобразование в аддоны. Так достаточно будет перейти в 1 директорию и запустить билд. Находится на верхнем уровне ядра так как содержит в основном алгоритмы которые будут общими для разных рабочих процессов.

<mark style="color:yellow;">**KLY\_Doppelgangers**</mark>

Предназначена для будущих релизов

<mark style="color:yellow;">**KLY\_ExternalServices**</mark>

Директория которая содержит все сторонние сервисы которые загружает ваш раннер. Является что-то типа общим хранилищем со следующей структурой

```
KLY_ExternalServices
|
|-- SomeOneService
|-- AnotherService
|-- Lokapala@1.3.37
|-- ...
`-- OneMoreService
```

Каждая директория здесь - это отдельный репозиторий с сервисом который запускается в вашей инфраструктуре.

<mark style="color:yellow;">**KLY\_Hostchains**</mark>

Большая и критически важная директория которая имеет такую структуру

```
KLY_Hostchains
│
│   
└───adapters
│   │   
│   │   README.md
│   │   
│   └───custom_MY_OWN_COLLECTION(kind of root directory for this pack)
│   │    │   
│   │    │───Solana(all files together)
│   │    │   └───configs.json
│   │    │   └───server.js
│   │    │   └───routes.js
│   │    │   └───...
│   │    │
│   │    │───XRP   
│   │    │   └───listener.rs(use different languages)
│   │    │   └───bot.js
│   │    │   └───Cargo.toml
│   │    │   └───...
│   │    │ 
│   │    │───RSK
│   │         └───...
│   │
│   └───dev0(developers' examples of adapters)
│        └───...
│
└───connectors
│   │ 
│   │  README.md
│   │   
│   └───dev0
│   │    │   
│   │    │───Solana(all files together)
│   │    │   └───configs.json
│   │    │   └───server.js
│   │    │   └───routes.js
│   │    │   └───...
│   │    │
│   │    │───XRP   
│   │    │   └───listener.rs(use different languages)
│   │    │   └───bot.js
│   │    │   └───Cargo.toml
│   │    │   └───...
│   │    │ 
│   │    │───RSK
│   │         └───...
│   │
│   └───dev0(developers' examples of adapters)
│        └───...
```

<mark style="color:yellow;">**KLY\_Plugins**</mark>

Содержит плагины которые загружаются оператором узла отдельно и служат для расширения возможностей ядра, рабочих процессов и так далее. Подробней о плагинах [_<mark style="color:red;">**здесь**</mark>_](../plaginy.md)_<mark style="color:red;">****</mark>_

<mark style="color:yellow;">**KLY\_Runners**</mark>

Содержит код раннеров которые прослушивают новые сервисы и запускают дальнейшую логику на основе конфигурации - что запускать, а что нет, в каком контейнере, какой скрипт выполнить и так далее. Там же будет находится дефолтный раннер от разработчиков Andromeda. Вы можете это увидеть взглянув на репозиторий

![](<../../.gitbook/assets/image (54).png>)

{% hint style="warning" %}
Не забывайте, что процесс разработки продолжается
{% endhint %}

<mark style="color:yellow;">**KLY\_Services**</mark>

Хранилище ваших сервисов. Структура аналогичная KLY\_ExternalServices за тем исключением, что сервисы здесь - разработанные вами

<mark style="color:yellow;">**KLY\_Tests**</mark>

Директория с отдельными unit и другими тестами

<mark style="color:yellow;">**KLY\_Utils**</mark>

Содержит алгоритмы и структуры данных. Опять таки, находится на верхнем уровне ввиду того, что алгоритмы и полезные функции тут общие для всех симбиотов. Можем даже посмотреть на это наглядно

![](<../../.gitbook/assets/image (59).png>)

<mark style="color:yellow;">**KLY\_KVM**</mark>

Директория необходимая для работы KLYNTAR VM(KLYNTAR VIRTUAL MACHINE). Так же является хранилищем для .wasm смарт-контрактов

<mark style="color:yellow;">**KLY\_Workflows**</mark>

Содержит репозитории с workflow для симбиотов

<mark style="color:yellow;">**MAINNET**</mark>

Абсолютно аналогичная структура как и у ANTIVENOM

### <mark style="color:red;">**Заключение**</mark>

Это было вводное объяснение ядра. Мы начали со структуры и дальше разбирать будем более детально и наглядно. Мы верим что такое пособие будет полезным и даст глубокое понимание KLYNTAR
