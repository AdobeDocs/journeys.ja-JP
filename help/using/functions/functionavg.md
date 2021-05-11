---
product: adobe campaign
solution: Journey Orchestration
title: avg
description: 関数avgについて
feature: ジャーニー
role: Data Engineer
level: Experienced
exl-id: 6c9f3a5d-20b4-4c0a-b17f-5221f5db51be
translation-type: tm+mt
source-git-commit: 8ab3951f9c97a0a964f5c123978ed256d3aedc45
workflow-type: tm+mt
source-wordcount: '50'
ht-degree: 14%

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
