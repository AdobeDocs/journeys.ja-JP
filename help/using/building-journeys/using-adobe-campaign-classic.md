---
product: adobe campaign
solution: Journey Orchestration
title: Adobe Campaign v7/v8 のアクションの使用
description: Adobe Campaign v7／v8 のアクションについて説明します
feature: Journeys
role: User
level: Intermediate
exl-id: 4e59a256-d494-4407-a0a8-a2523eb1084e
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '209'
ht-degree: 68%

---

# Adobe Campaign v7／v8 の使用 {#using_campaign_classic}


>[!CAUTION]
>
>**Adobe Journey Optimizerをお探しですか** Journey Optimizerのドキュメントについては、[ こちら ](https://experienceleague.adobe.com/ja/docs/journey-optimizer/using/ajo-home){target="_blank"} をクリックしてください。
>
>
>_このドキュメントでは、Journey Optimizerに置き換えられた従来のJourney Orchestration マテリアルについて説明します。 Journey OrchestrationやJourney Optimizerへのアクセスに関するご質問は、アカウントチームにお問い合わせください。_


統合は、Adobe Campaign v7 または v8 のユーザーが使用できます。これにより、Adobe Campaign のトランザクションメッセージ機能を使用して、メール、プッシュ通知、SMS などを送信できるようになります。

Journey Orchestration インスタンスと Campaign インスタンスとの接続は、プロビジョニング時にAdobeによって設定されます。 アドビにご連絡ください。

これを機能させるには、専用のアクションを設定する必要があります。[この節](../action/acc-action.md)を参照してください。

エンドツーエンドのユースケースについては、この[節](../usecase/campaign-classic-use-case.md)を参照してください。

1. イベントから始めて、ジャーニーを設計します。この[節](../building-journeys/journey.md)を参照してください。
1. パレットの「**アクション**」セクションで、Campaign アクションを選択してジャーニーに追加します。
1. **アクションパラメーター**&#x200B;には、メッセージペイロードで想定されるすべてのフィールドが表示されます。これらの各フィールドを、イベントまたはデータソースのいずれかから使用するフィールドにマッピングする必要があります。これはカスタムアクションと似ています。[この節](../building-journeys/using-custom-actions.md)を参照してください。

![](../assets/accintegration2.png)
