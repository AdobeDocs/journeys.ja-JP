---
title: toInteger
description: toInteger関数について説明します
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
source-git-commit: 939cde1f30a946ba4c20984dd72dcd1526d6e608
workflow-type: tm+mt
source-wordcount: '70'
ht-degree: 12%

---


# toInteger {#toInteger}

引数の値を整数に変換します。

## カテゴリ

コンバージョン変換

## 関数の構文

`toInteger(<parameter>)`

## パラメーター

| パラメーター | 説明 |
|--- |--- |
| 文字列 | 文字列値を整数に変換します。 |
| dateTime | 日付をミリ秒（エポックミリ秒）の数値として変換します。 |
| decimal | 小数部を削除して、整数に変換します(例： 1.5が1になる) |
| boolean | trueの場合はブール値を1に変換し、falseの場合は0に変換します。 |

## 署名と戻り値の型

`toInteger(<dateTime>)`

`toInteger(<decimal>)`

`toInteger(<integer>)`

`toInteger(<string>)`

`toInteger(<boolean>)`

整数を返します。

## 例

`toInteger(4)`

4を返します。
