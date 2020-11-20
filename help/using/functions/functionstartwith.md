---
product: adobe campaign
solution: Journey Orchestration
title: startWith
description: startWith関数について学びます。
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '43'
ht-degree: 27%

---


# startWith {#startWith}

2番目のパラメーターが最初のパラメーターのプレフィックスである場合は、trueを返します。

## カテゴリ

 バイト長文字列

## 関数の構文

`startWith(<parameters>)`

## パラメーター

| パラメーター | タイプ |
|-------------|--------|
| 文字列 | 文字列 |
| プレフィックス | 文字列 |

## 署名と戻り値の型

`startWith(<string>,<string>)`

ブール値を返します。

## 例

`startWith("Hello World", "Hello")`

trueを返します。

`startWith("Hello World", "World")`

falseを返します。
