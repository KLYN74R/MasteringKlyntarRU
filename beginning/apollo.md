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

### 📖 Содержание

* <mark style="color:red;"></mark>[<mark style="color:red;">Благодарность</mark>](apollo.md#blagodarnost)<mark style="color:red;"></mark>
* <mark style="color:red;"></mark>[<mark style="color:red;">Введение</mark>](apollo.md#vvedenie)<mark style="color:red;"></mark>
* <mark style="color:red;"></mark>[<mark style="color:red;">Как сбилдить & запустить</mark>](apollo.md#kak-sbildit-and-zapustit)<mark style="color:red;"></mark>
* <mark style="color:red;"></mark>[<mark style="color:red;">Модульность</mark>](apollo.md#modulnost)<mark style="color:red;"></mark>
* <mark style="color:red;"></mark>[<mark style="color:red;">Как активировать новые модули</mark>](apollo.md#kak-aktivirovat-novye-moduli)<mark style="color:red;"></mark>
* <mark style="color:red;"></mark>[<mark style="color:red;">Как написать собственный модуль</mark>](apollo.md#kak-napisat-sobstvennyi-modul)<mark style="color:red;"></mark>
* <mark style="color:red;"></mark>[<mark style="color:red;">Совет</mark>](apollo.md#sovet)<mark style="color:red;"></mark>

<mark style="color:red;"></mark>

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

Если вы всё таки собрались идти по более сложному пути, то пропустите установку с помощью Docker и перейдите [_<mark style="color:red;">**сюда**</mark>_](apollo.md#ustanovka-na-goloe-zhelezo) для "ручной" установки
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

### Установка на "голое железо"

Для представленного образа основным будет такой вот bash скрипт. Тут в целом шаг за шагом комментарии касательно того что вы устанавливаете. При этом, если у вас на машине уже установлены подобные компоненты, то вы можете пропустить их установку и скачать только то что вам нужно:

{% embed url="https://github.com/KLYN74R/KlyntarBaseImages/blob/main/Basic/setup.sh" %}

Для начала традиционно

```bash
apt-get update -y && apt-get upgrade -y
```

Затем установите необходимые бинарники

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

Последним необходимо установить Go

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

###

### ⚙️ <mark style="color:red;">Модульность</mark>

Working with different "hacking" tools,I've get the experience of so called 'best practises' of how to build real powerful tool. That's why, Apollo(as KLYNTAR) will be very modular. Just now,you have three ways to improve Apollo behaviour by loading modules to KLY\_Modules, KLY\_ServicesAPI and KLY\_WorkflowsAPI

\


#### **KLY\_Modules**

Directory for your external modules. This might be extra useful commands. Might be written by you or any other 3rd party. Must contain 2 directories **cli**(contains everything for commands in CLI) and **ui**(directory with everything for UI in browser). Soon we'll make a tutorial of HOWTO write modules for Apollo.

Each directory-is typically Git repository to allow you to easily update different modules independently if you need and swap versions. Moreover,soon you'll also have an amazing ability to verify authors cryptographically - via code signing. By having hash of repository you can verify authority and be sure that code is original using different crypto features like multisig or post-quantum cryptography,social staking and so on. We describe it in [Basic Security](https://mastering.klyntar.org/beginning/basic-security#additional-features) in our MasteringKlyntar book.

\
\


* CLI part

In CLI extra modules looks like ordinary commands. To allow your users to differ them, please, give them original prefix or make a single command with repository name and hide commands to subcommands

* UI part

If module also has a UI part(which is often the case), then you'll have ability to visit:

```shell

http(s)://<your_interface>:<port>/modules
```

to find there the entry point to your module.

\


**Summarizing this,your directories tree on these levels should look like this**

```
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

To update the repository with module go to appropriate directory **KLY\_Modules/\<your\_module>** and pull changes

\
\


#### **KLY\_ServicesAPI**

\


> **ServiceAPI** - directory with API repositories to interact with the scope of service runned on Klyntar. Imagine if all smart contracts on ETH will have a unique design in your wallet, separate page with all available features specific to contract. Since we have wider power, we also have so complicated way to improve abilities of your Apollo instance.

\


The same principle works for the services API. Each subdirectory - it's a repository. To check available services API go to

```shell

http(s)://<your_interface>:<port>/services
```

\
\


#### **KLY\_WorkflowsAPI**

\


> **WorkflowsAPI** - directory with API repositories to interact with symbiotes on Klyntar. Insofar as they can use different workflows(thanksfully to [Mutations principle](https://mastering.klyntar.org/beginning/mutations)),we need to make possible to use appropriate algorithms,build right events to send to symbiotes and use other specific features like traffic over TOR or threshold signatures. Imagine if you'll have ability to control your Bitcoin, Solana, Avalanche, Cosmos assets(native coins,tokens,etc.), execute smart contracts, make delegations using only one instrument. Yes,this is what Apollo do.

\


The same principle as for services API. Each subdirectory - it's a repository in this directory. To check your symbiotes and how to interact with them go to

```shell

http(s)://<your_interface>:<port>/symbiotes
```



### 🧐 <mark style="color:red;">Как активировать новые модули</mark>

### 🐱‍💻 <mark style="color:red;">Как написать собственный модуль</mark> 

### 🤓 <mark style="color:red;">Совет</mark>

Следите за нами, чтобы получать новости и обновления как можно скорее. Обсуждайте, делитесь идеями, советами, помогайте новичкам сделать наше сообщество сильнее. Мы рады привлечь новых участников в сообщество KLY 😊

\
[![](https://img.shields.io/badge/Reddit-FF4500?style=for-the-badge\&logo=reddit\&logoColor=white) ](https://www.reddit.com/r/KLYN74R/)[![](https://img.shields.io/badge/Twitter-1DA1F2?style=for-the-badge\&logo=twitter\&logoColor=white) ](https://twitter.com/KLYN74R)[![](https://img.shields.io/badge/Medium-12100E?style=for-the-badge\&logo=medium\&logoColor=white) ](https://klyntar.medium.com/)[![](https://img.shields.io/badge/TikTok-000000?style=for-the-badge\&logo=tiktok\&logoColor=white)](https://www.tiktok.com/@klyn74r)\
[![](https://img.shields.io/badge/Instagram-E4405F?style=for-the-badge\&logo=instagram\&logoColor=white) ](https://www.instagram.com/klyn74r/)[![](https://img.shields.io/badge/Pinterest-%23E60023.svg?\&style=for-the-badge\&logo=Pinterest\&logoColor=white) ](https://www.pinterest.com/klyn74r)[![](https://img.shields.io/badge/dev.to-0A0A0A?style=for-the-badge\&logo=devdotto\&logoColor=white) ](https://dev.to/klyntar)[![](https://img.shields.io/badge/GitHub-100000?style=for-the-badge\&logo=github\&logoColor=white)](https://github.com/KLYN74R)\
[![](https://img.shields.io/badge/Telegram-2CA5E0?style=for-the-badge\&logo=telegram\&logoColor=white) ](https://t.me/KLYN74R)[![](https://img.shields.io/badge/Discord-7289DA?style=for-the-badge\&logo=discord\&logoColor=white) ](https://discord.gg/f7e7fCp97r)[![](https://img.shields.io/badge/Tor%20site-330F63?style=for-the-badge\&logoColor=white) ](http://klyntar66kjwhyirucco6sjgyp2f7lfznelzgpjcp6oha2olzb4rlead.onion)[![](https://img.shields.io/badge/YouTube-FF0000?style=for-the-badge\&logo=youtube\&logoColor=white)](https://www.youtube.com/channel/UC3TiyK40an6rQlf3BarMDoQ)\
[![](https://img.shields.io/badge/Facebook-1877F2?style=for-the-badge\&logo=facebook\&logoColor=white) ](https://www.facebook.com/KLYN74R/)[![](https://img.shields.io/badge/GitLab-330F63?style=for-the-badge\&logo=gitlab\&logoColor=white) ](https://gitlab.com/KLYNTAR)[![](https://img.shields.io/badge/Tumblr-%2336465D.svg?\&style=for-the-badge\&logo=Tumblr\&logoColor=white) ](https://klyn74r.tumblr.com/)[![](https://img.shields.io/badge/Stack\_Overflow-FE7A16?style=for-the-badge\&logo=stack-overflow\&logoColor=white)](broken-reference)

