---
product: adobe campaign
solution: Journey Orchestration
title: concat
description: 関数の概要
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '40'
ht-degree: 27%

---


# concat {#concat}

2つの文字列パラメーターまたは1つのリスト列を連結します。

## カテゴリ

 バイト長文字列

## 関数の構文

`concat(<parameters>)`

## パラメーター

| パラメーター | タイプ |
|-----------|------------------|
| リスト | listString |
| 文字列 | 文字列 |

## 署名と戻り値の型

`concat(<string>,<string>)`

`concat(<listString>)`

文字列を返します。

## 例

`concat("Hello","World")`

&quot;HelloWorld&quot;を返します。

`concat(["Hello"," ","World"])`

「Hello World」を返します。
