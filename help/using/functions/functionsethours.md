---
title: setHours
description: setHours関数について学びます
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
workflow-type: tm+mt
source-wordcount: '76'
ht-degree: 11%

---


# setHours {#setHours}

日付の時刻または日付の時刻のみを設定します。 例えば、あす1時間まで待つ場合は、強制的に1時間に設定できます。

## カテゴリ

日付

## 関数の構文

`setHours(<parameter>)`

## パラメーター

| パラメーター | タイプ |
|--- |--- |
| 日時 | dateTime |
| タイムゾーンを考慮しない日付時刻 | dateTimeOnly |
| 時間 | integer |

## 署名と戻り値の型

`setHours(<dateTime>,<hours>)`

datetimeを返します。

`setHours(<dateTimeOnly>,<hours>)`

タイムゾーンを考慮せずに、datetimeを返します。

## 例

`setHours(toDateTime('2010-12-12T01:11:00Z'), 4))`

2010-12-12T04:11:00Zを返します。

`setHours(nowWithDelta(1, "days"), 20)`

明日の午後8時に戻ります。
