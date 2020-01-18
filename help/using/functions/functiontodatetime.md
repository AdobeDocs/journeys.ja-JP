---
title: toDateTime
description: toDateTime関数について
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 239efa9592b011c70e2fc331df8f33820301253d

---

# toDateTime {#toDateTime}

パラメーターを、タイプに応じて日付時刻値に変換します。

## カテゴリ

コンバージョン

## 関数の構文

`toDateTime(<parameters>)`

## パラメーター

| パラメーター | タイプ |
|-----------|------------------|
| ISO-8601形式の日付時刻 | 文字列 |
| タイムゾーンID | 文字列 |
| タイムゾーンのない日時 | dateTimeOnly |
| ミリ秒単位のエポックの整数値 | 整数 |

>[!NOTE]
>
>タイムゾーンIDは文字列定数である必要があります。 フィールド参照または式は使用できません。 データタイプの詳細については、を参照してくださ [](../expression/data-types.md)い。

## 署名と返される型

`toDateTime(<string>)`

`toDateTime(<dateTimeOnly>,<stringified time zone id>)`

`toDateTime(<integer>)`

dateTimeを返 **します**。

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

2016-08-18T23:17:59.123Zを返します。

`toDateTime(toDateTimeOnly("2016-08-18T23:17:59.123"),"UTC")`

2016-08-18T23:17:59.123Zを返します。

`toDateTime(1560762190189)`

戻り値2019-06-17T09:03:10.189Z

<!--`toDateTime ("2016-08-18T23:17:59.123", "UTC")`

Returns 2016-08-18T23:17:59.123Z.

`toDateTime("Z",2016,8,18,23,17,59)`

Returns 2016-08-18T23:17:59.000Z.

`toDateTime("Z",2016,8,18)`

Returns 2016-08-18T00:00:00.000Z.-->
