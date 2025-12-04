---
product: adobe campaign
title: countOnlyNull
description: countOnlyNull 関数について説明します
feature: Journeys
role: Developer
level: Experienced
exl-id: e6170a21-0418-4311-a43b-fd4f323cd020
source-git-commit: d3de66b9b28efa2636f5c0fd5a0d7ccb6132dbdd
workflow-type: tm+mt
source-wordcount: '49'
ht-degree: 100%

---

# countOnlyNull {#countOnlyNull}

リスト内の null 値の数をカウントします。

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
| リスト | listDateOnly |

## シグネチャと戻り値のタイプ

`countOnlyNull(<listAny>)`

整数を返します。

## 例

`countOnlyNull([10,2,10,null])`

1 を返します。
