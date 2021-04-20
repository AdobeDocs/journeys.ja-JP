---
product: adobe campaign
solution: Journey Orchestration
title: setDays
description: setDays関数について学びます
feature: Journeys
role: Data Engineer
level: Experienced
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '78'
ht-degree: 12%

---


# setDays {#setDays}

日付の時刻または日付の時刻のみを設定します。 例えば、月の特定の日まで待つ場合は、日を強制的に指定できます。

## カテゴリ

日付

## 関数の構文

`setDays(<parameter>)`

## パラメーター

| パラメーター | タイプ |
|--- |--- |
| 日時 | dateTime |
| タイムゾーンを考慮しない日付時刻 | dateTimeOnly |
| 日 | integer |

## 署名と戻り値の型

`setDays(<dateTime>,<days>)`

datetimeを返します。

`setDays(<dateTimeOnly>,<days>)`

タイムゾーンを考慮せずに、datetimeを返します。

## 例

`setDays(toDateTime('2010-12-12T01:11:00Z'), 25)`

2010-12-25T01:11:00Zを返します。

`setDays(toDateTimeOnly(@{MyEvent.registrationDate}), 1)`
