---
product: adobe campaign
title: inNextMonths
description: inNextMonths関数の詳細
feature: ジャーニー
role: Data Engineer
level: Experienced
exl-id: b5e8d514-a24d-42a2-b422-ec5d6617048a
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '45'
ht-degree: 20%

---

# inNextMonths {#inNextMonths}

指定された日付または日付が現在と現在+デルタの月の間の場合、trueを返します。

## カテゴリ

日付

## 関数の構文

`inNextMonths(<dateTime>,<delta>)`

## パラメーター

| パラメーター | タイプ |
|-----------|------------------|
| 日時 | dateTime |
| デルタ | 整数 |

## 署名と戻り値の型

`inNextMonths(<dateTime>,<integer>)`

ブール値を返します。

## 例

`inNextMonths(toDateTime('2020-01-12T01:11:00Z'), 4))`

trueを返します。
