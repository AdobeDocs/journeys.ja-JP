---
product: adobe campaign
solution: Journey Orchestration
title: notEqualWithIgnoreCase
description: notEqualWithIgnoreCase関数について学習します。
feature: ジャーニー
role: Data Engineer
level: Experienced
exl-id: d99601cf-2ba8-4150-afa7-df6b8af47bf6
translation-type: tm+mt
source-git-commit: 8ab3951f9c97a0a964f5c123978ed256d3aedc45
workflow-type: tm+mt
source-wordcount: '38'
ht-degree: 21%

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
