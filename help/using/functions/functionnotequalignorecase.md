---
title: notEqualWithIgnoreCase
description: notEqualWithIgnoreCase関数について学習します。
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: tm+mt
source-git-commit: b852c08a488a1bec02b8b31a1fccf1a8773b99af
workflow-type: tm+mt
source-wordcount: '37'
ht-degree: 18%

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
