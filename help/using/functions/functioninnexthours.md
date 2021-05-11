---
product: adobe campaign
solution: Journey Orchestration
title: inNextHours
description: NextHours関数について学習します
feature: ジャーニー
role: Data Engineer
level: Experienced
exl-id: 4bcbfdbc-fc95-4089-8abc-f9314dde2c06
translation-type: tm+mt
source-git-commit: 8ab3951f9c97a0a964f5c123978ed256d3aedc45
workflow-type: tm+mt
source-wordcount: '45'
ht-degree: 20%

---

# inNextHours {#inNextHours}

渡されたdateまたはdateTimeがnowとnow + delta時間の間にある場合、trueを返します。

## カテゴリ

日付

## 関数の構文

`inNextHours(<dateTime>,<delta>)`

## パラメーター

| パラメーター | タイプ |
|-----------|------------------|
| 日時 | dateTime |
| delta | integer |

## 署名と戻り値の型

`inNextHours(<dateTime>,<integer>)`

ブール値を返します。

## 例

`inNextHours(toDateTime('2010-12-12T01:11:00Z'), 4)`

trueを返します。
