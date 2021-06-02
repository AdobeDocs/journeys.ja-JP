---
product: adobe campaign
title: countOnlyNull
description: countOnlyNull関数の詳細
feature: ジャーニー
role: Data Engineer
level: Experienced
exl-id: e6170a21-0418-4311-a43b-fd4f323cd020
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '47'
ht-degree: 34%

---

# countOnlyNull {#countOnlyNull}

リスト内のnull値の数をカウントします。

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
