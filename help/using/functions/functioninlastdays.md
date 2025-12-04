---
product: adobe campaign
title: inLastDays
description: inLastDays 関数について説明します
feature: Journeys
role: Developer
level: Experienced
exl-id: 1fc29153-3554-4af1-bb2e-7bba53ffce69
source-git-commit: d3de66b9b28efa2636f5c0fd5a0d7ccb6132dbdd
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# inLastDays {#inLastDays}

指定された日付または日時が現在の日時とその delta 日前の間にある場合、true を返します。

## カテゴリ

日付

## 関数の構文

`inLastDays(<dateTime>,<delta>)`

## パラメーター

| パラメーター | タイプ |
|-----------|------------------|
| 日時 | 日時 |
| delta | 整数 |

## シグネチャと戻り値のタイプ

`inLastDays(<dateTime>,<integer>)`

ブール値を返します。

## 例

`inLastDays(toDateTime('2019-12-12T01:11:00Z'), 4)`

true を返します。
