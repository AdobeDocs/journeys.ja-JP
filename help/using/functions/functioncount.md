---
product: adobe campaign
title: count
description: count 関数について説明します
feature: Journeys
role: Developer
level: Experienced
exl-id: 46528642-18d5-4ca9-a344-de2c7f939d00
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
source-wordcount: '53'
ht-degree: 100%
---
# count {#count}

null 値を数に入れずに、リストの要素数を数えます。

## カテゴリ

集計

## 関数の構文

`count(<listAny>)`

## パラメーター

| パラメーター | タイプ |
|-----------|------------------|
| リスト | listString |
| リスト | listBoolean |
| リスト | listInteger |
| リスト | listDecimal |
| リスト | listDuration |
| リスト | listDateTime |
| リスト | listDateTimeOnly |
| リスト | listDateOnly |

## シグネチャと戻り値のタイプ

`count(<listAny>)`

整数を返します。

## 例

`count([10,2,10,null])`

3 を返します。
