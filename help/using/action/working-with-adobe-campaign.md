---
product: adobe campaign
title: Adobe Campaign の使用
description: Adobe Campaignのアクションについて説明します
feature: ジャーニー
role: Business Practitioner
level: Intermediate
exl-id: c7e08542-fde8-4072-a697-42d35d6c58ba
source-git-commit: 04aa7d95c2f12fe03497efe74f2ab8bd1a270b5b
workflow-type: tm+mt
source-wordcount: '747'
ht-degree: 32%

---

# Adobe Campaign の使用 {#using_adobe_campaign}

## Adobe Campaign Standardの使用 {#using_adobe_campaign_standard}

Adobe Campaign Standardのトランザクションメッセージング機能を使用して、Eメール、プッシュ通知およびSMSを送信できます。

[!DNL Journey Orchestration] には、Adobe Campaign Standardへの接続を許可する標準のアクションが付属しています。

Campaign Standardで使用するには、Journey Orchestrationトランザクションメッセージとそれに関連するイベントを公開する必要があります。 イベントが公開されてもメッセージが表示されない場合、Journey Orchestrationインターフェイスには表示されません。 メッセージが公開されても、関連するイベントが発行されない場合、Journey Orchestrationインターフェイスに表示されますが、使用できません。

>[!NOTE]
>
>Adobe Campaign Standard統合が設定されるとすぐに、Adobe Campaign Standardアクションに対して1秒あたり13呼び出しの制限ルールが自動的に定義されます。 これは、Adobe Campaign Standardトランザクションメッセージの公式スケールに対応します。
>
>トランザクションメッセージングSLAについて詳しくは、Adobe Campaign Standardの製品説明](https://helpx.adobe.com/jp/legal/product-descriptions/campaign-standard.html)を参照してください。[

設定の手順は次のとおりです。

1. 「**[!UICONTROL アクション]**」リストで、組み込みの「**[!UICONTROL AdobeCampaignStandard]**」アクションをクリックします。 画面の右側にアクション設定ペインが開きます。

   ![](../assets/actioncampaign.png)

1. Adobe Campaign StandardインスタンスのURLをコピーし、「**[!UICONTROL URL]**」フィールドに貼り付けます。

1. 「**[!UICONTROL インスタンスURLをテスト]**」をクリックして、インスタンスの有効性をテストします。

   >[!NOTE]
   >
   >このテストでは、次の点が検証されます。
   >
   >ホストは、「.campaign.adobe.com」、「.campaign-sandbox.adobe.com」、「.campaign-demo.adobe.com」、「.ats.adobe.com」または「.adls.adobe.com」です。
   >
   >URLはhttpsで始まり、
   >
   >このAdobe Campaign Standardインスタンスに関連付けられているORGは、Journey OrchestrationのORGと同じです。

ジャーニーを設計する際に、「**[!UICONTROL アクション]**」カテゴリに3つのアクションを使用できます。**[!UICONTROL Eメール]**、**[!UICONTROL プッシュ]**、**[!UICONTROL SMS]**([Adobe Campaignのアクション](../building-journeys/using-adobe-campaign-actions.md)の使用を参照)。 **反応** は、メッセージのクリック数、開封数などに反応することもできます。（[反応イベント](../building-journeys/reaction-events.md)を参照）。

![](../assets/journey58.png)

サードパーティシステムを使用してメッセージを送信する場合は、カスタムアクションを追加して設定する必要があります。 [カスタムアクションの設定について](../action/about-custom-action-configuration.md)を参照してください。

## Adobe Campaign v7/v8の使用 {#using_adobe_campaign_v7_v8}

この統合は、21.1リリース以降のAdobe Campaign Classic v7およびAdobe Campaign v8で使用できます。 Adobe Campaignのトランザクションメッセージ機能を使用して、Eメール、プッシュ通知、SMSを送信できます。

Journey Orchestration インスタンスと Campaign インスタンスとの接続は、プロビジョニング時にアドビによって設定されます。

エンドツーエンドの使用例については、この[節](../usecase/campaign-v7-v8-use-case.md)で説明します。

設定したアクションごとに、ジャーニーデザイナーパレットでアクションアクティビティを使用できます。[こちら](../building-journeys/using-adobe-campaign-actions.md)を参照してください。

### 重要な注意事項

* メッセージのスロットル処理はおこなわれません。Campaign の現行の SLA に基づいて、送信できるメッセージの数を 1 時間あたり 50,000 件に制限しています。この理由により、Journey Orchestration は単一の使用例（セグメントではなく個々のイベント）でのみ使用してください。

* 使用するテンプレートごとに、1 つのアクションをキャンバス上に設定する必要があります。Adobe Campaignから使用する各テンプレートに対して、Journey Orchestrationで1つのアクションを設定する必要があります。

* この統合用にホストされている専用の Message Center インスタンスを使用して、実行中の他の Campaign 操作に影響を与えないようにすることをお勧めします。マーケティングサーバーはホスト型でもオンプレミス型でも構いません。 必要なビルドは、21.1リリース候補以降です。

* ペイロードつまり Campaign メッセージが正しいかどうかは検証されません。

* セグメントの選定イベントでは、キャンペーンアクションを使用できません。

### 前提条件

Campaignでは、トランザクションメッセージとそれに関連するイベントを作成して公開する必要があります。 [Adobe Campaign のドキュメント](https://experienceleague.adobe.com/docs/campaign-classic/using/transactional-messaging/introduction/about-transactional-messaging.html#transactional-messaging)を参照してください。

以下のパターンに従う各メッセージに対応するJSONペイロードを作成できます。 その後、Journey Orchestrationでアクションを設定する際に、このペイロードを貼り付けます（以下を参照）

次に例を示します。

```
{
    "channel": "email",
    "eventType": "welcome",
    "email": "example@adobe.com",
    "ctx": {
        "firstName": "John"
    }
}
```

* **チャネル**:Campaignトランザクションテンプレート用に定義されたチャネル
* **eventType**:Campaignイベントの内部名
* **ctx**:変数は、メッセージに含まれているパーソナライゼーションに基づいて決まります。

### アクションの設定

Journey Orchestration では、トランザクションメッセージごとに 1 つのアクションを設定する必要があります。 次の手順に従います。

1. 新規アクションを作成します。[こちら](../action/action.md)を参照してください。
1. 名前と説明を入力します。
1. 「**アクションタイプ**」フィールドで、**Adobe Campaign Classic** を選択します。
1. 「**ペイロード**」フィールドをクリックし、 Campaign メッセージに対応する JSON ペイロードの例を貼り付けます。 アドビに問い合わせて、このペイロードを取得します。 
1. 異なるフィールドを静的または可変に調整します（フィールドキャンバスにマッピングする場合に応じて）。ジャーニー Eメールアドレスのチャネルパラメーターやパーソナライゼーションフィールド(ctx)のような特定のフィールドは、ジャーニーのコンテキストでマッピングの変数として定義するとよいでしょう。
1. 「**保存**」をクリックします。

![](../assets/accintegration1.png)


