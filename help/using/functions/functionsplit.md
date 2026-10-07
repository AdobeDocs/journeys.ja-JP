---
product: adobe campaign
title: split
description: split 関数について説明します
feature: Journeys
role: Developer
level: Experienced
exl-id: 44499a09-19e2-4085-bf2f-7d9080ec382d
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
source-wordcount: '64'
ht-degree: 100%
---
# split {#split}

1 番目の引数文字列を区切り記号列（2 番目の引数文字列：正規表現を指定可能）で分割して、文字列（トークン）のリストを作成します。

## カテゴリ

文字列

## 関数の構文

`split(<parameters>)`

## パラメーター

| パラメーター | タイプ |
|-----------|------------------|
| 入力文字列 | 文字列 |
| 区切り記号列 | 文字列 |

## シグネチャと戻り値のタイプ

`split(<input string>, <separator string>)`

文字列リストを返します。

## 例

`split(["A_B_C"], "_")`

`["A","B","C"]` を返します。

イベントフィールド「event.appVersion」の値が「20.45.2.3434」の場合の例

`split(@{event.appVersion}, "\\.")`

`["20", "45", "2", "3434"]` を返します
