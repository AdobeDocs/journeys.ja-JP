---
product: adobe campaign
title: toString
description: toString 関数について説明します
feature: Journeys
role: Developer
level: Experienced
exl-id: 942e7a44-1cb1-4c99-abd6-e0b045c42c80
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
source-wordcount: '107'
ht-degree: 100%
---
# toString {#toString}

引数の値を、タイプに応じて文字列値に変換します。 データタイプについて詳しくは、[このページ](../expression/data-types.md)を参照してください。

## カテゴリ

変換

## 関数の構文

`toString(<parameter>)`

## パラメーター

| パラメーター | 説明 |
|--- |--- |
| 日時 | 日付を UTC 日付フォーマットに変換します |
| 日時のみ | 日付を UTC 日付フォーマットに変換します |
| 期間 | 対応するミリ秒数の文字列に変換します |
| 整数 | 値の文字列表現に変換します（1 は「1」になります） |
| 小数 | 値の文字列表現に変換します（1.5 は「1.5」になります） |
| ブール値 | ブール値を true の場合は「true」、false の場合は「false」に変換します |

## シグネチャと戻り値のタイプ

`toString(<dateTimeOnly>)`

`toString(<dateTime>)`

`toString(<duration>)`

`toString(<boolean>)`

`toString(<integer>)`

`toString(<decimal>)`

文字列を返します。

## 例

`toString(4)`

「4」を返します。
