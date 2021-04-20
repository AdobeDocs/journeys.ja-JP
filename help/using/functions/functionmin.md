---
product: adobe campaign
solution: Journey Orchestration
title: min
description: min関数について説明します。
feature: Journeys
role: Data Engineer
level: Experienced
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '92'
ht-degree: 8%

---


# min {#min}

リストまたは2つの式として渡された、式のセットの中の最小値を返します。 null値は無視されます。

## カテゴリ

集計

## 関数の構文

`min(<parameters>)`

## パラメーター

* listDuration
* listInteger
* listDecimal
* listDateTime
* listDateTimeOnly
* duration
* integer
* decimal
* dateTime
* dateTimeOnly

## 署名と戻り値の型

`min(<listDuration>)`

期間を返します。

`min(<listInteger>)`

期間を返します。

`min(<listDateTimeOnly>)`

タイムゾーンを考慮せずに、datetimeを返します。

`min(<listDateTime>)`

datetimeを返します。

`min(<listDecimal>)`

小数を返します。

`min(<decimal>,<decimal>)`

小数を返します。

`min(<duration>,<duration>)`

期間を返します。

`min(<dateTime>,<dateTime>)`

datetimeを返します。

`min(<dateTimeOnly>,<dateTimeOnly>)`

タイムゾーンを考慮せずに、datetimeを返します。

`min(<integer>,<integer>)`

整数を返します。

## 例

`min(@{BarBeacon.inventory},5)`

`min([10,3,8])`

3を返します。

`min([10,null,8])`

8を返します。
