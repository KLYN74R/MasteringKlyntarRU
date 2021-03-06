---
description: То что сделает KLYNTAR поистине мощным
cover: ../.gitbook/assets/thumb-1920-1065736.jpg
coverY: 260.31088082901556
---

# 🔌 Плагины

![](<../.gitbook/assets/image (44).png>)

### <mark style="color:red;">Что это?</mark>

Ранее мы уже писали что модульность и расширения - это один из столбов KLYNTAR. Удобно когда система не дубовая, легко дополняется новыми возможностями, полезными API и все это благодаря множеству разработчиков которые будут ее перманентно улучшать.

В документации вы уже успели заметить это на уровне рабочих процессов симбиотов, на уровне Apollo и так далее. Сейчас же поговорим о плагинах верхнего уровня которые являются более общими. Дадим простое определение

{% hint style="info" %}
_<mark style="color:red;">**Плагин на KLYNTAR**</mark>_ - это отдельно скачиваемый вами репозиторий для вашей ноды / инфраструктуры который позволяет расширить и/или улучшить поведение KLYNTAR&#x20;
{% endhint %}

### <mark style="color:red;">**Применение**</mark>

Говоря о важности плагинов, достаточно просто перечислить потенциальное число юзкейсов для которых они годятся. Вот вам "всего лишь" "несколько" примеров:

<mark style="color:yellow;">**Для ботов**</mark>

Запустите сервер для бота(Telegram, Discord) который будет информировать вас о событиях на симбиотах на которых работают ваши ноды, который позволит проводить платежи в Telegram не выходя из вашего любимого мессенджера. Ну или же вовсе-дайте вашему боту больше привилегий для максимальных возможностей&#x20;

<mark style="color:yellow;">**Для кастомных механизмов логирования**</mark>

Получение детальной информации о происходящем - крайне важный элемент. С помощью плагинов вы сможете гибко и динамически менять и получать логи которые будут необходимы для вас&#x20;

<mark style="color:yellow;">**Для расширения доступных API**</mark>

Конечно мы тоже будем постоянно улучшать и дополнять существующий набор, но вы тут тоже получите большие возможности для контроля

<mark style="color:yellow;">**Для динамического снятия телеметрии, запуска своих обозревателей и т.д.**</mark>

Удобно когда вы получите фактически обозреватель из коробки

<mark style="color:yellow;">**Для запуска проверки снимков состояния, их сжатия и передачи**</mark>

Мы ранее писали про ставки на состояния. Так же можно использовать для большей скорости загрузки снепшота, разных проверок с использованием криптографической магии и многое другое

<mark style="color:yellow;">**Для динамического формирования списка подключённых узлов**</mark>

Блокчейны обычно работают в P2P среде и каждая нода имеет список подключённых к ней других узлов. Через плагины можно будет добавить логику их добавления или удаления из вашего списка

<mark style="color:yellow;">**Для установки слушателей на события БД**</mark>

Первая реализация ядра KLYNTAR использует LevelDB которая поддерживает обработку событий взаимодействия с БД

<mark style="color:yellow;">**Для установки шлюзов в сети**</mark>** **<mark style="color:red;">**TOR**</mark>** **<mark style="color:yellow;">**/**</mark>** **<mark style="color:red;">**I2P**</mark>** **<mark style="color:yellow;">**/**</mark>** **<mark style="color:red;">**ZeroNet**</mark>** **<mark style="color:yellow;">**и других**</mark>

Да, да, да. KLYNTAR будет поддерживать связь с ними. Тут мы указали лишь самые используемые и популярные. Используя такие мосты вы сможете запускать узлы KLYNTAR в TOR(как hidden service) или I2P и при этом взаимодействовать с ними так как если бы они были в обычной сети.

Так же можно использовать данный шлюз в качестве SOCKS прокси для Apollo чтоб взаимодействовать с KLYNTAR через упомянутый TOR

<mark style="color:yellow;">**Для менеджеров кэша**</mark>

Удаление, добавление, ротация. Фантазируйте, создавайте эффективные менеджеры для бОльшего быстродействия

### <mark style="color:red;">**Иерархия на уровне директорий**</mark>

Тут всё довольно просто. Плагины находятся в директории \
\
<mark style="color:orange;">**<**</mark><mark style="color:red;">**YOUR\_KLYNTAR\_DIRECTORY**</mark><mark style="color:orange;">**>/KLY\_Plugins**</mark>

```
KlyntarCore
│     
└───KLY_Plugins
│  │
│  │───Bot
│  │───Logger
│  │───CacheManager
   └───...
```

Так как вы можете запускать несколько демонов одновременно, то удобно иметь и обновлять аналогичные плагины в одном месте

{% hint style="info" %}
При запуске не забудьте убедится в том, что плагины не конфликтуют за порт, некоторую директорию и так далее
{% endhint %}

### <mark style="color:red;">Плагины от разработчиков</mark>

Все плагины от разработчиков KlyntarTeam будут иметь префикс _<mark style="color:purple;">**dev\_**</mark>_. Таким образом, легко будет их найти при разборе директорий или например через grep. Плагины от KlyntarTeam не означают что они чем-то лучше или круче нежели от сторонних разработчиков - мы ценим труд и вклад каждого. Однако стоит подчеркнуть что такие плагины имеют преимущество, потому что члены KlyntarTeam явно глубже понимают принципы работы KLYNTAR, особенности ядра и так далее. Стоит ожидать что подобные плагины будут иметь лучшую поддержку, меньше багов и будут лучше изучаться сообществом что хорошо с точки зрения безопасности.

Так например мы уже добавили плагины _<mark style="color:orange;">**dev\_nets\_gateway**</mark>, <mark style="color:orange;">**dev\_websocket**</mark>, <mark style="color:orange;">**dev\_proxy**</mark> _ и другие. Все они в настоящее время находятся в разработке_._

Так же помимо установки сторонних плагинов уже в самом репозитории ядра будут встроены некоторые плагины которые будут максимально популярные у сообщества

### <mark style="color:red;">Для разработчиков + где найти плагины</mark>

Для удобства мы создали отдельный репозиторий для плагинов куда разработчики могут заливать код, а желающие улучшить свою инфраструктуру могут устанавливать себе то, что им понравится

{% embed url="https://github.com/KLYN74R/Plugins" %}

{% hint style="info" %}
Мы вскоре опубликуем инструкцию как и что заливать в этот репозиторий
{% endhint %}

### <mark style="color:red;">**Заключение**</mark>

Плагины так же могут иметь уровни совместимости - быть универсальными или же под определённый рабочий процесс. Вскоре мы расскажем как улучшить совместимость. А пока творите!
