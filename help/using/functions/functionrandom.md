---
product: adobe campaign
title: random
description: ランダム関数の詳細
feature: ジャーニー
role: Data Engineer
level: Experienced
exl-id: c47dc5f0-ea69-4814-863b-e0e483ba7770
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '52'
ht-degree: 11%

---

# random {#random}

0 ～ 1の乱数を生成します。

## カテゴリ

数値計算

## 関数の構文

`random(<parameters>)`

## 署名と戻り値の型

`random()`

小数を返します。

## 例

`#{MarltonReservation.statistics.successRatio, defaultValue : random() * 100}`

説明：成功率に値がない/がnullの場合、デフォルト値が適用され、0 ～ 1 * 100(0 ～ 100)の間のランダムな数値が使用されます。
