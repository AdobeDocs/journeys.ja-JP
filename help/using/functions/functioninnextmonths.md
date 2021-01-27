---
product: adobe campaign
solution: Journey Orchestration
title: inNextMonths
description: NextMonths関数について学習します
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '44'
ht-degree: 18%

---


# inNextMonths {#inNextMonths}

渡されたdateまたはdateTimeが現在と現在の間の月+ deltaの間にある場合、trueを返します。

## カテゴリ

日付

## 関数の構文

`inNextMonths(<dateTime>,<delta>)`

## パラメーター

| パラメーター | タイプ |
|-----------|------------------|
| 日時 | dateTime |
| delta | integer |

## 署名と戻り値の型

`inNextMonths(<dateTime>,<integer>)`

ブール値を返します。

## 例

`inNextMonths(toDateTime('2020-01-12T01:11:00Z'), 4))`

trueを返します。
