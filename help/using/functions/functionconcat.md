---
title: concat
description: 関数の概要
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: tm+mt
source-git-commit: b852c08a488a1bec02b8b31a1fccf1a8773b99af
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
