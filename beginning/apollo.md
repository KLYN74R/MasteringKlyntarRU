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

* <mark style="color:red;">Благодарность</mark>
* <mark style="color:red;">Введение</mark>
* <mark style="color:red;">Как сбилдить & запустить</mark>
* <mark style="color:red;">Модульность</mark>
* <mark style="color:red;">Как активировать новые модули</mark>
* <mark style="color:red;">Как написать собственный модуль</mark>
* <mark style="color:red;">Совет</mark>

###

### 👨‍🚀 <mark style="color:red;">Благодарность</mark>

Поскольку KLYNTAR - проект "космических" масштабов, то и инструмент для взаимодействия с ним должен быть соответствующий. Много разных проектов или компаний называют свои продукты / протоколы в честь известных учёных, исторических личностей или событий. Мы в данном аспекте тоже поддержим общественный флэшмоб и поэтому решили назвать инструмент для взаимодействия с KLYNTAR в честь важного события в сфере астронавтики и изучения космоса - всем известной программы Аполлон, той самой, во время которой человечество впервые ступило на внеземное тело, а именно - на Луну.

![](https://monophy.com/media/lS7GfvzSVhWOhJKlng/monophy.gif)

Символизм здесь в том, что не всё было идеально, происходили аварии, разработки продолжались годами, но всё же благодаря плодотворной работе множества людей разных профессий человек все таки получил шанс стать межпланетным видом и добавить ещё одну галочку в список достижений рода людского. Мы надеемся что наш Apollo ждёт аналогичный успех ведь вложено множество сил и всё для того - чтоб подарить вам шанс выйти за рамки текущих достижений крипто индустрии.



### ⚡ <mark style="color:red;">Введение</mark>

Мы рады представить вам Apollo — наш мощный инструмент командной строки и пользовательского интерфейса для управления вашей инфраструктурой KLYNTAR. С помощью Apollo вы можете делать все — использовать его в качестве кошелька, взаимодействовать с децентрализованными сервисами, контролировать свои источники Unobtanium, использовать возможности Cryptoland — нашей удивительной коллекции криптоалгоритмов доступных на KLYNTAR и многое другое!

Здесь вы узнаете как начать работать с Apollo, некоторые основные указания и помощь чтоб быстрее начать работать с KLYNTAR. Мы планируем показать вам как загружать модули, как писать модули(если вы разработчик) для расширения возможностей как CLI так и UI, как контролировать свои кластеры из узлов и так далее.

Поскольку это довольно мощный инструмент(а не просто CLI с предварительным списком hardcoded команд), то мы постараемся дать вам самое важное - базовое понимание принципа работы, как оно всё взаимосвязанно. Стоит сказать что Apollo отличается от других подобных инструментов типа Metamask, Phantom и подобных тем, что здесь в работу будут включены всевозможные разработчики сервисов на KLYNTAR для создания персонализированных интерфейсов непосредственно для каждого сервиса, симбиота или группы сервисов. Это равносильно тому, если бы разработчики смарт-контрактов EVM-совместимых цепей которыми вы пользуетесь в том же Metamask предлагали бы уникальный интерфейс для каждого смарт-контракта.

Так, например, если это DeFi сервис работающий в экосистеме KLY, то перед вами в интерфейсе появятся необходимые данные, поля, последние новости из фида Твиттера этого проекта и так далее, если это основное меню Apollo, то в бегущей строке вы так же встретите объявления по предложениям стейкинга вашего унобтаниума на какие-то новые сервисы где вы сможете решить, что вам выгодно-поставить свои KLY на майнера BTC и получить , а перейдя на [<mark style="color:purple;">wikipedia.org</mark>](https://wikipedia.org) или читая какую-то статью на [<mark style="color:purple;">Medium</mark>](https://medium.com) вы сможете отблагодарить авторов и получить какой-то эксклюзивный контент от них. И всё это в одном чёрном ящике под названием Apollo. Думаю слюнки уже потекли, так что поехали 🤤



### 🏗️ <mark style="color:red;">Как сбилдить & запустить</mark>

Лучше 1 раз показать чем 100 сказать. С таким настроем переходим к запуску. Как вы наверняка уже прочитали ранее, KLYNTAR находится в симбиотических отношениях с другими блокчейнами-как уже существующими типа Bitcoin, Avalanche, XRP, Solana так и теми которые только будут изобретены в будущем.

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

Представляем вам наш первый образ [_<mark style="color:red;">**klyntar/all\_in\_one**</mark>_](https://hub.docker.com/repository/docker/klyntar/all\_in\_one/general) _<mark style="color:red;">****</mark>_ из коллекции Docker образов KLYNTAR. Это универсальный образ с предустановленными Node.js, Go, Python и некоторыми инструментами вроде pnpm, node-gyp, git и так далее. Мы создали его, чтобы сэкономить ваше время и нервную систему. Это базовый уровень для всех наших Dockerfiles (по крайней мере, для ядра и Apollo). Приблизительный сжатый размер составляет 606 мегабайт. Кроме того, в нашем репозитории[ _<mark style="color:red;">**KlyntarBaseImages**</mark>_](https://github.com/KLYN74R/KlyntarBaseImages) вы можете найти исходники всех файлов Docker базового уровня, так что вы можете cклонировать и собрать его самостоятельно или найти скрипт сборки bash и, таким образом, установить требования на свой хост-компьютер.&#x20;

Но в любом случае, мы рекомендуем вам использовать контейнеры.

![](https://user-images.githubusercontent.com/53381472/174490998-2041af0d-6cd5-4873-ad64-fa810cda02df.jpg)

```shell
docker pull klyntar/all_in_one@sha256:dff001a9cd3da6328c504b52ed8a5748c47d23219feae220930dac1c1981cfe7
```



**Запуск контейнера**

Мы рекомендуем вам пробросить порт 9691 который является портом по умолчанию для Apollo(опять таки отсылка:9691-это в обратном порядке 1969 год когда и был запуск Аполлон-11)

{% hint style="warning" %}
#### **ВНИМАНИЕ**

Это самый простой и стандартный способ запуска для быстрого старта. Если вы опытный пользователь, то вы можете запускать вручную с более сложными шагами-использовать тома, менять пользователя и уровни доступа и так далее
{% endhint %}

```shell
docker run -dtp 9691:9691 --name test_kly klyntar/all_in_one@sha256:dff001a9cd3da6328c504b52ed8a5748c47d23219feae220930dac1c1981cfe7
```

#### **Final**

Go into container to root dir

```shell
docker exec -ti test_kly bash

# Inside container

cd ~
```

Clone Apollo repository

```shell
git clone https://github.com/KLYN74R/Apollo.git

cd Apollo
```

Finally,run the only one command

```shell
pnpm run build
```

### **Now take a rest and see the building process. It may take some minutes,but you're free from self-install tons of libs,dependencies and walking among dirs**

\


![](https://i.pinimg.com/originals/d0/63/09/d063096ba4e07795c1bdf98572cb79a8.gif)

#### The signs that build was succesful are messages to console like this 

![](https://2131090630-files.gitbook.io/\~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2FphIHWZY173DpNXBbDjVg%2Fuploads%2FdewG1SQftz0ndvmG4fNa%2Fimage.png?alt=media\&token=ad2710a7-0fd1-43cb-ad80-62e78badb989)

#### ...and this

![](https://2131090630-files.gitbook.io/\~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2FphIHWZY173DpNXBbDjVg%2Fuploads%2FL3RavrjoA7nktQKFfV3i%2Fphoto\_2022-06-04\_11-55-04.jpg?alt=media\&token=6363785e-a243-4f98-80ca-5ee83b97da87)

#### Now try to run. You should see the following

![](https://user-images.githubusercontent.com/53381472/174460136-49cbf58b-fe08-4952-81b2-3b6e13d96444.jpg)

### ⚙️ Modularity

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

\
\


### 🤓 Advice

\


Follow us to get the news & updates ASAP. Discuss, share ideas, advices, help newbies to make our community more powerful.We're happy to involve new members to KLY community 😊

\
[![](https://img.shields.io/badge/Reddit-FF4500?style=for-the-badge\&logo=reddit\&logoColor=white) ](https://www.reddit.com/r/KLYN74R/)[![](https://img.shields.io/badge/Twitter-1DA1F2?style=for-the-badge\&logo=twitter\&logoColor=white) ](https://twitter.com/KLYN74R)[![](https://img.shields.io/badge/Medium-12100E?style=for-the-badge\&logo=medium\&logoColor=white) ](https://klyntar.medium.com/)[![](https://img.shields.io/badge/TikTok-000000?style=for-the-badge\&logo=tiktok\&logoColor=white)](https://www.tiktok.com/@klyn74r)\
[![](https://img.shields.io/badge/Instagram-E4405F?style=for-the-badge\&logo=instagram\&logoColor=white) ](https://www.instagram.com/klyn74r/)[![](https://img.shields.io/badge/Pinterest-%23E60023.svg?\&style=for-the-badge\&logo=Pinterest\&logoColor=white) ](https://www.pinterest.com/klyn74r)[![](https://img.shields.io/badge/dev.to-0A0A0A?style=for-the-badge\&logo=devdotto\&logoColor=white) ](https://dev.to/klyntar)[![](https://img.shields.io/badge/GitHub-100000?style=for-the-badge\&logo=github\&logoColor=white)](https://github.com/KLYN74R)\
[![](https://img.shields.io/badge/Telegram-2CA5E0?style=for-the-badge\&logo=telegram\&logoColor=white) ](https://t.me/KLYN74R)[![](https://img.shields.io/badge/Discord-7289DA?style=for-the-badge\&logo=discord\&logoColor=white) ](https://discord.gg/f7e7fCp97r)[![](https://img.shields.io/badge/Tor%20site-330F63?style=for-the-badge\&logoColor=white) ](http://klyntar66kjwhyirucco6sjgyp2f7lfznelzgpjcp6oha2olzb4rlead.onion)[![](https://img.shields.io/badge/YouTube-FF0000?style=for-the-badge\&logo=youtube\&logoColor=white)](https://www.youtube.com/channel/UC3TiyK40an6rQlf3BarMDoQ)\
[![](https://img.shields.io/badge/Facebook-1877F2?style=for-the-badge\&logo=facebook\&logoColor=white) ](https://www.facebook.com/KLYN74R/)[![](https://img.shields.io/badge/GitLab-330F63?style=for-the-badge\&logo=gitlab\&logoColor=white) ](https://gitlab.com/KLYNTAR)[![](https://img.shields.io/badge/Tumblr-%2336465D.svg?\&style=for-the-badge\&logo=Tumblr\&logoColor=white) ](https://klyn74r.tumblr.com/)[![](https://img.shields.io/badge/Stack\_Overflow-FE7A16?style=for-the-badge\&logo=stack-overflow\&logoColor=white)](broken-reference)

\
\


### 📚Docs

Read the docs here to find out more



:flag\_gb:: [![](https://img.shields.io/badge/Gitbook-000000?style=for-the-badge\&logo=gitbook\&logoColor=white)](https://mastering.klyntar.org)\
:flag\_ru:: [![](https://img.shields.io/badge/Gitbook-000000?style=for-the-badge\&logo=gitbook\&logoColor=white)](https://ru.mastering.klyntar.org)
