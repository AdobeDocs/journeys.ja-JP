---
product: adobe campaign
title: inNextDays
description: inNextDays 関数の詳細
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 47d31b56-b0ed-426d-bd79-3db3e441454b
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '44'
ht-degree: 20%

---

# inNextDays {#inNextDays}

指定された日付または dateTime が現在と今+デルタ日の間の場合、true を返します。

## カテゴリ

日付

## 関数の構文

`inNextDays(<dateTime>,<delta>)`

## パラメーター

| パラメーター | タイプ |
|-----------|------------------|
| 日時 | dateTime |
| デルタ | 整数 |

## 署名と戻り値の型

`inNextDays(<dateTime>,<integer>)`

ブール値を返します。

## 例

`inNextDays(toDateTime('2010-12-12T01:11:00Z'), 4)`

true を返します。
