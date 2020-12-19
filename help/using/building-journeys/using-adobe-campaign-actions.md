---
product: adobe campaign
solution: Journey Orchestration
title: Adobe Campaign のアクションの使用
description: Adobe Campaignの操作について
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '937'
ht-degree: 6%

---


# Adobe Campaign のアクションの使用 {#using_campaign_action}

Adobe Campaign Standardをお持ちの場合は、次の既成のアクションアクティビティを使用できます。**[!UICONTROL 電子メール]**、**[!UICONTROL プッシュ]**、**[!UICONTROL SMS]**。

>[!NOTE]
>
>この場合、組み込みのアクションを設定する必要があります。 [このページ](../action/working-with-adobe-campaign.md)を参照してください。

これらの各チャネルに対して、Adobe Campaign Standardトランザクションメッセージ&#x200B;**テンプレート**&#x200B;を選択します。 実際、[!DNL Journey Orchestration]はメッセージ送信の解決策ではありません。 組み込み型の電子メール、SMS、プッシュチャネルの場合、メッセージ送信を実行するのにトランザクションメッセージを使用します。 つまり、ジャーニーで特定のメッセージテンプレートを使用する場合は、Adobe Campaign Standardで公開する必要があります。 この機能の使い方については、[このページ](https://docs.adobe.com/content/help/ja-JP/campaign-standard/using/communication-channels/transactional-messaging/about-transactional-messaging.html)を参照してください。

>[!NOTE]
>
>Journey Orchestrationで使用するには、Campaign Standardトランザクションメッセージとそれに関連するイベントを公開する必要があります。 イベントが公開されているが、メッセージが表示されていない場合は、Journey Orchestrationインターフェイスに表示されません。 メッセージが発行されても関連イベントが発行されない場合は、Journey Orchestrationインターフェイスに表示されますが、使用できません。

![](../assets/journey59.png)

イベント（リアルタイム）またはプロファイルトランザクションメッセージングテンプレートを使用できます。

>[!NOTE]
>
>リアルタイムトランザクションメッセージ(rtEvent)を送信する場合、またはカスタムアクションの影響でサードパーティ製システムと共にメッセージをルーティングする場合は、疲労管理、ブロックリスト管理、購読解除管理に特定の設定が必要です。 例えば、「unsubscribe」属性がAdobe Experience Platformまたはサードパーティのシステムに保存されている場合、この条件を確認するためにメッセージを送信する前に条件を追加する必要があります。

テンプレートを選択すると、アクティビティのペイロードに必要なすべてのフィールドが、メッセージの設定ウィンドウの&#x200B;**[!UICONTROL アドレス]**&#x200B;と&#x200B;**[!UICONTROL パーソナライゼーションデータ]**&#x200B;の下に表示されます。 これらの各フィールドを、使用するフィールド(イベントまたはデータソース)にマップする必要があります。 また、高度な式エディターを使用して、手動で値を渡したり、取得した情報に対してデータ操作を実行したり（例えば、文字列を大文字に変換）、「if, then, else」などの関数を使用したりできます。 [このページ](../expression/expressionadvanced.md)を参照してください。

![](../assets/journey60.png)

## 電子メールとSMS {#section_asc_51g_nhb}

**[!UICONTROL 電子メール]**&#x200B;と&#x200B;**[!UICONTROL SMS]**&#x200B;の場合、パラメータは同じです。

>[!NOTE]
>
>電子メールの場合、プロファイルのトランザクションテンプレートを使用している場合、購読解除のメカニズムはCampaign Standardによってすぐに処理されます。 テンプレートに&#x200B;**[!UICONTROL 購読解除リンク]**&#x200B;コンテンツブロックを追加します（[詳細情報](https://docs.adobe.com/content/help/en/campaign-standard/using/communication-channels/transactional-messaging/about-transactional-messaging.html)）。 イベントベースのテンプレート(rtEvent)を使用している場合は、メッセージ内に、URLパラメーターにユーザーの電子メールを渡し、購読解除ランディングページを指すリンクを追加する必要があります。 このランディングページを作成し、登録解除の決定がAdobeに送信されることを確認する必要があります。

最初に、トランザクションメッセージングテンプレートを選択する必要があります。 [このページ](../building-journeys/about-action-activities.md)を参照してください。

