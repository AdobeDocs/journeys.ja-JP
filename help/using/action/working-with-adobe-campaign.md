---
product: adobe campaign
title: Adobe Campaign の使用
description: Adobe Campaignのアクションについて説明します
feature: ジャーニー
role: User
level: Intermediate
exl-id: c7e08542-fde8-4072-a697-42d35d6c58ba
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '314'
ht-degree: 8%

---

# Adobe Campaign Standard の使用 {#using_adobe_campaign_standard}

Adobe Campaign Standardのトランザクションメッセージング機能を使用して、Eメール、プッシュ通知およびSMSを送信できます。

[!DNL Journey Orchestration] には、Adobe Campaign Standardへの接続を許可する標準のアクションが付属しています。

Campaign Standardで使用するには、Journey Orchestrationトランザクションメッセージとそれに関連するイベントを公開する必要があります。 イベントが公開されてもメッセージが表示されない場合、Journey Orchestrationインターフェイスには表示されません。 メッセージが公開されても、関連するイベントが発行されない場合、Journey Orchestrationインターフェイスに表示されますが、使用できません。

>[!NOTE]
>
>Adobe Campaign Standard統合が設定されるとすぐに、Adobe Campaign Standardアクションに対して1秒あたり13呼び出しの制限ルールが自動的に定義されます。 これは、Adobe Campaign Standardトランザクションメッセージの公式スケールに対応します。
>
>トランザクションメッセージングSLAについて詳しくは、Adobe Campaign Standardの製品説明](https://helpx.adobe.com/jp/legal/product-descriptions/campaign-standard.html)を参照してください。[

設定の手順は次のとおりです。

1. 「**[!UICONTROL アクション]**」リストで、組み込みの「**[!UICONTROL AdobeCampaignStandard]**」アクションをクリックします。 画面右側にアクション設定ウィンドウが開きます。

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
