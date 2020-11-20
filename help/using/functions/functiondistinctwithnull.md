---
product: adobe campaign
solution: Journey Orchestration
title: distinctWithNull
description: distinctWithNull関数について学習します
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '99'
ht-degree: 15%

---


# distinctWithNull {#distinctWithNull}

リストの明確な値を返します。 リストに少なくとも1つのnull値が含まれる場合、返されるリストーにnull値が格納されます。

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

タイムゾーンを考慮せずに、日付時刻のリストを返します。

`distinctWithNull(<listDateTime>)`

日付時間のリストを返します。

`distinctWithNull(<listBoolean>)`

ブール値のリストを返します。

`distinctWithNull(<listDuration>)`

期間のリストを返します。

## 例

`distinctWithNull([10,2,10,null])`

10、 [2、nullを返します]
