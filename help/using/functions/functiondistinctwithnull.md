---
product: adobe campaign
title: distinctWithNull
description: distinctWithNull関数の詳細
feature: ジャーニー
role: Data Engineer
level: Experienced
exl-id: 65a904c1-14ff-42b3-8f03-abb97ef47625
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '100'
ht-degree: 16%

---

# distinctWithNull {#distinctWithNull}

リストのユニーク値を返します。 リストに少なくとも1つのnull値が含まれる場合、返されるリストにnull値が含まれます。

## カテゴリ

リスト

## 関数の構文

`distinctWithNull(<parameter>)`

## パラメーター

| パラメーター | タイプ |
|-----------|------------------|
| リスト | listString |
| リスト | listBoolean |
| リスト | listInteger |
| リスト | listDecimal |
| リスト | listDuration |
| リスト | listDateTime |
| リスト | listDateTimeOnly |

## 署名と戻り値の型

`distinctWithNull(<listInteger>)`

整数のリストを返します。

`distinctWithNull(<listDecimal>)`

小数のリストを返します。

`distinctWithNull(<listString>)`

文字列のリストを返します。

`distinctWithNull(<listDateTimeOnly>)`

タイムゾーンを考慮せずに日付のリストを返します。

`distinctWithNull(<listDateTime>)`

日付時間のリストを返します。

`distinctWithNull(<listBoolean>)`

ブール値のリストを返します。

`distinctWithNull(<listDuration>)`

期間のリストを返します。

## 例

`distinctWithNull([10,2,10,null])`

[10, 2, null]を返します