次の2つのカテゴリを使用できます。**[!UICONTROL アドレス]**&#x200B;と&#x200B;**[!UICONTROL パーソナライゼーションデータ]**。

**[!UICONTROL アドレス]**&#x200B;または&#x200B;**[!UICONTROL パーソナライゼーションデータ]**&#x200B;を取得する場所を、インターフェイスを使用して簡単に定義できます。 イベントや使用可能なデータソースのフィールドを参照できます。 高度な式エディターを使用すると、パラメーターの渡しや操作の実行が必要なデータソースの使用など、より高度な使用例に対しても使用できます。 [このページ](../expression/expressionadvanced.md)を参照してください。

**[!UICONTROL アドレス]**

>[!NOTE]
>
>このカテゴリは、「イベント」トランザクションメッセージを選択した場合にのみ表示されます。 「プロファイル」メッセージの場合、**[!UICONTROL アドレス]**&#x200B;フィールドは、システムによってAdobe Campaign Standardから自動的に取得されます。

以下は、メッセージの送信先をシステムが知るために必要なフィールドです。 電子メールテンプレートの場合は、電子メールアドレスです。 SMSの場合は、携帯電話番号です。

![](../assets/journey61.png)

**[!UICONTROL パーソナライゼーションデータ]**

>[!NOTE]
>
>個人設定データでコレクションを渡すことはできません。 トランザクション用の電子メールまたはSMSでコレクションが必要な場合は、機能しません。 また、パーソナライゼーションデータの形式が期待通りであることにも注意してください(例：文字列、10進数など)。 これらの想定される形式には注意が必要です。

これらは、Adobe Campaign Standardのメッセージで予想されるフィールドです。 これらのフィールドは、メッセージのパーソナライズ、条件付き書式の適用、特定のメッセージバリアントの選択を行うために使用できます。

![](../assets/journey62.png)

## プッシュ {#section_im3_hvf_nhb}

プッシュアクティビティを使用する前に、プッシュ通知を送信するCampaign Standardと共にモバイルアプリを設定する必要があります。 この[記事](https://helpx.adobe.com/jp/campaign/kb/integrate-mobile-sdk.html)を使用して、モバイルに必要な実装手順を実行します。

最初に、ドロップダウンリストとトランザクションメッセージからモバイルアプリを選択する必要があります。 [このページ](../building-journeys/about-action-activities.md)を参照してください。

![](../assets/journey62bis.png)

次の2つのカテゴリを使用できます。**[!UICONTROL ターゲット]**&#x200B;と&#x200B;**[!UICONTROL パーソナライゼーションデータ]**。

**[!UICONTROL ターゲット]**

>[!NOTE]
>
>このカテゴリは、イベントメッセージを選択した場合にのみ表示されます。 プロファイルメッセージの場合、**[!UICONTROL ターゲット]**&#x200B;フィールドは、Adobe Campaign Standardが実行した調整を使用して、システムによって自動的に取得されます。

この節では、**[!UICONTROL プッシュプラットフォーム]**&#x200B;を定義する必要があります。 ドロップダウンリストでは、**[!UICONTROL Apple Push Notification Server]**(iOS)または&#x200B;**[!UICONTROL Firebase Cloud Messaging]**(Android)を選択できます。 イベントまたはデータソースから特定のフィールドを選択するか、高度な式を定義することもできます。

また、**[!UICONTROL 登録トークン]**&#x200B;を定義する必要があります。 式は、イベントペイロードまたは他の[!DNL Journey Orchestration]情報でのトークンの定義方法に依存します。 単純なフィールドにすることも、例えばコレクション内でトークンが定義されている場合に備えて、より複雑な式にすることもできます。

```
@{Event_push._experience.campaign.message.profileSnapshot.pushNotificationTokens.first().token}
```

**[!UICONTROL パーソナライゼーションデータ]**

>[!NOTE]
>
>個人設定データでコレクションを渡すことはできません。 トランザクションプッシュでコレクションが必要な場合、機能しません。 また、パーソナライゼーションデータの形式が期待通りであることにも注意してください(例：文字列、10進数など)。 これらの想定される形式には注意が必要です。

これらは、Adobe Campaign Standardのメッセージで使用されるトランザクションテンプレートで期待されるフィールドです。 これらのフィールドは、メッセージをパーソナライズしたり、条件付き書式を適用したり、特定のメッセージバリアントを選択したりするために使用できます。
