---
title: now
description: この機能について
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
source-git-commit: 654888ee62a7b9b6e3d34fc3963fb83cac719003

---


# now {#now}

現在の日付を日付時刻形式で返します。 データタイプの詳細については、を参照してくださ [](../expression/data-types.md)い。

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

`"now(<timeZone id>")`

dateTimeを返します。

## 例

`now()`

2019-06-03T06:30Zを返します。

`toString(now())`

戻り値：&quot;2019-06-03T06:30Z&quot;

`now("Europe/Paris")`

2019-06-03T08:30+02:00を返します。