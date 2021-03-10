---
product: adobe campaign
solution: Journey Orchestration
title: notEqualWithIgnoreCase
description: notEqualWithIgnoreCase関数について学習します。
feature: ジャーニー
role: データエンジニア
level: 経験豊富な
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '41'
ht-degree: 19%

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
