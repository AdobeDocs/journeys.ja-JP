---
product: adobe campaign
solution: Journey Orchestration
title: countOnlyNull
description: 関数countOnlyNullについて学習します。
feature: ジャーニー
role: Data Engineer
level: Experienced
exl-id: e6170a21-0418-4311-a43b-fd4f323cd020
translation-type: tm+mt
source-git-commit: 8ab3951f9c97a0a964f5c123978ed256d3aedc45
workflow-type: tm+mt
source-wordcount: '47'
ht-degree: 34%

---

# countOnlyNull {#countOnlyNull}

リスト内のnull値の数を数えます。

## カテゴリ

集計

## 関数の構文

`countOnlyNull(<listAny>)`

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

`countOnlyNull(<listAny>)`

整数を返します。

## 例

`count([10,2,10,null])`

1を返します。
