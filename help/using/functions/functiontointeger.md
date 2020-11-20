---
product: adobe campaign
solution: Journey Orchestration
title: toInteger
description: toInteger関数について説明します
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
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
| decimal | 小数部を削除して、整数に変換します(例：1.5が1になる) |
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
