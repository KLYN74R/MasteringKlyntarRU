---
description: Посмотрим на то, с чего будут начинаться смарт-контракты нового поколения
cover: ../.gitbook/assets/Cyberpunk_final-uai-2880x1757.jpg
coverY: 232.6476683937824
---

# ⚙ Раннеры

### <mark style="color:red;">**С чего всё начинается**</mark>

После того, как вы успели ознакомится с возможностями сервисов, настало время рассказать более детально как они будут выполняться, что и где их будет запускать и как это работает в целом.

На KLYNTAR все сервисы так или иначе будут проходить через раннер и его правила. Раннер - это как промежуточное ПО которое принимает сервис из сети и на основе своих настроек принимает решения вида

* Стоит ли запускать сервис
* Как и сколько памяти выделять сервису
* Ставить ли какие-то ограничения
* Какой бюджет безопасности и сколько центров безопасности проверили данный репозиторий
* Входит ли адрес в дерево доверия
* Сколько потенциально можно получать с этого сервиса
* Стоит ли распространять и рекламировать сервис дальше по сети
* ...и другие решения

Раннер принимает решение запускать ли сервис на этой ноде или отправить на другие, давать ли доступ в сеть для сервиса, запускать ли его в отдельном контейнере или же в каком-то из существующих и так далее.

Вот как можно схематично представить раннер

![](<../.gitbook/assets/Runner.drawio (1).png>)

### <mark style="color:red;">В двух словах</mark>

Ноды прослушивают, распространяют и скачивают репозитории(если дана ссылка) или сжатые архивы(если сервис распространяется напрямую) и следуя правилам и настройкам раннера принимают решения как запускать сервис.

Ввиду независимости раннеров от сети и ее процессов, а также продолжая тему модульности, мы разрешим пользователям использовать для своих инфраструктур кастомные раннеры, а так же предоставим возможность гибкой конфигурации и настройки для максимально эффективной работы.

Хоть функционал раннера вы определяете сами, мы всё таки рекомендуем ориентироваться на официальные решения как на наиболее эффективные.

### <mark style="color:red;">**Раннер на уровне кода**</mark>

На уровне кода - раннер это отдельный репозиторий который лежит в директории _<mark style="color:red;">**KLY\_Runners**</mark>_. Вам уже должен быть знакомый принцип того, как мы храним данные, но мы всё равно для наглядности покажем структуру директорий.

Вот, к примеру как это выглядит на уровне редактора кода

![](<../.gitbook/assets/image (7).png>)

Вы можете обновлять репозитории независимо друг от друга. Демон KLYNTAR при запуске просматривает конфигурационный файл <mark style="color:orange;">**services.json**</mark> и опцию <mark style="color:orange;">**RUNNER**</mark> где указан путь к точке входа раннера.

Вот как это выглядит. Файл конфигурации _<mark style="color:red;">**services.json**</mark>_

```json
{
    "SERVICES":{
        
        //...define your services here to run in the same instance
    
    },

    "EXTERNAL_SERVICES":{

        //...define services of other
                
    },

    "RUNNER":"dev_andromeda/runner.js"
    
}
```

_<mark style="color:red;">**runner.js**</mark>_ представляет собой точку входа раннера который экспортирует функцию без имени которая на вход получает объект стандартной структуры и принимается за его обработку.

Вот как это выглядит

