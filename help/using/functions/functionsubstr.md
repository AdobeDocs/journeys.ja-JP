---
product: adobe campaign
title: substr
description: substr 関数について説明します
feature: Journeys
role: Developer
level: Experienced
exl-id: dda01de5-b865-4323-ac36-2e3d90d213ee
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
source-wordcount: '65'
ht-degree: 100%
---
# substr {#substr}

文字列式の開始インデックスと終了インデックスの間にある部分文字列を返します。 終了インデックスが指定されていない場合は、文字列式の開始インデックスと末尾の間にある部分文字列を返します。

## カテゴリ

文字列

## 関数の構文

`substr(<parameters>)`

## パラメーター

| パラメーター | タイプ |
|-------------|----------|
| 文字列 | 文字列 |
| beginIndex | 整数 |
| 終了インデックス | 整数 |

## シグネチャと戻り値のタイプ

`substr(<string>,<beginIndex>)`

`substr(<string>,<beginIndex>,<endIndex>)`

文字列を返します。

## 例

`substr("Hello World",6)`

「World」を返します。

`substr("Hello World", 0, 5)`

「Hello」を返します。
