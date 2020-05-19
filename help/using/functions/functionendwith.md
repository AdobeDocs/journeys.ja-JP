---
title: endWith
description: 関数endWithについて説明します。
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: a844adc1a073aebfb7fd8a719e52f305079260b7
workflow-type: tm+mt
source-wordcount: '43'
ht-degree: 25%

---


# endWith {#endWith}

2番目のパラメーターが最初のパラメーターのサフィックスである場合は、trueを返します。

## カテゴリ

文字列

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
