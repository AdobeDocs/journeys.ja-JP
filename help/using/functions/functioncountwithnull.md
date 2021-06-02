---
product: adobe campaign
title: countWithNull
description: countWithNull関数の詳細
feature: ジャーニー
role: Data Engineer
level: Experienced
exl-id: ea72dc20-8183-4661-8e08-ddb4f3727d3d
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '48'
ht-degree: 33%

---

# countWithNull {#countWithNull}

null値を含むリストのすべての要素をカウントします。

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
