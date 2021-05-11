---
product: adobe campaign
solution: Journey Orchestration
title: inNextYears
description: NextYears関数の詳細
feature: ジャーニー
role: Data Engineer
level: Experienced
exl-id: 8aab6f60-feba-4be2-9a32-ba4ed7f3d7de
translation-type: tm+mt
source-git-commit: 8ab3951f9c97a0a964f5c123978ed256d3aedc45
workflow-type: tm+mt
source-wordcount: '45'
ht-degree: 20%

---

# inNextYears {#inNextYears}

渡されたdateまたはdateTimeが現在と現在の差分年の間にある場合、trueを返します。

## カテゴリ

日付

## 関数の構文

`inNextYears(<dateTime>,<delta>)`

## パラメーター

| パラメーター | タイプ |
|-----------|------------------|
| 日時 | dateTime |
| delta | integer |

## 署名と戻り値の型

`inNextYears(<dateTime>,<integer>)`

ブール値を返します。

## 例

`inNextYears(toDateTime('2021-12-12T01:11:00Z'), 4))`

trueを返します。
