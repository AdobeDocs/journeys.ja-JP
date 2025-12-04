---
product: adobe campaign
title: distinct
description: distinct 関数について説明します
feature: Journeys
role: Developer
level: Experienced
exl-id: 034e4d77-2f0e-4117-9fd4-b9e35ef71a39
source-git-commit: d3de66b9b28efa2636f5c0fd5a0d7ccb6132dbdd
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# distinct {#distinct}

指定されたリストのユニークな値またはオブジェクトを返します。null エントリは無視されます。

## カテゴリ

リスト

## 関数の構文

`distinct(<parameters>)`

## パラメーター

| パラメーター | タイプ | 説明 |
|-----------|------------------|------------------|
| listToProcess | lilistString、listBoolean、listInteger、listDecimal、listDuration、listDateTime、listDateTimeOnly、listDateOnly、listObject のいずれか | 処理するリスト。listObject の場合は、フィールド参照にする必要があります。 |
| keyAttributeName | 文字列 | このパラメーターはオプションで、listObject に対してのみ使用できます。パラメーターを指定しないと、すべての属性の値が同じ場合、オブジェクトは重複していると見なされます。パラメーターを指定していて、指定された属性が同じ値を持つ場合、オブジェクトは重複していると見なされます。 |

## シグネチャと戻り値のタイプ

`distinct(<listInteger>)`

整数のリストを返します。

`distinct(<listDecimal>)`

小数のリストを返します。

`distinct(<listString>)`

文字列のリストを返します。

`distinct(<listDateTimeOnly>)`

タイムゾーンを考慮しない日時のリストを返します。

`distinct(<listDateTime>)`

日時のリストを返します。

`distinct(<listDateOnly>)`

日付のリストを返します。

`distinct(<listBoolean>)`

ブール値のリストを返します。

`distinct(<listDuration>)`

期間のリストを返します。

`distinct(<listObject>)`

`distinct(<listObject>,<string>)`

オブジェクトのリストを返します。


## 例

`distinct([10,2,10,null])`

`[10, 2]` を返します。
