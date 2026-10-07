---
product: adobe campaign
title: in
description: in 関数について説明します
feature: Journeys
role: Developer
level: Experienced
exl-id: 6a19ae25-99c9-47f9-8417-c3d247dbbe3f
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
source-wordcount: '113'
ht-degree: 100%
---
# in {#in}

最初の引数値がリストに含まれているかどうかを確認します。 確認は、各引数値に対して Equal を使用して実行されます。 引数の値が見つかった場合は true を返し、それ以外の場合は false を返します。

`<expression>` のタイプは、リストの項目と一致する必要があります。 なお、リストの項目のタイプは互いに一致する必要があります。

## カテゴリ

リスト

## 関数の構文

`in(<parameters>)`

## パラメーター

| パラメーター | タイプ |
|-----------|------------------|
| 文字列 | 文字列 |
| ブール | ブール |
| 整数 | 整数 |
| 小数 | 小数 |
| 期間 | 期間 |
| 日時 | 日時 |
| 日時のみ | 日時のみ |
| リスト | listString |
| リスト | listBoolean |
| リスト | listInteger |
| リスト | listDecimal |
| リスト | listDuration |
| リスト | listDateTime |
| リスト | listDateTimeOnly |
| リスト | listDateOnly |

## シグネチャと戻り値のタイプ

`in(<integer>,<listInteger>)`

`in(<decimal>,<listDecimal>)`

`in(<string>,<listString>)`

`in(<boolean>,<listBoolean>)`

`in(<dateTimeOnly>,<listDateTimeOnly>)`

`in(<dateTime>,<listDateTime>)`

`in(<dateOnly>,<listDateOnly>)`

`in(<duration>,<listDuration>)`

ブール値を返します。

## 例

`in(4,[4,5,3,4])`

true を返します。

`in(8,[4,5,3,4])`

false を返します。

`in(#{ExperiencePlatform.ProfileFieldGroup.profile.person.gender}, ["male"])`
