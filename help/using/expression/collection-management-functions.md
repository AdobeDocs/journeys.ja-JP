---
title: コレクション管理関数
description: 収集管理機能のデータ型について説明します。
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
source-git-commit: eb4474313d3c0470448f9959ed757902ef0ecd2a
workflow-type: tm+mt
source-wordcount: '599'
ht-degree: 1%

---


# コレクション管理関数 {#collection-management-functions}

また、式言語では、クエリコレクションに一連の関数が導入されます。

これらの機能については、以下に説明します。 次の例では、コレクションを含むイベントペイロードを使用します。

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

**関数&quot;all(`<condition>`)&quot;**

**[!UICONTROL all]** 関数は、ブール式を使用して、特定のコレクションに対するフィルターを定義できます。

```
<listExpression>.all(<condition>)
```

例えば、すべてのアプリユーザーの中で、IOS 13を使用するユーザーを取得できます(ブール式「app used == IOS 13」)。 この関数の結果は、ブール値の式に一致する項目を含むフィルターされたリストになります(例： アプリユーザー1、アプリユーザー34、アプリユーザー432)。

Data Source Conditionアクティビティでは、 **[!UICONTROL all]** 関数の結果がnullか否かをチェックできます。 また、この **[!UICONTROL すべての関数を、]** countなどの他の関数と組み合わせることもできます ****。 詳しくは、 [データソース条件のアクティビティを参照してください](../building-journeys/condition-activity.md#data_source_condition)。

**例 1:**

ユーザーが特定のバージョンのアプリケーションをインストールしたかどうかを確認します。 この場合、バージョンが1.0のモバイルアプリケーションに関連付けられたすべてのプッシュ通知トークンを取得します。次に、 **[!UICONTROL count]** 関数を使用して条件を実行し、返されたトークンリストに少なくとも1つの要素が含まれているかどうかを確認します。

```
count(@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.all(currentEventField.application.version == "1.0").token}) > 0
```

結果はtrueです。

**例 2:**

ここでは、 **[!UICONTROL count]** 関数を使用して、コレクションにプッシュ通知トークンが存在するかどうかを確認します。

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
>all()関数のフィルタリング条件が空の場合、 **** フィルタはリスト内のすべての要素を返します。 **ただし、コレクションの要素数をカウントする場合は、all関数は不要です。**


```
count(@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.token})
```

式の結果は **3です**。

**例3:**

ここでは、個人が過去24時間以内に連絡を受けていないかどうかを調べます。 ExperiencePlatformデータソースから取得したエクスペリエンスイベントのコレクションをフィルターし、コレクションの2つの式に基づく2つの要素を使用します。 特に、イベントのタイムスタンプは、 **[!UICONTROL nowWithDelta関数が返すdateTimeと比較され]** ます。

```
count(#{ExperiencePlatform.MarltonExperience.experienceevent.all(
   currentDataPackField.directMarketing.sends.value > 0 and
   currentDataPackField.timestamp > nowWithDelta(-1, "days")).timestamp}) == 0
```

2つの条件に一致するエクスペリエンスイベントがない場合、結果はtrueになります。

**例4:**

ここでは、個人が過去7日間に少なくとも1回アプリケーションを起動したかどうかを確認します。例えば、チュートリアルを開始するように勧めるプッシュ通知をトリガーするためです。

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
>**[!UICONTROL currentEventField]** は、イベントコレクションとcurrentDataPackFieldを操作する場合にのみ使用で **きます**
>データソースコレクションを操作する場合。 コレクションをす **[!UICONTROL べて]**、 **[!UICONTROL 最初と]** 最後 **[!UICONTROL 、]**すべてで処理する場合、
>コレクションの各要素を1つずつループします。 **[!UICONTROL currentEventField]** と **currentDataPackField**
>は、ループされる要素に対応します。

**関数&quot;first(`<condition>`)&quot;と&quot;last(`<condition>`)&quot;**

また、 **[!UICONTROL first]** 関数と **** last関数を使用すると、コレクションのフィルターを定義できます。このとき、フィルターを満たすリストの最初と最後の要素を返します。

_`<listExpression>.first(<condition>)`_

_`<listExpression>.last(<condition>)`_

**例 1:**

この式は、バージョン1.0のモバイルアプリケーションに関連付けられている最初のプッシュ通知トークンを返します。

```
@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.first(currentEventField.application.version == "1.0").token
```

結果は「token_1」になります。

**例 2:**

この式は、バージョン1.0のモバイルアプリケーションに関連付けられている最後のプッシュ通知トークンを返します。

```
@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.last&#8203;(currentEventField.application.version == "1.0").token}
```

結果は「token_2」です。

>[!NOTE]
>
>エクスペリエンスイベントは、暦の逆順にコレクションとしてAdobe Experience Platformから取得されます。したがって、次のようになります。
>* **[!UICONTROL first]** 関数は最新イベントを返します
>* **[!UICONTROL last]** 関数は、最も古い関数を返します。


**例3:**

DMA IDにゼロ以外の値を持つ最初の（最新の）Adobe Analyticsイベントの値が602に等しいかどうかを調べます。

```
#{ExperiencePlatform.AnalyticsProd_EvarsProps.experienceevent.first(
currentDataPackField.placeContext.geo.dmaID > 0).placeContext.geo.dmaID} == 602
```

**関数「at(`<index>`)」**

at **[!UICONTROL 関数を使用すると]** 、インデックスに従ってコレクション内の特定の要素を参照できます。
インデックス0は、コレクションの最初のインデックスです。

_`<listExpression>`.at(`<index>`)_

**例：**

この式は、リストの2番目のプッシュ通知トークンを返します。

```
@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.at(1).token}
```

結果は「token_2」です。