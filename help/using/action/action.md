---
title: アクションについて
description: アクションの設定方法を説明します
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
ht-degree: 100%

---


# アクションについて {#about_actions}

>[!CONTEXTUALHELP]
>id="jo_actions"
>title="アクションについて"
>abstract="ここでは、メッセージを送信するシステムへの接続を定義します。ここで定義したアクションは、ジャーニーの左側のパレットのアクションカテゴリで使用できるようになります。 "

アクションとは、プッシュ通知、E メール、SMS、またはビジネスで使用するその他のデジタルエンゲージメントの手段など、パーソナライズされたリアルタイムのエクスペリエンスを顧客に提供するための接続です。

カスタムアクションを使用すると、メッセージや API 呼び出しを送信するサードパーティシステムの接続を設定できます。アクションは、JSON 形式のペイロードを持つ REST API を介して呼び出すことのできる任意のプロバイダーからの任意のサービスで設定できます。

アクションは、ジャーニーの左側のパレットの&#x200B;**[!UICONTROL アクション]**&#x200B;カテゴリで使用できます（[](../building-journeys/about-action-activities.md)を参照）。

>[!NOTE]
>
>カスタムアクションの設定は、常に&#x200B;**技術ユーザー**&#x200B;が実行します。

**アクション**&#x200B;のリストで「c」を押すと、新しいジャーニー、アクション、データソース、イベントを作成できます。Journey Orchestration でのショートカットの詳細については、[](../about/user-interface.md#section_ksq_zr1_ffb)を参照してください。

アクションリストを表示したり、新しいアクションを設定したりするには、トップメニューの「**[!UICONTROL アクション]**」をクリックします。アクションのリストが表示されます。インターフェイスの詳細については、[](../about/user-interface.md)を参照してください。

![](../assets/custom1.png)

Adobe Campaign Standard を使用している場合は、Adobe Campaign Standard のトランザクションメッセージ機能を使用して E メール、プッシュ通知、SMS を送信するように、デフォルトアクションを設定する必要があります。[](../action/working-with-adobe-campaign.md)を参照してください。

サードパーティシステムを使用して Epsilon、Facebook、Adobe.io、Firebase などのメッセージを送信する場合は、カスタムアクションを追加して設定する必要があります。[](../action/about-custom-action-configuration.md)を参照してください。

Journey Orchestration のアクションを設定する方法、それをジャーニーで使用する方法の詳細については、この[ビデオチュートリアル](https://docs.adobe.com/content/help/en/platform-learn/tutorials/journey-orchestration/configure-actions.html)を参照してください。
