---
product: adobe campaign
solution: Journey Orchestration
title: sort
description: 関数の並べ替えについて説明します
feature: ジャーニー
role: Data Engineer
level: Experienced
exl-id: 8e86b919-41f5-45f9-a6af-9fe290405095
translation-type: tm+mt
source-git-commit: 8ab3951f9c97a0a964f5c123978ed256d3aedc45
workflow-type: tm+mt
source-wordcount: '105'
ht-degree: 19%

---

# sort {#sort}

値のリストを自然順に並べ替えます。 1つ目の引数は値のリスト、2つ目の引数は昇順(true)か降順(false)かを示すブール値です。

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
| ブール値 | ブール値 |

## 署名と戻り値の型

`sort(<listInteger>,<boolean>)`

整数のリストを返します。

`sort(<listDecimal>,<boolean>)`

小数のリストを返します。

`sort(<listString>,<boolean>)`

文字列のリストを返します。

`sort(<listDateTimeOnly>,<boolean>)`

タイムゾーンを考慮せずに、日付時刻のリストを返します。

`sort(<listDateTime>,<boolean>)`

日付時間のリストを返します。

`sort(<listBoolean>,<boolean>)`

ブール値のリストを返します。

## 例

`sort(["A", "C", "B"], true)`

戻り値 `["A","B","C"]`.

`sort([1, 3, 2], false)`

戻り値 `[3, 2, 1]`.
