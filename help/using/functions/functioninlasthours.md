---
product: adobe campaign
solution: Journey Orchestration
title: inLastHours
description: LastHours関数の詳細
feature: ジャーニー
role: データエンジニア
level: 経験豊富な
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '49'
ht-degree: 18%

---


# inLastHours {#inLastHours}

渡された日付時刻が現在と現在の間にある場合は、trueを返します。

## カテゴリ

日付

## 関数の構文

`inLastHours(<dateTime>,<delta>)`

## パラメーター

| パラメーター | タイプ |
|-----------|------------------|
| 日時 | dateTime |
| delta | integer |

## 署名と戻り値の型

`inLastHours(<dateTime>,<integer>)`

ブール値を返します。

## 例

`inLastHours(toDateTime('2019-12-12T01:11:00Z'), 4))`

trueを返します。

`inLastHours(@{MyEvent.timestamp}, 4)`

trueを返します。
