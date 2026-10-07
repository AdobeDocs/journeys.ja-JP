---
product: adobe campaign
title: setHours
description: setHours 関数について説明します
feature: Journeys
role: Developer
level: Experienced
exl-id: d4fe578f-c3be-4c8b-98b3-090dab0c41d1
product_v2:
  - id: cf67d108-ecf9-4fde-af49-3a3c39083bc8
    internal-label: Journey Orchestration
feature_v2:
  - id: 7de3230f-9523-5ba5-8d5c-2313288b27ef
    internal-label: Journeys
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: 255cd6677e7c9ebff63ea9a1028a042c19e63ecc
workflow-type: tm+mt
source-wordcount: '106'
ht-degree: 100%
---
# setHours {#setHours}

日時または日時のみの時を設定します。 例えば、明日の特定の正時まで待つ場合に、その正時を強制的に指定できます。

## カテゴリ

日付

## 関数の構文

`setHours(<parameter>)`

## パラメーター

| パラメーター | タイプ |
|--- |--- |
| 日時 | 日時 |
| タイムゾーンを考慮しない日時 | dateTimeOnly |
| 時 | 整数 |

## シグネチャと戻り値のタイプ

`setHours(<dateTime>,<hours>)`

日時を返します。

`setHours(<dateTimeOnly>,<hours>)`

タイムゾーンを無視して日時を返します。

## 例

`setHours(toDateTime('2010-12-12T01:11:00Z'), 4)`

2010-12-12T04:11:00Z を返します。

`setHours(nowWithDelta(1, "days"), 20)`

明日の午後 8:XY を返します（XY は現在時刻の分）。 評価が午前 2:45 に行われた場合、返される時刻は午後 8:45 になります。
