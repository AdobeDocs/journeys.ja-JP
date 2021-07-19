---
product: adobe campaign
title: setDays
description: setDays関数の詳細
feature: ジャーニー
role: Data Engineer
level: Experienced
exl-id: eee7bf61-9101-4959-aa93-27d0f221c517
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '75'
ht-degree: 14%

---

# setDays {#setDays}

日付の時刻または日付の時刻のみを設定します。 例えば、特定の日まで待つ場合は、強制的に日を指定できます。

## カテゴリ

日付

## 関数の構文

`setDays(<parameter>)`

## パラメーター

| パラメーター | タイプ |
|--- |--- |
| 日時 | dateTime |
| タイムゾーンを考慮しない日時 | dateTimeOnly |
| 日未満 | 整数 |

## 署名と戻り値の型

`setDays(<dateTime>,<days>)`

datetimeを返します。

`setDays(<dateTimeOnly>,<days>)`

タイムゾーンを考慮せずに、datetimeを返します。

## 例

`setDays(toDateTime('2010-12-12T01:11:00Z'), 25)`

2010-12-25T01:11:00Zを返します。

`setDays(toDateTimeOnly(@{MyEvent.registrationDate}), 1)`
