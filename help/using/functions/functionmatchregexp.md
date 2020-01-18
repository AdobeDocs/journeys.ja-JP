---
title: matchRegExp
description: 関数matchRegExpについて説明します。
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
source-git-commit: 939cde1f30a946ba4c20984dd72dcd1526d6e608

---


# matchRegExp {#matchRegExp}

最初のパラメーターの文字列が2番目のパラメーターの正規表現と一致する場合は、trueを返します。 For more information, see [this page](https://docs.oracle.com/javase/7/docs/api/java/util/regex/Pattern.html).

## カテゴリ

文字列

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

ここでは、文字列が正規表現（java構文）を満たしているかどうかを確認します。が「Hello」で始まり、任意の種類の文字列で始まり、「World」で終わります。
