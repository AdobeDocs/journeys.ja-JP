---
title: toDecimal
description: toDecimal関数について説明します。
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

---


# toDecimal {#toDecimal}

引数の値を、型に応じて10進数値に変換します。

## カテゴリ

コンバージョン

## 関数の構文

`toDecimal(<parameter>)`

## パラメーター

| パラメーター | 説明 |
|--- |--- |
| 文字列 | 文字列値を10進数に変換します。 |
| dateTime | 日付をミリ秒（エポックミリ秒）の数で変換します。 |
| boolean | trueの場合はブール値を1に、falseの場合は0に変換します。 |
| 整数 | を10進数に変換します(例：:1は1.0になります。 |

## 署名と返される型

`toDecimal(<integer>)`

`toDecimal(<decimal>)`

`toDecimal(<string>)`

`toDecimal(<boolean>)`

小数を返します。

## 例

`toDecimal("4.0")`

4.0を返します。
