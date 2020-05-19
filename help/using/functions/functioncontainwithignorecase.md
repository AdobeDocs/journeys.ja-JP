---
title: containWithIgnoreCase
description: 関数containWithIgnoreCaseについて
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
source-wordcount: '48'
ht-degree: 22%

---


# containWithIgnoreCase {#containWithIgnoreCase}

2番目の引数文字列が、大文字と小文字を区別せずに、最初の引数文字列に含まれているかどうかをチェックします。

## カテゴリ

文字列

## 関数の構文

`containWithIgnoreCase(<parameters>)`

## パラメーター

| パラメーター | タイプ |
|-----------|------------------|
| 文字列 | 文字列 |
| 検索文字列 | 文字列 |

## 署名と戻り値の型

`containWithIgnoreCase(<string>,<string>)`

ブール値を返します。

## 例

`containWithIgnoreCase("rowing is great', "GREAT")`

trueを返します。
