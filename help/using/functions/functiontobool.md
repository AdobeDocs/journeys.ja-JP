---
product: adobe campaign
title: toBool
description: toBool関数について説明します。
feature: ジャーニー
role: Data Engineer
level: Experienced
exl-id: 490144c2-1ecd-4772-ab15-e23b1b7d8f0c
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '75'
ht-degree: 14%

---

# toBool {#toBool}

引数の値を、型に応じてブール値に変換します。

* 開始文字列：文字列値をブール値として変換し、文字列値が「true」の場合は「true」、それ以外の場合はfalse
* 数値から：数値が0に等しくない場合はtrue 、それ以外の場合はfalse

## カテゴリ

コンバージョン

## 関数の構文

`toBool(<parameter>)`

## パラメーター

* decimal
* ブール型
* 文字列
* 整数

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
