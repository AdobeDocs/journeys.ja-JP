---
product: adobe campaign
solution: Journey Orchestration
title: concat
description: 関数の概要
feature: ジャーニー
role: Data Engineer
level: Experienced
exl-id: 7a516705-2bbe-4b42-97fc-aeae11082002
translation-type: tm+mt
source-git-commit: 8ab3951f9c97a0a964f5c123978ed256d3aedc45
workflow-type: tm+mt
source-wordcount: '41'
ht-degree: 29%

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
