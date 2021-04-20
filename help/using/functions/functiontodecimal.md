---
product: adobe campaign
solution: Journey Orchestration
title: toDecimal
description: toDecimal関数について
feature: Journeys
role: Data Engineer
level: Experienced
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '75'
ht-degree: 13%

---


# toDecimal {#toDecimal}

引数の値を、型に応じて10進数値に変換します。

## カテゴリ

コンバージョン変換

## 関数の構文

`toDecimal(<parameter>)`

## パラメーター

| パラメーター | 説明 |
|--- |--- |
| 文字列 | 文字列値を小数値に変換します。 |
| dateTime | 日付をミリ秒（エポックミリ秒）の数値として変換します。 |
| boolean | trueの場合はブール値を1に変換し、falseの場合は0に変換します。 |
| integer | を小数に変換します（例）。:1は1.0になります)。 |

## 署名と戻り値の型

`toDecimal(<integer>)`

`toDecimal(<decimal>)`

`toDecimal(<string>)`

`toDecimal(<boolean>)`

小数を返します。

## 例

`toDecimal("4.0")`

4.0を返します。
