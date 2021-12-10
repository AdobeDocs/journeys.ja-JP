---
product: adobe campaign
title: avg
description: avg 関数について説明します
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 6c9f3a5d-20b4-4c0a-b17f-5221f5db51be
source-git-commit: 5225045f02fb1b2a8505756d9d7f6f60a32b3ed6
workflow-type: tm+mt
source-wordcount: '49'
ht-degree: 100%

---

# avg {#avg}

リストまたは 2 つの式のいずれかで指定された一連の式の平均値を返します。null 値は無視されます。


## カテゴリ

集計

## 関数の構文

`avg(<parameter>)`

## パラメーター

サポートされているタイプ：

* listInteger
* listDecimal
* 小数
* 整数

## シグネチャと戻り値のタイプ

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

7.0 を返します。

`avg(10.2, 3)`

6.6 を返します。
