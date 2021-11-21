---
product: adobe campaign
title: Adobe Campaign の使用
description: Adobe Campaignのアクションの詳細
feature: Journeys
role: User
level: Intermediate
exl-id: c7e08542-fde8-4072-a697-42d35d6c58ba
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '313'
ht-degree: 8%

---

# Adobe Campaign Standard の使用 {#using_adobe_campaign_standard}

Adobe Campaign Standardのトランザクションメッセージ機能を使用して、E メール、プッシュ通知、SMS を送信できます。

[!DNL Journey Orchestration] には、Adobe Campaign Standardへの接続を許可する標準のアクションが付属しています。

Campaign Standardで使用するには、Journey Orchestrationトランザクションメッセージとそれに関連するイベントを公開する必要があります。 イベントが公開されてもメッセージが表示されない場合、メッセージインターフェイスにはJourney Orchestrationされません。 メッセージが公開されたが、関連するイベントが発生しなかった場合、そのメッセージはJourney Orchestrationインターフェイスに表示されますが、使用できなくなります。

>[!NOTE]
>
>Adobe Campaign Standard統合が設定されるとすぐに、Adobe Campaign Standardアクションに対して 1 秒あたり 13 呼び出しの制限ルールが自動的に定義されます。 これは、Adobe Campaign Standardトランザクションメッセージの公式な規模に対応しています。
>
>トランザクションメッセージング SLA の詳細については、 [Adobe Campaign Standard Product Description](https://helpx.adobe.com/jp/legal/product-descriptions/campaign-standard.html).

次に、設定手順を示します。

1. 次の **[!UICONTROL アクション]** リストで、組み込み **[!UICONTROL AdobeCampaignStandard]** アクション。 画面右側にアクション設定ウィンドウが開きます。

   ![](../assets/actioncampaign.png)

1. Adobe Campaign Standardインスタンスの URL をコピーし、 **[!UICONTROL URL]** フィールドに入力します。

1. 次をクリック： **[!UICONTROL インスタンス URL をテストします。]** をクリックして、インスタンスの有効性をテストします。

   >[!NOTE]
   >
   >このテストでは、次のことを検証します。
   >
   >ホストは、「.campaign.adobe.com」、「.campaign-sandbox.adobe.com」、「.campaign-demo.adobe.com」、「.ats.adobe.com」または「.adls.adobe.com」です。
   >
   >URL は https で始まり、
   >
   >このAdobe Campaign Standardインスタンスに関連付けられている ORG は、Journey Orchestrationの ORG と同じです。

ジャーニーを設計する際、 **[!UICONTROL アクション]** カテゴリ： **[!UICONTROL 電子メール]**, **[!UICONTROL プッシュ]**, **[!UICONTROL SMS]** ( [Adobe Campaignアクションの使用](../building-journeys/using-adobe-campaign-actions.md)) をクリックします。 **反応イベント** また、メッセージのクリック数、開封数などに対する反応も可能です。 ( [反応イベント](../building-journeys/reaction-events.md)) をクリックします。

![](../assets/journey58.png)

サードパーティのシステムを使用してメッセージを送信する場合は、カスタムアクションを追加して設定する必要があります。 詳しくは、 [カスタムアクション設定について](../action/about-custom-action-configuration.md).
