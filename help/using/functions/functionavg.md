---
product: adobe campaign
solution: Journey Orchestration
title: avg
description: 関数avgについて
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# avg {#avg}

リストまたは2つの式で指定された、式のセットの平均値を返します。 null値は無視されます。


## カテゴリ

集計

## 関数の構文

`avg(<parameter>)`

## パラメーター

サポートされるタイプ：

* listInteger
* listDecimal
* decimal
* integer

## 署名と戻り値の型

`avg(<listInteger>)`

`avg(<listInteger>)`

`avg(<listDecimal>)`

`avg(<decimal>,<decimal>)`

`avg(<decimal>,<integer>)`

`avg(<integer>,<decimal>)`

`avg(<integer>,<integer>)`

小数を返します。

## 例

`avg(@{BarBeacon.inventory},5)`

`avg([10,3,8])`

7.0を返します。

`avg(10.2, 3)`

6.6を返します。
