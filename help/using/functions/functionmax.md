---
product: adobe campaign
title: max
description: 関数maxの詳細
feature: ジャーニー
role: Data Engineer
level: Experienced
exl-id: 116713e0-7bbd-4150-8495-f87034eafb5f
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '89'
ht-degree: 8%

---

# max{#max}

一連の式の中で、リストまたは2つの式として指定された最大値を返します。 Null値は無視されます。

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
* 整数
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
