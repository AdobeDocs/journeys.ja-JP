---
product: adobe campaign
solution: Journey Orchestration
title: Adobe Campaign v7/v8アクションの使用
description: Adobe Campaign v7/v8のアクションについて説明します
feature: ジャーニー
role: Business Practitioner
level: Intermediate
exl-id: 4e59a256-d494-4407-a0a8-a2523eb1084e
source-git-commit: b2439788ef547b401dea64faf46d4398b9a1a0c7
workflow-type: tm+mt
source-wordcount: '165'
ht-degree: 58%

---

# Adobe Campaign v7/v8の使用 {#using_campaign_classic}

統合は、Adobe Campaign v7またはv8がある場合に使用できます。 Adobe Campaignのトランザクションメッセージ機能を使用して、Eメール、プッシュ通知、SMSを送信できます。

Journey Orchestration インスタンスと Campaign インスタンスとの接続は、プロビジョニング時にアドビによって設定されます。連絡先Adobe。

これを機能させるには、専用のアクションを設定する必要があります。 [こちら](../action/acc-action.md)を参照してください。

エンドツーエンドの使用例については、この[節](../usecase/campaign-classic-use-case.md)で説明します。

1. イベントから始めて、ジャーニーを設計します。 [こちら](../building-journeys/journey.md)を参照してください。
1. パレットの「**アクション**」セクションで、Campaign アクションを選択してジャーニーに追加します。
1. **アクションパラメーター**&#x200B;には、メッセージペイロードで想定されるすべてのフィールドが表示されます。 これらの各フィールドを、イベントまたはデータソースのいずれかから使用するフィールドにマッピングする必要があります。これはカスタムアクションと似ています。 [こちら](../building-journeys/using-custom-actions.md)を参照してください。

![](../assets/accintegration2.png)
