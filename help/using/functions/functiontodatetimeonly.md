---
product: adobe campaign
title: toDateTimeOnly
description: toDateTime関数の詳細
feature: ジャーニー
role: Data Engineer
level: Experienced
exl-id: 19a4b7f8-5636-4b8f-b81f-28ff7da99671
source-git-commit: 0c55ece133639ec001b58f73afcbc69787b98c0e
workflow-type: tm+mt
source-wordcount: '56'
ht-degree: 17%

---

# toDateTimeOnly{#toDateTimeOnly}

引数の値を日付時のみの値に変換します。

## カテゴリ

コンバージョン

## 関数の構文

`toDateTimeOnly(<parameters>)`

## パラメーター

| パラメーター | タイプ |
|-----------|------------------|
| ISO-8601形式または「YYYY-MM-DD」形式の日時（XDM日付形式） | 文字列 |
| 日時 | dateTime |

## 署名と戻り値の型

`toDateTimeOnly(<dateTime>)`

`toDateTimeOnly(<string>)`
<!--`toDateTimeOnly(<integer>,<integer>,<integer>)`
`toDateTimeOnly(<integer>,<integer>,<integer>,<integer>,<integer>,<integer>)`-->

タイムゾーンを考慮せずにdatetimeを返します。

## 例

`toDateTimeOnly ("2016-08-18")`

2016-08-18T00:00:00.000を表すdateTimeを返します

`toDateTimeOnly(now())`

<!--`toDateTimeOnly(2016,8,18,23,17,59)`

Returns 2016-08-18T23:17:59.000.

`toDateTimeOnly(2016,8,18)`

Returns 2016-08-18T00:00:00.000.-->
