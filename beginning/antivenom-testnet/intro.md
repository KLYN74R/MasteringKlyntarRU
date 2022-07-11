---
description: Первоначальный запуск и быстрый старт
cover: ../../.gitbook/assets/d84c40e770fba3b613c372e4e2df5e48.gif
coverY: 142.28421970357454
---

# ✴ Интро

{% hint style="info" %}
Данная страница в основном является копией нашего README по запуску тестнета. Однако, тут есть дополнительные подробности так что советуем пробежаться по данной странице даже если вы уже читали
{% endhint %}

![](https://readme-typing-svg.herokuapp.com/?font=Major+Mono+Display\&size=100\&color=C20000\&center=true\&vCenter=true\&width=500\&height=200\&lines=Klyntar)

### 🏗️ <mark style="color:red;">**Как билдить**</mark>

Как вы успели заметить, KLYNTAR находится в симбиотических отношениях с другими блокчейнами. Запуская различные узлы других проектов, работая с необходимыми им инструментами, самой ужасной и раздражающей проблемой была проблема с начальной настройкой - неправильные конфигурации, старые документы, ошибки версионирования, nightly версии и так далее. Вот почему мы подготовили Docker образы, чтобы вы могли быть уверены, что у вас будет 100% успешная установка. Рекомендуется использовать для запуска узлов и кластеров KLY, Apollo и т.д. Это необходимо для ускорения, чтобы не заставлять вас тратить время на поиск ошибок конфигураций, проблем с зависимостями и т.д. Просто запустите 1 команду и погнали 🚀\


{% hint style="warning" %}
Внимание\
\
Мы предполагаем что на вашей машине уже установлен Docker. Если нет, то вы можете установить его для Linux & Windows & Mac [_<mark style="color:red;">**здесь**</mark>_](https://docs.docker.com/engine/install/)
{% endhint %}

#### <mark style="color:yellow;">Проверка установленного Docker</mark>

```shell
johndoe@klyntar:~$ docker -v
Docker version 20.10.14, build a224086
```

#### <mark style="color:yellow;">**Загрузка образа**</mark>

Мы представляем вам наш первый образ [klyntar/all\_in\_one](https://hub.docker.com/repository/docker/klyntar/all\_in\_one).

\
![](http://dockeri.co/image/klyntar/all\_in\_one)\


Это универсальный образ с предустановленными Node.js, Go , Python и некоторыми другими инструментами типа `pnpm` , `node-gyp`, `git` и так далее. Это базовый слой для наших остальных Dockerfile(по крайней мере для ядра и Apollo). Приблезительный сжатый размер 606 мегабайт.

Так же в репозитории [_<mark style="color:red;">**KlyntarBaseImages**</mark>_](https://github.com/KLYN74R/KlyntarBaseImage) вы сможете найти исходники наших образов с их Dockerfile и скриптами для билда. Вы можете их клонировать и сбилдить образ локально или же просмотреть bash скрипт билда и пройтись по его командам для  установки всего необходимого на вашу хост-машину. Но в любом случае, мы бы рекомендовали использовать контейнеры

![](https://user-images.githubusercontent.com/53381472/174490998-2041af0d-6cd5-4873-ad64-fa810cda02df.jpg)

```shell

docker pull klyntar/all_in_one@sha256:dff001a9cd3da6328c504b52ed8a5748c47d23219feae220930dac1c1981cfe7
```

#### <mark style="color:yellow;">**Запуск контейнера**</mark>

Мы рекомендуем предоставить контейнеру несколько портов

Вообще вы можете выбирать любые, но рекомендуем ввиду некого "стандарта"

* **7331** - мейннет/kNULL дефолтный порт для первоначального симбиота kNULL (пасхалка - это 1337 наоборот **:)** )
* **9691** - дефолтный порт для Apollo UI сервера (пасхалка - это 1969 наоборот(год запуска Аполлон-11)
* **11111** - локальный тестнет(AntiVenom)\


{% hint style="warning" %}
**⚠ Внимание:**

Эта настройка является простейшей для быстрого старта. Если вам надо, то вы можете запускать контейнеры более продвинутым путём. Например, использовать тома, настраивать пользователя и его права, писать свои Dockerfiles и так далее&#x20;
{% endhint %}

Запустите контейнер

```shell
docker run -dtp 7331:7331 -p 9691:9691 -p 11111:11111 --name klyntar0 klyntar/all_in_one@sha256:dff001a9cd3da6328c504b52ed8a5748c47d23219feae220930dac1c1981cfe7
```

#### <mark style="color:yellow;">**Финал**</mark>

Зайдите в контейнер и перейдите в корневую директорию

```shell
docker exec -ti klyntar0 bash

# Inside container

cd ~
```

Склонируйте репозиторий KlyntarCore

```shell

git clone https://github.com/KLYN74R/KlyntarCore.git

cd KlyntarCore
```

И наконец, запустите 1 команду для билда

```shell

pnpm run build
```

### Теперь отдохните и посмотрите на процесс сборки. Это может занять несколько минут, но вы свободны от самостоятельной установки множества библиотек, зависимостей и обхода каталогов

\


![](https://i.pinimg.com/originals/d0/63/09/d063096ba4e07795c1bdf98572cb79a8.gif)

{% hint style="warning" %}
**⚠ Внимание:**

Как мы упоминали, это пример самой дефолтной настройки для быстрого старта & теста. Внутри билда происходит обход по каталогам и запуск необходимых программ(Typescript и Go компилятор,node-gyp для создания аддонов и т.д.), настройка прав доступа(700 для root пользователя) для скриптов, построение аддонов и связывание через _<mark style="color:red;">**npm link**</mark>_ для доступа к демону <mark style="color:purple;">**klyntar**</mark> через <mark style="color:yellow;">**PATH**</mark> путём симлинка в директории Node.js которая доступна из PATH
{% endhint %}

#### Сигналом того, что билд проходит успешно будут такие сообщения в консоли

![](https://user-images.githubusercontent.com/53381472/174610940-55ed92b8-bba3-4057-921e-2f1809c332d4.jpg)

#### ...а после билда аддонов такое

![](https://user-images.githubusercontent.com/53381472/174610936-3df6ea44-25fc-441d-8cc3-0f3dd414edf5.jpg)

#### **...и ещё кое-что**

Поскольку KLYNTAR имеет множество цепей (известных как _<mark style="color:red;">**симбиоты**</mark>_), которые симбиотически связаны с _<mark style="color:red;">**хостчейнами**</mark>_(Bitcoin, Ethereum, Avalanche, Solana, Dogecoin, XRP и другие цепочки), нам нужны _<mark style="color:red;">**коннекторы**</mark>_, чтобы позволить симбиотам взаимодействовать с хостчейнами(например, для чтения состояния контракта, получение блоков, запись в хостчейны и так далее)

Вот какая ситуация с коннекторами для симбиотов сейчас

*   #### **kNULL**

    Наш начальный симбиот который будет запущен командой KlyntarTeam будет использовать [**dev0** ](https://github.com/KLYN74R/KlyntarCore/tree/main/KLY\_Hostchains/connectors/dev0)пак с коннекторами. Начальный набор хостчейнов будет опубликован позже
*   #### **AntiVenom**

    Тестнет используя свою конфигурацию по умолчанию **ANTIVENOM/CONFIGS/symbiotes.json** и работая используя dev\_controller рабочий процесс имеет приостановленное состояние взаимодействия с хостчейнами(или их тестнетами), но в любом случае, вы можете их активировать. При этом не забудьте установить необходимые зависимости для коннекторов

Итак, если вы хотите сделать коннекторы доступными активируйте их в конфигурации

```json
//Где-то внутри symbiotes.json
//Для активации смените на false

"STOP_HOSTCHAINS":{
        
        "ltc":true,
        "bsc":true,
        "eth":true
    
}
```

После активации, перейдите в директорию с набором коннекторов и запустите загрузку зависимостей

```shell
# In KlyntarCore directory

cd KLY_Hostchains/connectors/dev0

pnpm install
```

{% hint style="success" %}
Мы предполагаем что вы выберете пак dev0**.** По крайней мере для запуска kNULL именно этот пак и понадобится
{% endhint %}

### &#x20;                              **🚀Отлично, теперь всё готово🚀**



### ☄️Запуск **тестнета**

Каталог testnet называется KlyntarCore/ANTIVENOM и имеет следующую структуру:

```
KlyntarCore
│     
│   
└───ANTIVENOM (default testnet directory if you don't override it via env variable)
│   │   
│   │   
│   └───CHAINDATA(will be created after the daemon run in testnet mode)
│   │    │
│   │    └───Wvzv9zGXJL4FngTKACPPDpHgCjE2k22jB9EnjmZr81Bi 
│   │       │
│   │       │───CANDIDATES
│   │       │───CONTROLLER_BLOCKS
│   │       │───HOSTCHAINS_DATA
│   │       │───INSTANT_BLOCKS
│   │       │───METADATA
│   │       └───STATE
│   │        
│   └───CONFIGS
│   │    │
│   │    │───network.json
│   │    │───node.json
│   │    │───services.json
│   │    └───symbiotes.json
│   │
│   └───GENESIS
│   │ 
│   └───LOGS
│   │ 
│   └───SNAPSHOTS
```

#### **Рекомендация**

Для запуска любого симбиота(в том числе и тестнета) вам нужны 2 директории - **CONFIGS** and **GENESIS**. Вы сможете найти их на нашем сайте или на ресурсах той компании или сообщества что запускает симбиот. Давайте создадим отдельную директорию для нашего тестнета AntiVenom с конфигурацией по умолчанию.

```shell

# In ~/KlyntarCore

# Создаем директорию для нашего симбиота(тестнет в данном случае)
mkdir -p ANTIVENOM_0

cd ANTIVENOM

cp -r CONFIGS GENESIS ../ANTIVENOM_0
```

Теперь нужно сохранить несколько переменных среды. Вскоре вы узнаете и про другие переменные среды, но сейчас нам нужны только две

```shell
#Установка директории для запуска тестнета
export SYMBIOTE_DIR=~/KlyntarCore/ANTIVENOM_0
```

И тестовый режим

```shell
export KLY_MODE=test
```

Теперь запустите демон

```shell
klyntar
```

### Вы должны будете увидеть следующее

![](https://user-images.githubusercontent.com/53381472/174685058-ae9d42e3-c37c-483b-b462-2ec45230fca9.jpg)

Поскольку вы используете конфигурацию по умолчанию, то тут есть предустановленная пара ключей, режим работы(workflow) и т.д. Приватный ключ как говорилось ранее - зашифрован, а тут вы увидите запрос пароля. Пароль `qwerty`

#### Подсказка

Now you have locally runned symbiote AntiVenom. Your node is a single one and works as **Controller** for **dev\_controller** workflow. Soon we'll show who to make your network more advanced by adding **InstantGenerators**, changing workflows, make your network semi-public, join your symbiote to external AntiVenom testnets, make your AntiVenom network in TOR network(via hidden services) and other cool features!

\


### KLYNTAR - your provider to new generation of crypto projects

#### **Advice**

Find out more about advanced options,configs,flags and so on our resources



### &#x20;                      🔥Cool,now you are the part of KLYNTAR🔥



### ⚙️ **Итог**

****

KLYNTAR can do literally everything. Described here is less than 0.001% of potential. Soon you'll get to know about another features like:

* Interactions with the hostchains, services, mutualism
* How to make your AntiVenom more advanced by making it semi-public, by adding tons of plugins and so on
* How to use Cryptoland with cool crypto features like VRF, multi & threshold & linkable ring signatures, post quantum cryptography and so on
* How to run clusters
* How to create workflows and this way-change the consensus
* How to take part in social consensus & voting
* How to use Unobtanium - your united resources from other blockchains e.g. bitcoin mined blocks, frozen stakes on Polygon, miner on Helium and so on

\
\


## **It's just beginning**

\
\


### 🤓 **Advice**

\


Follow us to get the news & updates ASAP. Discuss, share ideas, advices, help newbies to make our community more powerful.We're happy to involve new members to KLY community 😊

\
[![](https://img.shields.io/badge/Reddit-FF4500?style=for-the-badge\&logo=reddit\&logoColor=white) ](https://www.reddit.com/r/KLYN74R/)[![](https://img.shields.io/badge/Twitter-1DA1F2?style=for-the-badge\&logo=twitter\&logoColor=white) ](https://twitter.com/KLYN74R)[![](https://img.shields.io/badge/Medium-12100E?style=for-the-badge\&logo=medium\&logoColor=white) ](https://klyntar.medium.com/)[![](https://img.shields.io/badge/TikTok-000000?style=for-the-badge\&logo=tiktok\&logoColor=white)](https://www.tiktok.com/@klyn74r)\
[![](https://img.shields.io/badge/Instagram-E4405F?style=for-the-badge\&logo=instagram\&logoColor=white) ](https://www.instagram.com/klyn74r/)[![](https://img.shields.io/badge/Pinterest-%23E60023.svg?\&style=for-the-badge\&logo=Pinterest\&logoColor=white) ](https://www.pinterest.com/klyn74r)[![](https://img.shields.io/badge/dev.to-0A0A0A?style=for-the-badge\&logo=devdotto\&logoColor=white) ](https://dev.to/klyntar)[![](https://img.shields.io/badge/GitHub-100000?style=for-the-badge\&logo=github\&logoColor=white)](https://github.com/KLYN74R)\
[![](https://img.shields.io/badge/Telegram-2CA5E0?style=for-the-badge\&logo=telegram\&logoColor=white) ](https://t.me/KLYN74R)[![](https://img.shields.io/badge/Discord-7289DA?style=for-the-badge\&logo=discord\&logoColor=white) ](https://discord.gg/f7e7fCp97r)[![](https://img.shields.io/badge/Tor%20site-330F63?style=for-the-badge\&logoColor=white) ](http://klyntar66kjwhyirucco6sjgyp2f7lfznelzgpjcp6oha2olzb4rlead.onion)[![](https://img.shields.io/badge/YouTube-FF0000?style=for-the-badge\&logo=youtube\&logoColor=white)](https://www.youtube.com/channel/UC3TiyK40an6rQlf3BarMDoQ)\
[![](https://img.shields.io/badge/Facebook-1877F2?style=for-the-badge\&logo=facebook\&logoColor=white) ](https://www.facebook.com/KLYN74R/)[![](https://img.shields.io/badge/GitLab-330F63?style=for-the-badge\&logo=gitlab\&logoColor=white) ](https://gitlab.com/KLYNTAR)[![](https://img.shields.io/badge/Tumblr-%2336465D.svg?\&style=for-the-badge\&logo=Tumblr\&logoColor=white) ](https://klyn74r.tumblr.com/)![](https://img.shields.io/badge/Stack\_Overflow-FE7A16?style=for-the-badge\&logo=stack-overflow\&logoColor=white)

\
\


### 📚**Docs**

Read the docs here to find out more. For example, how to use plugins, prepare & change configs, run on a host machine, how to start a KLY Service and so on!

\


[🇬🇧 ![](https://img.shields.io/badge/Gitbook-000000?style=for-the-badge\&logo=gitbook\&logoColor=white)](https://mastering.klyntar.org)\
[🇷🇺 ![](https://img.shields.io/badge/Gitbook-000000?style=for-the-badge\&logo=gitbook\&logoColor=white)](https://ru.mastering.klyntar.org)
