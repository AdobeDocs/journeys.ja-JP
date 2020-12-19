---
product: adobe campaign
solution: Journey Orchestration
title: endWith
description: 関数endWithについて説明します。
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# endWith {#endWith}

2番目のパラメーターが最初のパラメーターのサフィックスである場合は、trueを返します。

## カテゴリ

 バイト長文字列

## 関数の構文

`endWith(<parameters>)`

## パラメーター

| パラメーター | タイプ |
|-----------|------------------|
| 文字列 | 文字列 |
| 接尾辞 | 文字列 |

## 署名と戻り値の型

`endWith(<string>,<string>)`

ブール値を返します。

## 例

`endWith("Hello World", "World")`

trueを返します。

`endWith("Hello World", "Hello")`

falseを返します。
