---
title: setDays
description: setDays関数について説明します。
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
source-git-commit: d6360d616199d597255610959432c7b93fd4e25c

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
| 日 | 整数 |

## 署名と戻り値の型

`setDays(<dateTime>,<days>)`

日時を返します。

`setDays(<dateTimeOnly>,<days>)`

タイムゾーンを考慮せずにdatetimeを返します。

## 例

`setDays(toDateTime('2010-12-12T01:11:00Z'), 25)`

2010-12-25T01:11:00Zを返します。

`setDays(toDateTimeOnly(@{MyEvent.registrationDate}), 1)`
