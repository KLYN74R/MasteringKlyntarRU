---
description: >-
  Подробный обзор нашего инструмента CLI и пользовательского интерфейса для
  управления вашей империей KLY🪐
cover: >-
  https://files.gitbook.com/v0/b/gitbook-x-prod.appspot.com/o/spaces%2FphIHWZY173DpNXBbDjVg%2Fuploads%2FSBgfolMbGT8Jll4XTAaT%2Fgiphy.gif?alt=media&token=56ed2895-5248-40c2-a780-be901a0d113d
coverY: 55.23975588491717
---

# 🌚 Apollo



![](https://user-images.githubusercontent.com/53381472/174458851-d6cbe7cd-3696-48ef-8839-975f061e393f.png)

![](https://readme-typing-svg.herokuapp.com/?font=Major+Mono+Display\&size=48\&duration=4000\&color=C20000\&center=true\&vCenter=true\&width=300\&height=80\&lines=Apollo)



### 👨‍🚀 <mark style="color:red;">Благодарность</mark>

Поскольку KLYNTAR - проект "космических" масштабов, то и инструмент для взаимодействия с ним должен быть соответствующий. Много разных проектов или компаний называют свои продукты / протоколы в честь известных учёных, исторических личностей или событий. Мы в данном аспекте тоже поддержим общественный флэшмоб и поэтому решили назвать инструмент для взаимодействия с KLYNTAR в честь важного события в сфере астронавтики и изучения космоса - всем известной программы Аполлон, той самой, во время которой человечество впервые ступило на внеземное тело, а именно - на Луну.

![](https://monophy.com/media/lS7GfvzSVhWOhJKlng/monophy.gif)

Символизм здесь в том, что не всё было идеально, происходили аварии, разработки продолжались годами, но всё же благодаря плодотворной работе множества людей разных профессий человек все таки получил шанс стать межпланетным видом и добавить ещё одну галочку в список достижений рода людского. Мы надеемся что наш Apollo ждёт аналогичный успех ведь вложено множество сил и всё для того - чтоб подарить вам шанс выйти за рамки текущих достижений крипто индустрии.



### ⚡ <mark style="color:red;">Введение</mark>

Мы рады представить вам Apollo — наш мощный инструмент командной строки и пользовательского интерфейса для управления вашей инфраструктурой KLYNTAR. С помощью Apollo вы можете делать все — использовать его в качестве кошелька, взаимодействовать с децентрализованными сервисами, контролировать свои источники Unobtanium, использовать возможности Cryptoland — нашей удивительной коллекции криптоалгоритмов доступных на KLYNTAR и многое другое!

Здесь вы узнаете как начать работать с Apollo, некоторые основные указания и помощь чтоб быстрее начать работать с KLYNTAR. Мы планируем показать вам как загружать модули, как писать модули(если вы разработчик) для расширения возможностей как CLI так и UI, как контролировать свои кластеры из узлов и так далее.

Поскольку это довольно мощный инструмент(а не просто CLI с предварительным списком hardcoded команд), то мы постараемся дать вам самое важное - базовое понимание принципа работы, как оно всё взаимосвязанно. Стоит сказать что Apollo отличается от других подобных инструментов типа Metamask, Phantom и подобных тем, что здесь в работу будут включены всевозможные разработчики сервисов на KLYNTAR для создания персонализированных интерфейсов непосредственно для каждого сервиса, симбиота или группы сервисов. Это равносильно тому, если бы разработчики смарт-контрактов EVM-совместимых цепей которыми вы пользуетесь в том же Metamask предлагали бы уникальный интерфейс для каждого смарт-контракта.

Так, например, если это DeFi сервис работающий в экосистеме KLY, то перед вами в интерфейсе появятся необходимые данные, поля, последние новости из фида Твиттера этого проекта и так далее, если это основное меню Apollo, то в бегущей строке вы так же встретите объявления по предложениям стейкинга вашего унобтаниума на какие-то новые сервисы где вы сможете решить, что вам более выгодно-поставить свой унобтаниум добытый майнером BTC и получить место валидатора сервиса или же подтвердить объем зарезервированного хранилища в Filecoin и оставить унобтаниум для будущего голосования за самые полезные плагины для KLYNTAR в рамках процедур социального консенсуса, а перейдя на [<mark style="color:purple;">wikipedia.org</mark>](https://wikipedia.org) или читая какую-то статью на [<mark style="color:purple;">Medium</mark>](https://medium.com) вы сможете отблагодарить авторов и получить какой-то эксклюзивный контент от них. И всё это в одном чёрном ящике под названием Apollo. Думаю слюнки уже потекли, так что поехали 🤤



### 🏗️ <mark style="color:red;">Как сбилдить & запустить</mark>

Лучше 1 раз показать чем 100 сказать. С таким настроем переходим к запуску. Как вы наверняка уже прочитали ранее, KLYNTAR находится в симбиотических отношениях с другими блокчейнами-как уже существующими типа Bitcoin, Avalanche, XRP, Solana так и теми которые только будут изобретены в будущем.

### Запуск вместе с Docker

Запуская различные узлы других проектов, работая с необходимыми им инструментами, самой ужасной и раздражающей проблемой была проблема с начальной настройкой - неправильные конфигурации, старые документы или плохая документация от разработчиков, ошибки версионирования, nightly версии и так далее. Вот почему мы подготовили Docker образы, чтобы вы могли быть уверены, что у вас будет 100% успешная установка. Итак, приступим 🚀

{% hint style="warning" %}
**ВНИМАНИЕ**

Перед началом установки, убедитесь что у вас установлен Docker. Если нет, то вы можете скачать его на Linux & Windows & Mac [_<mark style="color:purple;">**здесь**</mark>_](https://docs.docker.com/engine/install/)_<mark style="color:purple;">****</mark>_
{% endhint %}

Для того чтоб проверить установлен ли Docker введите

```bash
klyntar@apollo:~# docker -v
Docker version 20.10.14, build a224086
```

#### **Загрузка образа**

![](http://dockeri.co/image/klyntar/all\_in\_one)

Представляем вам наш первый образ [_<mark style="color:red;">**klyntar/all\_in\_one**</mark>_](https://hub.docker.com/repository/docker/klyntar/all\_in\_one/general) _<mark style="color:red;">****</mark>_ из коллекции Docker образов KLYNTAR. Это универсальный образ с предустановленными <mark style="color:purple;">Node.js</mark>, <mark style="color:purple;">Go</mark>, <mark style="color:purple;">Python</mark> и некоторыми инструментами вроде <mark style="color:purple;">pnpm</mark>, <mark style="color:purple;">node-gyp</mark>, <mark style="color:purple;">git</mark> и так далее которые необходимы для сборки. Мы создали его, чтобы сэкономить ваше время и нервную систему. Это базовый уровень для всех наших Dockerfiles (по крайней мере, для ядра и Apollo). Приблизительный сжатый размер составляет 606 мегабайт, на на его основе работает ядро,Apollo и другие компоненты системы. Кроме того, в нашем репозитории[ _<mark style="color:red;">**KlyntarBaseImages**</mark>_](https://github.com/KLYN74R/KlyntarBaseImages) вы можете найти исходники всех файлов Docker базового уровня, так что вы можете cклонировать и собрать образ самостоятельно или найти скрипт сборки bash и установить требуемые компоненты прямо свою хост машину.

{% hint style="info" %}
**ПРИМЕЧАНИЕ**

Если вы всё таки собрались идти по более сложному пути, то пропустите установку с помощью Docker и перейдите [_<mark style="color:red;">**сюда**</mark>_](./#ustanovka-na-goloe-zhelezo) для "ручной" установки
{% endhint %}

Но в любом случае, мы рекомендуем вам использовать контейнеры.

![](https://user-images.githubusercontent.com/53381472/174490998-2041af0d-6cd5-4873-ad64-fa810cda02df.jpg)

Итак, клонируем образ:

```shell
docker pull klyntar/all_in_one@sha256:dff001a9cd3da6328c504b52ed8a5748c47d23219feae220930dac1c1981cfe7
```

{% hint style="info" %}
Вы наверняка заметили что как здесь, так и на уровне Dockerfile'ов мы используем привязку к хэшам. Помимо безопасности, это ещё будет необходимо и для того, чтоб вы могли проверять образы, репозитории сервисов, плагины и так далее от разработчиков KlyntarTeam или других программистов с помощью Apollo и возможностей Cryptoland.\
\
Так например вы сможете проверить плагин для вашей инфраструктуры с помощью мультиподписей и возможности агрегации, тогда как в команде может работать больше сотни человек. Или например, разработчик сервиса установил правило что за принятие изменений необходимо чтоб проголосовало больше 2/3 пользователей с помощью комбинаций кольцевых подписей. Для удобства + проверок как раз таки и необходимы будут хэши.&#x20;
{% endhint %}

**Запуск контейнера**

Мы рекомендуем вам пробросить порт 9691 который является портом по умолчанию для Apollo(опять таки отсылка:9691-это в обратном порядке 1969 год когда и был запуск Аполлон-11)

{% hint style="warning" %}
#### **ВНИМАНИЕ**

Это самый простой и стандартный способ запуска для быстрого старта. Если вы опытный пользователь, то вы можете запускать вручную с более сложными шагами-использовать тома, менять пользователя и уровни доступа и так далее
{% endhint %}

```shell
docker run -dtp 9691:9691 --name test_kly klyntar/all_in_one@sha256:dff001a9cd3da6328c504b52ed8a5748c47d23219feae220930dac1c1981cfe7
```

#### Осталось чуть-чуть

Зайдите в контейнер и перейдите в домашнюю директорию

```shell
docker exec -ti test_kly bash

# Внутри контейнера

cd ~
```

Склонируйте репозиторий Apollo

```shell
git clone https://github.com/KLYN74R/Apollo.git

cd Apollo
```

Ну и в конце-концов запустите 1 команду для билда

```shell
pnpm run build
```

### Теперь отдохните и посмотрите на процесс сборки. Это может занять несколько минут, но вы освобождены от самостоятельной установки множества библиотек, зависимостей и обхода по древу каталогов.

![](https://i.pinimg.com/originals/d0/63/09/d063096ba4e07795c1bdf98572cb79a8.gif)

Промежуточным сигналом про успешность первого этапа сборки будет такое вот в консоли

![](https://2131090630-files.gitbook.io/\~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2FphIHWZY173DpNXBbDjVg%2Fuploads%2FdewG1SQftz0ndvmG4fNa%2Fimage.png?alt=media\&token=ad2710a7-0fd1-43cb-ad80-62e78badb989)

...а после построения аддонов такое

![](https://2131090630-files.gitbook.io/\~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2FphIHWZY173DpNXBbDjVg%2Fuploads%2FL3RavrjoA7nktQKFfV3i%2Fphoto\_2022-06-04\_11-55-04.jpg?alt=media\&token=6363785e-a243-4f98-80ca-5ee83b97da87)

Теперь попробуйте запустить. В консоли вы должны увидеть такое

![Попытайтесь найти "космическую пасхалку"🌠](https://user-images.githubusercontent.com/53381472/174460136-49cbf58b-fe08-4952-81b2-3b6e13d96444.jpg)

Также вы можете запустить Apollo в UI режиме. Так вы получите веб-версию Apollo. Для этого запустите

```bash
apollo ui
```

Теперь перейдите в браузер на [_<mark style="color:red;">**localhost:9691**</mark>_](http://localhost:9691). Вы должны будете увидеть такое:

![Надеюсь вы оцените наш стиль @\_@](../../.gitbook/assets/photo\_2022-06-25\_00-28-45.jpg)

### Установка на "голое железо"

{% hint style="info" %}
В данном случае я использую Debian
{% endhint %}

Для представленного образа основой является представленный ниже bash скрипт. Тут в целом шаг за шагом расписаны комментарии касательно того что вы устанавливаете. При этом, если у вас на машине уже установлены подобные компоненты, то вы можете пропустить их установку и скачать только то что вам нужно:

{% embed url="https://github.com/KLYN74R/KlyntarBaseImages/blob/main/Basic/setup.sh" %}

Для начала традиционно

```bash
apt-get update && apt-get upgrade -y
```

Затем установите необходимые пакеты

```bash
apt-get install nano sudo git curl wget build-essential libreadline-dev libncursesw5-dev libssl-dev libsqlite3-dev tk-dev libgdbm-dev libc6-dev libbz2-dev libffi-dev zlib1g-dev -y
```

_****_[_<mark style="color:red;">**Тут**</mark>_](https://github.com/KLYN74R/KlyntarBaseImages/blob/263c335d1539b31cee280f5dae6d051d3a7aef0c/Basic/setup.sh#L20) установка <mark style="color:purple;">Python v3.10</mark>. Python нужен для сборки аддонов на Go для их использования в Node.js

```bash
#Fetch
wget -c https://www.python.org/ftp/python/3.10.0/Python-3.10.0.tar.xz

#Unpack
tar -Jxvf Python-3.10.0.tar.xz

cd Python-3.10.0

./configure --enable-optimizations

make altinstall

update-alternatives --install /usr/bin/python python /usr/local/bin/python3.10 1
update-alternatives --install /usr/bin/pip pip /usr/local/bin/pip3.10 1

#Finally-delete useless
cd ..
rm -r Python-3.10.0  Python-3.10.0.tar.xz
```

Далее установите <mark style="color:purple;">Node.js v17.x</mark>

```bash
apt install software-properties-common -y

curl -sL https://deb.nodesource.com/setup_17.x | bash - 

apt update

#Install npm and node
apt install -y nodejs
```

Поскольку мы с вами более продвинутые ребята, то установим ещё кое-что, более продвинутую версию <mark style="color:red;">npm</mark> - [_<mark style="color:purple;">**pnpm**</mark>_](https://pnpm.io/) _<mark style="color:purple;">****</mark>_ и _<mark style="color:purple;">****</mark>_ [_<mark style="color:purple;">**node-gyp**</mark>_](https://github.com/nodejs/node-gyp) _<mark style="color:purple;">****</mark>_ для билда аддонов.

```bash
npm install pnpm -g
#And node-gyp to build Golang addons(Go => C => .node addons)
npm install node-gyp -g
```

Последним необходимо установить <mark style="color:purple;">Go</mark>

```bash
#Fetch archive
wget https://go.dev/dl/go1.18.linux-amd64.tar.gz

#Unpack
rm -rf /usr/local/go && tar -C /usr/local -xzf go1.18.linux-amd64.tar.gz


#Add vars to PATH
echo 'export GO111MODULE="auto"' >> ~/.bashrc
echo "export PATH=$PATH:/usr/local/go/bin" >> ~/.bashrc

source ~/.bashrc

#Don't need archive anymore
rm go1.18.linux-amd64.tar.gz
```

Финальный штрих - установка дополнительных компонентов

```shell
npm i pnpm node-gyp -g
```

Затем просто склонируйте и запустите билд

```shell
git clone https://github.com/KLYN74R/Apollo.git

cd Apollo

pnpm run build
```

###

### ⚙️ <mark style="color:red;">Модульность</mark>

Работая с различными «хакерскими» инструментами, я получил опыт так называемых «лучших практик» для создания действительно мощных инструментов. Вот почему Apollo (как и KLYNTAR) будет динамически расширяем и модульным. Вы, мы, а так же миллионы других разработчиков смогут улучшать и дополнять возможности Apollo новыми командами в CLI, новыми разделами в UI, новыми паками для работы с симбиотами и сервисами на KLYNTAR.

Прямо сейчас у вас есть три способа апгрейднуть возможности Apollo, загрузив расширения в такие директории

* <mark style="color:purple;">KLY\_Modules</mark>
* <mark style="color:purple;">KLY\_ServicesAPI</mark>
* <mark style="color:purple;">KLY\_WorkflowsAPI</mark>

### _<mark style="color:red;">И мы конечно же покажем как это сделать!</mark>_

### _**KLY\_Modules**_

Каталог для ваших внешних модулей. Это могут быть дополнительные полезные команды такие как генерация новых типов пар ключей для нового алгоритма подписи или получения актуальных данных по состоянию ваших узлов. Может быть написано вами или любым другим третьим лицом.&#x20;

Итак, _<mark style="color:purple;">**подключаемый модуль**</mark>_ - это репозиторий. Это сделано для удобства так как все умеют работать с Git(мы предполагаем что вы будете использовать именно эту систему контроля версий), да и контролировать изменения таким образом будет легче. Обновлять модули вы можете независимо друг от друга и при надобности-бегать между коммитами или ветками.

Что касается структуры, то типичный модуль должен содержать 2 каталога

* _<mark style="color:red;">**cli**</mark>_ (содержит новые команды для CLI)
* _<mark style="color:red;">**ui**</mark>_ (каталог со всем для расширения интерфейса в браузере. Это поддиректории со стилями, маршрутами [_<mark style="color:purple;">**Fastify**</mark>_](https://github.com/fastify/fastify), скриптами и html шаблонами)

{% hint style="info" %}
Как уже упоминалось ранее, скоро у вас появится удивительная возможность криптографически проверять авторов — с помощью подписи кода(так называемый Code Signing). Имея хэш репозитория, вы можете проверить подпись и быть уверенным, что код является оригинальным, используя различные криптографические функции, такие как мультиподпись или постквантовая криптография, социальный консенсус и так далее. Мы описываем это в разделе [_<mark style="color:red;">**Базовая безопасность**</mark>_](../bazovaya-bezopasnost.md) в нашей книге MasteringKlyntar.
{% endhint %}

**Подводя итог, ваше дерево каталогов должно выглядеть так:**

```bash
Apollo
│     
│   
└───KLY_Modules
│   │   
│   │
│   │   
│   └───init(default module,the entry point for the other)
│   │    │   
│   │    │───cli(directory for files to improve CLI)
│   │    │   │
│   │    │   └───init.js 
│   │    │
│   │    └───ui(directory for files to improve UI)
│   │        │
│   │        │───routes.js
│   │        │───templates(.ejs files)
│   │        │     └─...
│   │        │───configs.json
│   │        └───...
│   │   
│   │
│   └───your_custom_module
│        │   
│        │───cli(directory for files to improve CLI)
│        │    │   
│        │    └───init.js
│        │
│        └───ui(directory for files to improve UI)
│            │
│            │───routes.js
│            │───templates(.ejs files)
│            │     └─...
│            │───configs.json
│            └───...
│
│
└───KLY_ServicesAPI
    └───...
```

\
<mark style="color:purple;">**CLI part**</mark>

В CLI дополнительные модули выглядят как обычные команды. Чтобы ваши пользователи могли различать их и не происходило коллизий(например когда в двух модулях будут идентичные команды), дайте им оригинальный префикс или сделайте единую команду с именем репозитория и скройте команды в подкомандах. Мы сейчас покажем как.

<mark style="color:purple;">****</mark>

<mark style="color:purple;">**UI part**</mark>

Если у модуля также есть UI часть (что зачастую так и будет), вы сможете посетить:

```shell
http(s)://<your_interface>:<port>/modules
```

для того, чтобы обнаружить там точку входа в ваш модуль\


### _**KLY\_ServicesAPI**_

> **ServiceAPI** - каталог с репозиториями API для взаимодействия с сервисами, запущенными на Klyntar. Представьте, что все смарт-контракты на Ethereum будут иметь уникальный дизайн в вашем кошельке, отдельную страницу со всеми доступными функциями, характерными для контракта и т.д. Apollo дает возможность разработчикам проявить фантазию для того, чтоб вы получили лучшее!

Иерархия для этой директории аналогична KLY\_Modules. Для просмотра доступных модулей перейдите по этому URL

```shell
http(s)://<your_interface>:<port>/services
```



### _**KLY\_WorkflowsAPI**_

> **WorkflowsAPI** - каталог с репозиториями API для взаимодействия с симбиотами на Klyntar. Поскольку они могут использовать разные рабочие процессы(читай workflows) благодаря принципу [_<mark style="color:red;">**мутаций**</mark>_](../mutacii.md), то нам необходимо сделать возможным использование соответствующих алгоритмов, реализовать взаимодействия с хостчейнами, создание правильных событий для отправки симбиотам и использование других специфических функций, таких как трафик через TOR или пороговые подписи. Представьте, что у вас будет возможность контролировать свои активы Bitcoin, Solana, Avalanche, Cosmos (нативные монеты, токены и т. д.), выполнять смарт-контракты, делегировать полномочия, используя только один инструмент. Да, это то, что делает Apollo.

...ну...иии...тут абсолютно аналогичная структура. Только для просмотра доступных симбиотов с которыми вы взаимодействуете перейдите на такой адрес:

```shell
http(s)://<your_interface>:<port>/symbiotes
```



### 🐱‍💻 <mark style="color:red;">Как написать собственный модуль</mark>

### _<mark style="color:purple;">**CLI**</mark>_

Переходим к сладкому

Предлагаю в качестве тестового примера сделать что-то более полезное чем HelloWorld. Например, давайте представим что где-то в интернете есть API сервер который принимает от вас перечень ваших адресов Bitcoin и Polygon и предоставляет информацию относительно того, куда лучше застейкать ваш унобтаниум на основании того, что на предоставленных адресах имеется + учитывая дополнительные параметры (количество добытых блоков BTC, их возраст, сложность, возраст ваших входов и т.д. Для Polygon это может быть набор токенов что имеются на ваших адресах)

Прикинув, мы можем предположить что в CLI это должно выглядеть как-то так:

```shell
apollo uno-stats \
--addresses btc:1A1zP1eP5QGefi2DMPTfTL5SLmv7DivfNa,\
polygon:0xe6E9a384AD6D138eBAA7006F0Be3BD46f873c027
```

В ответ пусть приходят данные вида

```json
{
    "btc":{
    
        "1A1zP1eP5QGefi2DMPTfTL5SLmv7DivfNa":{
        
            "blocks":[
            
                "000000000019d6689c085ae165831e934ff763ae46a2a6c172b3f1b60a8ce26f":{
                    "index":0
                    "difficulty":"0x00000000000404CB000000000000000000000000000000000000000000000000"
                }
            ],
            
            "inputs":[
            
                "4a5e1e4baab89f3a32518a88c31bc87f618f76673e2cc77ab2127b7afdeda33b":{
                
                    "age":742186
                
                }
            
            ],
            
            "interesting_services":[
            
                "uniswap_kly":{
                
                    "description":"Uniswap in KLY network",
                    "rewards":"13.37%"
                    "unobtanium_stakes":{
                        "btc":"inputs,blocks",
                        "sol":"staking on NWr9GKgcBkP9nQkhS8mRKrK99iAXxBbkTCjQXJkwDK93",
                        "matic":"ownership of ShitCoin1 and UselessToken2"
                    }
                
                },
                
                "some_useful_service":{
                    ...
                }
            
            ]
        
        }
    
    },
    "polygon":{
    
        "0xe6E9a384AD6D138eBAA7006F0Be3BD46f873c027":{
        
            "ShitCoin1":1000000,
            "Tether":1337.111,
            "ShitCoin3":13379999999999999999999
        },
        
        "interesting_services":[
            
                "sol_algo_storage":{
                
                    "description":"Storage for Solana & Algorand smart contracts",
                    "rewards":"9.76% | 79% | 11.11%"
                    "unobtanium_stakes":{
                        "btc":"blocks older than 600000",
                        "near":">10000$ freeze on dac17f958d2ee523a2206206994597c13d831ec7.factory.bridge.near Tether(NEAR)",
                        "algo":"ownership of 312769(Tether) or 31566704(USDC)"
                    }
                
                }
            
            ]
    
    }

}
```

Переходим к написанию. Создадим репозиторий в котором будут 2 директории. UI часть пока что оставим в покое и займёмся CLI частью

```shell
mkdir MySuperModule

cd MySuperModule

git init

#Создание двух сабдиректорий
mkdir cli ui

cd cli

touch module.js
```

CLI в Apollo работает на основе NPM пакета Commander

![](<../../.gitbook/assets/image (2) (1) (1).png>)

{% embed url="https://github.com/tj/commander.js" %}
Здесь можете узнать больше
{% endembed %}

Тут вы можете найти документацию для более топовых возможностей. Что касается KLYNTAR, то мы предоставляем глобальный объект <mark style="color:red;">PROGRAM</mark> прямо как в документации по Commander'у

И так, ваш _<mark style="color:purple;">**module.js**</mark>_ выглядит так:

```javascript

PROGRAM //globalvar

.command('uno-stats')
.alias('us')

.description(`Get the propositions to stake your Unobtanium`)

// Тут передаем флаги
.option('-a, --addresses <value>','TICKER:ADRR in CSV format.Example btc:1A1zP1eP5QGefi2DMPTfTL5SLmv7DivfNa,polygon:0xe6E9a384AD6D138eBAA7006F0Be3BD46f873c027')
.option('-u, --url <value>','API server to get info')

.action(async(opts,_cmd)=>{

    // Тут уже парсите команды, параметры и выполняете нужную логику  
    
})
```

Ок, можно сказать что уже готово, осталось только подключить ваш модуль для того чтоб он стал доступен из CLI. Для этого отредактируйте файл configuration.json в корне Apollo. Файл имеет такой вид(в случае простейшей конфигурации)

```json
{
    "DEFAULT":{
        "LANG":"EN",
        "MODE":"light"
    },

    "FASTIFY_OPTIONS":{
        "logger":false,
        "http2":false,
        "https":{
            "enable":false,
            "key":"resources/cert.key",
            "cert":"resources/cert.pem"
        }
    },

    "EXTRA_CLI": [
        "KLY_Modules/init/cli/init.js"
    ],

    "EXTRA_UI": [
        
        {

            "TYPE":"service",
            
            "ALIAS":"Service 0",

            "PATH":"KLY_ServicesAPI/some_service/ui/route0.js",
            
            "OPTIONS":{
             
                "prefix":"/service0"
            
            }

        },

        {

            "PATH":"KLY_Modules/init/ui/routes.js",

            "OPTIONS":{
             
                "prefix":"/"
            
            }

        }
        
    ]

}
```

Добавьте путь к вашему модулю в EXTRA\_CLI

```json
"EXTRA_CLI": [
        "KLY_Modules/init/cli/init.js",
        "KLY_Modules/MySuperModule/cli/module.js",
],
```

Теперь запустив CLI вы должны будете обнаружить команды из данного модуля в списке общедоступных.

![](<../../.gitbook/assets/image (2) (1).png>)

### _<mark style="color:purple;">**UI**</mark>_

Теперь коротко об UI части. Опять таки можем представить что мы работаем с тем же выдуманным модулем который предоставляет нам советы по стейкингу унобтаниума.

Что у такого модуля может быть в UI части? Ну он сможет автоматом для вас подгрузить ссылки на Telegram каналы данных сервисов, загрузить в iframe главную страницу сайтов рекомендуемых сервисов или построить график на котором предположительно вы увидите ваш доход в зависимости от стратегии стейкинга.

### Пару слов про веб-часть

Прежде чем начать, познакомим вас с одним проектом на котором и основана UI часть Apollo. Итак, в основе лежит репозиторий _<mark style="color:red;">**Fastify**</mark>_-быстрый и мощный веб сервер который очень популярный у JS разработчиков, имеет более 24 тысяч звёзд на GitHub, обладает мощной экосистемой плагинов и активно поддерживается(часть команды-это разработчики Node.js)

![](../../.gitbook/assets/fastify-landscape-outlined.svg)

{% embed url="https://github.com/fastify/fastify" %}

![Если вам интересно, то можете познакомится ближе с данным продуктом](<../../.gitbook/assets/image (3) (1) (1) (1) (1) (1).png>)

А вот собственно набор плагинов. Они так же могут дополнить возможности вашего Apollo путём включения их как модулей.

{% embed url="https://www.fastify.io/ecosystem/" %}

```bash
cd MySuperModule/ui

#Создайте необходимую и удобную вам иерархию
mkdir templates scripts styles

#Создадим точку входа
touch routes.js
```

Пусть _<mark style="color:purple;">**routes.js**</mark>_ выглядит как-то так

```javascript
export default (fastify, options, next) => {

    //_______________________________________ DEFAULT ROUTES ________________________________________

    //Start page
    fastify.get('/',(request, reply) =>
    
        handler(reply,'KLY_Modules/init/ui/templates/index.ejs',{text:'Hello,this is the entry point to control Klyntar'})

    )

    fastify.get('/another',(request, reply)=>
        
        // your own logic
        
    )

```

После этого, перейдите в тот же конфиг и добавьте путь к модулю в раздел EXTRA\_UI

```javascript
"EXTRA_UI":[

    ...,

    {

            "PATH":"KLY_Modules/MySuperModule/ui/routes.js",

            "OPTIONS":{
             
                "prefix":"/mysupermodule"
            
            }

        }

]
```

После этого, вам станет доступен функционал вашего модуля по адресу

```
http(s)://<interface>:port/modules/mysupermodule
```

Однако, вы сможете получить доступ даже просто перейдя на главную страницу, а дальше следуя указаниям и привязкам к кнопкам в главном меню.

{% hint style="info" %}
Мы это упомянули так как по дефолту в UI уже будет автоматически включён модуль _<mark style="color:red;">**init.**</mark>_ Он включает в себя логику главной страницы(), стили и так далее, но главное - он обеспечивает доступ ко всем остальным возможностям Apollo-создаст кнопки для перехода к другим модулям, API сервисов и так далее. _<mark style="color:red;">****</mark>_&#x20;
{% endhint %}

![](<../../.gitbook/assets/image (2).png>)

### 🧐 <mark style="color:red;">В чём преимущества такого подхода</mark>

Подобно тому как мутации происходят в природе, постоянно наделяя организмы новыми способностями, Apollo тоже будет развиваться за счёт роста экосистемы KLY и всей блокчейн индустрии.

На уровне кода можно сказать что удобность в том, что каждый дополняемый элемент может быть как независимым, так и взаимодействовать с другими модулями(так как запросы происходят в одном домене). Разработчики получают полную свободу относительно используемых инструментов-внутри модуля может быть какая-то библиотека на Rust, запущенный отдельным процессом однострочник на Python, билд конфигурация для TypeScript и так далее!

Всё удобно, понятно, документации доступны-так что удачи) &#x20;

### 🤓 <mark style="color:red;">Совет</mark>

Следите за нами, чтобы получать новости и обновления как можно скорее. Обсуждайте, делитесь идеями, советами, помогайте новичкам сделать наше сообщество сильнее. Мы рады привлечь новых участников в сообщество KLY 😊

\
[![](https://img.shields.io/badge/Reddit-FF4500?style=for-the-badge\&logo=reddit\&logoColor=white) ](https://www.reddit.com/r/KLYN74R/)[![](https://img.shields.io/badge/Twitter-1DA1F2?style=for-the-badge\&logo=twitter\&logoColor=white) ](https://twitter.com/KLYN74R)[![](https://img.shields.io/badge/Medium-12100E?style=for-the-badge\&logo=medium\&logoColor=white) ](https://klyntar.medium.com/)[![](https://img.shields.io/badge/TikTok-000000?style=for-the-badge\&logo=tiktok\&logoColor=white)](https://www.tiktok.com/@klyn74r)\
[![](https://img.shields.io/badge/Instagram-E4405F?style=for-the-badge\&logo=instagram\&logoColor=white) ](https://www.instagram.com/klyn74r/)[![](https://img.shields.io/badge/Pinterest-%23E60023.svg?\&style=for-the-badge\&logo=Pinterest\&logoColor=white) ](https://www.pinterest.com/klyn74r)[![](https://img.shields.io/badge/dev.to-0A0A0A?style=for-the-badge\&logo=devdotto\&logoColor=white) ](https://dev.to/klyntar)[![](https://img.shields.io/badge/GitHub-100000?style=for-the-badge\&logo=github\&logoColor=white)](https://github.com/KLYN74R)\
[![](https://img.shields.io/badge/Telegram-2CA5E0?style=for-the-badge\&logo=telegram\&logoColor=white) ](https://t.me/KLYN74R)[![](https://img.shields.io/badge/Discord-7289DA?style=for-the-badge\&logo=discord\&logoColor=white) ](https://discord.gg/f7e7fCp97r)[![](https://img.shields.io/badge/Tor%20site-330F63?style=for-the-badge\&logoColor=white) ](http://klyntar66kjwhyirucco6sjgyp2f7lfznelzgpjcp6oha2olzb4rlead.onion)[![](https://img.shields.io/badge/YouTube-FF0000?style=for-the-badge\&logo=youtube\&logoColor=white)](https://www.youtube.com/channel/UC3TiyK40an6rQlf3BarMDoQ)\
[![](https://img.shields.io/badge/Facebook-1877F2?style=for-the-badge\&logo=facebook\&logoColor=white) ](https://www.facebook.com/KLYN74R/)[![](https://img.shields.io/badge/GitLab-330F63?style=for-the-badge\&logo=gitlab\&logoColor=white) ](https://gitlab.com/KLYNTAR)[![](https://img.shields.io/badge/Tumblr-%2336465D.svg?\&style=for-the-badge\&logo=Tumblr\&logoColor=white) ](https://klyn74r.tumblr.com/)[![](https://img.shields.io/badge/Stack\_Overflow-FE7A16?style=for-the-badge\&logo=stack-overflow\&logoColor=white)](broken-reference)

