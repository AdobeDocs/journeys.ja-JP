---
title: アクションについて
description: アクションの設定方法
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

---


# アクションについて {#about_actions}

>[!CONTEXTUALHELP]
>id=&quot;jo_actions&quot;
>title=&quot;アクションについて&quot;
>abstract=&quot;ここで、メッセージを送信するシステムへの接続を定義します。 ここで定義したアクションは、旅の左側のパレットの「アクション」カテゴリで使用できます。 &quot;

アクションとは、プッシュ通知、電子メール、SMS、またはビジネスで使用するその他のデジタルエンゲージメント手段など、パーソナライズされたリアルタイムエクスペリエンスを顧客に提供するための接続です。

カスタムアクションを使用すると、メッセージやAPI呼び出しを送信するサードパーティ製システムの接続を設定できます。 アクションは、JSON形式のペイロードを持つREST APIを介して呼び出すことのできる、任意のプロバイダーからの任意のサービスを使用して設定できます。

アクションは、ジャーニーの左側のパレットのカテゴリで使用で **[!UICONTROL Action]** きます(を参 [](../building-journeys/about-action-activities.md) 照)。

>[!NOTE]
>
>カスタムアクションの設定は、常に技術ユーザーが実 **行します**。

「アクション」のリ **ストで**、「c」を押すと、新しいジャーニー、アクション、データソースまたはイベントを作成できます。 Jargeny Orchestrationのショートカットの詳細については、を参照してくださ [](../about/user-interface.md#section_ksq_zr1_ffb)い。

アクションリストを表示するか、新しいアクションを設定するには、上部のメ **[!UICONTROL Actions]** ニューのをクリックします。 アクションのリストが表示されます。 インターフ [](../about/user-interface.md) ェイスの詳細については、を参照してください。

![](../assets/custom1.png)

Adobe Campaign Standardをお持ちの場合は、Adobe Campaign Standardのトランザクションメッセージ機能を使用して電子メール、プッシュ通知およびSMSを送信するための、あらかじめ用意されたアクションを設定する必要があります。 [](../action/working-with-adobe-campaign.md)を参照してください。

サードパーティ製のシステムを使用してEpsilon、Facebook、Adobe.io、Firebaseなどのメッセージを送信する場合は、カスタムアクションを追加して設定する必要があります。 [](../action/about-custom-action-configuration.md)を参照してください。

Jargeny Orchestration用のアクションの設定方法と、そのアクションを遍歴で使用する方法の詳細については、このビデオチュートリアルを参 [照してください](https://docs.adobe.com/content/help/en/platform-learn/tutorials/journey-orchestration/configure-actions.html)。
