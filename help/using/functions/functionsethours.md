---
product: adobe campaign
solution: Journey Orchestration
title: setHours
description: setHours関数について学びます
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '76'
ht-degree: 11%

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
