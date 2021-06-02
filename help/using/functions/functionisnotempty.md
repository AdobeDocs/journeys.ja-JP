---
product: adobe campaign
title: isNotEmpty
description: 関数isNotEmptyについて説明します
feature: ジャーニー
role: Data Engineer
level: Experienced
exl-id: 32bb3d72-7abe-4220-acae-f19a09f83657
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '37'
ht-degree: 21%

---

# isNotEmpty {#isNotEmpty}

パラメーター内の文字列が空でない場合はtrueを返します。

## カテゴリ

 バイト長文字列

## 関数の構文

`isNotEmpty(<parameters>)`

## パラメーター

* 文字列

## 署名と戻り値の型

`isNotEmpty(<string>)`

ブール値を返します。

## 例

`isNotEmpty("")`

falseを返します。

`isNotEmpty("hello")`

trueを返します。
