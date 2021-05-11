---
product: adobe campaign
solution: Journey Orchestration
title: random
description: 関数randomについて説明します。
feature: ジャーニー
role: Data Engineer
level: Experienced
exl-id: c47dc5f0-ea69-4814-863b-e0e483ba7770
translation-type: tm+mt
source-git-commit: 8ab3951f9c97a0a964f5c123978ed256d3aedc45
workflow-type: tm+mt
source-wordcount: '52'
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
