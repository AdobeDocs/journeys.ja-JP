---
title: 置換
description: 関数replaceについて説明します。
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
source-git-commit: d6360d616199d597255610959432c7b93fd4e25c

---


# replace {#replace}

ターゲット文字列に一致する最初の文字列をベース文字列内の置換文字列で置換します。

置換は文字列の先頭から末尾まで続きます。例えば、文字列「aaa」の「aa」を「b」に置き換えると、「ab」ではなく「ba」になります。

## カテゴリ

文字列

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
