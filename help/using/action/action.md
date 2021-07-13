---
product: adobe campaign
title: アクションについて
description: アクションの設定方法を説明します
feature: ジャーニー
role: User
level: Intermediate
exl-id: 34f7666b-1c91-4edd-b5d6-4c0513b9c4f3
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '314'
ht-degree: 94%

---

# アクションについて {#about_actions}

>[!CONTEXTUALHELP]
>id="jo_actions"
>title="アクションについて"
>abstract="ここでは、メッセージを送信するシステムへの接続を定義します。ここで定義したアクションは、ジャーニーの左側のパレットのアクションカテゴリで使用できるようになります。 "

アクションとは、プッシュ通知、メール、SMS、またはビジネスで使用するその他のデジタルエンゲージメントの手段など、パーソナライズされたリアルタイムのエクスペリエンスを顧客に提供するための接続です。

カスタムアクションを使用すると、メッセージや API 呼び出しを送信するサードパーティシステムの接続を設定できます。アクションは、JSON 形式のペイロードを持つ REST API を介して呼び出すことのできる任意のプロバイダーからの任意のサービスで設定できます。

アクションは、ジャーニーの左側のパレットの「**[!UICONTROL アクション]**」カテゴリで使用できます。[このページ](../building-journeys/about-action-activities.md)を参照してください。

>[!NOTE]
>
>カスタムアクションの設定は、常に&#x200B;**技術ユーザー**&#x200B;が実行します。

**アクション**&#x200B;のリストで「c」を押すと、新しいジャーニー、アクション、データソース、イベントを作成できます。[!DNL Journey Orchestration]でのショートカットの詳細については、[この節](../about/user-interface.md#section_ksq_zr1_ffb)を参照してください。

アクションリストを表示したり、新しいアクションを設定したりするには、トップメニューの「**[!UICONTROL アクション]**」をクリックします。アクションのリストが表示されます。インターフェイスの詳細については、[このページ](../about/user-interface.md)を参照してください。

![](../assets/custom1.png)

Adobe Campaign Standard を使用している場合は、Adobe Campaign Standard のトランザクションメッセージ機能を使用して E メール、プッシュ通知、SMS を送信するように、デフォルトアクションを設定する必要があります。[このページ](../action/working-with-adobe-campaign.md)を参照してください。

Adobe Campaign v7 または v8 をお持ちの場合は、リクエストに応じて統合を利用できます。 [このページ](../action/acc-action.md)を参照してください。

サードパーティシステムを使用して Epsilon、Facebook、Adobe.io、Firebase などのメッセージを送信する場合は、カスタムアクションを追加して設定する必要があります。[このページ](../action/about-custom-action-configuration.md)を参照してください。

[!DNL Journey Orchestration] のアクションを設定し、ジャーニーで使用する方法について詳しくは、この[ビデオチュートリアル](https://experienceleague.adobe.com/docs/platform-learn/tutorials/journey-orchestration/configure-actions.html)を参照してください。
