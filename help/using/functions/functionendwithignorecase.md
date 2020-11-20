---
product: adobe campaign
solution: Journey Orchestration
title: endWithIgnoreCase
description: 関数endWithIgnoreCaseについて学習します
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '48'
ht-degree: 18%

---


# endWithIgnoreCase {#endWithIgnoreCase}

最初の引数文字列が、大文字と小文字を区別せずに特定の文字列（2番目の引数文字列）で終わるかどうかをチェックします。

## カテゴリ

 バイト長文字列

## 関数の構文

`endWithIgnoreCase(<parameters>)`

## パラメーター

| パラメーター | タイプ |
|-----------|------------------|
| 文字列 | 文字列 |
| 接尾辞 | 文字列 |

## 署名と戻り値の型

`endWithIgnoreCase(<string>,<string>)`

ブール値を返します。

## 例

`endWithIgnoreCase("rowing is great', "AT")`

trueを返します。
