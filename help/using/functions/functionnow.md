---
product: adobe campaign
title: now
description: now 関数について説明します
feature: Journeys
role: Developer
level: Experienced
exl-id: ab1f9efe-cbb7-4e3a-ace0-24f2fb6165cb
source-git-commit: d3de66b9b28efa2636f5c0fd5a0d7ccb6132dbdd
workflow-type: tm+mt
source-wordcount: '54'
ht-degree: 75%

---

# now {#now}

現在の日付を日時形式で返します。データタイプについて詳しくは、[このページ](../expression/data-types.md)を参照してください。

## カテゴリ

日付

## 関数の構文

`now(<parameter>)`

## パラメーター

| パラメーター | 説明 |
|--- |--- |
| 文字列 |  |

## シグネチャと戻り値のタイプ

`now()`

`now("<timeZone id>")`

日時を返します。

## 例

`now()`

2019-06-03T06:30Z を返します。

`toString(now())`

「2019-06-03T06:30Z」を返します。

`now("Europe/Paris")`

2019-06-03T08:30+02:00 を返します。
