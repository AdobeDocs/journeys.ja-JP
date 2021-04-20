---
product: adobe campaign
solution: Journey Orchestration
title: equalWithIgnoreCase
description: 関数equalWithIgnoreCaseについて
feature: Journeys
role: Data Engineer
level: Experienced
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '40'
ht-degree: 20%

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
