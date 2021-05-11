---
product: adobe campaign
solution: Journey Orchestration
title: toBool
description: toBool関数について学びます。
feature: ジャーニー
role: Data Engineer
level: Experienced
exl-id: 490144c2-1ecd-4772-ab15-e23b1b7d8f0c
translation-type: tm+mt
source-git-commit: 8ab3951f9c97a0a964f5c123978ed256d3aedc45
workflow-type: tm+mt
source-wordcount: '75'
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
