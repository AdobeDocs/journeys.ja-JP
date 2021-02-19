---
product: adobe campaign
solution: Journey Orchestration
title: max
description: 関数maxについて説明します。
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '88'
ht-degree: 7%

---

# max{#max}

リストまたは2つの式として渡された、式のセットの中の最大値を返します。 null値は無視されます。

## カテゴリ

集計

## 関数の構文

`max(<parameter>)`

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

`max(<listDuration>)`

期間を返します。

`max(<listInteger>)`

期間を返します。

`max(<listDateTimeOnly>)`

タイムゾーンを考慮せずに、datetimeを返します。

`max(<listDateTime>)`

datetimeを返します。

`max(<listDecimal>)`

小数を返します。

`max(<decimal>,<decimal>)`

小数を返します。

`max(<duration>,<duration>)`

期間を返します。

`max(<dateTime>,<dateTime>)`

datetimeを返します。

`max(<dateTimeOnly>,<dateTimeOnly>)`

タイムゾーンを考慮せずに、datetimeを返します。

`max(<integer>,<integer>)`

整数を返します。

## 例

`max(@{BarBeacon.inventory},5)`

`max([10,3,8])`

10を返します。

`max([10,null,8])`

10を返します。
