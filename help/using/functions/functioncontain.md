---
product: adobe campaign
solution: Journey Orchestration
title: contain
description: 関数に次を含むことについて説明します。
feature: Journeys
role: Data Engineer
level: Experienced
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '40'
ht-degree: 20%

---


# contain {#contain}

2番目の引数文字列が最初の引数文字列に含まれているかどうかを確認します。

## カテゴリ

 バイト長文字列

## 関数の構文

`contain(<parameters>)`

## パラメーター

* 文字列

## 署名と戻り値の型

`contain(<string>,<string>)`

ブール値を返します。

## 例

`contain("rowing is great', "great")`

trueを返します。
