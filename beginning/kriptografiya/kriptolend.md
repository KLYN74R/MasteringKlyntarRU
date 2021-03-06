---
description: Чё за Диснейленд ещё?!
cover: ../../.gitbook/assets/ScZyDB.webp
coverY: -478.0082987551868
---

# 🎢 Криптоленд

### <mark style="color:red;">Важность для всех</mark>

Поскольку мы в рамках нашей экосистемы планируем развивать большое количество проектов, очевидным становится факт что если все они будут тем или иным образом связаны с KLYNTAR, то значит ожидается использование разного рода криптографических примитивов.

Для того, чтобы отделить криптографические возможности от конкретных реализаций модулей KLYNTAR(например для workflow симбиотов или в рамках рабочих процессов сервисов) мы решили создать отдельный удобный репозиторий где собрали разного рода алгоритмы - от обычных подписей до кольцевых и мультиподписей. От пост-квантовых алгоритмов обмена ключами и до пост-квантовых подписей(в основном это текущие NIST кандидаты 1-5 уровней безопасности). Короче, можете сами исследовать репозиторий.

Стоит ещё упомянуть что в production версии ядра KLYNTAR используются разные языки - от основного JS и до отдельных компонентов на WASM, Go, C и Rust. Таким образом мы как бы подсказываем разработчикам что они могут публиковать разного рода решения на любом языке который они знают и могут предложить какое-то интересное и полезное нововведение для KLYNTAR или других проектов. В любом случае, можно будет их использовать путём компиляции в WASM, использования аддонов, библиотек и так далее.

Цель создания этого репозитория так же в том, чтоб дать как разработчикам KLYNTAR так и просто сторонним девелоперам для своих проектов возможность быстро "влиться" в суть алгоритма для того, чтоб придумать потенциальные юзкейсы. Так же мы ожидаем и со стороны разработчиков простой и понятный API для работы с алгоритмом и потенциальные предложения по тому как встраивать их в проект.

Так же можно ещё добавить что на протяжении времени разработок KLYNTAR мы сами сталкивались в проблемами отсутствия внятных формулировок. Например, как было указано ранее, многие из алгоритмов взяты с репозиториев известных компаний(таких как Coinbase, Google, Cloudflare) у которых наверняка в штабе работают криптографы или по крайней мере люди хорошо понимающие базу. Но тем не менее, не везде было легко портировать например код на Go в C или из C в Node.js аддоны - где-то были проблемы с сериализацией, где-то с плохим описанием. Вроде есть код, вроде как работает, а вот API для быстрого использования нет - не все умеют писать нормальный README.

Здесь же в _<mark style="color:purple;">**Cryptoland**</mark>_ мы предполагаем что авторы будут делать форк репозитория, добавлять свою директорию внутри категорий алгоритмов и добавлять туда как файлы своих работ так и понятное описание как и где это можно использовать.

#### <mark style="color:red;">Приведу примеры:</mark>

* <mark style="color:yellow;">Вы добавляете какой-то новый алгоритм подписи</mark>\
  \
  Во-первых, постройте правильную структуру проекта будь то ESM модуль JS, Rust крейт или библиотека Go. Предоставьте понятные внешние интерфейсы для того, чтоб сторонний разработчик даже не углубляясь мог легко заметить типичные функции "sign", "verify", "generateKeypair" и так далее. Предоставьте в README несколько примеров использования как на примере ниже

```javascript
import {sign,verify,generateKeys} from '@org/your-package'

//Generate keypair
//Note - use defualt keysizes. Supports 32 and 64 bytes
let keypair = generateKeys(32)


//Sign any data
let signature = sign(keypair.privateKey,"YOU DATA TO SIGN")


//Let's verify
let isVerified = verify(keypair.publicKey,"YOU DATA TO SIGN",signature)
```

Это ускорит работу других программистов которые на основе данных алгоритмов создадут новые кошельки или интерфейсы для Apollo, новые сервисы на KLYNTAR и так далее

