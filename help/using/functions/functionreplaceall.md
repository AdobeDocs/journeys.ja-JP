---
product: adobe campaign
solution: Journey Orchestration
title: replaceAll
description: replaceAll関数の詳細
feature: ジャーニー
role: Data Engineer
level: Experienced
exl-id: d60059e5-6bf8-4a57-88a4-5323d5f0fa0b
translation-type: tm+mt
source-git-commit: 8ab3951f9c97a0a964f5c123978ed256d3aedc45
workflow-type: tm+mt
source-wordcount: '76'
ht-degree: 17%

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
