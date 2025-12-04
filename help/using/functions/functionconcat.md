---
product: adobe campaign
title: concat
description: concat 関数について説明します
feature: Journeys
role: Developer
level: Experienced
exl-id: 7a516705-2bbe-4b42-97fc-aeae11082002
source-git-commit: d3de66b9b28efa2636f5c0fd5a0d7ccb6132dbdd
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# concat {#concat}

2 つの文字列パラメーターまたは 1 つの文字列リストを連結します。

## カテゴリ

文字列

## 関数の構文

`concat(<parameters>)`

## パラメーター

| パラメーター | タイプ |
|-----------|------------------|
| リスト | listString |
| 文字列 | 文字列 |

## シグネチャと戻り値のタイプ

`concat(<string>,<string>)`

`concat(<listString>)`

文字列を返します。

## 例

`concat("Hello","World")`

「HelloWorld」を返します。

`concat(["Hello"," ","World"])`

「Hello World」を返します。
