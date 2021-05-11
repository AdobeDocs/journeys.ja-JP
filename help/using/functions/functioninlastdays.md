---
product: adobe campaign
solution: Journey Orchestration
title: inLastDays
description: LastDays関数について学習します
feature: ジャーニー
role: Data Engineer
level: Experienced
exl-id: 1fc29153-3554-4af1-bb2e-7bba53ffce69
translation-type: tm+mt
source-git-commit: 8ab3951f9c97a0a964f5c123978ed256d3aedc45
workflow-type: tm+mt
source-wordcount: '45'
ht-degree: 20%

---

# inLastDays {#inLastDays}

渡されたdateまたはdateTimeが現在と現在の間にある場合は、trueを返します（差分日）。

## カテゴリ

日付

## 関数の構文

`inLastDays(<dateTime>,<delta>)`

## パラメーター

| パラメーター | タイプ |
|-----------|------------------|
| 日時 | dateTime |
| delta | integer |

## 署名と戻り値の型

`inLastDays(<dateTime>,<integer>)`

ブール値を返します。

## 例

`inLastDays(toDateTime('2019-12-12T01:11:00Z'), 4))`

trueを返します。
