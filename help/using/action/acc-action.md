---
product: adobe campaign
title: Campaign v7/v8統合について
description: Campaign v7/v8統合について説明します
feature: ジャーニー
role: Business Practitioner
level: Intermediate
exl-id: 4b321b63-c624-4c2a-ae92-f9a2a95688d4
source-git-commit: 8d10739381b4f5b09ad7070498d5f1566961c221
workflow-type: tm+mt
source-wordcount: '443'
ht-degree: 51%

---

# Adobe Campaign v7/v8の操作{#integrating-with-adobe-campaign-classic}

この統合は、21.1リリース以降のAdobe Campaign Classic v7およびAdobe Campaign v8で使用できます。 Adobe Campaignのトランザクションメッセージ機能を使用して、Eメール、プッシュ通知、SMSを送信できます。

Journey Orchestration インスタンスと Campaign インスタンスとの接続は、プロビジョニング時にアドビによって設定されます。

エンドツーエンドの使用例については、この[節](../usecase/campaign-classic-use-case.md)で説明します。

設定したアクションごとに、ジャーニーデザイナーパレットでアクションアクティビティを使用できます。[こちら](../building-journeys/using-adobe-campaign-classic.md)を参照してください。

## 重要な注意事項

* メッセージのスロットル処理はおこなわれません。Campaign の現行の SLA に基づいて、送信できるメッセージの数を 1 時間あたり 50,000 件に制限しています。この理由により、Journey Orchestration は単一の使用例（セグメントではなく個々のイベント）でのみ使用してください。

* 使用するテンプレートごとに、1 つのアクションをキャンバス上に設定する必要があります。Adobe Campaignから使用する各テンプレートに対して、Journey Orchestrationで1つのアクションを設定する必要があります。

* この統合用にホストされている専用の Message Center インスタンスを使用して、実行中の他の Campaign 操作に影響を与えないようにすることをお勧めします。マーケティングサーバーはホスト型でもオンプレミス型でも構いません。 必要なビルドは、21.1リリース候補以降です。

* ペイロードつまり Campaign メッセージが正しいかどうかは検証されません。

* セグメントの選定イベントでは、キャンペーンアクションを使用できません。

## 前提条件

Campaignでは、トランザクションメッセージとそれに関連するイベントを作成して公開する必要があります。 [Adobe Campaign のドキュメント](https://experienceleague.adobe.com/docs/campaign-classic/using/transactional-messaging/introduction/about-transactional-messaging.html#transactional-messaging)を参照してください。

以下のパターンに従う各メッセージに対応するJSONペイロードを作成できます。 その後、Journey Orchestrationでアクションを設定する際に、このペイロードを貼り付けます（以下を参照）

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

* **チャネル**:Campaignトランザクションテンプレート用に定義されたチャネル
* **eventType**:Campaignイベントの内部名
* **ctx**:変数は、メッセージに含まれているパーソナライゼーションに基づいて決まります。

## アクションの設定

Journey Orchestration では、トランザクションメッセージごとに 1 つのアクションを設定する必要があります。 次の手順に従います。

1. 新規アクションを作成します。[こちら](../action/action.md)を参照してください。
1. 名前と説明を入力します。
1. 「**アクションタイプ**」フィールドで、**Adobe Campaign Classic** を選択します。
1. 「**ペイロード**」フィールドをクリックし、 Campaign メッセージに対応する JSON ペイロードの例を貼り付けます。 アドビに問い合わせて、このペイロードを取得します。 
1. 異なるフィールドを静的または可変に調整します（フィールドキャンバスにマッピングする場合に応じて）。ジャーニー Eメールアドレスのチャネルパラメーターやパーソナライゼーションフィールド(ctx)のような特定のフィールドは、ジャーニーのコンテキストでマッピングの変数として定義するとよいでしょう。
1. 「**保存**」をクリックします。

![](../assets/accintegration1.png)


