---
product: adobe campaign
solution: Journey Orchestration
title: inLastMonths
description: LastMonths関数について学習します
feature: ジャーニー
role: データエンジニア
level: 経験豊富な
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '48'
ht-degree: 18%

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
