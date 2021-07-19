---
product: adobe campaign
title: notEqualWithIgnoreCase
description: notEqualWithIgnoreCase関数の詳細
feature: ジャーニー
role: Data Engineer
level: Experienced
exl-id: d99601cf-2ba8-4150-afa7-df6b8af47bf6
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '38'
ht-degree: 21%

---

# notEqualWithIgnoreCase {#notEqualWithIgnoreCase}

2番目の引数文字列を持つ最初の引数文字列が異なるかどうかを確認し、大文字と小文字の区別は無視します。

## カテゴリ

文字列

## 関数の構文

`notEqualWithIgnoreCase(<parameters>)`

## パラメーター

* 文字列

## 署名と戻り値の型

`notEqualWithIgnoreCase(<string>,<string>)`

ブール値を返します。

## 例

`notEqualWithIgnoreCase(@{iOSPushPermissionAllowed.device.model}, "iPad"))`
