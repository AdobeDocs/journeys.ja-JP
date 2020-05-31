---
title: アクションについて
description: アクションの設定方法を学びます
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
source-git-commit: 87910a9f3dbf2c34776a8d2ab1f00426e8b0704c
workflow-type: tm+mt
source-wordcount: '291'
ht-degree: 3%

---


# アクションについて {#about_actions}

>[!CONTEXTUALHELP]
>id="jo_actions"
>title="アクションについて"
>abstract="ここで、メッセージを送信するシステムへの接続を定義します。 ここで定義したアクションは、ジャーニーの左側のパレットのアクションカテゴリで使用できます。 "

アクションとは、プッシュ通知、電子メール、SMS、またはビジネスで使用するその他のデジタルエンゲージメントの手段など、顧客に対して、パーソナライズされたリアルタイムのエクスペリエンスを提供するための接続です。

カスタムアクションを使用すると、メッセージやAPI呼び出しを送信するサードパーティ製システムの接続を設定できます。 アクションは、JSON形式のペイロードを持つREST APIを介して呼び出すことのできる任意のプロバイダーからの任意のサービスを使用して設定できます。

アクションは、遍歴の左側のパレットの **[!UICONTROL アクション]** カテゴリで使用できます(を参照 [](../building-journeys/about-action-activities.md) )。

>[!NOTE]
>
>カスタムアクションの設定は、常に **技術ユーザーが実行します**。

「 **アクション**」のリストで、「c」を押すと、新しいジャーニー、アクション、データソースまたはイベントを作成できます。 Journey Orchestrationのショートカットの詳細については、を参照してくだ [](../about/user-interface.md#section_ksq_zr1_ffb)さい。

アクションリストを表示したり、新しいアクションを設定したりするには、トップメニューの **[!UICONTROL 「アクション]** 」をクリックします。 アクションのリストが表示されます。 インターフェイス [](../about/user-interface.md) の詳細については、を参照してください。

![](../assets/custom1.png)

Adobe Campaign標準を使用している場合は、標準のトランザクションメッセージ機能を使用して電子メール、プッシュ通知、およびSMSを送信するように、標準搭載のAdobe Campaignを設定する必要があります。 [](../action/working-with-adobe-campaign.md)を参照してください。

サードパーティ製システムを使用してEpsilon、Facebook、Adobe.io、Firebaseなどのメッセージを送信する場合は、カスタムアクションを追加して設定する必要があります。 [](../action/about-custom-action-configuration.md)を参照してください。

アクションをJourney Orchestration用に設定する方法と遍歴での使用方法について詳しくは、この [ビデオチュートリアルを参照してください](https://docs.adobe.com/content/help/en/platform-learn/tutorials/journey-orchestration/configure-actions.html)。
