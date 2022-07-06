---
description: Пожалуй, самое простое
cover: ../../.gitbook/assets/3092916.jpg
coverY: 0
---

# 🔐 Схемы генерации ключей

### <mark style="color:red;">Ed25519</mark>

Для любых типов взаимодействия с KLYNTAR необходимо иметь пару ключей. Приватным ключом вы подписываете данные, а публичный используется для проверки подписи. В целом, принцип знакомый для всех.

В качестве самой дефолтной пары KLYNTAR использует Ed25519. Размеры ключей(как приватного так и публичного) - 32 байта. Публичный ключ в Base58 - это и есть ваш адрес на KLYNTAR.

Кстати, KLYNTAR адреса совместимы с Solana. Более того, транзакция коммита _<mark style="color:red;">**useful.txt**</mark>_ на мейнете Solana(с вызовом Memo программы) была произведена парой ключей KLYNTAR

![Вы можете просмотреть транзакцию на официальном обозревателе Solana](<../../.gitbook/assets/image (3).png>)

{% embed url="https://explorer.solana.com/tx/36cs4bjKZJNcTsMA8N6Bz8mm2yBUX5WvcT74oT3Pn2sD6cMGprRQvmYVdPGQJmrnHPDrypJYkT9Zg6UHw4vuPssT" %}

Поскольку разработка KLYNTAR&#x20;
