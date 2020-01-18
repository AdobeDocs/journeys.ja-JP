---
title: max
description: 関数maxについて
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

# max{#max}

リストまたは2つの式に渡された、式のセットの中の最大値を返します。 Null値は無視されます。

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

## 署名と返される型

`max(<listDuration>)`

期間を返します。

`max(<listInteger>)`

期間を返します。

`max(<listDateTimeOnly>)`

タイムゾーンを考慮せずにdatetimeを返します。

`max(<listDateTime>)`

日時を返します。

`max(<listDecimal>)`

小数を返します。

`max(<decimal>,<decimal>)`

小数を返します。

`max(<duration>,<duration>)`

期間を返します。

`max(<dateTime>,<dateTime>)`

日時を返します。

`max(<dateTimeOnly>,<dateTimeOnly>)`

タイムゾーンを考慮せずにdatetimeを返します。

`max(<integer>,<integer>)`

整数を返します。

## 例

`max(@{BarBeacon.inventory},5)`

`max([10,3,8])`

10を返します。

`max([10,null,8])`

10を返します。
