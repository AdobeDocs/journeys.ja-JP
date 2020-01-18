---
title: notEqualWithIgnoreCase
description: notEqualWithIgnoreCase関数について
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
source-git-commit: 939cde1f30a946ba4c20984dd72dcd1526d6e608

---


# notEqualWithIgnoreCase {#notEqualWithIgnoreCase}

2番目の引数文字列を持つ最初の引数文字列が異なるかどうかを確認します。大文字と小文字の区別は無視します。

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
