---
product: adobe campaign
title: setDays
description: setDays 関数について説明します
feature: Journeys
role: Developer
level: Experienced
exl-id: eee7bf61-9101-4959-aa93-27d0f221c517
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
source-wordcount: '75'
ht-degree: 100%
---
# setDays {#setDays}

日時または日時のみの日を設定します。 例えば、その月の特定の日まで待つ場合に、その日を強制的に指定できます。

## カテゴリ

日付

## 関数の構文

`setDays(<parameter>)`

## パラメーター

| パラメーター | タイプ |
|--- |--- |
| 日時 | 日時 |
| タイムゾーンを考慮しない日時 | dateTimeOnly |
| 日 | 整数 |

## シグネチャと戻り値のタイプ

`setDays(<dateTime>,<days>)`

日時を返します。

`setDays(<dateTimeOnly>,<days>)`

タイムゾーンを無視して日時を返します。

## 例

`setDays(toDateTime('2010-12-12T01:11:00Z'), 25)`

2010-12-25T01:11:00Z を返します。

`setDays(toDateTimeOnly(@{MyEvent.registrationDate}), 1)`
