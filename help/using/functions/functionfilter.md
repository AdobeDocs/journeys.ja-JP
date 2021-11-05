---
product: adobe campaign
title: フィルター
description: 関数フィルターの詳細
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 19a4b7f8-5636-4b8f-b81f-28ff7da99671
source-git-commit: 5225045f02fb1b2a8505756d9d7f6f60a32b3ed6
workflow-type: tm+mt
source-wordcount: '109'
ht-degree: 10%

---

# フィルター{#filter}

指定されたキー値の 1 つに一致する key 属性を持つオブジェクトを持つ listObject を返します。

## カテゴリ

リスト

## 関数の構文

`filter(<parameters>)`

## パラメーター

| パラメーター | タイプ | 説明 |
|-----------|------------------|------------------|
| listToFilter | listObject | フィルタ処理するオブジェクトのリスト。 フィールド参照にする必要があります。 |
| keyAttributeName | 文字列 | 指定されたリストのオブジェクト内の属性名。フィルタリングのキーとして使用されます |
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

listObject を返します。

## 例

次に、受信イベント「myevent」で渡されるペイロードの例を示します。

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

「product2」と「product3」を id として持つ 2 つのオブジェクトを含む listObject を返します。
