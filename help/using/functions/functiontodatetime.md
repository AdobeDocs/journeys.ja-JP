---
product: adobe campaign
title: toDateTime
description: toDateTime 関数の詳細
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 0b8d1a82-a55a-4a4d-ad1b-35499d52b469
source-git-commit: 2aa73498f44f22a70bb2268afca7d1a62e434542
workflow-type: tm+mt
source-wordcount: '93'
ht-degree: 11%

---

# toDateTime {#toDateTime}

パラメーターを、タイプに応じて日時値に変換します。

## カテゴリ

コンバージョン

## 関数の構文

`toDateTime(<parameters>)`

## パラメーター

| パラメーター | タイプ |
|-----------|------------------|
| ISO-8601 形式の日時 | 文字列 |
| タイムゾーン id | 文字列 |
| タイムゾーンのない日時 | dateTimeOnly |
| ミリ秒単位のエポックの整数値 | 整数 |

>[!NOTE]
>
>タイムゾーン ID は、文字列定数である必要があります。 フィールド参照や式は使用できません。 データタイプについて詳しくは、 [このページ](../expression/data-types.md).

## 署名と戻り値の型

`toDateTime(<string>)`

`toDateTime(<stringified time zone id>, <dateTimeOnly>)`

`toDateTime(<integer>)`

を返す **dateTime**.

<!--`toDateTime(<year>,<month>,<dayOfMonth>,<hour>,<minute>,<second>)`

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

戻り値2016-08-18T23:17:59.123Z

`toDateTime(toDateTimeOnly("UTC", "2016-08-18T23:17:59.123"))`

戻り値2016-08-18T23:17:59.123Z

`toDateTime(1560762190189)`

戻り値2019-06-17T09:03:10.189Z

<!--`toDateTime ("2016-08-18T23:17:59.123", "UTC")`

Returns 2016-08-18T23:17:59.123Z.

`toDateTime("Z",2016,8,18,23,17,59)`

Returns 2016-08-18T23:17:59.000Z.

`toDateTime("Z",2016,8,18)`

Returns 2016-08-18T00:00:00.000Z.-->