* <mark style="color:yellow;">Вы добавляете какой-то новый алгоритм из сферы</mark> <mark style="color:red;">**Zero-Knowledge-Proofs**</mark>\
  \
  Объясните криптографическую базу, предоставьте ссылки и/или названия для того, чтоб было легче искать альтернативы. Опять таки предоставьте что-то типа директории с примерами где простым языком людям будет описан процесс использования. Так же, ввиду того что вы разработчик и явно понимаете о чём пишите - предложите интересные юзкейсы использования.

{% embed url="https://github.com/KLYN74R/Cryptoland" %}

### <mark style="color:red;">Упоминание ValarDohaeris</mark>

Так же помимо  Cryptoland у нас существует и другой репозиторий - ValarDohaeris

{% embed url="https://github.com/KLYN74R/ValarDohaeris" %}

Целью создания такого репозитория была подготовка к релизу [_<mark style="color:purple;">**ValarDohaeris**</mark>_](../relizy/valardohaeris.md) <mark style="color:red;"></mark> в рамках которого мы работали над тем, чтоб владельцы приватных ключей других блокчейн проектов могли легко взаимодействовать с KLYNTAR. Так например в Apollo вы можете подтвердить владения своими приватными ключами чтоб узлы KLYNTAR распознали количество унобтаниума на ваших кошельках и могли понять сколько блоков вы сгенерировали в Filecoin или сколько токенов на вашем счету в BSC. Глядя на него и можно понять что мы имели ввиду когда говорили про удобство использования - хороший и понятный README и однотипная структура и вот уже кто угодно может ним пользоваться.

```javascript
//CRYPTO is klyntar,algorand,arweave,eos,eth_like,filecoin,harmony,helium,mina,polkadot,ripple,solana,stellar,zilliqa(unimplemented)
//TIP: Check the directories of package to get available formats or https://github.com/KLYN74R/ValarDohaeris

import VD from '@klyntar/valardohaeris/<CRYPTO>/vd.js'


//_______________________________ USE DEFAULT SETS OF FUNCTIONS _______________________________


let keys=await VD.generate()

console.log(keys)//Make sure format is OK

//Sign data in the string format
let data='SIGN ME',

    signature=await VD.sign(data,keys.privateKey)

console.log('Your signature in transportable format => ',signature)

console.log('Is ok => ',await VD.verify('ANOTHER DATA',signature,keys.address),` (should be ❌)`)

console.log('Is ok => ',await VD.verify(data,signature,keys.address),'(should be ✔️)')



//_______________________________ AND EXPLORE SPECIFIC FUNCTIONS _______________________________

console.log('Address in another format: ',VD.toPUB_K1(keys.address))
```

### <mark style="color:red;">Награды разработчикам</mark>

Разумеется работа на пользу KLYNTAR не может оказаться незамеченной. Подробней вы сможете узнать в разделе [_<mark style="color:yellow;">**Контрибуторам**</mark>_](../kontributoram.md), а сейчас просто коротко упомяну что в рамках социального консенсуса, прямо в интерфейсе Apollo(или других 3rd party инструментов) пользователи смогут проголосовать за наиболее полезные вклады в KLYNTAR. Неважно, разработчик плагинов вы, создали несколько паков с коннекторами или добавили много алгоритмов(как в данном случае речь идёт именно об этом) - всё это будет учтено на уровне метрик типа количество клонирований, личное предпочтение пользователей и разработчиков, количество сервисов и/или смарт контрактов с использованием данных алгоритмов(и их активность) и так далее.

Ввиду этого мы допускаем что фонд сформированный на основе комиссий будет распределён между командами разработок или одиночными разработчиками.

Что ещё интересно, так это разного рода фичи(ну куда же без них). Так например разработчик который победит сможет вместо награды заставить определенные адреса обменять KLY на какие-то токены поверх KLYNTAR. Однако об этом узнаете в указанной ссылке для контрибуторов.

