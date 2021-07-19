---
product: adobe campaign
title: min
description: min関数の詳細
feature: ジャーニー
role: Data Engineer
level: Experienced
exl-id: 7e13a08c-c51a-4d40-a3e2-ef70bd3edca5
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '89'
ht-degree: 10%

---

# min {#min}

リストまたは2つの式に指定された、式のセットの中の最小値を返します。 Null値は無視されます。

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
* 整数
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
