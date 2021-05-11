---
product: adobe campaign
solution: Journey Orchestration
title: Adobe Campaign の使用
description: Adobe Campaignの操作について
feature: ジャーニー
role: Business Practitioner
level: Intermediate
exl-id: c7e08542-fde8-4072-a697-42d35d6c58ba
translation-type: tm+mt
source-git-commit: 8ab3951f9c97a0a964f5c123978ed256d3aedc45
workflow-type: tm+mt
source-wordcount: '313'
ht-degree: 4%

---

# Adobe Campaign の使用 {#using_adobe_campaign_standard}

Adobe Campaign Standardのトランザクションメッセージング機能を使用して、電子メール、プッシュ通知、およびSMSを送信できます。

[!DNL Journey Orchestration] には、Adobe Campaign Standardとの接続を可能にする、すぐに使えるアクションが付属しています。

Journey Orchestrationで使用するには、Campaign Standardトランザクションメッセージとそれに関連するイベントを公開する必要があります。 イベントが公開されているが、メッセージが表示されていない場合は、Journey Orchestrationインターフェイスに表示されません。 メッセージが発行されても関連イベントが発行されない場合は、Journey Orchestrationインターフェイスに表示されますが、使用できません。

>[!NOTE]
>
>Adobe Campaign Standard統合が設定されるとすぐに、1秒あたり13コールのキャップルールがAdobe Campaign Standardアクションに対して自動的に定義されます。 これは、Adobe Campaign Standard・トランザクション・メッセージングの公式な規模に相当します。
>
>トランザクションメッセージングSLAの詳細については、[Adobe Campaign Standard製品の説明](https://helpx.adobe.com/jp/legal/product-descriptions/campaign-standard.html)を参照してください。

設定手順は次のとおりです。

1. **[!UICONTROL アクション]**&#x200B;リストから、組み込みの&#x200B;**[!UICONTROL AdobeCampaignStandard]**&#x200B;アクションをクリックします。 アクション設定ペインが画面の右側に開きます。

   ![](../assets/actioncampaign.png)

1. Adobe Campaign StandardインスタンスURLをコピーして、**[!UICONTROL URL]**&#x200B;フィールドに貼り付けます。

1. **[!UICONTROL インスタンスURL]**&#x200B;をテストして、インスタンスの有効性をテストします。

   >[!NOTE]
   >
   >このテストでは、次のことを確認します。
   >
   >ホストは、「。キャンペーン.adobe.com」、「。キャンペーン-sandbox.adobe.com」、「。キャンペーン — デモ.adobe.com」、「.ats.adobe.com」、「.adls.adobe.com」のいずれかです。
   >
   >httpsを含むURL開始ー、
   >
   >このAdobe Campaign Standardのインスタンスに関連付けられているORGは、Journey OrchestrationのORGと同じです。

ジャーニーを設計する際、**[!UICONTROL アクション]**&#x200B;カテゴリで3つのアクションを使用できます。**[!UICONTROL 電子メール]**、**[!UICONTROL プッシュ]**、**[!UICONTROL SMS]**([Adobe Campaignアクションの使用](../building-journeys/using-adobe-campaign-actions.md)を参照)。 **反応** はまた、メッセージのクリック数や開き数に対する反応も可能です。([反応イベント](../building-journeys/reaction-events.md)を参照)。

![](../assets/journey58.png)

サードパーティ製システムを使用してメッセージを送信する場合は、カスタムアクションを追加して設定する必要があります。 [カスタムアクションの設定について](../action/about-custom-action-configuration.md)を参照してください。
