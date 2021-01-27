---
product: adobe campaign
solution: Journey Orchestration
title: equalWithIgnoreCase
description: 関数equalWithIgnoreCaseについて
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '36'
ht-degree: 19%

---


# equalWithIgnoreCase {#equalWithIgnoreCase}

最初の引数文字列と2番目の引数文字列を比較し、大文字と小文字の区別は無視します。

## カテゴリ

 バイト長文字列

## 関数の構文

`equalWithIgnoreCase(<parameters>)`

## パラメーター

* 文字列

## 署名と戻り値の型

`equalWithIgnoreCase(<string>,<string>)`

ブール値を返します。

## 例

`equalWithIgnoreCase("rowing is great', "rowing is GREAT")`

trueを返します。
