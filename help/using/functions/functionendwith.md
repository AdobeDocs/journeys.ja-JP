---
product: adobe campaign
title: endWith
description: endWith 関数について説明します
feature: Journeys
role: Developer
level: Experienced
exl-id: 6eee6057-1daf-4b9d-ae94-2b35843e3a49
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
source-wordcount: '43'
ht-degree: 100%
---
# endWith {#endWith}

2 番目のパラメーターが最初のパラメーターの末尾にある場合、true を返します。

## カテゴリ

文字列

## 関数の構文

`endWith(<parameters>)`

## パラメーター

| パラメーター | タイプ |
|-----------|------------------|
| 文字列 | 文字列 |
| 末尾の文字列 | 文字列 |

## シグネチャと戻り値のタイプ

`endWith(<string>,<string>)`

ブール値を返します。

## 例

`endWith("Hello World", "World")`

true を返します。

`endWith("Hello World", "Hello")`

false を返します。
