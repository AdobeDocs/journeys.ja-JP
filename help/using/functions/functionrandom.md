---
title: random
description: 関数randomについて説明します。
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: tm+mt
source-git-commit: b852c08a488a1bec02b8b31a1fccf1a8773b99af
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
