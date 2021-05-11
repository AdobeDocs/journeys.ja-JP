---
product: adobe campaign
solution: Journey Orchestration
title: toDateTimeOnly
description: toDateTime関数について
feature: ジャーニー
role: Data Engineer
level: Experienced
exl-id: 19a4b7f8-5636-4b8f-b81f-28ff7da99671
translation-type: tm+mt
source-git-commit: 8ab3951f9c97a0a964f5c123978ed256d3aedc45
workflow-type: tm+mt
source-wordcount: '48'
ht-degree: 20%

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
