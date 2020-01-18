---
title: 収集管理機能
description: コレクション管理機能のデータ型について説明します
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 017d502e21605b3e0b8c61e5fea0b4f6a65d4470

---


# 収集管理機能 {#collection-management-functions}

また、式の言語には、コレクションに対してクエリーを実行するための関数のセットが含まれています。

以下に、これらの関数について説明します。 次の例では、コレクションを含むイベントペイロードを使用します。

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

この関 **[!UICONTROL all]**数は、ブール式を使用して、特定のコレクションに対するフィルターを定義できるようにします。

```
<listExpression>.all(<condition>)
```

例えば、すべてのアプリユーザーの中で、IOS 13を使用するアプリを取得できます（boolean式「app used == IOS 13」）。 この関数の結果は、ブール式に一致する項目を含むフィルターされたリストになります(例：アプリユーザー1、アプリユーザー34、アプリユーザー432)。

Data Source Conditionアクティビティでは、関数の結果がnullかどうか **[!UICONTROL all]**を確認できます。 また、この関数を、などの他**[!UICONTROL all]** の関数と組み合わせることもできま **[!UICONTROL count]**す。 詳しくは、「データソース条件」ア[クティビティを参照してくださ](../building-journeys/condition-activity.md#data_source_condition)い。

**例 1：**

ユーザーが特定のバージョンのアプリケーションをインストールしているかどうかを確認します。 この場合、バージョンが1.0のモバイルアプリケーションに関連付けられたすべてのプッシュ通知トークンが取得されます。次に、関数で条件を実行し、返され **[!UICONTROL count]**たトークンのリストに少なくとも1つの要素が含まれていることを確認します。

```
count(@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.all(currentEventField.application.version == "1.0").token}) > 0
```

結果はtrueです。

**例2:**

ここでは、この関数を使 **[!UICONTROL count]**用して、コレクションにプッシュ通知トークンが存在するかどうかを確認します。

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

A query of experience events recorded on the platform may or may not include the current event that triggered the current Journey. This will depend on the relative processing time with which Journey Orchestration sees an event and started evaluating conditions, versus the time it takes for that event to be ingested into the platform. For example, when using the .all() syntax to query experience events from the platform, we recommend enforcing the exclusion of the current event (by requiring an
earlier timestamp) in order to only consider prior events.-->

>[!NOTE]
>
>all()関数のフィルター条件 **が空の場合** 、フィルターはリスト内のすべての要素を返します。 **ただし、コレクションの要素数をカウントするために、all関数は必要ありません。**


```
count(@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.token})
```

式の結果は **3です**。

**例3:**

ここでは、個人が過去24時間以内に通信を受け取っていないかどうかを確認します。 ExperiencePlatformデータソースから取得したエクスペリエンスイベントのコレクションを、コレクションの2つの要素に基づく2つの式を使用してフィルタリングします。 特に、イベントのタイムスタンプは、関数から返されるdateTimeと比較され **[!UICONTROL nowWithDelta]**ます。

```
count(#{ExperiencePlatform.MarltonExperience.experienceevent.all(
   currentDataPackField.directMarketing.sends.value > 0 and
   currentDataPackField.timestamp > nowWithDelta(-1, "days")).timestamp}) == 0
```

2つの条件に一致するエクスペリエンスイベントがない場合、結果はtrueになります。

**例4:**

ここでは、個人が過去7日間に少なくとも1回アプリケーションを起動したかどうかを確認します。例えば、チュートリアルを開始するよう招待するプッシュ通知をトリガーするためです。

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
>**[!UICONTROL currentEventField]**は、イベントコレクションとcurrentDataPackFieldを操作する場合にのみ使用で**&#x200B;きます&#x200B;**>データソースコレクションを操作する場合。 とを使用してコレクションを処**[!UICONTROL all]**&#x200B;理する **[!UICONTROL first]**場合、**[!UICONTROL last]**次の手順に従います。
>コレクションの各要素を1つずつループします。 **[!UICONTROL currentEventField]**および** currentDataPackField **>は、ループされる要素に対応します。

**関数「first(`<condition>`)」と「last(`<condition>`)」**

また、 **[!UICONTROL first]**関数**[!UICONTROL last]** と関数を使用すると、コレクションに対するフィルターの定義を有効にし、フィルターに一致するリストの最初または最後の要素を返すこともできます。

_`<listExpression>.first(<condition>)`_

_`<listExpression>.last(<condition>)`_

**例 1：**

この式は、バージョンが1.0のモバイルアプリケーションに関連付けられている最初のプッシュ通知トークンを返します。

```
@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.first(currentEventField.application.version == "1.0").token
```

結果は「token_1」です。

**例2:**

この式は、バージョンが1.0のモバイルアプリケーションに関連付けられている最後のプッシュ通知トークンを返します。

```
@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.last&#8203;(currentEventField.application.version == "1.0").token}
```

結果は「token_2」です。

>[!NOTE]
>
>エクスペリエンスイベントは、時系列の逆順にコレクションとしてエクスペリエンスプラットフォームから取得されます。
>* **[!UICONTROL first]**関数は最新のイベントを返します。
>* **[!UICONTROL last]**関数は最も古い関数を返す。


**例3:**

DMA IDにゼロ以外の値を持つ最初の（最新の）Adobe Analyticsイベントの値が602かどうかを確認します。

```
#{ExperiencePlatform.AnalyticsProd_EvarsProps.experienceevent.first(
currentDataPackField.placeContext.geo.dmaID > 0).placeContext.geo.dmaID} == 602
```

**関数「at(`<index>`)」**

この関 **[!UICONTROL at]**数を使用すると、インデックスに従ってコレクション内の特定の要素を参照できます。
インデックス0は、コレクションの最初のインデックスです。

_`<listExpression>`.at(`<index>`)_

**例：**

この式は、リストの2番目のプッシュ通知トークンを返します。

```
@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.at(1).token}
```

結果は「token_2」です。