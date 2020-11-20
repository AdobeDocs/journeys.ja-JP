---
product: adobe campaign
solution: Journey Orchestration
title: distinctCount
description: distinctCount関数について
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '47'
ht-degree: 31%

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
