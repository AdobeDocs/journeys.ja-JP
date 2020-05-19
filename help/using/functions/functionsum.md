---
title: sum
description: 関数の合計について
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
source-git-commit: 654888ee62a7b9b6e3d34fc3963fb83cac719003
workflow-type: tm+mt
source-wordcount: '51'
ht-degree: 13%

---


# sum {#sum}

一連の式の値の合計を返します。 null値は無視されます。

## カテゴリ

集計

## 関数の構文

`sum(<parameters>)`

## パラメーター

* listInteger
* listDecimal
* duration
* integer
* decimal

## 署名と戻り値の型

`sum(<listDecimal>)`

小数を返します。

`sum(<listInteger>)`

整数を返します。

`sum(<integer>,<integer>)`

整数を返します。

`sum(<decimal>,<decimal>)`

小数を返します。

## 例

`sum(@{BarBeacon.inventory},5)`

`sum([10,3,8])`

21を返します。

`sum([10.5,null,8.1])`

18.6を返します。
