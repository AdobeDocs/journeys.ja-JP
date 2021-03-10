---
product: adobe campaign
solution: Journey Orchestration
title: endWith
description: 関数endWithについて説明します。
feature: ジャーニー
role: データエンジニア
level: 経験豊富な
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '47'
ht-degree: 25%

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
