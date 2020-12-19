---
product: adobe campaign
solution: Journey Orchestration
title: matchRegExp
description: matchRegExp関数について学習します
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# matchRegExp {#matchRegExp}

最初のパラメーター内の文字列が2番目のパラメーター内の正規式と一致する場合は、trueを返します。 詳しくは、[このページ](https://docs.oracle.com/javase/7/docs/api/java/util/regex/Pattern.html)を参照してください。

## カテゴリ

 バイト長文字列

## 関数の構文

`matchRegExp(<parameters>)`

## パラメーター

| パラメーター | タイプ |
|--- |--- |
| 文字列 | 文字列 |
| regexp | 文字列 |

## 署名と戻り値の型

`matchRegExp(<string>,<string>)`

trueを返します。

## 例

`matchRegExp("Hello World", "Hello\s+World")`

trueを返します。

説明：

ここで、文字列が正規式（Java構文）を満たしているかどうかを確認します。「Hello」を持つ開始、次に任意の種類の文字列、最後に「World」を持つ文字列。
