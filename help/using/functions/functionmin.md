---
product: adobe campaign
title: min
description: min 関数について説明します
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 7e13a08c-c51a-4d40-a3e2-ef70bd3edca5
source-git-commit: 9c33474a72542b6ad1d1ae0854622dfd7575f2d9
workflow-type: tm+mt
source-wordcount: '92'
ht-degree: 100%

---

# min {#min}

リストまたは 2 つの式のいずれかで指定された一連の式の中の最小値を返します。null 値は無視されます。

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
* listDateOnly
* 期間
* 整数
* 小数
* 日時
* 日時のみ

## シグネチャと戻り値のタイプ

`min(<listDuration>)`

期間を返します。

`min(<listInteger>)`

期間を返します。

`min(<listDateTimeOnly>)`

タイムゾーンを無視して日時を返します。

`min(<listDateTime>)`

日時を返します。

`min(<listDateOnly>)`

日付を返します。

`min(<listDecimal>)`

小数を返します。

`min(<decimal>,<decimal>)`

小数を返します。

`min(<duration>,<duration>)`

期間を返します。

`min(<dateTime>,<dateTime>)`

日時を返します。

`min(<dateTimeOnly>,<dateTimeOnly>)`

タイムゾーンを無視して日時を返します。

`min(<integer>,<integer>)`

整数を返します。

## 例

`min(@{BarBeacon.inventory},5)`

`min([10,3,8])`

3 を返します。

`min([10,null,8])`

「8」を返します。
