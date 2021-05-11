---
product: adobe campaign
solution: Journey Orchestration
title: startWithIgnoreCase
description: startWithIgnoreCase関数について学習します。
feature: ジャーニー
role: Data Engineer
level: Experienced
exl-id: 0ef098d8-b56c-4509-bbbd-2688ecc547bf
translation-type: tm+mt
source-git-commit: 8ab3951f9c97a0a964f5c123978ed256d3aedc45
workflow-type: tm+mt
source-wordcount: '45'
ht-degree: 28%

---

# startWithIgnoreCase {#startWithIgnoreCase}

2番目のパラメーターが、大文字と小文字を区別せずに最初のパラメーターのプレフィックスである場合は、trueを返します。

## カテゴリ

 バイト長文字列

## 関数の構文

`startWithIgnoreCase(<parameters>)`

## パラメーター

| パラメーター | タイプ |
|-------------|--------|
| 文字列 | 文字列 |
| プレフィックス | 文字列 |

## 署名と戻り値の型

`startWithIgnoreCase(<string>,<string>)`

ブール値を返します。

## 例

`startWith("rowing is great', "RO")`

trueを返します。
