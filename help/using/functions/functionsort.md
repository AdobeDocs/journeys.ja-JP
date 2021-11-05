---
product: adobe campaign
title: sort
description: 関数の並べ替えの詳細
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 8e86b919-41f5-45f9-a6af-9fe290405095
source-git-commit: 9c33474a72542b6ad1d1ae0854622dfd7575f2d9
workflow-type: tm+mt
source-wordcount: '111'
ht-degree: 18%

---

# 並べ替え {#sort}

値のリストを自然順に並べ替えます。 最初の引数は値のリストで、2 番目は昇順 (true) か降順 (false) かを示すブール値です。

## カテゴリ

リスト

## 関数の構文

`sort(<parameters>)`

## パラメーター

| パラメーター | タイプ |
|-----------|------------------|
| リスト | listString |
| リスト | listBoolean |
| リスト | listInteger |
| リスト | listDecimal |
| リスト | listDuration |
| リスト | listDateTime |
| リスト | listDateTimeOnly |
| リスト | listDateOnly |
| Boolean | ブール値 |

## 署名と戻り値の型

`sort(<listInteger>,<boolean>)`

整数のリストを返します。

`sort(<listDecimal>,<boolean>)`

小数のリストを返します。

`sort(<listString>,<boolean>)`

文字列のリストを返します。

`sort(<listDateTimeOnly>,<boolean>)`

タイムゾーンを考慮せずに、日時のリストを返します。

`sort(<listDateTime>,<boolean>)`

日時のリストを返します。

`sort(<listDateOnly>,<boolean>)`

日付のリストを返します。

`sort(<listBoolean>,<boolean>)`

ブール値のリストを返します。

## 例

`sort(["A", "C", "B"], true)`

戻り値 `["A","B","C"]`.

`sort([1, 3, 2], false)`

戻り値 `[3, 2, 1]`.
