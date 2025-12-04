---
product: adobe campaign
title: sum
description: sum 関数について説明します
feature: Journeys
role: Developer
level: Experienced
exl-id: 04289d72-aade-4725-b1f5-47cf55e3a40b
source-git-commit: d3de66b9b28efa2636f5c0fd5a0d7ccb6132dbdd
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# sum {#sum}

 一連の式の値の合計を返します。null 値は無視されます。

## カテゴリ

集計

## 関数の構文

`sum(<parameters>)`

## パラメーター

* listInteger
* listDecimal
* 期間
* 整数
* 小数

## シグネチャと戻り値のタイプ

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

21 を返します。

`sum([10.5,null,8.1])`

18.6 を返します。
