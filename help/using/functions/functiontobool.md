---
title: toBool
description: toBool関数について学びます。
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
source-wordcount: '74'
ht-degree: 9%

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
