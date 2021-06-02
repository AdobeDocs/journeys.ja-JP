---
product: adobe campaign
title: now
description: 関数の詳細を今すぐ確認する
feature: ジャーニー
role: Data Engineer
level: Experienced
exl-id: ab1f9efe-cbb7-4e3a-ace0-24f2fb6165cb
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '50'
ht-degree: 20%

---

# now {#now}

現在の日付を日付時刻形式で返します。 データタイプの詳細については、[このページ](../expression/data-types.md)を参照してください。

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

戻り値は「2019-06-03T06:30Z」

`now("Europe/Paris")`

2019-06-03T08:30+02:00を返します。
