---
product: adobe campaign
solution: Journey Orchestration
title: containWithIgnoreCase
description: 関数containWithIgnoreCaseについて
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

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
