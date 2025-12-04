---
product: adobe campaign
title: inNextMonths
description: inNextMonths 関数について説明します
feature: Journeys
role: Developer
level: Experienced
exl-id: b5e8d514-a24d-42a2-b422-ec5d6617048a
source-git-commit: d3de66b9b28efa2636f5c0fd5a0d7ccb6132dbdd
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# inNextMonths {#inNextMonths}

指定された日付または日時が現在の日時とその delta か月後の間にある場合、true を返します。

## カテゴリ

日付

## 関数の構文

`inNextMonths(<dateTime>,<delta>)`

## パラメーター

| パラメーター | タイプ |
|-----------|------------------|
| 日時 | 日時 |
| delta | 整数 |

## シグネチャと戻り値のタイプ

`inNextMonths(<dateTime>,<integer>)`

ブール値を返します。

## 例

`inNextMonths(toDateTime('2020-01-12T01:11:00Z'), 4)`

true を返します。
