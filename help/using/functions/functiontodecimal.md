---
product: adobe campaign
title: toDecimal
description: toDecimal 関数について説明します
feature: Journeys
role: Developer
level: Experienced
exl-id: 11d7013c-2190-4654-8466-920861c836f5
source-git-commit: d3de66b9b28efa2636f5c0fd5a0d7ccb6132dbdd
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# toDecimal {#toDecimal}

引数の値をタイプに応じて小数値に変換します。

## カテゴリ

変換

## 関数の構文

`toDecimal(<parameter>)`

## パラメーター

| パラメーター | 説明 |
|--- |--- |
| 文字列 | 文字列値を小数に変換します |
| 日時 | 日付をミリ秒数（エポックミリ秒）に変換します |
| ブール値 | ブール値を true の場合は 1 に、false の場合は 0 に変換します |
| 整数 | 小数に変換します（例：1 は 1.0 になります） |

## シグネチャと戻り値のタイプ

`toDecimal(<integer>)`

`toDecimal(<decimal>)`

`toDecimal(<string>)`

`toDecimal(<boolean>)`

小数を返します。

## 例

`toDecimal("4.0")`

4.0 を返します。
