---
product: adobe campaign
title: filter
description: 関数名の詳細
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 19a4b7f8-5636-4b8f-b81f-28ff7da99671
source-git-commit: 729ee71e063ae73c7c10f20bb3a410c43cb75faf
workflow-type: tm+mt
source-wordcount: '109'
ht-degree: 10%

---

# フィルター{#filter}

指定されたキー値の1つに一致するkey属性を持つオブジェクトを持つlistObjectを返します。

## カテゴリ

リスト

## 関数の構文

`filter(<parameters>)`

## パラメーター

| パラメーター | タイプ | 説明 |
|-----------|------------------|------------------|
| listToFilter | listObject | フィルタするオブジェクトのリスト。 フィールド参照にする必要があります。 |
| keyAttributeName | 文字列 | 特定のリストのオブジェクト内の属性名。フィルタリングのキーとして使用されます。 |
| keyValueList | list | フィルタリング用のキー値の配列 |

## 署名と戻り値の型

`filter(listObject, string, listString)`

`filter(listObject, string, listInteger)`

`filter(listObject, string, listDecimal)`

`filter(listObject, string, listDateTime)`

`filter(listObject, string, listDateTimeOnly)`

`filter(listObject, string, listDateOnly)`

`filter(listObject, string, listDuration)`

`filter(listObject, string, listBoolean)`

listObjectを返します。

## 例

次に、受信イベント「myevent」で渡されるペイロードの例を示します。

```
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

```
filter(
 @{myevent.productListItems},
 id", 
 ["product2", "product3", "product4"]
)
```

「product2」と「product3」をIDとして持つ2つのオブジェクトを含むlistObjectを返します。
