---
product: adobe campaign
title: toDateTime
description: toDateTime 関数について説明します
feature: Journeys
role: Developer
level: Experienced
exl-id: 0b8d1a82-a55a-4a4d-ad1b-35499d52b469
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
source-wordcount: '97'
ht-degree: 100%
---
# toDateTime {#toDateTime}

パラメーターをタイプに応じて日時値に変換します。

## カテゴリ

変換

## 関数の構文

`toDateTime(<parameters>)`

## パラメーター

| パラメーター | タイプ |
|-----------|------------------|
| ISO-8601 形式の日時 | 文字列 |
| タイムゾーン ID | 文字列 |
| タイムゾーンを含まない日時 | dateTimeOnly |
| エポックのミリ秒単位の整数値 | 整数 |

>[!NOTE]
>
>タイムゾーン ID は文字列定数である必要があります。 フィールド参照や式は使用できません。 データタイプについて詳しくは、[このページ](../expression/data-types.md)を参照してください。

## シグネチャと戻り値のタイプ

`toDateTime(<string>)`

`toDateTime(<stringified time zone id>, <dateTimeOnly>)`

`toDateTime(<integer>)`

**dateTime** を返します。

<!--
`toDateTime(<year>,<month>,<dayOfMonth>,<hour>,<minute>,<second>)`

Returns a date time with default time zone UTC.

`toDateTime(<year>,<month>,<dayOfMonth>)`
`toDateTime(<stringified timeZone>,<year>,<month>,<dayOfMonth>)`
`toDateTime(<timeZone>,<year>,<month>,<dayOfMonth>)`

Return a datetime where hour, minute and second set to 0.

`toDateTime(<stringified timeZone>,<year>,<month>,<dayOfMonth>,<hour>,<minute>,<second>)`
`toDateTime(<string>)`
`toDateTime(<string>,<integer>)`
`toDateTime(<stringified timeZone>,<dateTimeOnly)`

`toDateTime(<timeZone>,<integer>)`

Return a datetime.

-->

## 例

`toDateTime ("2016-08-18T23:17:59.123Z")`

2016-08-18T23:17:59.123Z を返します。

`toDateTime(toDateTimeOnly("UTC", "2016-08-18T23:17:59.123"))`

2016-08-18T23:17:59.123Z を返します。

`toDateTime(1560762190189)`

2019-06-17T09:03:10.189Z を返します。

<!--
`toDateTime ("2016-08-18T23:17:59.123", "UTC")`

Returns 2016-08-18T23:17:59.123Z.

`toDateTime("Z",2016,8,18,23,17,59)`

Returns 2016-08-18T23:17:59.000Z.

`toDateTime("Z",2016,8,18)`

Returns 2016-08-18T00:00:00.000Z.
-->
