---
product: adobe campaign
solution: Journey Orchestration
title: endWith
description: 関数endWithについて説明します。
feature: ジャーニー
role: Data Engineer
level: Experienced
exl-id: 6eee6057-1daf-4b9d-ae94-2b35843e3a49
translation-type: tm+mt
source-git-commit: 8ab3951f9c97a0a964f5c123978ed256d3aedc45
workflow-type: tm+mt
source-wordcount: '44'
ht-degree: 27%

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
