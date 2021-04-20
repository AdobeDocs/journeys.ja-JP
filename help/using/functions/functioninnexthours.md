---
product: adobe campaign
solution: Journey Orchestration
title: inNextHours
description: NextHours関数について学習します
feature: Journeys
role: Data Engineer
level: Experienced
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '48'
ht-degree: 18%

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
