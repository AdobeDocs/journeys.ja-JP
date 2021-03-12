---
product: adobe campaign
solution: Journey Orchestration
title: countWithNull
description: countWithNull関数について学習します
feature: ジャーニー
role: データエンジニア
level: 経験豊富な
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '51'
ht-degree: 31%

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
