---
product: adobe campaign
title: matchRegExp
description: matchRegExp 関数の詳細
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 751fdcde-0af5-4f98-8cea-aae3ebefdb04
source-git-commit: 5225045f02fb1b2a8505756d9d7f6f60a32b3ed6
workflow-type: tm+mt
source-wordcount: '85'
ht-degree: 24%

---

# matchRegExp {#matchRegExp}

最初のパラメーターの文字列が 2 番目のパラメーターの正規表現と一致する場合は、true を返します。 詳しくは、 [このページ](https://docs.oracle.com/javase/7/docs/api/java/util/regex/Pattern.html).

## カテゴリ

文字列

## 関数の構文

`matchRegExp(<parameters>)`

## パラメーター

| パラメーター | タイプ |
|--- |--- |
| 文字列 | 文字列 |
| 正規表現 | 文字列 |

## 署名と戻り値の型

`matchRegExp(<string>,<string>)`

ブール値を返します。

## 例

`matchRegExp("Hello World", "Hello\s+World")`

true を返します。

説明:

ここでは、文字列が正規表現（Java 構文）を満たしているかどうかを確認します。「Hello」で始まり、任意の種類の文字列で始まり、「World」で終わります。
