---
product: adobe campaign
title: endWithIgnoreCase
description: 関数endWithIgnoreCaseについて説明します
feature: ジャーニー
role: Data Engineer
level: Experienced
exl-id: 3d14fe82-e287-4474-8d78-10efbf55d338
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '49'
ht-degree: 20%

---

# endWithIgnoreCase {#endWithIgnoreCase}

最初の引数文字列が特定の文字列（2番目の引数文字列）で終わっているかどうかをチェックし、大文字と小文字の区別をしません。

## カテゴリ

文字列

## 関数の構文

`endWithIgnoreCase(<parameters>)`

## パラメーター

| パラメーター | タイプ |
|-----------|------------------|
| 文字列 | 文字列 |
| 接尾辞 | 文字列 |

## 署名と戻り値の型

`endWithIgnoreCase(<string>,<string>)`

ブール値を返します。

## 例

`endWithIgnoreCase("rowing is great', "AT")`

trueを返します。
