---
title: setDays
description: setDays関数について学びます
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
source-wordcount: '74'
ht-degree: 12%

---


# setDays {#setDays}

日付の時刻または日付の時刻のみを設定します。 例えば、月の特定の日まで待つ場合は、日を強制的に指定できます。

## カテゴリ

日付

## 関数の構文

`setDays(<parameter>)`

## パラメーター

| パラメーター | タイプ |
|--- |--- |
| 日時 | dateTime |
| タイムゾーンを考慮しない日付時刻 | dateTimeOnly |
| 日 | integer |

## 署名と戻り値の型

`setDays(<dateTime>,<days>)`

datetimeを返します。

`setDays(<dateTimeOnly>,<days>)`

タイムゾーンを考慮せずに、datetimeを返します。

## 例

`setDays(toDateTime('2010-12-12T01:11:00Z'), 25)`

2010-12-25T01:11:00Zを返します。

`setDays(toDateTimeOnly(@{MyEvent.registrationDate}), 1)`
