---
product: adobe campaign
solution: Journey Orchestration
title: カスタムアクションを使用したコレクションの動的な受け渡し
description: Campaign v7 または v8 を使用したメッセージの送信
exl-id: 9ed62a74-3c51-4f15-af8a-d530ddf80b51
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '473'
ht-degree: 90%

---

# カスタムアクションを使用したコレクションの動的な受け渡し{#passing-collection}


>[!CAUTION]
>
>**Adobe Journey Optimizerをお探しですか** Journey Optimizerのドキュメントについては、[ こちら ](https://experienceleague.adobe.com/ja/docs/journey-optimizer/using/ajo-home){target="_blank"} をクリックしてください。
>
>
>_このドキュメントでは、Journey Optimizerに置き換えられた従来のJourney Orchestration マテリアルについて説明します。 Journey OrchestrationやJourney Optimizerへのアクセスに関するご質問は、アカウントチームにお問い合わせください。_


実行時に値が動的に設定されるカスタムアクションパラメーターにコレクションを渡すことができます。次の 2 種類のコレクションがサポートされています。

* 単純なコレクション：単純なデータタイプを要素とする配列。以下に listString の例を示します。

  ```
  {
   "deviceTypes": [
       "android",
       "ios"
   ]
  }
  ```

* オブジェクトコレクション：JSON オブジェクトの配列。以下に例を示します。

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

* オブジェクト配列内にオブジェクトの配列がネストされたコレクションは、現時点ではサポートされていません。以下に例を示します。

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

* テストモードを使用してコレクションをテストするには、コードビューモードを使用する必要があります。ビジネスイベントに対しては、現時点ではコードビューモードはサポートされていません。コレクションは、単一の要素でのみ送信できます。

## 一般的な手順 {#general-procedure}

この節では、次のサンプル JSON ペイロードを使用します。これは、単純なコレクションのフィールドを持つオブジェクトの配列です。

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

「products」は 2 つのオブジェクトの配列であることがわかります。少なくとも 1 つのオブジェクトが必要です。

1. カスタムアクションを作成します。[このページ](../action/about-custom-action-configuration.md)を参照してください。

1. 「**[!UICONTROL アクションパラメーター]**」セクションに、JSON の例を貼り付けます。表示される構造は静的です。ペイロードを貼り付けたときに、すべてのフィールドが定数として定義されます。

   ![](../assets/uc-collection-1.png)

1. 必要に応じて、フィールドタイプを調整します。コレクションでは、listString、listInteger、listDecimal、listBoolean、listDateTime、listDateTimeOnly、listDateOnly、listObject の各フィールドタイプがサポートされています。

   >[!NOTE]
   >
   >フィールドタイプは、ペイロードの例に従って自動的に推測されます。

1. オブジェクトを動的に渡す場合は、変数として設定する必要があります。この例では、「products」を変数として設定します。オブジェクトに含まれているすべてのオブジェクトフィールドは、変数に自動的に設定されます。

   >[!NOTE]
   >
   >サンプルペイロードの最初のオブジェクトは、フィールドの定義に使用されます。

1. フィールドごとに、ジャーニーキャンバスに表示されるラベルを定義します。

   ![](../assets/uc-collection-2.png)

1. ジャーニーを作成し、作成したカスタムアクションを追加します。[このページ](../building-journeys/using-custom-actions.md)を参照してください。

1. 「**[!UICONTROL アクションパラメーター]**」セクションで、高度な式エディターを使用して配列パラメーター（この例では「products」）を定義します。

   ![](../assets/uc-collection-3.png)

1. 次のオブジェクトフィールドごとに、ソース XDM スキーマ内の対応するフィールド名を入力します。名前が同じ場合は、この操作は不要です。この例では、「product id」と「color」のみを定義する必要があります。

   ![](../assets/uc-collection-4.png)

配列フィールドの場合は、高度な式エディターを使用してデータ操作を実行することもできます。次の例では、[filter](../functions/functionfilter.md) 関数と [intersect](../functions/functionintersect.md) 関数を使用しています。

![](../assets/uc-collection-5.png)

## 特殊な例{#examples}

異種混在タイプと配列の配列の場合、配列は listAny タイプで定義されます。個々の項目のみをマッピングできますが、配列を変数に変更することはできません。

![](../assets/uc-collection-heterogeneous.png)

異種混在タイプの例：

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

配列の配列の例：

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
