---
title: updateTimeZone
description: 関数updateTimeZoneについて学習します
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: tm+mt
source-git-commit: b852c08a488a1bec02b8b31a1fccf1a8773b99af
workflow-type: tm+mt
source-wordcount: '41'
ht-degree: 9%

---


# updateTimeZone {#updateTimeZone}

新しいタイムゾーンを同じ瞬間に持つ新しい日時を返します。

## カテゴリ

日付

## 関数の構文

`updateTimeZone(<parameters>)`

## パラメーター

* タイムゾーンID:string
* dateTime

## 署名と戻り値の型

`updateTimeZone(<dateTime>,<timeZone id>)`

datetimeを返します。

## 例

`updateTimeZone( toDateTime("2019-08-28T08:15:30.123-07:00"), "Europe/Paris"))`

2019-08-28T17:15:30.123+02:00を返します。

<!--`updateTimeZone( toDateTime("2019-08-28T08:15:30.123-07:00"), toTimeZone("Europe/Paris")))`

Returns "2019-08-28T17:15:30.123+02:00".-->
