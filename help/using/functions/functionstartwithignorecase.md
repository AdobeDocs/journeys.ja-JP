---
product: adobe campaign
title: startWithIgnoreCase
description: startWithIgnoreCase 関数の詳細
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 0ef098d8-b56c-4509-bbbd-2688ecc547bf
source-git-commit: 5225045f02fb1b2a8505756d9d7f6f60a32b3ed6
workflow-type: tm+mt
source-wordcount: '44'
ht-degree: 27%

---

# startWithIgnoreCase {#startWithIgnoreCase}

2 番目のパラメーターが、大文字と小文字を区別せずに最初のパラメーターのプレフィックスである場合、true を返します。

## カテゴリ

文字列

## 関数の構文

`startWithIgnoreCase(<parameters>)`

## パラメーター

| パラメーター | タイプ |
|-------------|--------|
| 文字列 | 文字列 |
| prefix | 文字列 |

## 署名と戻り値の型

`startWithIgnoreCase(<string>,<string>)`

ブール値を返します。

## 例

`startWithIgnoreCase("rowing is great", "RO")`

true を返します。
