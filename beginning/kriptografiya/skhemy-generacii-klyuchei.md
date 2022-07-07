---
description: Пожалуй, самое простое
cover: ../../.gitbook/assets/3092916.jpg
coverY: 0
---

# 🔐 Схемы генерации ключей

### <mark style="color:red;">Ed25519</mark>

Ed25519 был представлен в OpenSSH версии 6.5. Это реализация EdDSA с использованием [<mark style="color:yellow;">кривой Twisted Edwards</mark>](https://en.wikipedia.org/wiki/Twisted\_Edwards\_curve) . Он использует криптографию с эллиптическими кривыми, которая обеспечивает лучшую безопасность и более высокую производительность по сравнению с DSA или ECDSA.

Для любых типов взаимодействия с KLYNTAR необходимо иметь пару ключей. Приватным ключом вы подписываете данные, а публичный используется для проверки подписи. В целом, принцип знакомый для всех.

В качестве самой дефолтной пары KLYNTAR использует Ed25519. Размеры ключей(как приватного так и публичного) - 32 байта. Публичный ключ в Base58 - это и есть ваш адрес на KLYNTAR.

Кстати, KLYNTAR адреса совместимы с Solana(учитывая тот факт что их дефолтные адреса-это просто публичный ключ в Base58). Более того, транзакция коммита _<mark style="color:red;">**useful.txt**</mark>_ на мейнете Solana(с вызовом Memo программы) была произведена парой ключей KLYNTAR

![Вы можете просмотреть транзакцию на официальном обозревателе Solana](<../../.gitbook/assets/image (3) (1).png>)

{% embed url="https://explorer.solana.com/tx/36cs4bjKZJNcTsMA8N6Bz8mm2yBUX5WvcT74oT3Pn2sD6cMGprRQvmYVdPGQJmrnHPDrypJYkT9Zg6UHw4vuPssT" %}

Вот типичный пример пары ключей сгенерированной например через CLI или UI в Apollo

```
{
    publicKey: 'FmiD6J3EnJWce3M1UWwmbTSk4ss6HwX9Bq1ZGVJTq9Va',
    privateKey: 'MC4CAQAwBQYDK2VwBCIEIFBUTTsdsx2gq6XstzmhhU7AF0NExjJF3C15z8D4rHwJ'
}
```

![](<../../.gitbook/assets/image (6).png>)

<mark style="color:red;">**Node.js генерирует пару ключей в DER формате**</mark>

1.Публичный SPKI типа. Так он имеет такой вид сразу после генерации

`MCowBQYDK2VwAyEAsqv+zpsKO6vdklZ7wGcXzkpb27j+buojClSpqj78F3U=`

Все ключи подобного типа имеют общие 12 байт которые незачем хранить публично. Мы их срезаем и переводим оставшиеся 32 байта в Base58. Данный процесс можно визуализировать так

![](<../../.gitbook/assets/ed25519.drawio (1).png>)

2.Приватный PKCS8 типа. Аналогично, все приватные имеют общие 16 байт, однако поскольку они не публикуются, то менять их размер незачем. Мы просто применяем Base64 к такому ключу и он имеет следующий вид

`MC4CAQAwBQYDK2VwBCIEIKiJ1JIhmP4NelCCV5IAgQdOSfS/t3+9EjiL4zgG1HA0`

### <mark style="color:red;">Генерация через OpenSSL</mark>

Вы так же можете повторить всё это через OpenSSL

```shell
openssl genpkey -algorithm ed25519 -outform DER -out ed25519_private

cat ed25519_private | base64

//...что то типа MC4CAQAwBQYDK2VwBCIEIDNfdnUlKdo4fYCG+NzoEQRyanCphYKZUA9XX8uFI7nV
```

Генерация публичного

```shell
openssl pkey -outform DER -pubout -in ed25519_private -inform DER -out ed25519_pub

cat ed25519_pub | base64

//...MCowBQYDK2VwAyEA4PbMaYPMC+iTYtEfcNJmdoa4o8L0+yvQB2JEHLzRfi8=
```

Останется только перевести в байтовую форму публичный ключ, убрать первые 12 байт и перевести в Base58.

### <mark style="color:red;">Подпись</mark>

Подпись стандартная и занимает 64 байт. На KLYNTAR мы используем ее в Base64.

### <mark style="color:red;">А почему не через seed фразу</mark>

Тут как говориться coming soon. Мы также добавим позднее HD(hierarchical deterministic) возможности в кошелёк, а пока вот таким вот образом.

### <mark style="color:red;">Ещё пару слов</mark>

Мы так же решили не идти по пути генерации каких-то чексумм, определённых префиксов и так далее. Так же мы не стали разделять адреса на mainnet / testnet форматы ввиду бесполезности и неудобства(учитывая опыт работы с Bitcoin и форками).

Ed25519 был выбран как наилучший из всех доступных кандидатов для того чтоб стать универсальным для симбиотов, сервисов, для использования в смарт контрактах и других проектах в экосистеме.

### <mark style="color:red;">Ссылки</mark>

{% embed url="https://ed25519.cr.yp.to/" %}

{% embed url="https://cryptobook.nakov.com/digital-signatures/eddsa-and-ed25519" %}
