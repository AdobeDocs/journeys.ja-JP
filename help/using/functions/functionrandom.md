---
product: adobe campaign
solution: Journey Orchestration
title: random
description: 関数randomについて説明します。
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '51'
ht-degree: 7%

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
