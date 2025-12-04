---
product: adobe campaign
title: split
description: split 関数について説明します
feature: Journeys
role: Developer
level: Experienced
exl-id: 44499a09-19e2-4085-bf2f-7d9080ec382d
source-git-commit: d3de66b9b28efa2636f5c0fd5a0d7ccb6132dbdd
workflow-type: tm+mt
source-wordcount: '65'
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
