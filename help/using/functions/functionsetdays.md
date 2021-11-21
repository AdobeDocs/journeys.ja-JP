---
product: adobe campaign
title: setDays
description: setDays 関数の詳細
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: eee7bf61-9101-4959-aa93-27d0f221c517
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '74'
ht-degree: 13%

---

# setDays {#setDays}

日付の日付と時刻のみを設定します。 例えば、特定の日まで待つ場合は、日を強制的に指定できます。

## カテゴリ

日付

## 関数の構文

`setDays(<parameter>)`

## パラメーター

| パラメーター | タイプ |
|--- |--- |
| 日時 | dateTime |
| タイムゾーンを考慮しない日時 | dateTimeOnly |
| 日 | 整数 |

## 署名と戻り値の型

`setDays(<dateTime>,<days>)`

日時を返します。

`setDays(<dateTimeOnly>,<days>)`

タイムゾーンを考慮せずに、日時を返します。

## 例

`setDays(toDateTime('2010-12-12T01:11:00Z'), 25)`

戻り値2010-12-25T01:11:00Z

`setDays(toDateTimeOnly(@{MyEvent.registrationDate}), 1)`
