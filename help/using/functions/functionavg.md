---
product: adobe campaign
title: avg
description: 関数avgの詳細
feature: ジャーニー
role: Data Engineer
level: Experienced
exl-id: 6c9f3a5d-20b4-4c0a-b17f-5221f5db51be
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '50'
ht-degree: 18%

---

# avg {#avg}

一連の式の平均値を返します。リストまたは2つの式が指定されます。 Null値は無視されます。


## カテゴリ

集計

## 関数の構文

`avg(<parameter>)`

## パラメーター

サポートされるタイプ：

* listInteger
* listDecimal
* decimal
* 整数

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
