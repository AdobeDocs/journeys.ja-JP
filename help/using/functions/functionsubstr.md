---
product: adobe campaign
solution: Journey Orchestration
title: substr
description: 関数substrについて学習します
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '64'
ht-degree: 15%

---


# substr {#substr}

開始インデックスと終了インデックスの間の文字列式のサブ文字列を返します。 終了インデックスが定義されていない場合、開始インデックスと終了インデックスの間にあります。

## カテゴリ

 バイト長文字列

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