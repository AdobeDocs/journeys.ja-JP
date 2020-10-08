---
title: sort
description: 関数の並べ替えについて説明します
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
source-wordcount: '104'
ht-degree: 16%

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

を返し `["A","B","C"]`ます。

`sort([1, 3, 2], false)`

を返し `[3, 2, 1]`ます。
