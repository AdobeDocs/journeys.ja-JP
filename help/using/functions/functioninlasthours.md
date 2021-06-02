---
product: adobe campaign
title: inLastHours
description: inLastHours関数の詳細
feature: ジャーニー
role: Data Engineer
level: Experienced
exl-id: 9baeb836-e029-4e19-b08e-7b7b5f27ff8f
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '46'
ht-degree: 19%

---

# inLastHours {#inLastHours}

指定された日付時刻が現在と現在の間（差分時間）の場合にtrueを返します。

## カテゴリ

日付

## 関数の構文

`inLastHours(<dateTime>,<delta>)`

## パラメーター

| パラメーター | タイプ |
|-----------|------------------|
| 日時 | dateTime |
| デルタ | 整数 |

## 署名と戻り値の型

`inLastHours(<dateTime>,<integer>)`

ブール値を返します。

## 例

`inLastHours(toDateTime('2019-12-12T01:11:00Z'), 4))`

trueを返します。

`inLastHours(@{MyEvent.timestamp}, 4)`

trueを返します。
