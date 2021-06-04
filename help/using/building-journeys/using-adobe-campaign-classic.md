---
product: adobe campaign
solution: Journey Orchestration
title: Adobe Campaign のアクションの使用
description: Adobe Campaignのアクションについて説明します
feature: ジャーニー
role: Business Practitioner
level: Intermediate
exl-id: 4e59a256-d494-4407-a0a8-a2523eb1084e
source-git-commit: c17808a4cae7ebbd1129f6b28ad2ea945098f826
workflow-type: tm+mt
source-wordcount: '161'
ht-degree: 63%

---

# Adobe Campaign Classicの使用 {#using_campaign_classic}

Adobe Campaign Classicがある場合は、統合を使用できます。 Adobe Campaign Classicのトランザクションメッセージ機能を使用して、Eメール、プッシュ通知、SMSを送信できます。

Journey Orchestration インスタンスと Campaign Classic インスタンスとの接続は、プロビジョニング時にアドビによって設定されます。連絡先Adobe。

これを機能させるには、専用のアクションを設定する必要があります。 [こちら](../action/acc-action.md)を参照してください。

エンドツーエンドの使用例については、この[節](../usecase/campaign-classic-use-case.md)で説明します。

1. イベントから始めて、ジャーニーを設計します。 [こちら](../building-journeys/journey.md)を参照してください。
1. パレットの「**アクション**」セクションで、Campaign Classic アクションを選択してジャーニーに追加します。
1. **アクションパラメーター**&#x200B;には、メッセージペイロードで想定されるすべてのフィールドが表示されます。 これらの各フィールドを、イベントまたはデータソースのいずれかから使用するフィールドにマッピングする必要があります。これはカスタムアクションと似ています。 [こちら](../building-journeys/using-custom-actions.md)を参照してください。

![](../assets/accintegration2.png)
