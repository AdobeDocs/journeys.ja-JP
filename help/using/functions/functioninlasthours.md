---
product: adobe campaign
solution: Journey Orchestration
title: inLastHours
description: LastHours関数の詳細
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '45'
ht-degree: 17%

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
