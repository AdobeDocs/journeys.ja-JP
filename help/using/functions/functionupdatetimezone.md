---
product: adobe campaign
title: updateTimeZone
description: 関数 updateTimeZone の詳細
feature: Journeys
role: Data Engineer
level: Experienced
source-git-commit: a5d063784b278120b61f8d2641264baf40e34a90
workflow-type: tm+mt
source-wordcount: '53'
ht-degree: 7%

---

# updateTimeZone {#updateTimeZone}

新しい日時を返します。新しいタイムゾーンは同時に返されます。

## カテゴリ

日付

## 関数の構文

`updateTimeZone(<parameters>)`

## パラメーター

* タイムゾーン id:文字列
* dateTime

## 署名と戻り値の型

`updateTimeZone(<dateTime>,<timeZone id>)`

日時を返します。

## 例

`updateTimeZone( toDateTime("2019-08-28T08:15:30.123-07:00"), "Europe/Paris"))`

戻り値2019-08-28T17:15:30.123+02:00。

<!--`updateTimeZone( toDateTime("2019-08-28T08:15:30.123-07:00"), toTimeZone("Europe/Paris")))`
Returns "2019-08-28T17:15:30.123+02:00".-->

`updateTimeZone(@{MyExpEvent.timestamp}, "Australia/Sydney")`

timestamp フィールドの値が `2021-11-16T16:55:12.939318+01:00`を返した場合、関数は `2021-11-17T02:55:12.942115+11:00`.
