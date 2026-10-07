---
product: adobe campaign
title: isNotEmpty
description: isNotEmpty 関数について説明します
feature: Journeys
role: Developer
level: Experienced
exl-id: 32bb3d72-7abe-4220-acae-f19a09f83657
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
source-wordcount: '36'
ht-degree: 100%
---
# isNotEmpty {#isNotEmpty}

パラメーター内の文字列が空でない場合、true を返します。

## カテゴリ

文字列

## 関数の構文

`isNotEmpty(<parameters>)`

## パラメーター

* 文字列

## シグネチャと戻り値のタイプ

`isNotEmpty(<string>)`

ブール値を返します。

## 例

`isNotEmpty("")`

false を返します。

`isNotEmpty("hello")`

true を返します。
