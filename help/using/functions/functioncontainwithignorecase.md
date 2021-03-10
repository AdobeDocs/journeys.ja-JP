---
product: adobe campaign
solution: Journey Orchestration
title: containWithIgnoreCase
description: 関数containWithIgnoreCaseについて
feature: ジャーニー
role: データエンジニア
level: 経験豊富な
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '52'
ht-degree: 23%

---


# containWithIgnoreCase {#containWithIgnoreCase}

2番目の引数文字列が、大文字と小文字を区別せずに、最初の引数文字列に含まれているかどうかをチェックします。

## カテゴリ

 バイト長文字列

## 関数の構文

`containWithIgnoreCase(<parameters>)`

## パラメーター

| パラメーター | タイプ |
|-----------|------------------|
| 文字列 | 文字列 |
| 検索文字列 | 文字列 |

## 署名と戻り値の型

`containWithIgnoreCase(<string>,<string>)`

ブール値を返します。

## 例

`containWithIgnoreCase("rowing is great', "GREAT")`

trueを返します。
