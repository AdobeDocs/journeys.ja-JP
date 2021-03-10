---
product: adobe campaign
solution: Journey Orchestration
title: now
description: 関数について説明します
feature: ジャーニー
role: データエンジニア
level: 経験豊富な
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '53'
ht-degree: 18%

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