---
description: Узнайте больше про фильтры как часть рабочих процессов симбиотов
cover: ../.gitbook/assets/GrfE.gif
coverY: 0
---

# 🛑 Фильтры

![](<../.gitbook/assets/image (71).png>)

### <mark style="color:red;">**В целом**</mark>

Роль фильтров на первый взгляд кажется менее значимой чем роль коннекторов или плагинов. Однако, они так же крайне важные так как помогают вам лучше фильтровать входящие данные на ваши ноды.

Как вы уже успели прочитать в прошлых разделах, потоки генерации и валидации блоков - асинхронные и независимы друг от друга. Да, в KLYNTAR блоки могут генерироваться раньше чем проверяться. Благодаря особенностям работы и ставкам пользователей на собственную честность нам и удается добиваться максимумов в производительности и масштабируемости.

Между тем, чтобы в целом предотвратить попадание разного рода гадости в блокчейн нам и нужны фильтры.&#x20;

Набор фильтров обычно идёт в одном паке вместе с репозиторием workflow, так как предполагается что разработчик уже позаботился про минимальный уровень безопасности - учёл доступные транзакции на workflow, лучше разбирается в их подводных камнях и так далее.

Между тем, можно заметить что фильтры не фиксируются на уровне манифеста симбиота. Это потому, что каждая нода или группа узлов самостоятельно принимает решение касательно приема тех или иных данных.

### <mark style="color:red;">Где находится или куда помещать собственные фильтры</mark>

Фильтры находятся в паке с workflows, то бишь по такому пути

<mark style="color:orange;">**<**</mark><mark style="color:red;">**YOUR\_KLYNTAR\_DIRECTORY**</mark><mark style="color:orange;">**>/KLY\_Workflows/<**</mark><mark style="color:red;">**имя рабочего процесса**</mark><mark style="color:orange;">**>/filters.js**</mark>

{% hint style="info" %}
Это необязательный путь, потому что разработчик workflow может сменить положение фильтров в иерархии - например разбить на категории, добавить конфигурационный файл и так далее
{% endhint %}

Что касается разработчиков KlyntarTeam, то мы для простоты помещаем фильтры сразу. Вот как это выглядит

![Довольно простая иерархия](<../.gitbook/assets/image (1) (1) (1).png>)

### <mark style="color:red;"></mark>

### <mark style="color:red;">Что из себя представляют фильтры на уровне кода</mark>

Фильтры представляют из себя простой файл с одним объектом на экспорт в котором перечислены различного рода триггеры на приходящие к вам события - транзакции, блокировки, делегации и так далее.

В зависимости от их типа вы уже и принимаете решения - принимать их в мемпул или же нет&#x20;

{% hint style="warning" %}
Рекомендуется всё таки пользоваться фильтрами от разработчиков пака workflow. Это обезопасит вас от того, что вы забудете обработать какое-то событие или же обрабатывать его неправильно.\
\
Разработчикам в свою же очередь рекомендуется вводить некоторый конфигурационный файл на уровне пака рабочего процесса в котором можно будет просто назначать минимальный уровень комиссии, блокировать приходящие события от адресов из чёрных списков и так далее
{% endhint %}

![](<../.gitbook/assets/image (60).png>)

### <mark style="color:red;">**Репозиторий с фильтрами**</mark>

Мы так же создали репозиторий с фильтрами куда разные разработчики могут публиковать свои фильтры.

{% embed url="https://github.com/KLYN74R/Filters" %}
