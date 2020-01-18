---
title: toBool
description: toBool関数について
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


# toBool {#toBool}

引数の値を型に応じてboolean値に変換します。

* 開始文字列：文字列値をブール値として変換し、文字列値が「true」の場合は「true」から、それ以外の場合は「false」に変換します。
* 開始番号：数値が0以外の場合はtrue、それ以外の場合はfalse

## カテゴリ

コンバージョン

## 関数の構文

`toBool(<parameter>)`

## パラメーター

* decimal
* boolean
* 文字列
* 整数

## 署名と返される型

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
