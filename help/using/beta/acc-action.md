---
product: adobe campaign
solution: Journey Orchestration
title: Campaign Classic の統合について
description: Campaign Classic の統合について学ぶ
hide: true
hidefromtoc: true
feature: ジャーニー
role: ビジネス従事者
level: 中級者
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '444'
ht-degree: 100%

---


# Adobe Campaign Classic との統合 {#integrating-with-adobe-campaign-classic}

この統合により、Adobe Campaign Classic のトランザクションメッセージ機能を使用して、E メール、プッシュ通知、SMS を送信できるようになります。

Journey Orchestration インスタンスと Campaign Classic インスタンスとの接続は、プロビジョニング時にアドビによって設定されます。

>[!CAUTION]
>
> この統合は非公開のベータ版としてリリースされています。すべての Journey Orchestration ユーザーにご利用いただけるわけではありません。

## 重要な注意事項

* メッセージのスロットル処理はおこなわれません。Campaign Classic の現行の SLA に基づいて、送信できるメッセージの数を 1 時間あたり 50,000 件に制限しています。この理由により、Journey Orchestration は単一の使用例（セグメントではなく個々のイベント）でのみ使用してください。

* 使用するテンプレートごとに、1 つのアクションをキャンバス上に設定する必要があります。

* この統合用にホストされている専用の Message Center インスタンスを使用して、実行中の他の Campaign Classic 操作に影響を与えないようにすることをお勧めします。マーケティングサーバーはホスト型でもオンプレミス型でも構いません。 必要なビルドは 21.1 リリース候補です。

* ペイロードつまり Campaign Classic メッセージが正しいかどうかは検証されません。

* Campaign Classic アクションをセグメント認定で使用することはできません。

## 前提条件

Campaign Classic では、トランザクションメッセージとそれに関連するイベントを作成して公開する必要があります。  [Adobe Campaign Classic のドキュメント](https://experienceleague.adobe.com/docs/campaign-classic/using/transactional-messaging/introduction/about-transactional-messaging.html#transactional-messaging)を参照してください。

アドビに問い合わせて、各メッセージに対応する JSON ペイロードを取得します。 次に、Journey Orchestration でアクションを設定する際にこのペイロードを貼り付けます（以下を参照）。

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

Journey Orchestration では、トランザクションメッセージごとに 1 つのアクションを設定する必要があります。 次の手順に従います。

1. 新規アクションを作成します。[こちら](../action/action.md)を参照してください。
1. 名前と説明を入力します。
1. 「**アクションタイプ**」フィールドで、**Adobe Campaign Classic** を選択します。
1. 「**ペイロード**」フィールドをクリックし、 Campaign Classic メッセージに対応する JSON ペイロードの例を貼り付けます。 アドビに問い合わせて、このペイロードを取得します。 
1. 各種フィールドを調整します。 チャネルパラメーターやパーソナライゼーションフィールド（ctx）などの特定のフィールドは、変数として定義する必要があります。
1. 「**保存**」をクリックします。

![](../assets/accintegration1.png)

設定したアクションごとに、ジャーニーデザイナーパレットでアクションアクティビティを使用できます。

## ジャーニーへのメッセージの追加

1. イベントから始めて、ジャーニーを設計します。 [こちら](../building-journeys/journey.md)を参照してください。
1. パレットの「**アクション**」セクションで、Campaign Classic アクションを選択してジャーニーに追加します。
1. **アクションパラメーター**&#x200B;には、メッセージペイロードで想定されるすべてのフィールドが表示されます。 これらの各フィールドを、イベントまたはデータソースのいずれかから使用するフィールドにマッピングする必要があります。これはカスタムアクションと似ています。 [こちら](../building-journeys/using-custom-actions.md)を参照してください。

![](../assets/accintegration2.png)

