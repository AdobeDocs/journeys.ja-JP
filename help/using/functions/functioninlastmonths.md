---
product: adobe campaign
solution: Journey Orchestration
title: inLastMonths
description: LastMonths関数について学習します
feature: ジャーニー
role: Data Engineer
level: Experienced
exl-id: ff8effa9-404a-482b-8842-a276f029e2ed
translation-type: tm+mt
source-git-commit: 8ab3951f9c97a0a964f5c123978ed256d3aedc45
workflow-type: tm+mt
source-wordcount: '45'
ht-degree: 20%

---

# inLastMonths {#inLastMonths}

渡されたdateまたはdateTimeが現在と現在の間にある場合は、trueを返します（差分月）。

## カテゴリ

日付

## 関数の構文

`inLastMonths(<dateTime>,<delta>)`

## パラメーター

| パラメーター | タイプ |
|-----------|------------------|
| 日時 | dateTime |
| delta | integer |

## 署名と戻り値の型

`inLastMonths(<dateTime>,<integer>)`

ブール値を返します。

## 例

`inLastMonths(toDateTime('2010-12-12T01:11:00Z'), 4))`

trueを返します。