```javascript
export default async service=>{

    if(typeof service.title==='string' && service.desc.length<RUNNER_CONFIGS.DESC_MAX_LEN){

        LOG({data:`Received new service \x1b[31;1m${service.desc}\x1b[0m`,pid:process.pid},'CD')

        //...logic

    }
    
}
```

Что касается рабочих процессов, то поскольку они составляют набор обработчиков роутов и сами создают маршруты на сервер, то они должны предоставить обработчик и для раннера, чтоб просто получить данные из сети, передать в функцию и дальше раннер сам сделает свою работу.

К примеру, рабочие процессы _<mark style="color:red;">**dev\_controller**</mark> _ и _ <mark style="color:red;">**dev\_bft**</mark>_ предоставляют такие обработчики

```javascript
import {SAFE_ADD,PARSE_JSON} from '../../../KLY_Utils/utils.js'



//Get our runner
let SERVICE_RUNNER=await import(`../../../KLY_Runners/${CONFIG.RUNNER}`).then(m=>m.default).catch(e=>console.log(e))




export let SERVICES = {
    
    //Only this one function available for ordinary users(the others can be called by node owner)
    services:a=>{
        
        let total=0,buf=Buffer.alloc(0)
        
        a.writeHeader('Access-Control-Allow-Origin','*').onAborted(()=>{}).onData(async(chunk,last)=>{
         
            if(total+chunk.byteLength<=CONFIG.MAX_PAYLOAD_SIZE){
            
                buf=await SAFE_ADD(buf,chunk,a)//build full data from chunks
    
                total+=chunk.byteLength
                
                if(last){

                    let body=await PARSE_JSON(buf)

                    a.end(body?'OK':'ERR')

                    //Run further stage
                    SERVICE_RUNNER(body)

                }
  
            }
        
        })

    }

}



//Register route
UWS_SERVER

.post('/service',SERVICES.services)
```

Как видно, сервер просто принимает некоторый JSON объект сервиса и передает на обработку раннеру, а сам просто отправляет простой HTTP ответ.

### <mark style="color:red;">**Пример конфигурации раннера**</mark>

Для того, чтоб ещё больше понять принцип работы, можно заглянуть в конфигурации

```javascript
{
    "DOCKER_CONFIGS":{
        
        "protocol":"http",
        "host":"localhost",
        "port":2375
    
    },

    "DESC_MAX_LEN":200,
    "REDIRECTION_DEPTH":3,

    "STATIC_NODES":[
        "https://someklyntarpool.io",
        "htts://api-klyntar.coinbase.com"
    ],

    "TRUSTED_HUBS":{
        "WoD3FV8ByzerAUUCZ5rF58aTLpz5kTNxHnyBS5vzuqeq":{},
        "7HHKSu9BNF7GuB3CX8BbUEzx9pp1SqLksigvfMZz9hopvWJJRSW4qrXTKWFq5ExSpm":{},
        "63dMQGT8u5BvsAE7UniDSbBDmK6igBvcwSVHotaQ6938eMRYPbZSHwAYTgQcACQ2KK":{}       
    },

    "PREFER_TOOLCHAIN":{
        
        "docker":["rust","node.js","c","c++"],

        "host":["rust","node.js","c","c++"]
        
    },

    "KEYWORDS":["web3","defi","bridge","tor","control","storage","api"],

    "NETCAP":{
 
    },

    "PREFER_SYMBIOTES":{
    
        "QfzhbWJsPa9NjqxepcXSbp1X58pkQNACS2ReyRo2SMCK":{
            "MIN_FREEZE":0
        },
        "NrHwU6YMS5VZatxo9Z188ptR7dbNyYexRKCYickQBJG4":{},
        "LvjcXxRbXbKnHSgaJrDWLx7vo8yR3BwpkBXApKukoaGX":{}
    },
    
    "PREFER_HOSTCHAINS":{
    
        "btc":{
            "MIN_FREEZE":0
        },
        "algo":{},
        "sol":{}
    },
    
    "DORMITORY":{
        
    },
    
    "ALLOWED_STORAGE":[
        "github.com",
        "gitlab.com",
        "pkg.go.dev",
        "crates.io",
        "npmjs.com",
        "rubygems.org",
        "getcomposer.org",
        "www.nuget.org",
        "hackage.haskell.org",
        "index.scala-lang.org"
    ],


    "REGISTRIES":{

        "NODE.JS":[
            
            "https://localhost:4873"
        
        ],
        "PYTHON":[


        ],
        "RUST":[


        ],
        "DOCKER":[
            
            "https://localhost:5000"
            
        ]

    },

    "CONTAINERS":[
        "group1-WoD3FV8ByzerAUUCZ5rF58aTLpz5kTNxHnyBS5vzuqeq-node",
        "group1-JeVZcdi8TQZaX6TKhtSKLCzMQMRCx5JjsQTiGbAaLPXW-rust.node.go.python"
    ]
    
}
```

Тут раннер может определять из каких ресурсов разрешена загрузка файлов, определять контейнеры с которыми он будет работать, устанавливать доверенные центры-это могут быть мультисиг адреса которые к примеру пришлют вам подпись о безопасности сервиса и вы убедитесь что если за безопасность сервиса уже проголосовало определенное количество адресов с общим балансом более нескольких миллионов KLY и прочие опции.

Всё это, ещё раз подчёркивает гибкие возможности KLYNTAR и возможности раннеров.

### <mark style="color:red;">**Дефолтные раннеры**</mark>

По умолчанию вам будет доступен стандартный раннер от разработчиков KLYNTAR. Мы назвали его в честь нашей галактики-соседки Андромеды. Это символизм так как мы сравниваем обычные смарт-контракты с нашей, относительно хорошо известной галактикой Млечный путь. А вот сервисы в том виде, в котором они будут на KLYNTAR - это нечто новое, какая-то новая галактика - не столь далёкая, но всё же - открывает нам новые возможности

![](../.gitbook/assets/spiral-galaxy-hi.png)

{% hint style="info" %}
В настоящее время все раннеры находятся в разработке и не будут доступны первое время для использования в сети
{% endhint %}
