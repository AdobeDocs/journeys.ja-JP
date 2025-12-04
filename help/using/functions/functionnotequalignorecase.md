---
product: adobe campaign
title: notEqualIgnoreCase
description: notEqualIgnoreCase 関数について説明します
feature: Journeys
role: Developer
level: Experienced
exl-id: d99601cf-2ba8-4150-afa7-df6b8af47bf6
source-git-commit: d3de66b9b28efa2636f5c0fd5a0d7ccb6132dbdd
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# notEqualIgnoreCase {#notEqualIgnoreCase}

最初の引数の文字列と 2 番目の引数の文字列が異なるかどうかを、大文字と小文字の区別を無視して確認します。

## カテゴリ

文字列

## 関数の構文

`notEqualIgnoreCase(<parameters>)`

## パラメーター

* 文字列

## シグネチャと戻り値のタイプ

`notEqualIgnoreCase(<string>,<string>)`

ブール値を返します。

## 例

`notEqualIgnoreCase(@{iOSPushPermissionAllowed.device.model}, "iPad")`
