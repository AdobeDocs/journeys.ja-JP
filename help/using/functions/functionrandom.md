---
product: adobe campaign
solution: Journey Orchestration
title: random
description: 関数randomについて説明します。
feature: Journeys
role: Data Engineer
level: Experienced
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '55'
ht-degree: 9%

---


# random {#random}

0 ～ 1の乱数を生成します。

## カテゴリ

数学

## 関数の構文

`random(<parameters>)`

## 署名と戻り値の型

`random()`

小数を返します。

## 例

`#{MarltonReservation.statistics.successRatio, defaultValue : random() * 100}`

説明：成功率に値/値がnullでない場合、デフォルト値が適用され、0 ～ 1 * 100(0 ～ 100)のランダムな数値になります。
