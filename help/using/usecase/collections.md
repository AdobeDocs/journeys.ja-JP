---
product: adobe campaign
solution: Journey Orchestration
title: カスタムアクションを使用してコレクションを動的に渡す
description: Campaign v7／v8 を使用したメッセージの送信
exl-id: 8832d306-5842-4be5-9fb9-509050fcbb01
source-git-commit: 5fa7df4f2e778c0b0fd31d81edab34e86ee40c47
workflow-type: tm+mt
source-wordcount: '458'
ht-degree: 5%

---


# カスタムアクションを使用してコレクションを動的に渡す{#passing-collection}

実行時に動的に設定されるカスタムアクションパラメーターでコレクションを渡すことができます。 次の2種類のコレクションがサポートされています。

* 単純なコレクション：単純なデータ型の配列（例：listString）

   ```
   {
    "deviceTypes": [
        "android",
        "ios"
    ]
   }
   ```

* オブジェクトコレクション：JSONオブジェクトの配列。次に例を示します。

   ```
   {
   "products":[
      {
         "id":"productA",
         "name":"A",
         "price":20.1
      },
      {
         "id":"productB",
         "name":"B",
         "price":10.0
      },
      {
         "id":"productC",
         "name":"C",
         "price":5.99
      }
    ]
   }
   ```

## 制限事項 {#limitations}

* サブオブジェクトを含むオブジェクトの配列はサポートされていません。 以下に例を示します。

   ```
   {
   "products":[
     {
        "id":"productA",
        "name":"A",
        "details": {
        "color":"blue"
        },
        "price":20.0
     }
    ]
   }
   ```

* オブジェクト配列内のオブジェクトのネストされた配列は、現時点ではサポートされていません。 以下に例を示します。

   ```
   {
   "products":[
     {
        "id":"productA",
        "name":"A",
        "price":20,
        "locations": [{"name": "Paris"}, {"name": "London"}]
     },
    ]
   }
   ```
* テストモードを使用してコレクションをテストするには、コードビューモードを使用する必要があります。 現時点では、ビジネスイベントのコードビューモードはサポートされていません。 1つの要素でのみコレクションを送信できます。

## 一般的な手順 {#general-procedure}

この節では、次のJSONペイロードの例を使用します。 これは、単純なコレクションのフィールドを持つオブジェクトの配列です。

```
{
  "ctxt": {
    "products": [
      {
        "id": "productA",
        "name": "A",
        "price": 20.1,
        "color":"blue",
        "locations": [
          "Paris",
          "London"
        ]
      },
      {
        "id": "productB",
        "name": "B",
        "price": 10.99
      }
    ]
  }
}
```

「products」は2つのオブジェクトの配列であることがわかります。 少なくとも1つのオブジェクトが必要です。

1. カスタムアクションを作成します。 [このページ](../action/about-custom-action-configuration.md)を参照してください。

1. 「**[!UICONTROL アクションパラメーター]**」セクションに、JSONの例を貼り付けます。 表示される構造は静的です。ペイロードを貼り付ける際、すべてのフィールドは定数として定義されます。

   ![](../assets/uc-collection-1.png)

1. 必要に応じて、フィールドタイプを調整します。 コレクションでは、次のフィールドタイプがサポートされています。listString, listInteger, listDecimal, listBoolean, listDateTime, listDateTimeOnly, listDateOnly, listObject

   >[!NOTE]
   >
   >フィールドタイプは、ペイロードの例に従って自動的に推論されます。

1. オブジェクトを動的に渡す場合は、変数として設定する必要があります。 この例では、「products」を変数に設定します。 オブジェクトに含まれるすべてのオブジェクトフィールドは、変数に自動的に設定されます。

   >[!NOTE]
   >
   >ペイロード例の最初のオブジェクトを使用して、フィールドを定義します。

1. 各フィールドについて、ジャーニーキャンバスに表示するラベルを定義します。

   ![](../assets/uc-collection-2.png)

1. ジャーニーを作成し、作成したカスタムアクションを追加します。 [このページ](../building-journeys/using-custom-actions.md)を参照してください。

1. **[!UICONTROL アクションパラメーター]**&#x200B;セクションで、高度な式エディターを使用して配列パラメーター（この例では「products」）を定義します。

   ![](../assets/uc-collection-3.png)

1. 次の各オブジェクトフィールドに、ソースXDMスキーマの対応するフィールド名を入力します。 同じ名前の場合は、この操作は不要です。 この例では、「product id」と「color」を定義するだけで済みます。

   ![](../assets/uc-collection-4.png)

配列フィールドの場合は、高度な式エディターを使用してデータ操作を実行することもできます。 次の例では、[filter](https://git.corp.adobe.com/AdobeDocs/journeys.en/blob/fvi-21.9/help/using/functions/functionfilter.md)関数と[intersect](https://git.corp.adobe.com/AdobeDocs/journeys.en/blob/fvi-21.9/help/using/functions/functiontintersect.md)関数を使用します。

![](../assets/uc-collection-5.png)

## 特定の事例{#examples}

異種の型と配列の場合、配列はlistAny型で定義されます。 個々の項目のマッピングのみ可能で、配列を変数に変更することはできません。

![](../assets/uc-collection-heterogeneous.png)

異種タイプの例：

```
{
    "data_mixed-types": [
        "test",
        "test2",
        null,
        0
    ]
}
```

配列の例：

```
{
    "data_multiple-arrays": [
        [
            "test",
            "test1",
            "test2"
        ]
    ]
}
```

**関連トピック**

[カスタムアクションの使用](../building-journeys/using-custom-actions.md)