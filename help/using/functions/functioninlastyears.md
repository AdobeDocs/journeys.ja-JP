---
product: adobe campaign
solution: Journey Orchestration
title: inLastYears
description: LastYears関数の詳細
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '44'
ht-degree: 18%

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
