---
product: adobe campaign
title: setHours
description: setHours関数の詳細
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: d4fe578f-c3be-4c8b-98b3-090dab0c41d1
source-git-commit: 51536b20e81cde1a7fdd7f4654d70bfe6176b0d4
workflow-type: tm+mt
source-wordcount: '101'
ht-degree: 9%

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
| 時間 | 整数 |

## 署名と戻り値の型

`setHours(<dateTime>,<hours>)`

datetimeを返します。

`setHours(<dateTimeOnly>,<hours>)`

タイムゾーンを考慮せずに、datetimeを返します。

## 例

`setHours(toDateTime('2010-12-12T01:11:00Z'), 4))`

2010-12-12T04:11:00Zを返します。

`setHours(nowWithDelta(1, "days"), 20)`

明日の午後8:XY PMに戻り、XYは現在の時間評価の時点の分です。 評価が午前2時45分におこなわれた場合、返される時間は午後8時45分になります。
