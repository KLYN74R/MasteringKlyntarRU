---
description: То чего все так ждали от других
cover: ../../.gitbook/assets/223e6792880429.5e569ff84ebef.gif
coverY: -200.6217616580311
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

### <mark style="color:yellow;">**Дерево директорий**</mark>

Прежде чем начинать разбираться с кодом, стоит обратить внимание на структуру директорий ядра. Она имеет следующий вид

{% hint style="info" %}
Использовано ограничение глубины равное 1
{% endhint %}

```
|-- ANTIVENOM
|
|-- GENESIS
|
|-- KLY_Addons
|
|-- KLY_Blocks
|
|-- KLY_Doppelgangers
|
|-- KLY_Essences
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
|-- KLY_Workflows
|
|-- CONFIGS
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
|   |-- doppelgangers.json
|   |-- network.json
|   |-- node.json
|   |-- services.json
|   |-- symbiotes.json
|   `-- tracking.json
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
