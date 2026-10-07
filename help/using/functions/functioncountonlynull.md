---
product: adobe campaign
title: countOnlyNull
description: countOnlyNull 関数について説明します
feature: Journeys
role: Developer
level: Experienced
exl-id: e6170a21-0418-4311-a43b-fd4f323cd020
product_v2:
  - id: cf67d108-ecf9-4fde-af49-3a3c39083bc8
    internal-label: Journey Orchestration
feature_v2:
  - id: 7de3230f-9523-5ba5-8d5c-2313288b27ef
    internal-label: Journeys
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: 255cd6677e7c9ebff63ea9a1028a042c19e63ecc
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
