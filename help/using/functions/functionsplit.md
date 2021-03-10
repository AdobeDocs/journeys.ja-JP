---
product: adobe campaign
solution: Journey Orchestration
title: split
description: 関数の分割について説明します
feature: ジャーニー
role: データエンジニア
level: 経験豊富な
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '67'
ht-degree: 19%

---


# split {#split}

最初の引数文字列を区切り文字列(2番目の引数文字列、正規式にすることができる)で分割し、文字列（トークン）のリストを生成します。

## カテゴリ

 バイト長文字列

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

値が「イベント.appVersion」のイベントフィールドの例：&quot;20.45.2.3434&quot;

`split(@{event.appVersion}, "\\.")`

戻り値 `["20", "45", "2", "3434"]`
