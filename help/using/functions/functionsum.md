---
product: adobe campaign
solution: Journey Orchestration
title: sum
description: 関数の合計について
feature: ジャーニー
role: Data Engineer
level: Experienced
exl-id: 04289d72-aade-4725-b1f5-47cf55e3a40b
translation-type: tm+mt
source-git-commit: 8ab3951f9c97a0a964f5c123978ed256d3aedc45
workflow-type: tm+mt
source-wordcount: '52'
ht-degree: 15%

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
