---
title: toDateTimeOnly
description: toDateTime関数について
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
source-wordcount: '47'
ht-degree: 19%

---


# toDateTimeOnly{#toDateTimeOnly}

引数の値を日付のみの値に変換します。

## カテゴリ

コンバージョン変換

## 関数の構文

`toDateTimeOnly(<parameters>)`

## パラメーター

| パラメーター | タイプ |
|-----------|------------------|
| ISO-8601形式の日時 | 文字列 |
| 日時 | dateTime |

## 署名と戻り値の型

`toDateTimeOnly(<dateTime>)`

`toDateTimeOnly(<string>)`
<!--`toDateTimeOnly(<integer>,<integer>,<integer>)`
`toDateTimeOnly(<integer>,<integer>,<integer>,<integer>,<integer>,<integer>)`-->

タイムゾーンを考慮せずにdatetimeを返します。

## 例

`toDateTimeOnly ("2016-08-18T23:17:59.123Z")`

2016-08-18T23:17:59.123を返します。

`toDateTimeOnly(now())`

<!--`toDateTimeOnly(2016,8,18,23,17,59)`

Returns 2016-08-18T23:17:59.000.

`toDateTimeOnly(2016,8,18)`

Returns 2016-08-18T00:00:00.000.-->
