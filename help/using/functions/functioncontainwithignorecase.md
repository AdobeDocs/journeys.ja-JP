---
product: adobe campaign
solution: Journey Orchestration
title: containWithIgnoreCase
description: 関数containWithIgnoreCaseについて
feature: ジャーニー
role: Data Engineer
level: Experienced
exl-id: ebec646e-9dbb-4432-a430-ab69fb7d75cf
translation-type: tm+mt
source-git-commit: 8ab3951f9c97a0a964f5c123978ed256d3aedc45
workflow-type: tm+mt
source-wordcount: '49'
ht-degree: 24%

---

# containWithIgnoreCase {#containWithIgnoreCase}

2番目の引数文字列が、大文字と小文字を区別せずに、最初の引数文字列に含まれているかどうかをチェックします。

## カテゴリ

 バイト長文字列

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
