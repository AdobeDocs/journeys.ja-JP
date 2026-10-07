---
product: adobe campaign
title: toBool
description: toBool 関数について説明します
feature: Journeys
role: Developer
level: Experienced
exl-id: 490144c2-1ecd-4772-ab15-e23b1b7d8f0c
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
# toBool {#toBool}

引数の値をタイプに応じてブール値に変換します。

* 文字列から変換する場合：文字列値をブール値として変換します。文字列値が「true」の場合は true、それ以外の場合は false を返します。
* 数値から変換する場合：数値が 0 に等しくない場合は true 、それ以外の場合は false を返します。

## カテゴリ

変換

## 関数の構文

`toBool(<parameter>)`

## パラメーター

* 小数
* ブール値
* 文字列
* 整数

## シグネチャと戻り値のタイプ

`toBool(<decimal>)`

`toBool(<boolean>)`

`toBool(<string>)`

`toBool(<integer>)`

ブール値を返します。

## 例

`toBool("true")`

`toBool(1)`

true を返します。

`toBool("this is not a boolean")`

false を返します。
