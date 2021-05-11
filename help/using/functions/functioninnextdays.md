---
product: adobe campaign
solution: Journey Orchestration
title: inNextDays
description: NextDays関数について学習します
feature: ジャーニー
role: Data Engineer
level: Experienced
exl-id: 47d31b56-b0ed-426d-bd79-3db3e441454b
translation-type: tm+mt
source-git-commit: 8ab3951f9c97a0a964f5c123978ed256d3aedc45
workflow-type: tm+mt
source-wordcount: '45'
ht-degree: 20%

---

# inNextDays {#inNextDays}

渡されたdateまたはdateTimeがnowとnow + deltaの間にある場合、trueを返します。

## カテゴリ

日付

## 関数の構文

`inNextDays(<dateTime>,<delta>)`

## パラメーター

| パラメーター | タイプ |
|-----------|------------------|
| 日時 | dateTime |
| delta | integer |

## 署名と戻り値の型

`inNextDays(<dateTime>,<integer>)`

ブール値を返します。

## 例

`inNextDays(toDateTime('2010-12-12T01:11:00Z'), 4)`

trueを返します。
