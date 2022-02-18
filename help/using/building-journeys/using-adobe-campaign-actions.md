---
product: adobe campaign
title: Adobe Campaign のアクションの使用
description: Adobe Campaignのアクションの詳細
feature: Journeys
role: User
level: Intermediate
source-git-commit: 2195ee3863b38ead504eb6785ceb3c37735fade9
workflow-type: tm+mt
source-wordcount: '933'
ht-degree: 9%

---

# Adobe Campaign Standard の使用 {#using_campaign_action}

Adobe Campaign Standardがある場合は、次の標準のアクションアクティビティを使用できます。 **[!UICONTROL 電子メール]**, **[!UICONTROL プッシュ]** および **[!UICONTROL SMS]**.

>[!NOTE]
>
>この場合は、組み込みのアクションを設定する必要があります。 [このページ](../action/working-with-adobe-campaign.md)を参照してください。

これらのチャネルごとに、Adobe Campaign Standardトランザクションメッセージを選択します **テンプレート**. 実際 [!DNL Journey Orchestration] は、メッセージ送信ソリューションではありません。 組み込みの E メール、SMS、プッシュチャネルの場合、メッセージ送信の実行にはトランザクションメッセージを使用します。 つまり、ジャーニーで特定のメッセージテンプレートを使用する場合は、Adobe Campaign Standardで公開する必要があります。 参照： [このページ](https://experienceleague.adobe.com/docs/campaign-standard/using/communication-channels/transactional-messaging/getting-started-with-transactional-msg.html?lang=ja) この機能の使用方法を学ぶには、以下を参照してください。

>[!NOTE]
>
>Campaign Standardで使用するには、Journey Orchestrationトランザクションメッセージとそれに関連するイベントを公開する必要があります。 イベントが公開されてもメッセージが表示されない場合、メッセージインターフェイスにはJourney Orchestrationされません。 メッセージが公開されたが、関連するイベントが発生しなかった場合、そのメッセージはJourney Orchestrationインターフェイスに表示されますが、使用できなくなります。

![](../assets/journey59.png)

イベント（リアルタイムとも呼ばれます）またはプロファイルトランザクションメッセージテンプレートを使用できます。

>[!NOTE]
>
>リアルタイムトランザクションメッセージ (rtEvent) を送信する場合、またはカスタムアクションによってサードパーティシステムでメッセージをルーティングする場合、疲労、ブロックリスト、購読解除の管理には、特定の設定が必要です。 例えば、「購読解除」属性がAdobe Experience Platformまたはサードパーティシステムに保存されている場合、メッセージが送信される前に条件を追加して、この条件を確認する必要があります。

テンプレートを選択すると、メッセージペイロードで期待されるすべてのフィールドが、アクティビティ設定ペインの下に表示されます **[!UICONTROL 住所]** および **[!UICONTROL パーソナライゼーションデータ]**. これらの各フィールドを、イベントまたはデータソースのいずれかから使用するフィールドにマッピングする必要があります。また、高度な式エディターを使用して、値を手動で渡したり、取得した情報に対してデータ操作（例えば、文字列を大文字に変換）を実行したり、「if, then, else」などの関数を使用したりできます。 [このページ](../expression/expressionadvanced.md)を参照してください。

![](../assets/journey60.png)

## E メールと SMS {#section_asc_51g_nhb}

の場合 **[!UICONTROL 電子メール]** および **[!UICONTROL SMS]**&#x200B;の場合、パラメーターは同じです。

>[!NOTE]
>
>E メールの場合、プロファイルトランザクションテンプレートを使用している場合、購読解除メカニズムは、Campaign Standardによって標準で処理されます。 単に **[!UICONTROL 購読解除リンク]** テンプレートのコンテンツブロック ([詳細情報](https://experienceleague.adobe.com/docs/campaign-standard/using/communication-channels/transactional-messaging/getting-started-with-transactional-msg.html)) をクリックします。 イベントベースのテンプレート (rtEvent) を使用している場合は、URL パラメーターにユーザーの E メールを渡し、購読解除ランディングページを指すリンクをメッセージに追加する必要があります。 このランディングページを作成し、ユーザーの購読解除の決定がAdobeに送信されることを確認する必要があります。

まず、トランザクションメッセージテンプレートを選択する必要があります。 [このページ](../building-journeys/about-action-activities.md)を参照してください。

次の 2 つのカテゴリを使用できます。 **[!UICONTROL 住所]** および **[!UICONTROL パーソナライゼーションデータ]**.

取得する **[!UICONTROL 住所]** または **[!UICONTROL パーソナライゼーションデータ]** インターフェイスを使用します。 イベントや使用可能なデータソースのフィールドを参照できます。 高度な式エディターは、パラメーターの渡しや操作の実行を必要とするデータソースの使用など、より高度な使用例にも使用できます。 [このページ](../expression/expressionadvanced.md)を参照してください。

**[!UICONTROL Address]**

>[!NOTE]
>
>このカテゴリは、「イベント」トランザクションメッセージを選択した場合にのみ表示されます。 「プロファイル」メッセージの場合、 **[!UICONTROL 住所]** フィールドは、システムによってAdobe Campaign Standardから自動的に取得されます。

これらは、システムがメッセージの送信先を知るために必要なフィールドです。 E メールテンプレートの場合は、E メールアドレスです。 SMS の場合は、携帯電話番号です。

![](../assets/journey61.png)

**[!UICONTROL パーソナライゼーションデータ]**

>[!NOTE]
>
>パーソナライゼーションデータでコレクションを渡すことはできません。 トランザクション E メールまたは SMS でコレクションが必要な場合は、機能しません。 また、パーソナライゼーションデータの形式は想定どおりです ( 例：文字列、小数など )。 これらの想定される形式に従うように注意する必要があります。

これらは、Adobe Campaign Standardメッセージで想定されるフィールドです。 これらのフィールドを使用して、メッセージのパーソナライズ、条件付き書式の適用、特定のメッセージバリアントの選択をおこなうことができます。

![](../assets/journey62.png)

## プッシュ {#section_im3_hvf_nhb}

プッシュアクティビティを使用する前に、プッシュ通知を送信するCampaign Standardと共にモバイルアプリを設定する必要があります。 使用する [記事](https://helpx.adobe.com/jp/campaign/kb/integrate-mobile-sdk.html) モバイルに必要な実装手順を実行する。

まず、ドロップダウンリストとトランザクションメッセージからモバイルアプリを選択する必要があります。 [このページ](../building-journeys/about-action-activities.md)を参照してください。

![](../assets/journey62bis.png)

次の 2 つのカテゴリを使用できます。 **[!UICONTROL ターゲット]** および **[!UICONTROL パーソナライゼーションデータ]**.

**[!UICONTROL Target]**

>[!NOTE]
>
>このカテゴリは、イベントメッセージを選択した場合にのみ表示されます。 プロファイルメッセージの場合、 **[!UICONTROL ターゲット]** フィールドは、Adobe Campaign Standardが実行した紐付けを使用して、システムによって自動的に取得されます。

この節では、 **[!UICONTROL プッシュプラットフォーム]**. ドロップダウンリストで、 **[!UICONTROL Apple Push Notification Server]** (iOS) または **[!UICONTROL Firebase Cloud Messaging]** (Android)。 または、イベントやデータソースから特定のフィールドを選択したり、高度な式を定義したりできます。

また、 **[!UICONTROL 登録トークン]**. 式は、イベントペイロードまたはその他のでのトークンの定義方法によって異なります [!DNL Journey Orchestration] 情報。 トークンがコレクションに定義されている場合は、単純なフィールドにするか、より複雑な式にすることができます。

```
@{Event_push._experience.campaign.message.profileSnapshot.pushNotificationTokens.first().token}
```

**[!UICONTROL パーソナライゼーションデータ]**

>[!NOTE]
>
>パーソナライゼーションデータでコレクションを渡すことはできません。 トランザクションプッシュでコレクションが必要な場合は、機能しません。 また、パーソナライゼーションデータの形式は想定どおりです ( 例：文字列、小数など )。 これらの想定される形式に従うように注意する必要があります。

これらは、Adobe Campaign Standardメッセージで使用されるトランザクションテンプレートで想定されるフィールドです。 これらのフィールドを使用して、メッセージをパーソナライズしたり、条件付き書式を適用したり、特定のメッセージバリアントを選択したりできます。
