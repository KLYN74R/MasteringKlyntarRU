---
description: Пару слов о zkSNARK и zkSTARK
cover: >-
  ../../.gitbook/assets/permainan-video-cyberpunk-2077-cyborg-girl-cosplay-kertas-dinding-2560x1920_27.jpg
coverY: 265.25597657470735
---

# 🤔 Доказательства с нулевым разглашением

### <mark style="color:red;">zkSNARK на KLYNTAR</mark>

Мы понимаем важность применения криптографии с нулевым разглашением в различных сферах и стремимся к полной интеграции с существующими и новыми решениями.&#x20;

Поскольку KLYNTAR имеет модульную архитектуру и поддержку как WASM так и EVM совместимых виртуальных машин(а так же и других в будущем), то вы можете использовать существующие ныне решения для написания своих контрактов и сервисов с применением технологий zkSNARK. Более того, благодаря мутациям на KLYNTAR вы сможете вызывать zk контракты на EVM из WASM и наоборот, использовать оффчейн возможности и многое другое! Ознакомьтесь с библиотеками и репозиториями ниже которые вам понадобятся при работе. Все они имеют хорошую документацию, рейтинг на GitHub, коммьюнити разработчиков и используются в других проектах. Рекомендуем следовать руководствам и рекомендациям.

### <mark style="color:red;">**Circom**</mark>

<figure><img src="../../.gitbook/assets/image (131).png" alt=""><figcaption><p><a href="https://github.com/iden3/circom">https://github.com/iden3/circom</a></p></figcaption></figure>

Circom - это специальный язык который может использоваться для написания логики которая затем будет использована для построение R1CS, ключей верификации и прочего. Новая версия компилятора написана на Rust. В документации имеется достаточное количество примеров и пошаговых объяснений что необходимо делать для создания логики с нулевым разглашением.&#x20;

### <mark style="color:red;">**SnarkJS**</mark>

В паре с circom идёт snarkjs. С его помощью можно проводить церемонию доверенной настройки, генерировать Solidity-контракт верификатора и многое другое.

<figure><img src="../../.gitbook/assets/image (1).png" alt=""><figcaption></figcaption></figure>

Больше информации можно узнать на официальных сайтах. Ниже вы увидите ссылки на репозитории которые помогут вам при создании своего zero-knowledge проекта

<figure><img src="../../.gitbook/assets/image (130).png" alt=""><figcaption></figcaption></figure>

* [https://github.com/iden3/circom](https://github.com/iden3/circom)
* [https://docs.circom.io/](https://docs.circom.io/)
* [https://github.com/iden3/snarkjs](https://github.com/iden3/snarkjs)

### <mark style="color:red;">zkSTARK</mark>

Coming soon
