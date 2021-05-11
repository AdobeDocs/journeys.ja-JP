---
product: adobe campaign
solution: Journey Orchestration
title: inNextMonths
description: NextMonths関数について学習します
feature: ジャーニー
role: Data Engineer
level: Experienced
exl-id: b5e8d514-a24d-42a2-b422-ec5d6617048a
translation-type: tm+mt
source-git-commit: 8ab3951f9c97a0a964f5c123978ed256d3aedc45
workflow-type: tm+mt
source-wordcount: '45'
ht-degree: 20%

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
