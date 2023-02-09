---
product: adobe campaign
title: filter
description: filter 関数について説明します
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 3c1c188c-0ffd-44c5-b1b3-1758ed12235e
source-git-commit: a9a129b1949d64c4a412d3ea4002b32e3563ea96
workflow-type: tm+mt
source-wordcount: '109'
ht-degree: 100%

---

# filter{#filter}

指定されたキー値の 1 つに一致するキー属性を持つオブジェクトで構成される listObject（オブジェクトリスト）を返します。

## カテゴリ

リスト

## 関数の構文

`filter(<parameters>)`

## パラメーター

| パラメーター | タイプ | 説明 |
|-----------|------------------|------------------|
| listToFilter | listObject（オブジェクトリスト） | フィルタリングの対象となるオブジェクトリスト。 フィールド参照にする必要があります。 |
| keyAttributeName | 文字列 | 指定されたリストのオブジェクト内の属性名。フィルタリングのキーとして使用されます |
| keyValueList | リスト | フィルタリングに使用するキー値の配列 |

## シグネチャと戻り値のタイプ

`filter(listObject, string, listString)`

`filter(listObject, string, listInteger)`

`filter(listObject, string, listDecimal)`

`filter(listObject, string, listDateTime)`

`filter(listObject, string, listDateTimeOnly)`

`filter(listObject, string, listDateOnly)`

`filter(listObject, string, listDuration)`

`filter(listObject, string, listBoolean)`

listObject を返します。

## 例

受信イベント「myevent」で渡されるペイロードの例を次に示します。

```json
"productListItems": [{
   "id": "product1",
   "name": "the product 1",
   "price": 20
},{
   "id": "product2",
   "name": "the product 2",
   "price": 30
},{
   "id": "product3",
   "name": "the product 3",
   "price": 50
}]
```

次の式を使用できます。

```json
filter(
 @{myevent.productListItems},
 "id", 
 ["product2", "product3", "product4"]
)
```

「product2」と「product3」を id とする 2 つのオブジェクトから成る listObject を返します。
