---
product: adobe campaign
title: toDecimal
description: toDecimal 関数について説明します
feature: Journeys
role: Developer
level: Experienced
exl-id: 11d7013c-2190-4654-8466-920861c836f5
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
source-wordcount: '76'
ht-degree: 89%
---
# toDecimal {#toDecimal}

引数の値をタイプに応じて小数値に変換します。

## カテゴリ

変換

## 関数の構文

`toDecimal(<parameter>)`

## パラメーター

| パラメーター | 説明 |
|--- |--- |
| 文字列 | 文字列値を小数に変換します |
| 日時 | 日付をミリ秒数（エポックミリ秒）に変換します |
| ブール値 | ブール値を true の場合は 1 に、false の場合は 0 に変換します |
| 整数 | 10進数に変換します（例：1は1.0になります）。 |

## シグネチャと戻り値のタイプ

`toDecimal(<integer>)`

`toDecimal(<decimal>)`

`toDecimal(<string>)`

`toDecimal(<boolean>)`

小数を返します。

## 例

`toDecimal("4.0")`

4.0 を返します。
