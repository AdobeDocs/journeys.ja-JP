---
product: adobe campaign
title: avg
description: avg 関数について説明します
feature: Journeys
role: Developer
level: Experienced
exl-id: 6c9f3a5d-20b4-4c0a-b17f-5221f5db51be
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
source-wordcount: '51'
ht-degree: 100%
---
# avg {#avg}

リストまたは 2 つの式のいずれかで指定された一連の式の平均値を返します。 null 値は無視されます。


## カテゴリ

集計

## 関数の構文

`avg(<parameter>)`

## パラメーター

サポートされているタイプ：

* listInteger
* listDecimal
* 小数
* 整数

## シグネチャと戻り値のタイプ

`avg(<listInteger>)`

`avg(<listDecimal>)`

`avg(<decimal>,<decimal>)`

`avg(<decimal>,<integer>)`

`avg(<integer>,<decimal>)`

`avg(<integer>,<integer>)`

小数を返します。

## 例

`avg(@{BarBeacon.inventory},5)`

`avg([10,3,8])`

7.0 を返します。

`avg(10.2, 3)`

6.6 を返します。
