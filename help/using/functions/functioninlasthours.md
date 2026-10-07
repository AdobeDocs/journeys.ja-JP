---
product: adobe campaign
title: inLastHours
description: inLastHours 関数について説明します
feature: Journeys
role: Developer
level: Experienced
exl-id: 9baeb836-e029-4e19-b08e-7b7b5f27ff8f
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
source-wordcount: '45'
ht-degree: 100%
---
# inLastHours {#inLastHours}

指定された日時が現在の日時とその delta 時間前の間にある場合、true を返します。

## カテゴリ

日付

## 関数の構文

`inLastHours(<dateTime>,<delta>)`

## パラメーター

| パラメーター | タイプ |
|-----------|------------------|
| 日時 | 日時 |
| delta | 整数 |

## シグネチャと戻り値のタイプ

`inLastHours(<dateTime>,<integer>)`

ブール値を返します。

## 例

`inLastHours(toDateTime('2019-12-12T01:11:00Z'), 4)`

true を返します。

`inLastHours(@{MyEvent.timestamp}, 4)`

true を返します。
