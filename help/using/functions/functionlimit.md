---
product: adobe campaign
title: limit
description: 関数 limit について説明します
feature: Journeys
role: Developer
level: Experienced
exl-id: 7e006660-1206-4b8a-9e5b-c6fbeee9cc8f
product_v2:
  - id: cf67d108-ecf9-4fde-af49-3a3c39083bc8
    internal-label: Journey Orchestration
feature_v2:
  - id: 7de3230f-9523-5ba5-8d5c-2313288b27ef
    internal-label: Journeys
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: 255cd6677e7c9ebff63ea9a1028a042c19e63ecc
workflow-type: tm+mt
source-wordcount: '135'
ht-degree: 100%
---
# limit {#limit}

リストの先頭または末尾の N 個の要素を返します。

## カテゴリ

リスト

## 関数の構文

`limit(<parameters>)`

## パラメーター

| パラメーター | タイプ | 説明 |
|-----------|------------------|------------------|
| listToProcess | listString、listBoolean、listInteger、listDecimal、listDuration、listDateTime、listDateTimeOnly、listDateOnly、listObject のいずれか | 並べ替えるリスト。 listObject の場合は、フィールド参照にする必要があります。 |
| numberOfItems | 整数 | 指定されたリストから返される項目の数。 |
| firstOrLastItems | ブール値 | このパラメーターはオプションです（デフォルトは true）。 true の場合は、先頭の項目を返します。 false の場合は、末尾の項目を返します。 |

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
