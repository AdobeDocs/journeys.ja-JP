---
product: adobe campaign
title: replaceAll
description: replaceAll 関数について説明します
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: d60059e5-6bf8-4a57-88a4-5323d5f0fa0b
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '75'
ht-degree: 100%

---

# replaceAll {#replaceAll}

ターゲット文字列に一致するすべての出現箇所をベース文字列内の置換文字列で置き換えます。

置換は、文字列の先頭から末尾に向かって行われます。例えば、文字列「aaa」の「aa」を「b」に置き換えると、「ab」ではなく「ba」になります。

## カテゴリ

文字列

## 関数の構文

`replaceAll(<parameters>)`

## パラメーター

| パラメーター | タイプ |
|-----------|--------------|
| base（ベース文字列） | 文字列 |
| target（ターゲット文字列） | 文字列 |
| replacement（置換文字列） | 文字列 |

## シグネチャと戻り値のタイプ

`replaceAll(<baseString>,<sourceString>,<replacementString>)`

文字列を返します。

## 例

`replaceAll("Hello World", "l", "x")`

「Hexxo Worxd」を返します。
