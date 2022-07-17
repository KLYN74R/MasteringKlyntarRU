# 🥵 Apollo и WorkflowsAPI

Поскольку разные симбиоты работают следуя разному функционалу, имеют свой набор он-чейн событий, свои смарт-контракты и свои связи с хостчейнами, то необходимо предоставить соответствующий функционал для взаимодействия с симбиотом.

Для этого и существуют WorkflowsAPI. Они размещаются в директории KLY\_Workflows и имеют аналогичную структуру с директориями cli и ui

```
Apollo
│     
│   
└───KLY_Workflows
│   │   
│   │
│   │   
│   └───dev_controller
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

Для активации, внесите изменения в конфигурацию Apollo

```json
 "EXTRA_CLI": [
        "KLY_Modules/init/cli/init.js",
        "KLY_"
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

В Apollo вы увидите их в разделе SYMBIOTES после подключения модуля в конфигурационном файле и перезапуска сервера

![](<../../.gitbook/assets/image (15) (1).png>)

{% hint style="info" %}
Эта страница будет дополнена со временем
{% endhint %}
