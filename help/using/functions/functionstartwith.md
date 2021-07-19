---
product: adobe campaign
title: startWith
description: startWith関数の詳細
feature: ジャーニー
role: Data Engineer
level: Experienced
exl-id: bf0e75d6-cc7c-4a76-b215-8735eb62163b
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '44'
ht-degree: 29%

---

# startWith {#startWith}

2番目のパラメーターが最初のパラメーターのプレフィックスである場合はtrueを返します。

## カテゴリ

文字列

## 関数の構文

`startWith(<parameters>)`

## パラメーター

| パラメーター | タイプ |
|-------------|--------|
| 文字列 | 文字列 |
| prefix | 文字列 |

## 署名と戻り値の型

`startWith(<string>,<string>)`

ブール値を返します。

## 例

`startWith("Hello World", "Hello")`

trueを返します。

`startWith("Hello World", "World")`

falseを返します。
