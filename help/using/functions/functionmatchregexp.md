---
title: matchRegExp
description: matchRegExp関数について学習します
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: tm+mt
source-git-commit: b852c08a488a1bec02b8b31a1fccf1a8773b99af
workflow-type: tm+mt
source-wordcount: '85'
ht-degree: 12%

---


# matchRegExp {#matchRegExp}

最初のパラメーター内の文字列が2番目のパラメーター内の正規式と一致する場合は、trueを返します。 For more information, see [this page](https://docs.oracle.com/javase/7/docs/api/java/util/regex/Pattern.html).

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
