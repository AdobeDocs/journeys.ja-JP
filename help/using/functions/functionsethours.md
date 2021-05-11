---
product: adobe campaign
solution: Journey Orchestration
title: setHours
description: setHours関数について学びます
feature: ジャーニー
role: Data Engineer
level: Experienced
exl-id: d4fe578f-c3be-4c8b-98b3-090dab0c41d1
translation-type: tm+mt
source-git-commit: 8ab3951f9c97a0a964f5c123978ed256d3aedc45
workflow-type: tm+mt
source-wordcount: '77'
ht-degree: 12%

---

# setHours {#setHours}

日付の時刻または日付の時刻のみを設定します。 例えば、あす1時間まで待つ場合は、強制的に1時間に設定できます。

## カテゴリ

日付

## 関数の構文

`setHours(<parameter>)`

## パラメーター

| パラメーター | タイプ |
|--- |--- |
| 日時 | dateTime |
| タイムゾーンを考慮しない日付時刻 | dateTimeOnly |
| 時間 | integer |

## 署名と戻り値の型

`setHours(<dateTime>,<hours>)`

datetimeを返します。

`setHours(<dateTimeOnly>,<hours>)`

タイムゾーンを考慮せずに、datetimeを返します。

## 例

`setHours(toDateTime('2010-12-12T01:11:00Z'), 4))`

2010-12-12T04:11:00Zを返します。

`setHours(nowWithDelta(1, "days"), 20)`

明日の午後8時に戻ります。
