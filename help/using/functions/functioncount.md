---
product: adobe campaign
solution: Journey Orchestration
title: count
description: 関数の数について説明します
feature: ジャーニー
role: Data Engineer
level: Experienced
exl-id: 46528642-18d5-4ca9-a344-de2c7f939d00
translation-type: tm+mt
source-git-commit: 8ab3951f9c97a0a964f5c123978ed256d3aedc45
workflow-type: tm+mt
source-wordcount: '51'
ht-degree: 31%

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
