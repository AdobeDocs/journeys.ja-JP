---
product: adobe campaign
solution: Journey Orchestration
title: round
description: 関数ラウンドについて
feature: ジャーニー
role: Data Engineer
level: Experienced
exl-id: 16fe7c3a-8300-49d6-a3d6-a037fa1461f3
translation-type: tm+mt
source-git-commit: 8ab3951f9c97a0a964f5c123978ed256d3aedc45
workflow-type: tm+mt
source-wordcount: '41'
ht-degree: 14%

---

# round {#round}

引数に最も近い整数値を返します。この値は、正の無限大に丸められます。

## カテゴリ

数学

## 関数の構文

`round(<parameters>)`

## パラメーター

* decimal
* integer

## 署名と戻り値の型

`round(<decimal>)`

`round(<integer>)`

整数を返します。

## 例

`round(3.14)`

3を返します。

`round(3.54)`

4を返します。

`round(-3.14)`

-3を返します。

`round(3)`

3を返します。
