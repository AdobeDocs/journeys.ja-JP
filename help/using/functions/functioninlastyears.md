---
product: adobe campaign
title: inLastYears
description: inLastYears関数の詳細
feature: ジャーニー
role: Data Engineer
level: Experienced
exl-id: 95ca3d7d-2340-4378-9af4-aa1188bed614
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '45'
ht-degree: 22%

---

# inLastYears {#inLastYears}

指定された日付またはdateTimeが現在と現在の間の場合（デルタ年）にtrueを返します。

## カテゴリ

日付

## 関数の構文

`inLastYears(<dateTime>,<delta>)`

## パラメーター

| パラメーター | タイプ |
|-----------|------------------|
| 日時 | dateTime |
| デルタ | 整数 |

## 署名と戻り値の型

`inLastYears(<dateTime>,<integer>)`

ブール値を返します。

## 例

`inLastYears(toDateTime('2010-12-12T01:11:00Z'), 4))`

trueを返します。
