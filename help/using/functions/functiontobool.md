---
product: adobe campaign
solution: Journey Orchestration
title: toBool
description: toBool関数について学びます。
feature: Journeys
role: Data Engineer
level: Experienced
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '78'
ht-degree: 10%

---


# toBool {#toBool}

引数の値を、型に応じてboolean値に変換します。

* 開始文字列：文字列値をブール値として変換し、文字列値が「true」の場合は「true」、それ以外の場合は「false」
* 開始数値：数値が0でない場合はtrue、それ以外の場合はfalse

## カテゴリ

コンバージョン変換

## 関数の構文

`toBool(<parameter>)`

## パラメーター

* decimal
* boolean
* 文字列
* integer

## 署名と戻り値の型

`toBool(<decimal>)`

`toBool(<boolean>)`

`toBool(<string>)`

`toBool(<integer>)`

ブール値を返します。

## 例

`toBool("true")`

`toBool(1)`

trueを返します。

`toBool("this is not a boolean")`

falseを返します。
