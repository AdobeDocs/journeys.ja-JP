---
title: Adobe Campaignアクションの使用
description: Adobe Campaignのアクションについて説明します。
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
source-git-commit: 1bc8d845716044671a11c200e4bab92302841994

---


# Adobe Campaignアクションの使用 {#using_campaign_action}

Adobe Campaign Standardをお持ちの場合は、次のアクションアクティビティをすぐに使用できます。 **[!UICONTROL Email]**、お**[!UICONTROL Push]** よび **[!UICONTROL SMS]**。

>[!NOTE]
>
>この場合は、組み込みのアクションを設定する必要があります。 [](../action/working-with-adobe-campaign.md)を参照してください。

これらの各チャネルに対して、Adobe Campaign Standardのトランザクションメッセージングテンプレートを選択 **します**。 確かに、Jureny Orchestrationはメッセージ送信ソリューションではありません。 組み込み型の電子メール、SMS、プッシュチャネルの場合、メッセージ送信を実行するのにトランザクションメッセージングを使用します。 つまり、特定のメッセージテンプレートをジャーニーで使用する場合は、Adobe Campaign Standardで公開する必要があります。 この機能の使い方 [法は](https://docs.adobe.com/content/help/en/campaign-standard/using/communication-channels/transactional-messaging/about-transactional-messaging.html) 、このページを参照してください。

![](../assets/journey59.png)

イベント（リアルタイム）またはプロファイルトランザクションメッセージングテンプレートを使用できます。

>[!NOTE]
>
>リアルタイムトランザクションメッセージ(rtEvent)を送信する場合、またはカスタムアクションによってサードパーティのシステムでメッセージをルーティングする場合、疲労管理、ブラックリスト管理または購読解除管理に特定の設定が必要です。 例えば、属性「blacklist」または「unsubscribe」がプラットフォームまたはサードパーティシステムに保存されている場合、この条件を確認するためにメッセージを送信する前に条件を追加する必要があります。

テンプレートを選択すると、メッセージペイロードに必要なすべてのフィールドが、およびの下のアクティビティ設定ペインに表示 **[!UICONTROL Address]**されま**[!UICONTROL Personalization Data]**&#x200B;す。 これらの各フィールドを、イベントまたはデータソースから使用するフィールドにマップする必要があります。 また、高度な式エディターを使用して、手動で値を渡したり、取得した情報に対してデータ操作（例えば、文字列を大文字に変換）を実行したり、「if, then, else」などの関数を使用したりすることもできます。 [](../expression/expressionadvanced.md)を参照してください。

![](../assets/journey60.png)

## 電子メールとSMS {#section_asc_51g_nhb}

との場 **[!UICONTROL Email]**合、パ**[!UICONTROL SMS]**&#x200B;ラメータは同じです。

>[!NOTE]
>
>プロファイルトランザクションテンプレートを使用している電子メールの場合、購読解除メカニズムはCampaign Standardによってそのまま使用できます。 テンプレートにコンテ **[!UICONTROL Unsubscription link]**ンツブロックを追加するだけで済みます([詳細](https://docs.adobe.com/content/help/en/campaign-standard/using/communication-channels/transactional-messaging/about-transactional-messaging.html))。 イベントベースのテンプレート(rtEvent)を使用している場合は、URLパラメーターに電子メールを渡し、購読解除のランディングページを指すリンクをメッセージに追加する必要があります。 このランディングページを作成し、登録解除の決定がアドビに送信されることを確認する必要があります。

まず、トランザクションメッセージングテンプレートを選択する必要があります。 [](../building-journeys/about-action-activities.md)を参照してください。

次の2つのカテゴリを使用できます。 **[!UICONTROL Address]**と**[!UICONTROL Personalization Data]**。

インターフェイスを使用して、を呼び出す場所や **[!UICONTROL Address]**を簡単に**[!UICONTROL Personalization Data]** 定義できます。 イベントや利用可能なデータソースのフィールドを参照できます。 また、高度な式エディターを使用すると、パラメーターの渡しや操作を必要とするデータソースの使用など、より高度な使用例を見ることもできます。 [](../expression/expressionadvanced.md)を参照してください。

**[!UICONTROL Address]**

>[!NOTE]
>
>このカテゴリは、「イベント」トランザクションメッセージを選択した場合にのみ表示されます。 「プロファイル」メッセージの場合、こ **[!UICONTROL Address]**のフィールドはシステムによってAdobe Campaign Standardから自動的に取得されます。

メッセージの送信先をシステムが知るために必要なフィールドは次のとおりです。 電子メールテンプレートの場合は、電子メールアドレスです。 SMSの場合は、携帯電話番号です。

![](../assets/journey61.png)

**[!UICONTROL Personalization Data]**

>[!NOTE]
>
>パーソナライゼーションデータでコレクションを渡すことはできません。 トランザクション用の電子メールまたはSMSがコレクションを想定している場合は、機能しません。 また、パーソナライゼーションデータの形式が期待通りであることにも注意してください(例：文字列、10進数など)。 これらの期待される形式には注意が必要です。

Adobe Campaign Standardのメッセージでは、以下のフィールドが必要です。 これらのフィールドを使用して、メッセージをパーソナライズしたり、条件付き書式を適用したり、特定のメッセージバリアントを選択したりできます。

![](../assets/journey62.png)

## プッシュ {#section_im3_hvf_nhb}

プッシュアクティビティを使用する前に、プッシュ通知を送信するには、Campaign Standardと共にモバイルアプリを設定する必要があります。 この記事を使 [用して](https://helpx.adobe.com/campaign/kb/integrate-mobile-sdk.html) 、モバイルに必要な実装手順を実行します。

まず、ドロップダウンリストからモバイルアプリを選択し、トランザクションメッセージを選択する必要があります。 [](../building-journeys/about-action-activities.md)を参照してください。

![](../assets/journey62bis.png)

次の2つのカテゴリを使用できます。 **[!UICONTROL Target]**と**[!UICONTROL Personalization Data]**。

**[!UICONTROL Target]**

>[!NOTE]
>
>このカテゴリは、イベントメッセージを選択した場合にのみ表示されます。 プロファイルメッセージの場合、フ **[!UICONTROL Target]**ィールドは、Adobe Campaign Standardによって実行された調整を使用して、システムによって自動的に取得されます。

この節では、を定義する必要があります **[!UICONTROL Push platform]**。 ドロップダウンリストでは、(iOS)ま**[!UICONTROL Apple Push Notification Server]** たは **[!UICONTROL Firebase Cloud Messaging]**(Android)を選択できます。 または、イベントやデータソースから特定のフィールドを選択したり、高度な式を定義したりできます。

また、を定義する必要がありま **[!UICONTROL Registration Token]**す。 式は、イベントペイロードまたは他のJureny Orchestration情報でのトークンの定義方法に依存します。 単純なフィールドにすることも、例えばコレクション内でトークンが定義されている場合に備えて、より複雑な式にすることもできます。

```
@{Event_push._experience.campaign.message.profileSnapshot.pushNotificationTokens.first().token}
```

**[!UICONTROL Personalization Data]**

>[!NOTE]
>
>パーソナライゼーションデータでコレクションを渡すことはできません。 トランザクションのプッシュでコレクションが必要な場合は、機能しません。 また、パーソナライゼーションデータの形式が期待通りであることにも注意してください(例：文字列、10進数など)。 これらの期待される形式には注意が必要です。

これらは、Adobe Campaign Standardメッセージで使用されるトランザクションテンプレートで想定されるフィールドです。 これらのフィールドを使用して、メッセージをパーソナライズしたり、条件付き書式を適用したり、特定のメッセージバリアントを選択したりできます。
