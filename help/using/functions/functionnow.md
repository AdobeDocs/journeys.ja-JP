---
product: adobe campaign
solution: Journey Orchestration
title: now
description: 関数について説明します
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '49'
ht-degree: 18%

---


# now {#now}

現在の日付を日付時間形式で返します。 For more information on data types, refer to [this page](../expression/data-types.md).

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