---
product: adobe campaign
title: toInteger
description: toInteger 関数の詳細
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 3fcbf4dd-3ca5-4f4b-b774-af6ac3170768
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '70'
ht-degree: 15%

---

# toInteger {#toInteger}

引数の値を整数に変換します。

## カテゴリ

コンバージョン

## 関数の構文

`toInteger(<parameter>)`

## パラメーター

| パラメーター | 説明 |
|--- |--- |
| 文字列 | 文字列値を整数に変換します |
| dateTime | 日付をミリ秒数（エポックミリ秒）に変換します |
| decimal | 小数部を削除して整数に変換します ( 例：1.5 は 1 になります ) |
| ブール型 | true の場合はブール値を 1 に、false の場合は 0 に変換します |

## 署名と戻り値の型

`toInteger(<dateTime>)`

`toInteger(<decimal>)`

`toInteger(<integer>)`

`toInteger(<string>)`

`toInteger(<boolean>)`

整数を返します。

## 例

`toInteger("4")`

4 を返します。
