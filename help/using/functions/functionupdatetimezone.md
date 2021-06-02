---
product: adobe campaign
title: updateTimeZone
description: 関数updateTimeZoneの詳細
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '41'
ht-degree: 9%

---


# updateTimeZone {#updateTimeZone}

新しいタイムゾーンを同時に持つ新しい日付時刻を返します。

## カテゴリ

日付

## 関数の構文

`updateTimeZone(<parameters>)`

## パラメーター

* タイムゾーンID:文字列
* dateTime

## 署名と戻り値の型

`updateTimeZone(<dateTime>,<timeZone id>)`

datetimeを返します。

## 例

`updateTimeZone( toDateTime("2019-08-28T08:15:30.123-07:00"), "Europe/Paris"))`

2019-08-28T17:15:30.123+02:00を返します。

<!--`updateTimeZone( toDateTime("2019-08-28T08:15:30.123-07:00"), toTimeZone("Europe/Paris")))`

Returns "2019-08-28T17:15:30.123+02:00".-->
