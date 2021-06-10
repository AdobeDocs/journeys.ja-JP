---
product: adobe campaign
title: コレクション管理関数
description: コレクション管理関数のデータ型について説明します
feature: ジャーニー
role: Data Engineer
level: Experienced
exl-id: e80b04fe-b2d3-4c1b-ba22-7e37a9ad1d57
source-git-commit: e0bf1a6f9c160b72da28feaca1ca52665f365630
workflow-type: tm+mt
source-wordcount: '602'
ht-degree: 2%

---

# コレクション管理関数 {#collection-management-functions}

また、式言語では、クエリコレクションに対する一連の関数を導入します。

以下に、これらの機能について説明します。 次の例では、コレクションを含むイベントペイロードを使用します。

```
                { 
   "_experience":{ 
      "campaign":{ 
         "message":{ 
            "profile":{ 
               "pushNotificationTokens":[ 
                  { 
                     "token":"token_1",
                     "application":{ 
                        "_id":"APP1",
                        "name":"MarltonMobileApp",
                        "version":"1.0"
                     }
                  },
                  { 
                     "token":"token_2",
                     "application":{ 
                        "_id":"APP2",
                        "name":"MarketplaceApp",
                        "version":"1.0"
                     }
                  },
                  { 
                     "token":"token_3",
                     "application":{ 
                        "_id":"APP3",
                        "name":"VendorApp",
                        "version":"2.0"
                     }
                  }
               ]
            }
         }
      }
   },
   "timestamp":"1536160728"
}
```

**関数「all(`<condition>`)」**

**[!UICONTROL all]**&#x200B;関数は、ブール式を使用して、特定のコレクションに対するフィルターを定義できます。

```
<listExpression>.all(<condition>)
```

例えば、すべてのアプリユーザーの中で、IOS 13を使用するユーザーを取得できます(ブール式「app used == IOS 13」)。 この関数の結果は、ブール式に一致する項目を含むフィルターされたリストになります(例：アプリユーザー1、アプリユーザー34、アプリユーザー432)。

データソース条件アクティビティで、**[!UICONTROL all]**&#x200B;関数の結果がnullかどうかを確認できます。 また、この&#x200B;**[!UICONTROL all]**&#x200B;関数を&#x200B;**[!UICONTROL count]**&#x200B;などの他の関数と組み合わせることもできます。 詳しくは、[データソース条件アクティビティ](../building-journeys/condition-activity.md#data_source_condition)を参照してください。

**例 1:**

ユーザーが特定のバージョンのアプリケーションをインストールしているかどうかを確認します。 この場合、バージョンが1.0のモバイルアプリケーションに関連付けられているすべてのプッシュ通知トークンを取得します。次に、**[!UICONTROL count]**&#x200B;関数を使用して条件を実行し、返されたトークンのリストに少なくとも1つの要素が含まれていることを確認します。

```
count(@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.all(currentEventField.application.version == "1.0").token}) > 0
```

結果はtrueです。

**例 2:**

ここでは、**[!UICONTROL count]**&#x200B;関数を使用して、コレクションにプッシュ通知トークンがあるかどうかを確認します。

```
count(@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.all().token}) > 0
```

結果はtrueになります。

<!--Alternatively, you can check if there is no token in the collection:

   ```
   count(@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.all().token}) == 0
   ```

The result will be false.

Here we use the count function in a condition to count the number of push notification tokens in the event.

`count(@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.all().token})`

The result is true.

Note that when the condition in the **all()** function is empty, the filter will return all the elements in the list. Hence, the expression above is equivalent to:

`count(@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.application.name})`

In both cases, the result of the expression is **3**.

A query of experience events recorded on the Adobe Experience Platform may or may not include the current event that triggered the current Journey. This will depend on the relative processing time with which [!DNL Journey Orchestration] sees an event and started evaluating conditions, versus the time it takes for that event to be ingested into the Adobe Experience Platform. For example, when using the .all() syntax to query experience events from the Adobe Experience Platform, we recommend enforcing the exclusion of the current event (by requiring an
earlier timestamp) in order to only consider prior events.-->

>[!NOTE]
>
>**all()**&#x200B;関数のフィルター条件が空の場合、フィルターはリスト内のすべての要素を返します。 **ただし、コレクションの要素数をカウントするためにall関数は必要ありません。**


```
count(@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.token})
```

式の結果は&#x200B;**3**&#x200B;です。

**例 3:**

