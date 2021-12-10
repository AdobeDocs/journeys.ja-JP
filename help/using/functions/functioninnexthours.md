---
product: adobe campaign
title: inNextHours
description: inNextHours 関数について説明します
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 4bcbfdbc-fc95-4089-8abc-f9314dde2c06
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '44'
ht-degree: 100%

---

# inNextHours {#inNextHours}

指定された日付または日時が現在と現在 + デルタ時間の間にある場合、true を返します。

## カテゴリ

日付

## 関数の構文

`inNextHours(<dateTime>,<delta>)`

## パラメーター

| パラメーター | タイプ |
|-----------|------------------|
| 日時 | 日時 |
| delta | 整数 |

## シグネチャと戻り値のタイプ

`inNextHours(<dateTime>,<integer>)`

ブール値を返します。

## 例

`inNextHours(toDateTime('2010-12-12T01:11:00Z'), 4)`

true を返します。
