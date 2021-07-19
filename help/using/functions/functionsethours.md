---
product: adobe campaign
title: setHours
description: setHours関数の詳細
feature: ジャーニー
role: Data Engineer
level: Experienced
exl-id: d4fe578f-c3be-4c8b-98b3-090dab0c41d1
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '77'
ht-degree: 14%

---

# setHours {#setHours}

日付の時刻または日付の時刻のみを設定します。 例えば、あす1時間まで待つ場合は、強制的に時間を指定できます。

## カテゴリ

日付

## 関数の構文

`setHours(<parameter>)`

## パラメーター

| パラメーター | タイプ |
|--- |--- |
| 日時 | dateTime |
| タイムゾーンを考慮しない日時 | dateTimeOnly |
| 時間未満 | 整数 |

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
