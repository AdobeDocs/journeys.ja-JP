---
product: adobe campaign
title: notEqualIgnoreCase
description: notEqualIgnoreCase 関数の詳細
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: d99601cf-2ba8-4150-afa7-df6b8af47bf6
source-git-commit: 5225045f02fb1b2a8505756d9d7f6f60a32b3ed6
workflow-type: tm+mt
source-wordcount: '37'
ht-degree: 13%

---

# notEqualIgnoreCase {#notEqualIgnoreCase}

2 番目の引数文字列を持つ最初の引数文字列が異なるかどうかを確認し、大文字と小文字の区別を無視します。

## カテゴリ

文字列

## 関数の構文

`notEqualIgnoreCase(<parameters>)`

## パラメーター

* 文字列

## 署名と戻り値の型

`notEqualIgnoreCase(<string>,<string>)`

ブール値を返します。

## 例

`notEqualIgnoreCase(@{iOSPushPermissionAllowed.device.model}, "iPad")`
