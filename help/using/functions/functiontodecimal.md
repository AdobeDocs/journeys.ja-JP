---
product: adobe campaign
title: toDecimal
description: toDecimal関数の詳細
feature: ジャーニー
role: Data Engineer
level: Experienced
exl-id: 11d7013c-2190-4654-8466-920861c836f5
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '72'
ht-degree: 13%

---

# toDecimal {#toDecimal}

引数の値を、型に応じて10進数に変換します。

## カテゴリ

コンバージョン変換

## 関数の構文

`toDecimal(<parameter>)`

## パラメーター

| パラメーター | 説明 |
|--- |--- |
| 文字列 | 文字列値を小数に変換します |
| dateTime | 日付をミリ秒数（エポックミリ秒）に変換します |
| boolean | trueの場合はブール値を1に、falseの場合は0に変換します |
| 整数 | を10進数に変換します(例：:1は1.0になります。 |

## 署名と戻り値の型

`toDecimal(<integer>)`

`toDecimal(<decimal>)`

`toDecimal(<string>)`

`toDecimal(<boolean>)`

小数を返します。

## 例

`toDecimal("4.0")`

4.0を返します。
