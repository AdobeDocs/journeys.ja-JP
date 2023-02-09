---
product: adobe campaign
title: distinctWithNull
description: distinctWithNull 関数について説明します
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 65a904c1-14ff-42b3-8f03-abb97ef47625
source-git-commit: 052ecdeb0813dcc2c4c870e8ec6b12676fbf60f1
workflow-type: tm+mt
source-wordcount: '167'
ht-degree: 100%

---

# distinctWithNull {#distinctWithNull}

指定されたリストのユニークな値またはオブジェクトを返します。リストに null エントリが少なくとも 1 つ含まれる場合、返されるリストに null エントリが含まれます。

## カテゴリ

リスト

## 関数の構文

`distinctWithNull(<parameters>)`

## パラメーター

| パラメーター | タイプ | 説明 |
|-----------|------------------|------------------|
| listToProcess | listString、listBoolean、listInteger、listDecimal、listDuration、listDateTime、listDateTimeOnly、listDateOnly、listObject のいずれか | 処理するリスト。listObject の場合は、フィールド参照にする必要があります。 |
| keyAttributeName | 文字列 | このパラメーターはオプションで、listObject に対してのみ使用できます。パラメーターを指定しないと、すべての属性の値が同じ場合、オブジェクトは重複していると見なされます。パラメーターを指定していて、指定された属性が同じ値を持つ場合、オブジェクトは重複していると見なされます。 |

## シグネチャと戻り値のタイプ

`distinctWithNull(<listInteger>)`

整数のリストを返します。

`distinctWithNull(<listDecimal>)`

小数のリストを返します。

`distinctWithNull(<listString>)`

文字列のリストを返します。

`distinctWithNull(<listDateTimeOnly>)`

タイムゾーンを考慮しない日時のリストを返します。

`distinctWithNull(<listDateTime>)`

日時のリストを返します。

`distinctWithNull(<listDateOnly>)`

日付のリストを返します。

`distinctWithNull(<listBoolean>)`

ブール値のリストを返します。

`distinctWithNull(<listDuration>)`

期間のリストを返します。

`distinctWithNull(<listObject>)`

`distinctWithNull(<listObject>,<string>)`

オブジェクトのリストを返します。

## 例

`distinctWithNull([10,2,10,null])`

[10, 2, null] を返します。
