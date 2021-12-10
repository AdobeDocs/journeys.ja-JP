---
product: adobe campaign
title: コレクション管理関数
description: コレクション管理関数のデータタイプについて説明します
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: e80b04fe-b2d3-4c1b-ba22-7e37a9ad1d57
source-git-commit: 579e5a0dbdc11369248c2683c399b090130a7262
workflow-type: tm+mt
source-wordcount: '601'
ht-degree: 100%

---

# コレクション管理関数 {#collection-management-functions}

また、式言語にも、コレクションをクエリするための一連の関数が導入されています。

これらの関数について以下で説明します。 次の例では、コレクションを含んだイベントペイロードを使用します。

```json
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

この **[!UICONTROL all]** 関数では、ブール式を使用して指定のコレクションに対するフィルターを定義することができます。

```json
<listExpression>.all(<condition>)
```

例えば、すべてのアプリユーザーの中から、iOS 13 を使用しているユーザーを取得できます（ブール式「app used == IOS 13」）。この関数の結果は、ブール式に一致する項目（例：アプリユーザー 1、アプリユーザー 34、アプリユーザー 432）を含んだフィルター済みリストになります。

「データソースの条件」アクティビティでは、**[!UICONTROL all]** 関数の結果が null かどうかを確認できます。 また、この **[!UICONTROL all]** 関数を、**[!UICONTROL count]** 関数などの他の関数と組み合わせることができます。詳しくは、[「データソースの条件」アクティビティ](../building-journeys/condition-activity.md#data_source_condition)を参照してください。

**例 1：**

ユーザーが特定のバージョンのアプリケーションをインストールしてあるかどうかを確認します。 この目的のために、バージョンが 1.0 のモバイルアプリケーションに関連付けられたすべてのプッシュ通知トークンを取得します。その後、**[!UICONTROL count]** 関数で条件分けをして、返されたトークンリストに少なくとも 1 つの要素が含まれているかどうかを確認します。

```json
count(@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.all(currentEventField.application.version == "1.0").token}) > 0
```

結果は true です。

**例 2：**

ここでは、 **[!UICONTROL count]** 関数を使用して、コレクションにプッシュ通知トークンがあるかどうかを確認します。

```json
count(@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.all().token}) > 0
```

結果は true になります。

<!--Alternatively, you can check if there is no token in the collection:

   ```json
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
>**all()** 関数のフィルター条件に何も指定していない場合、フィルターはリスト内のすべての要素を返します。 **ただし、コレクションの要素数をカウントするためには、all 関数は不要です。**


```json
count(@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.token})
```

式の結果は **3** です。

**例 3：**

ここでは、個人が過去 24 時間以内に連絡を受け取っていないかどうかを確認します。 ExperiencePlatform データソースから取得したエクスペリエンスイベントのコレクションを、コレクションの 2 つの要素に基づく 2 つの式を使用してフィルタリングします。 特に、イベントのタイムスタンプを、**[!UICONTROL nowWithDelta]** 関数から返される日時と比較します。

```json
count(#{ExperiencePlatform.MarltonExperience.experienceevent.all(
   currentDataPackField.directMarketing.sends.value > 0 and
   currentDataPackField.timestamp > nowWithDelta(-1, "days")).timestamp}) == 0
```

2 つの条件に一致するエクスペリエンスイベントがない場合、結果は true になります。

**例 4：**

ここでは、個人が過去 7 日間に少なくとも 1 回アプリケーションを起動したかどうかを確認します。例えば、チュートリアルを開始するよう招待するプッシュ通知をトリガーするためです。

```json
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
>**[!UICONTROL currentEventField]** は、イベントコレクションの操作時にのみ使用でき、**currentDataPackField** は、
>データソースコレクションの操作時にのみ使用できます。**[!UICONTROL all]**、**[!UICONTROL first]** および **[!UICONTROL last]** を使用してコレクションを処理する場合は、
>コレクションの各要素を 1 つずつループ処理します。**[!UICONTROL currentEventField]** と **currentDataPackField** は、
>ループ処理する要素に対応します。

**関数「first(`<condition>`)」と「last(`<condition>`)」**

**[!UICONTROL first]** 関数と **[!UICONTROL last]** 関数では、コレクションのフィルターを定義できる一方、フィルター条件を満たすリストの最初または最後の要素を返すこともできます。

_`<listExpression>.first(<condition>)`_

_`<listExpression>.last(<condition>)`_

**例 1：**

この式は、バージョンが 1.0 のモバイルアプリケーションに関連付けられた最初のプッシュ通知トークンを返します。

```json
@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.first(currentEventField.application.version == "1.0").token
```

結果は「token_1」です。

**例 2：**

この式は、バージョンが 1.0 のモバイルアプリケーションに関連付けられた最後のプッシュ通知トークンを返します。

```json
@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.last&#8203;(currentEventField.application.version == "1.0").token}
```

結果は「token_2」です。

>[!NOTE]
>
>エクスペリエンスイベントは、Adobe Experience Platform からコレクションとして新しい順に取得されます。したがって、次のようになります。
>
>* **[!UICONTROL first]** 関数は、最新のイベントを返します。
>* **[!UICONTROL last]** 関数は、最も古いイベントを返します。


**例 3：**

DMA ID のゼロ以外の値を持つ最初（最新）の Adobe Analytics イベントの値が 602 に等しいかどうかを確認します。

```json
#{ExperiencePlatform.AnalyticsProd_EvarsProps.experienceevent.first(
currentDataPackField.placeContext.geo.dmaID > 0).placeContext.geo.dmaID} == 602
```

**関数「at(`<index>`)」**

**[!UICONTROL at]** 関数を使用すると、インデックスに従ってコレクション内の特定の要素を参照できます。
インデックス 0 はコレクションの最初のインデックスです。

_`<listExpression>`.at(`<index>`)_

**例：**

この式は、リストの 2 番目のプッシュ通知トークンを返します。

```json
@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.at(1).token}
```

結果は「token_2」です。

**その他の例**

```json
#{ExperiencePlatform.ExperienceEventFieldGroup.experienceevent. all(currentDataPackField._aepgdcdevenablement2.purchase_event.receipt_nbr == "10-337-4016"). 
_aepgdcdevenablement2.purchase_event.productListItems. all(currentDataPackField.SKU == "AB17 1234 1775 19DT B4DR 8HDK 762").name}
```

```json
 #{ExperiencePlatform.ExperienceEventFieldGroup.experienceevent.last(
currentDataPackField.eventType == "commerce.productListAdds").productListItems.last(currentDataPackField.priceTotal >= 150).name}
```
