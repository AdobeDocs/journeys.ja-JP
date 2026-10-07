---
product: adobe campaign
title: toInteger
description: toInteger 関数について説明します
feature: Journeys
role: Developer
level: Experienced
exl-id: 3fcbf4dd-3ca5-4f4b-b774-af6ac3170768
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
# toInteger {#toInteger}

引数の値を整数に変換します。

## カテゴリ

変換

## 関数の構文

`toInteger(<parameter>)`

## パラメーター

| パラメーター | 説明 |
|--- |--- |
| 文字列 | 文字列値を整数に変換します |
| 日時 | 日付をミリ秒数（エポックミリ秒）に変換します |
| 小数 | 小数部を削除して整数に変換します（例：1.5 は 1 になります） |
| ブール値 | ブール値を true の場合は 1 に、false の場合は 0 に変換します |

## シグネチャと戻り値のタイプ

`toInteger(<dateTime>)`

`toInteger(<decimal>)`

`toInteger(<integer>)`

`toInteger(<string>)`

`toInteger(<boolean>)`

整数を返します。

## 例

`toInteger("4")`

4 を返します。
