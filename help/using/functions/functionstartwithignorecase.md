---
product: adobe campaign
solution: Journey Orchestration
title: startWithIgnoreCase
description: startWithIgnoreCase関数について学習します。
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '44'
ht-degree: 27%

---


# startWithIgnoreCase {#startWithIgnoreCase}

2番目のパラメーターが、大文字と小文字を区別せずに最初のパラメーターのプレフィックスである場合は、trueを返します。

## カテゴリ

 バイト長文字列

## 関数の構文

`startWithIgnoreCase(<parameters>)`

## パラメーター

| パラメーター | タイプ |
|-------------|--------|
| 文字列 | 文字列 |
| プレフィックス | 文字列 |

## 署名と戻り値の型

`startWithIgnoreCase(<string>,<string>)`

ブール値を返します。

## 例

`startWith("rowing is great', "RO")`

trueを返します。
