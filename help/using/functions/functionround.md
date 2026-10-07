---
product: adobe campaign
title: round
description: round 関数について説明します
feature: Journeys
role: Developer
level: Experienced
exl-id: 16fe7c3a-8300-49d6-a3d6-a037fa1461f3
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
source-wordcount: '44'
ht-degree: 100%
---
# round {#round}

引数に最も近い整数値を返します。差が同じ場合は正の無限大側に丸められます。

## カテゴリ

数値計算

## 関数の構文

`round(<parameters>)`

## パラメーター

* 小数
* 整数

## シグネチャと戻り値のタイプ

`round(<decimal>)`

`round(<integer>)`

整数を返します。

## 例

`round(3.14)`

3 を返します。

`round(3.54)`

4 を返します。

`round(-3.14)`

-3 を返します。

`round(3)`

3 を返します。
