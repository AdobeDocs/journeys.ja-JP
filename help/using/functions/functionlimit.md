---
product: adobe campaign
title: 制限
description: 関数制限の詳細
feature: Journeys
role: Data Engineer
level: Experienced
source-git-commit: 052ecdeb0813dcc2c4c870e8ec6b12676fbf60f1
workflow-type: tm+mt
source-wordcount: '135'
ht-degree: 45%

---

# 制限 {#limit}

リストの最初または最後の N 個の要素を返します。

## カテゴリ

リスト

## 関数の構文

`limit(<parameters>)`

## パラメーター

| パラメーター | タイプ | 説明 |
|-----------|------------------|------------------|
| listToProcess | listString、listBoolean、listInteger、listDecimal、listDuration、listDateTime、listDateTimeOnly、listDateOnly、listObject のいずれか | 並べ替えるリスト。 listObject の場合は、フィールド参照である必要があります。 |
| numberOfItems | 整数 | 指定されたリストから返される項目の数。 |
| firstOrLastItems | ブール値 | このパラメーターはオプションです（デフォルトは true）。 true の場合は、最初の項目を返します。 false の場合、最後の項目を返します。 |

## シグネチャと戻り値のタイプ

`limit(<listString>,<integer>)`
`limit(<listString>,<integer>,<boolean>)`

文字列のリストを返します。

`limit(<listInteger>,<integer>)`
`limit(<listInteger>,<integer>,<boolean>)`

整数のリストを返します。

`limit(<listDecimal>,<integer>)`
`limit(<listDecimal>,<integer>,<boolean>)`

小数のリストを返します。

`limit(<listBoolean>,<integer>)`
`limit(<listBoolean>,<integer>,<boolean>)`

ブール値のリストを返します。

`limit(<listDateOnly>,<integer>)`
`limit(<listDateOnly>,<integer>,<boolean>)`

日付のリストを返します。

`limit(<listDateTimeOnly>,<integer>)`
`limit(<listDateTimeOnly>,<integer>,<boolean>)`

タイムゾーンを考慮しない日時のリストを返します。

`limit(<listDateTime>,integer>)`
`limit(<listDateTime>,<integer>,<boolean>)`

日時のリストを返します。

`limit(<listDuration>,<integer>)`
`limit(<listDuration>,<integer>,<boolean>)`

期間のリストを返します。

`limit(<listObject>,<integer>)`
`limit(<listObject>,<integer>,<boolean>)`

オブジェクトのリストを返します。

## 例

`limit(["A", "B", "C", "D", "E"], 3)`

`["A","B","C"]` を返します。

`limit(["A", "B", "C", "D", "E"], 3, false)`

`["C","D","E"]` を返します。
