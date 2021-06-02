---
product: adobe campaign
title: startWithIgnoreCase
description: startWithIgnoreCase関数の詳細
feature: ジャーニー
role: Data Engineer
level: Experienced
exl-id: 0ef098d8-b56c-4509-bbbd-2688ecc547bf
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '45'
ht-degree: 28%

---

# startWithIgnoreCase {#startWithIgnoreCase}

2番目のパラメーターが、大文字と小文字を区別せずに最初のパラメーターのプレフィックスである場合、trueを返します。

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
