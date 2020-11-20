---
product: adobe campaign
solution: Journey Orchestration
title: replaceAll
description: replaceAll関数の詳細
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '75'
ht-degree: 16%

---


# replaceAll {#replaceAll}

ターゲット文字列に一致するすべての出現箇所を、ベース文字列内の置換文字列で置換します。

置換は、文字列の先頭から末尾まで続きます。例えば、文字列「aa」の「b」を「aaa」の「b」に置き換えると、「ab」ではなく「ba」になります。

## カテゴリ

 バイト長文字列

## 関数の構文

`replaceAll(<parameters>)`

## パラメーター

| パラメーター | タイプ |
|-----------|--------------|
| base | 文字列 |
| target | 文字列 |
| 交換 | 文字列 |

## 署名と戻り値の型

`replaceAll(<baseString>,<sourceString>,<replacementString>)`

文字列を返します。

## 例

`replaceAll("Hello World", "l", "x")`

&quot;Hexxo Worxd&quot;を返します。
