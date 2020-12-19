---
product: adobe campaign
solution: Journey Orchestration
title: countWithNull
description: countWithNull関数について学習します
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# countWithNull {#countWithNull}

null値を含むリストのすべての要素を数えます。

## カテゴリ

集計

## 関数の構文

`countWithNull(<listAny>)`

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

`countWithNull(<listAny>)`

整数を返します。

## 例

`count([10,2,10,null])`

4を返します。
