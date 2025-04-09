---
product: adobe campaign
title: Adobe Campaignの操作
description: Adobe Campaignのアクションについて学ぶ
feature: Journeys
role: User
level: Intermediate
exl-id: c7e08542-fde8-4072-a697-42d35d6c58ba
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '356'
ht-degree: 34%

---

# Adobe Campaign Standard の使用 {#using_adobe_campaign_standard}


>[!CAUTION]
>
>**Adobe Journey Optimizerをお探しですか** Journey Optimizerのドキュメントについては、[ こちら ](https://experienceleague.adobe.com/ja/docs/journey-optimizer/using/ajo-home){target="_blank"} をクリックしてください。
>
>
>_このドキュメントでは、Journey Optimizerに置き換えられた従来のJourney Orchestration マテリアルについて説明します。 Journey OrchestrationやJourney Optimizerへのアクセスに関するご質問は、アカウントチームにお問い合わせください。_


Adobe Campaign Standard のトランザクションメッセージ機能を使用して、メール、プッシュ通知、SMS を送信できます。

[!DNL Journey Orchestration] には、Adobe Campaign Standardへの接続を可能にする標準のアクションが付属しています。

Journey Orchestrationで使用するには、Campaign Standard トランザクションメッセージとそれに関連するイベントを公開する必要があります。 イベントが公開されてもメッセージが表示されない場合、Journey Orchestration インターフェイスには表示されません。 メッセージが公開されても、関連するイベントが公開されなかった場合、Journey Orchestration インターフェイスには表示されますが、使用はできません。

>[!NOTE]
>
>Adobe Campaign Standardの統合が設定されるとすぐに、Adobe Campaign Standard アクションに対して 5 分あたり 4,000 回の呼び出しのキャッピングルールが自動的に定義されます。 これは、Adobe Campaign Standard トランザクションメッセージの公式な規模に対応しています。
>
>トランザクションメッセージ SLA の詳細については、[Adobe Campaign Standard 製品説明](https://helpx.adobe.com/jp/legal/product-descriptions/campaign-standard.html)を参照してください。

次に、設定手順を示します。

1. **[!UICONTROL アクション]** リストから、組み込み **[!UICONTROL AdobeCampaignStandard]** アクションをクリックします。 画面右側にアクション設定ペインが開きます。

   ![](../assets/actioncampaign.png)

1. Adobe Campaign Standard インスタンスの URL をコピーし、「**[!UICONTROL URL]**」フィールドにペーストします。

1. 「**[!UICONTROL インスタンス URL をテスト]**」をクリックし、インスタンスの有効性をテストします。

   >[!NOTE]
   >
   >このテストでは、次のことを検証します。
   >
   >ホストは「.campaign.adobe.com」、「.campaign-sandbox.adobe.com」、「.campaign-demo.adobe.com」、「.ats.adobe.com」または「.adls.adobe.com」です。
   >
   >https で始まる URL
   >
   >このAdobe Campaign Standard インスタンスに関連付けられている ORG は、Journey Orchestrationの ORG と同じです。

ジャーニーをデザインする際、**[!UICONTROL アクション]** カテゴリでは、**[!UICONTROL メール]**、**[!UICONTROL プッシュ]**、**[!UICONTROL SMS]** の 3 つのアクションが利用可能になります（[Adobe Campaign アクションの使用 ](../building-journeys/using-adobe-campaign-actions.md) を参照してください）。 **反応イベント** を使用すると、メッセージのクリック数や開封数などに反応することもできます。 （[ 反応イベント ](../building-journeys/reaction-events.md)）を参照してください。

![](../assets/journey58.png)

サードパーティのシステムを使用してメッセージを送信する場合は、カスタムアクションを追加および設定する必要があります。[カスタムアクション設定について](../action/about-custom-action-configuration.md)を参照してください。
