---
product: adobe campaign
title: now
description: now 関数について説明します
feature: Journeys
role: Developer
level: Experienced
exl-id: ab1f9efe-cbb7-4e3a-ace0-24f2fb6165cb
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
source-wordcount: '58'
ht-degree: 70%
---
# now {#now}

現在の日付を日時形式で返します。 データタイプについて詳しくは、[このページ](../expression/data-types.md)を参照してください。

## カテゴリ

日付

## 関数の構文

`now(<parameter>)`

## パラメーター

| パラメーター | 説明 |
|--- |--- |
| 文字列 |  |

## シグネチャと戻り値のタイプ

`now()`

`now("<timeZone id>")`

日時を返します。

## 例

`now()`

2019-06-03T06:30Zを返します。

`toString(now())`

「2019-06-03T06:30Z」を返します

`now("Europe/Paris")`

2019-06-03T08:30+02:00を返します。
