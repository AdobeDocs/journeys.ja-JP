---
product: adobe campaign
solution: Journey Orchestration
title: split
description: 関数の分割について説明します
translation-type: tm+mt
source-git-commit: 135485c097f99483c2ddb3d03e0552f9ac134b44
workflow-type: tm+mt
source-wordcount: '63'
ht-degree: 15%

---


# 分割{#split}

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