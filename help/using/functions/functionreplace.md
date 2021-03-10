---
product: adobe campaign
solution: Journey Orchestration
title: replace
description: 関数replaceについて
feature: ジャーニー
role: データエンジニア
level: 経験豊富な
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '80'
ht-degree: 16%

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
