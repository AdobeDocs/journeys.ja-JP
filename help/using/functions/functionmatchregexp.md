---
product: adobe campaign
title: matchRegExp
description: 関数matchRegExpについて説明します。
feature: ジャーニー
role: Data Engineer
level: Experienced
exl-id: 751fdcde-0af5-4f98-8cea-aae3ebefdb04
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '86'
ht-degree: 13%

---

# matchRegExp {#matchRegExp}

最初のパラメーターの文字列が2番目のパラメーターの正規表現と一致する場合、trueを返します。 詳しくは、[このページ](https://docs.oracle.com/javase/7/docs/api/java/util/regex/Pattern.html)を参照してください。

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

ここでは、文字列が正規表現（java構文）を満たしているかどうかを確認します。は「Hello」で始まり、任意の種類の文字列で始まり、「World」で終わります。
