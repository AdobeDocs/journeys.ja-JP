---
title: Adobe Campaign の使用
description: Adobe Campaignの操作について
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
source-git-commit: 2a55139697347ade80959f60bf52bfde39e43eb9
workflow-type: tm+mt
source-wordcount: '293'
ht-degree: 2%

---


# Adobe Campaign の使用 {#using_adobe_campaign_standard}

Adobe Campaign Standardのトランザクションメッセージング機能を使用して、電子メール、プッシュ通知、およびSMSを送信できます。

[!DNL Journey Orchestration] には、Adobe Campaign Standardとの接続を可能にする、すぐに使用できるアクションが付属しています。

Journey Orchestrationで使用するには、Campaign Standardトランザクションメッセージとそれに関連するイベントを公開する必要があります。 イベントが公開されているが、メッセージが表示されていない場合は、Journey Orchestrationインターフェイスに表示されません。 メッセージが発行されても関連イベントが発行されない場合は、Journey Orchestrationインターフェイスに表示されますが、使用できません。

>[!NOTE]
>
>Adobe Campaign Standardトランザクションメッセージングの過負荷を防ぐには、Campaign Standard統合の **キャップルール** (capping rule)を設定することをお勧めします。
>
>トランザクションメッセージングSLAについて詳しくは、 [Adobe Campaign Standardの製品の説明を参照してください](https://helpx.adobe.com/legal/product-descriptions/campaign-standard.html)。

設定手順は次のとおりです。

1. 「 **[!UICONTROL アクション]** 」リストで、組み込みのAdobeCampaignStandard **** アクションをクリックします。 アクション設定ペインが画面の右側に開きます。

   ![](../assets/actioncampaign.png)

1. Adobe Campaign StandardインスタンスのURLをコピーして、「 **[!UICONTROL URL]** 」フィールドに貼り付けます。

1. 「インスタンスURLを **[!UICONTROL テスト]** 」をクリックして、インスタンスの有効性をテストします。

   >[!NOTE]
   >
   >このテストでは、次のことを確認します。
   >
   >* ホストは、「。キャンペーン.adobe.com」または「。キャンペーン — サンドボックス.adobe.com」です。
   >* httpsを含むURL開始ー、
   >* このAdobe Campaign Standardのインスタンスに関連付けられているORGは、Journey OrchestrationのORGと同じです。


遍歴をデザインする際、アクション **[!UICONTROL カテゴリでは次の3つのアクションを実行できます]** 。 **[!UICONTROL 電子メール]**、 **[!UICONTROL プッシュ]**、 **[!UICONTROL SMS]** (Adobe Campaignアクションの [使用を参照](../building-journeys/using-adobe-campaign-actions.md))。 **反応のイベント** (Reactions)では、メッセージのクリック数、開封数などに対する反応も可能です。 ( [反応イベント](../building-journeys/reaction-events.md))。

![](../assets/journey58.png)

サードパーティ製システムを使用してメッセージを送信する場合は、カスタムアクションを追加して設定する必要があります。 See [About custom action configuration](../action/about-custom-action-configuration.md).
