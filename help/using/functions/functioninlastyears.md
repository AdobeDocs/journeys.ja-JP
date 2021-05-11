---
product: adobe campaign
solution: Journey Orchestration
title: inLastYears
description: LastYears関数の詳細
feature: ジャーニー
role: Data Engineer
level: Experienced
exl-id: 95ca3d7d-2340-4378-9af4-aa1188bed614
translation-type: tm+mt
source-git-commit: 8ab3951f9c97a0a964f5c123978ed256d3aedc45
workflow-type: tm+mt
source-wordcount: '45'
ht-degree: 20%

---

# inLastYears {#inLastYears}

渡されたdateまたはdateTimeが現在と現在の間にある場合は、trueを返します（差分年）。

## カテゴリ

日付

## 関数の構文

`inLastYears(<dateTime>,<delta>)`

## パラメーター

| パラメーター | タイプ |
|-----------|------------------|
| 日時 | dateTime |
| delta | integer |

## 署名と戻り値の型

`inLastYears(<dateTime>,<integer>)`

ブール値を返します。

## 例

`inLastYears(toDateTime('2010-12-12T01:11:00Z'), 4))`

trueを返します。
