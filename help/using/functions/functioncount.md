---
product: adobe campaign
solution: Journey Orchestration
title: count
description: 関数の数について説明します
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '50'
ht-degree: 30%

---


# count {#count}

null値を考慮しないリストの要素を数えます。

## カテゴリ

集計

## 関数の構文

`count(<listAny>)`

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

`count(<listAny>)`

整数を返します。

## 例

`count([10,2,10,null])`

3を返します。
