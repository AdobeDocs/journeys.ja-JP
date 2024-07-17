---
product: adobe campaign
title: round
description: round 関数について説明します
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 16fe7c3a-8300-49d6-a3d6-a037fa1461f3
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '44'
ht-degree: 100%

---

# round {#round}

引数に最も近い整数値を返します。差が同じ場合は正の無限大側に丸められます。

## カテゴリ

数値計算

## 関数の構文

`round(<parameters>)`

## パラメーター

* 小数
* 整数

## シグネチャと戻り値のタイプ

`round(<decimal>)`

`round(<integer>)`

整数を返します。

## 例

`round(3.14)`

3 を返します。

`round(3.54)`

4 を返します。

`round(-3.14)`

-3 を返します。

`round(3)`

3 を返します。
