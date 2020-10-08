---
title: now
description: 関数について説明します
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


# now {#now}

現在の日付を日付時間形式で返します。 For more information on data types, refer to [](../expression/data-types.md).

## カテゴリ

日付

## 関数の構文

`now(<parameter>)`

## パラメーター

| パラメーター | 説明 |
|--- |--- |
| 文字列 |  |

## 署名と戻り値の型

`now()`

`now("<timeZone id>")`

dateTimeを返します。

## 例

`now()`

2019-06-03T06:30Zを返します。

`toString(now())`

&quot;2019-06-03T06:30Z&quot;を返します

`now("Europe/Paris")`

2019-06-03T08:30+02:00を返します。