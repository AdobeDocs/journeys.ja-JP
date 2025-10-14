---
product: adobe campaign
title: アクションについて
description: アクションの設定方法を学ぶ
feature: Journeys
role: User
level: Intermediate
exl-id: 34f7666b-1c91-4edd-b5d6-4c0513b9c4f3
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '329'
ht-degree: 83%

---

# アクションについて {#about_actions}


>[!CAUTION]
>
>**Adobe Journey Optimizerをお探しですか** Journey Optimizerのドキュメントについては、[&#x200B; こちら &#x200B;](https://experienceleague.adobe.com/ja/docs/journey-optimizer/using/ajo-home){target="_blank"} をクリックしてください。
>
>
>_このドキュメントでは、Journey Optimizerに置き換えられた従来のJourney Orchestration マテリアルについて説明します。 Journey OrchestrationやJourney Optimizerへのアクセスに関するご質問は、アカウントチームにお問い合わせください。_


>[!CONTEXTUALHELP]
>id="jo_actions"
>title="アクションについて"
>abstract="ここでは、メッセージを送信するシステムへの接続を定義します。ここで定義されたアクションは、ジャーニーの左側のパレットの「アクション」カテゴリで使用できます。 "

アクションとは、プッシュ通知、メール、SMS、またはビジネスで使用するその他のデジタルエンゲージメントの手段など、パーソナライズされたリアルタイムのエクスペリエンスを顧客に提供するための接続です。

カスタムアクションを使用すると、メッセージや API 呼び出しを送信するサードパーティシステムの接続を設定できます。アクションは、JSON 形式のペイロードを使用した REST API を介して呼び出すことができる、任意のプロバイダーの任意のサービスで設定できます。

アクションは、ジャーニーの左側のパレットの「**[!UICONTROL アクション]**」カテゴリで使用できます。[このページ](../building-journeys/about-action-activities.md)を参照してください。

>[!NOTE]
>
>カスタムアクションの設定は、常に&#x200B;**技術ユーザー**&#x200B;が実行します。

**アクション**&#x200B;のリストで「c」を押すと、新しいジャーニー、アクション、データソース、イベントを作成できます。[!DNL Journey Orchestration] のショートカットについて詳しくは、[&#x200B; この節 &#x200B;](../about/user-interface.md#section_ksq_zr1_ffb) を参照してください。

アクションリストを表示したり、新しいアクションを設定したりするには、トップメニューの「**[!UICONTROL アクション]**」をクリックします。アクションのリストが表示されます。インターフェイスの詳細については、[このページ](../about/user-interface.md)を参照してください。

![](../assets/custom1.png)

Adobe Campaign Standard を使用している場合は、Adobe Campaign Standard のトランザクションメッセージ機能を使用してメール、プッシュ通知、SMS を送信するように、デフォルトアクションを設定する必要があります。詳しくは、[このページ](../action/working-with-adobe-campaign.md)を参照してください。

Adobe Campaign v7 または v8 をお持ちの場合は、リクエストに応じて統合を利用できます。[このページ](../action/acc-action.md)を参照してください。

サードパーティシステムを使用して Epsilon、Facebook、Adobe.io、Firebase などのメッセージを送信する場合は、カスタムアクションを追加して設定する必要があります。[このページ](../action/about-custom-action-configuration.md)を参照してください。

