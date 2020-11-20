---
product: adobe campaign
solution: Journey Orchestration
title: replace
description: 関数replaceについて
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '76'
ht-degree: 15%

---


# replace {#replace}

ターゲット文字列に一致する最初の文字を、ベース文字列内の置換文字列で置換します。

置換は、文字列の先頭から末尾まで続きます。例えば、文字列「aa」の「b」を「aaa」の「b」に置き換えると、「ab」ではなく「ba」になります。

## カテゴリ

 バイト長文字列

## 関数の構文

`replace(<parameters>)`

## パラメーター

| パラメーター | タイプ |
|-----------|--------------|
| base | 文字列 |
| target | 文字列 |
| 交換 | 文字列 |

## 署名と戻り値の型

`replace(<base>,<target>,<replacement>)`

文字列を返します。

## 例

`replace("Hello World", "l", "x")`

&quot;Hexlo World&quot;を返します。
