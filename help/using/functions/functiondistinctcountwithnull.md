---
product: adobe campaign
solution: Journey Orchestration
title: distinctCountWithNull
description: distinctCountWithNull関数について学習します
feature: ジャーニー
role: Data Engineer
level: Experienced
exl-id: b8380d30-160e-45c2-b187-34eb42845923
translation-type: tm+mt
source-git-commit: 8ab3951f9c97a0a964f5c123978ed256d3aedc45
workflow-type: tm+mt
source-wordcount: '48'
ht-degree: 33%

---

# distinctCountWithNull {#distinctCountWithNull}

null値を含む異なる値の数を数えます。

## カテゴリ

集計

## 関数の構文

`distinctCountWithNull(<listAny>)`

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

`distinctCountwithNull(<listAny>)`

整数を返します。

## 例

`distinctCountWithNull([10,2,10,null])`

3を返します。
