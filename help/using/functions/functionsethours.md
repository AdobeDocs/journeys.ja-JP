---
product: adobe campaign
title: setHours
description: setHours 関数の詳細
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: d4fe578f-c3be-4c8b-98b3-090dab0c41d1
source-git-commit: 5225045f02fb1b2a8505756d9d7f6f60a32b3ed6
workflow-type: tm+mt
source-wordcount: '101'
ht-degree: 9%

---

# setHours {#setHours}

日付の時間または日時のみを設定します。 例えば、あす特定の時間まで待つ場合は、時間を強制できます。

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

日時を返します。

`setHours(<dateTimeOnly>,<hours>)`

タイムゾーンを考慮せずに、日時を返します。

## 例

`setHours(toDateTime('2010-12-12T01:11:00Z'), 4)`

戻り値2010-12-12T04:11:00Z

`setHours(nowWithDelta(1, "days"), 20)`

明日の午後 8:XY PM に戻り、XY は現在の時間評価の時点の分です。 評価が午前 2 時 45 分におこなわれた場合、返される時刻は午後 8 時 45 分になります。
