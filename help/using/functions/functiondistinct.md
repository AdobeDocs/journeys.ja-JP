---
product: adobe campaign
title: distinct
description: distinct 関数について説明します
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 034e4d77-2f0e-4117-9fd4-b9e35ef71a39
source-git-commit: 052ecdeb0813dcc2c4c870e8ec6b12676fbf60f1
workflow-type: tm+mt
source-wordcount: '151'
ht-degree: 44%

---

# distinct {#distinct}

指定されたリストのユニーク値またはオブジェクトを返します。 Null エントリは無視されます。

## カテゴリ

リスト

## 関数の構文

`distinct(<parameters>)`

## パラメーター

| パラメーター | タイプ | 説明 |
|-----------|------------------|------------------|
| listToProcess | listString、listBoolean、listInteger、listDecimal、listDuration、listDateTime、listDateTimeOnly、listDateOnly、listObject のいずれか | 処理するリスト。 listObject の場合は、フィールド参照である必要があります。 |
| keyAttributeName | 文字列 | このパラメーターはオプションで、 listObject に対してのみ使用できます。 パラメーターを指定しない場合、すべての属性の値が同じ場合、オブジェクトは重複していると見なされます。 それ以外の場合、指定された属性が同じ値を持つ場合、オブジェクトは重複していると見なされます。 |

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
