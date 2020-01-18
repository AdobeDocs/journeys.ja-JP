---
title: 分
description: 関数minについて説明します。
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


# 分 {#min}

リストまたは2つの式に渡された、式のセットの中の最小値を返します。 Null値は無視されます。

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

## 署名と返される型

`min(<listDuration>)`

期間を返します。

`min(<listInteger>)`

期間を返します。

`min(<listDateTimeOnly>)`

タイムゾーンを考慮せずにdatetimeを返します。

`min(<listDateTime>)`

日時を返します。

`min(<listDecimal>)`

小数を返します。

`min(<decimal>,<decimal>)`

小数を返します。

`min(<duration>,<duration>)`

期間を返します。

`min(<dateTime>,<dateTime>)`

日時を返します。

`min(<dateTimeOnly>,<dateTimeOnly>)`

タイムゾーンを考慮せずにdatetimeを返します。

`min(<integer>,<integer>)`

整数を返します。

## 例

`min(@{BarBeacon.inventory},5)`

`min([10,3,8])`

3を返します。

`min([10,null,8])`

8を返します。
