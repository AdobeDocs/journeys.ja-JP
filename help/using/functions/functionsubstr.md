---
title: substr
description: 関数substrについて学習します
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: d6360d616199d597255610959432c7b93fd4e25c
workflow-type: tm+mt
source-wordcount: '64'
ht-degree: 15%

---


# substr {#substr}

開始インデックスと終了インデックスの間の文字列式のサブ文字列を返します。 終了インデックスが定義されていない場合、開始インデックスと終了インデックスの間にあります。

## カテゴリ

文字列

## 関数の構文

`substr(<parameters>)`

## パラメーター

| パラメーター | type |
|-------------|----------|
| 文字列 | 文字列 |
| beginIndex | integer |
| endIndex | integer |

## 署名と戻り値の型

`substr(<string>,<beginIndex>)`

`substr(<string>,<beginIndex>,<endIndex>)`

文字列を返します。

## 例

`substr("Hello World",6)`

&quot;World&quot;を返します。

`substr("Hello World", 0, 5)`

「Hello」を返します。