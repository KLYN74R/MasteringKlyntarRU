---
description: Кастомные интерфейсы для KLYNTAR Services в Apollo
---

# 🥶 Apollo и ServicesAPI

{% hint style="info" %}
Здесь мы расскажем как разрабатывать и добавлять функционал сервисов чтоб использовать их в едином интерфейсе
{% endhint %}

### <mark style="color:red;">**Немного информации**</mark>

Было бы круто если б кошельки которыми вы пользовались ранее генерировали интерфейс и поля непосредственно для каждого Dapp и/или смарт-контракта с которым вы взаимодействуете. Кроме того, разработчики кошелька могут допустить некоторые ошибки и не всегда будут успевать за всеми новинками индустрии.

В KLYNTAR разработчики сервисов могут сами создавать свои интерфейсы и API для взаимодействия с ними.

Так к примеру, если вы перейдёте на сервис который будет представлять децентрализованную биржу, то вы увидите необходимые поля для ввода, полезную информацию взятую из API сайта разработчиков этого сервиса.

Если это Play-to-Earn сервис, то вы сможете увидеть свою коллекцию в красивой витрине, а через API Telegram опубликовать объявления о продаже в нужных Telegram каналах. &#x20;



В плане дерева директорий - ничего нового

```
Apollo
│     
│   
└───KLY_ServicesAPI
│   │   
│   │
│   │   
│   └───AMAZING_SERVICE_1
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
```

Новые API подключаются с помощью настроек конфигурации

```json
"EXTRA_CLI": [
        "KLY_Modules/init/cli/init.js",
        "KLY_ServicesAPI/some_service/cli/init.js"
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
```

В <mark style="color:yellow;">**OPTIONS**</mark> вы указываете префикс для вашего сервиса. Таким образом полный путь до главной страницы API сервиса будет такой **http(s)://localhost:9691/**<mark style="color:red;">**services**</mark>**/**<mark style="color:red;">**<**</mark><mark style="color:orange;">**YOUR\_PREFIX**</mark><mark style="color:red;">**>**</mark>

Так же вы можете выбрать алиас для сервиса(опция ALIAS). Рекомендуется выбирать что-то понятное для вас.

Так же укажите <mark style="color:yellow;">**TYPE**</mark>=service как на примере выше. Это необходимо для выделения сервисов среди прочих роутов.

Наконец, перезагрузите Apollo и перейдите в раздел с сервисами.

![](<../../.gitbook/assets/image (8).png>)

![](<../../.gitbook/assets/image (1).png>)

Сбоку появятся кнопки которые и приведут вас к главной странице API вашего сервиса

### <mark style="color:red;">**Coming soon**</mark> 👻

Больше информации появиться в будущем
