---
product: adobe campaign
title: toInteger
description: toInteger 関数について説明します
feature: Journeys
role: Developer
level: Experienced
exl-id: 3fcbf4dd-3ca5-4f4b-b774-af6ac3170768
source-git-commit: d3de66b9b28efa2636f5c0fd5a0d7ccb6132dbdd
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# toInteger {#toInteger}

引数の値を整数に変換します。

## カテゴリ

変換

## 関数の構文

`toInteger(<parameter>)`

## パラメーター

| パラメーター | 説明 |
|--- |--- |
| 文字列 | 文字列値を整数に変換します |
| 日時 | 日付をミリ秒数（エポックミリ秒）に変換します |
| 小数 | 小数部を削除して整数に変換します（例：1.5 は 1 になります） |
| ブール値 | ブール値を true の場合は 1 に、false の場合は 0 に変換します |

## シグネチャと戻り値のタイプ

`toInteger(<dateTime>)`

`toInteger(<decimal>)`

`toInteger(<integer>)`

`toInteger(<string>)`

`toInteger(<boolean>)`

整数を返します。

## 例

`toInteger("4")`

4 を返します。
