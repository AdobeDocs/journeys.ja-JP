---
product: adobe campaign
solution: Journey Orchestration
title: inLastHours
description: LastHours関数の詳細
feature: ジャーニー
role: Data Engineer
level: Experienced
exl-id: 9baeb836-e029-4e19-b08e-7b7b5f27ff8f
translation-type: tm+mt
source-git-commit: 8ab3951f9c97a0a964f5c123978ed256d3aedc45
workflow-type: tm+mt
source-wordcount: '46'
ht-degree: 19%

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
