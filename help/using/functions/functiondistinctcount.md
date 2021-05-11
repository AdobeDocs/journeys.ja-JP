---
product: adobe campaign
solution: Journey Orchestration
title: distinctCount
description: distinctCount関数について
feature: ジャーニー
role: Data Engineer
level: Experienced
exl-id: b7844bce-1286-4d9e-b9e6-619c2d467c91
translation-type: tm+mt
source-git-commit: 8ab3951f9c97a0a964f5c123978ed256d3aedc45
workflow-type: tm+mt
source-wordcount: '48'
ht-degree: 33%

---

# distinctCount{#distinctCount}

null値を無視する異なる値の数を数えます。

## カテゴリ

集計

## 関数の構文

`distinctCount(<listAny>)`

## パラメーター

| パラメーター | タイプ |
|-----------|------------------|
| リスト | listString |
| リスト | listBoolean |
| リスト | listInteger |
| リスト | listDecimal |
| リスト | listDuration |
| リスト | listDateTime |
| リスト | listDateTimeOnly |

## 署名と戻り値の型

`distinctCount(<listAny>)`

整数を返します。

## 例

`distinctCount([10,2,10,null])`

2を返します。
