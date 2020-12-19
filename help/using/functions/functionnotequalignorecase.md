---
product: adobe campaign
solution: Journey Orchestration
title: notEqualWithIgnoreCase
description: notEqualWithIgnoreCase関数について学習します。
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# notEqualWithIgnoreCase {#notEqualWithIgnoreCase}

最初の引数文字列と2番目の引数文字列が異なるかどうかを確認し、大文字と小文字の区別は無視します。

## カテゴリ

 バイト長文字列

## 関数の構文

`notEqualWithIgnoreCase(<parameters>)`

## パラメーター

* 文字列

## 署名と戻り値の型

`notEqualWithIgnoreCase(<string>,<string>)`

ブール値を返します。

## 例

`notEqualWithIgnoreCase(@{iOSPushPermissionAllowed.device.model}, "iPad"))`
