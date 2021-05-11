---
product: adobe campaign
solution: Journey Orchestration
title: setDays
description: setDays関数について学びます
feature: ジャーニー
role: Data Engineer
level: Experienced
exl-id: eee7bf61-9101-4959-aa93-27d0f221c517
translation-type: tm+mt
source-git-commit: 8ab3951f9c97a0a964f5c123978ed256d3aedc45
workflow-type: tm+mt
source-wordcount: '75'
ht-degree: 13%

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
