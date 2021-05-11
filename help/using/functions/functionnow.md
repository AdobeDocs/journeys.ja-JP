---
product: adobe campaign
solution: Journey Orchestration
title: now
description: 関数について説明します
feature: ジャーニー
role: Data Engineer
level: Experienced
exl-id: ab1f9efe-cbb7-4e3a-ace0-24f2fb6165cb
translation-type: tm+mt
source-git-commit: 8ab3951f9c97a0a964f5c123978ed256d3aedc45
workflow-type: tm+mt
source-wordcount: '50'
ht-degree: 20%

---

# now {#now}

現在の日付を日付時間形式で返します。 データタイプの詳細については、[このページ](../expression/data-types.md)を参照してください。

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
