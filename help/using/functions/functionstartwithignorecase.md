---
product: adobe campaign
solution: Journey Orchestration
title: startWithIgnoreCase
description: startWithIgnoreCase関数について学習します。
feature: Journeys
role: Data Engineer
level: Experienced
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '48'
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
