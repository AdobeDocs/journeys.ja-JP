---
product: adobe campaign
solution: Journey Orchestration
title: countOnlyNull
description: 関数countOnlyNullについて学習します。
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

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