ここでは、過去24時間以内に連絡を受け取っていないかどうかを確認します。 ExperiencePlatformデータソースから取得したエクスペリエンスイベントのコレクションを、コレクションの2つの要素に基づく2つの式を使用してフィルタリングします。 特に、イベントのタイムスタンプは、 **[!UICONTROL nowWithDelta]**&#x200B;関数が返すdateTimeと比較されます。

```
count(#{ExperiencePlatform.MarltonExperience.experienceevent.all(
   currentDataPackField.directMarketing.sends.value > 0 and
   currentDataPackField.timestamp > nowWithDelta(-1, "days")).timestamp}) == 0
```

2つの条件に一致するエクスペリエンスイベントがない場合、結果はtrueになります。

**例 4:**

ここでは、例えば、チュートリアルを開始するよう招待されたプッシュ通知をトリガーするために、個人が過去7日間に少なくとも1回アプリケーションを起動したかどうかを確認します。

```
count(
 #{ExperiencePlatform.AnalyticsData.experienceevent.all(
 nowWithDelta(-7,"days") <= currentDataPackField.timestamp
 and currentDataPackField.application.firstLaunches.value > 0
)._id}) > 0
```

<!--**"All + Count" example 4:** here we use the count function in a boolean expression to see if there is push notification tokens in the collection.

`count(@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.all().application.name}) > 0`

The result will be:

`true`

Alternatively, you can check if there is NO token in the collection:

`count(@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.all().application.name}) =0`

The result will be:

`false`-->

>[!NOTE]
>
>**** currentEventFieldsは、イベントコレクションとcurrentDataPackFieldを操作する場合にのみ使用 **できます**
>データソースコレクションを操作する場合 **[!UICONTROL all]**、**[!UICONTROL first]**、**[!UICONTROL last]**でコレクションを処理する場合、
>コレクションの各要素を1つずつループします。 **** currentEventFieldおよび **currentDataPackField**
>は、ループする要素に対応します。

**関数「first(`<condition>`)」と「last(`<condition>`)」**

また、**[!UICONTROL first]**&#x200B;関数と&#x200B;**[!UICONTROL last]**&#x200B;関数を使用して、フィルターを満たすリストの最初と最後の要素を返しながら、コレクションのフィルターを定義できます。

_`<listExpression>.first(<condition>)`_

_`<listExpression>.last(<condition>)`_

**例 1:**

この式は、バージョンが1.0のモバイルアプリケーションに関連付けられた最初のプッシュ通知トークンを返します。

```
@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.first(currentEventField.application.version == "1.0").token
```

結果は「token_1」になります。

**例 2:**

この式は、バージョンが1.0のモバイルアプリケーションに関連付けられた最後のプッシュ通知トークンを返します。

```
@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.last&#8203;(currentEventField.application.version == "1.0").token}
```

結果は「token_2」になります。

>[!NOTE]
>
>エクスペリエンスイベントは、時系列の逆順にコレクションとしてAdobe Experience Platformから取得されます。したがって、次のようになります。
>* **** firstfunctionは最新のイベントを返します
>* **** lastfunctionは最も古い関数を返します。


**例 3:**

DMA IDのゼロ以外の値を持つ最初の（最新の）Adobe Analyticsイベントの値が602に等しい値かどうかを確認します。

```
#{ExperiencePlatform.AnalyticsProd_EvarsProps.experienceevent.first(
currentDataPackField.placeContext.geo.dmaID > 0).placeContext.geo.dmaID} == 602
```

**関数「at(`<index>`)」**

**[!UICONTROL at]**関数を使用すると、インデックスに従ってコレクション内の特定の要素を参照できます。
インデックス0は、コレクションの最初のインデックスです。

_`<listExpression>`.at(`<index>`)_

**例：**

この式は、リストの2番目のプッシュ通知トークンを返します。

```
@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.at(1).token}
```

結果は「token_2」になります。

**その他の例**

```
#{ExperiencePlatform.ExperienceEventFieldGroup.experienceevent. all(currentDataPackField._aepgdcdevenablement2.purchase_event.receipt_nbr == "10-337-4016"). 
_aepgdcdevenablement2.purchase_event.productListItems. all(currentDataPackField.SKU == "AB17 1234 1775 19DT B4DR 8HDK 762").name}
```

```
 #{ExperiencePlatform.ExperienceEventFieldGroup.experienceevent.last(
currentDataPackField.eventType == "commerce.productListAdds").productListItems.last(currentDataPackField.priceTotal >= 150).name}
```
