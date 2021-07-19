---
product: adobe campaign
title: split
description: 関数分割の詳細
feature: ジャーニー
role: Data Engineer
level: Experienced
exl-id: 44499a09-19e2-4085-bf2f-7d9080ec382d
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '64'
ht-degree: 20%

---

# split {#split}

最初の引数文字列を区切り文字列（正規表現に使用できる2番目の引数文字列）で分割し、文字列（トークン）のリストを生成します。

## カテゴリ

文字列

## 関数の構文

`split(<parameters>)`

## パラメーター

| パラメーター | タイプ |
|-----------|------------------|
| 入力文字列 | 文字列 |
| 区切り文字列 | 文字列 |

## 署名と戻り値の型

`split(<input string>, <separator string>)`

listStringを返します。

## 例

`split(["A_B_C"], "_")`

戻り値 `["A","B","C"]`

値を持つイベントフィールド「event.appVersion」の例：&quot;20.45.2.3434&quot;

`split(@{event.appVersion}, "\\.")`

戻り値 `["20", "45", "2", "3434"]`
