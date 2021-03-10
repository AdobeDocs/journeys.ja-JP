---
product: adobe campaign
solution: Journey Orchestration
title: Campaign Classic統合について
description: Campaign Classicの統合について
hide: true
hidefromtoc: true
feature: ジャーニー
role: 開業医
level: 中級
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '444'
ht-degree: 5%

---


# Adobe Campaign Classicとの統合{#integrating-with-adobe-campaign-classic}

この統合により、Adobe Campaign Classicトランザクションメッセージング機能を使用して、電子メール、プッシュ通知、およびSMSを送信できます。

Journey OrchestrationインスタンスとCampaign Classicインスタンス間の接続は、プロビジョニング時にAdobeによって設定されます。

>[!CAUTION]
>
> この統合はプライベートベータ版としてリリースされます。 すべてのJourney Orchestrationのお客様がご利用いただけるわけではありません。

## 重要な注意事項

* メッセージの数を制限していません。 現在のCampaign ClassicのSLAに基づき、1時間あたり50,000件に送信できるメッセージの数を制限します。 このため、ジャーニーオーケストレーションは、単一の使用例(セグメントではなく個々のイベント)でのみ使用する必要があります。

* 使用するテンプレートごとに、キャンバス上で1つのアクションを設定する必要があります。

* この統合用にホストされている専用のMessage Centerインスタンスを使用して、今後のその他のCampaign Classic操作に影響を与えないようにすることをお勧めします。 マーケティングサーバーは、ホストまたはオンプレミスのどちらでも構いません。 必要なビルドは21.1 Release Candidateです。

* ペイロードまたはCampaign Classicメッセージが正しいことを確認する必要はありません。

* Campaign Classicアクションは、セグメントの資格と共に使用できません。

## 前提条件

Campaign Classicでは、トランザクションメッセージとその関連イベントを作成して公開する必要があります。 [Adobe Campaign Classicのドキュメント](https://experienceleague.adobe.com/docs/campaign-classic/using/transactional-messaging/introduction/about-transactional-messaging.html#transactional-messaging)を参照してください。

Adobeに問い合わせて、各メッセージに対応するJSONペイロードを取得します。 このペイロードは、Journey Orchestrationでアクションを設定する際に貼り付けます（以下を参照）。

次に例を示します。

```
{
    "channel": "email",
    "eventType": "welcome",
    "email": "example@adobe.com",
    "ctx": {
        "firstName": "John"
    }
}
```

## アクションの設定

Journey Orchestrationでは、トランザクションメッセージごとに1つのアクションを設定する必要があります。 次の手順に従います。

1. 新しいアクションを作成します。 [こちら](../action/action.md)を参照してください。
1. 名前と説明を入力します。
1. 「**アクションタイプ**」フィールドで、「**Adobe Campaign Classic**」を選択します。
1. **Payload**&#x200B;フィールドをクリックし、Campaign Classicメッセージに対応するJSONペイロードの例を貼り付けます。 Adobeに連絡して、このペイロードを取得してください。
1. 異なるフィールドを調整します。 チャネルパラメーターやパーソナライゼーションフィールド(ctx)などの特定のフィールドは、変数として定義する必要があります。
1. 「**保存**」をクリックします。

![](../assets/accintegration1.png)

設定したアクションごとに、ジャーニーデザイナーパレットでアクションアクティビティを使用できます。

## ジャーニーへのメッセージの追加

1. イベントから始めて、ジャーニーを設計します。 この[節](../building-journeys/journey.md)を参照してください。
1. パレットの「**アクション**」セクションで、Campaign Classicアクションを選択し、ジャーニーに追加します。
1. **アクションパラメーター**&#x200B;には、メッセージペイロードで予想されるすべてのフィールドが表示されます。 これらの各フィールドを、使用するフィールド(イベントまたはデータソース)にマップする必要があります。 これは、カスタムアクションと似ています。 [こちら](../building-journeys/using-custom-actions.md)を参照してください。

![](../assets/accintegration2.png)

