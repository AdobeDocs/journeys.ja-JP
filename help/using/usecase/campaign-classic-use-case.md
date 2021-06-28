---
product: adobe campaign
solution: Journey Orchestration
title: Campaign v7／v8 を使用したメッセージの送信
description: Campaign v7／v8 を使用したメッセージの送信
source-git-commit: 8d10739381b4f5b09ad7070498d5f1566961c221
workflow-type: ht
source-wordcount: '394'
ht-degree: 100%

---


# Campaign v7／v8 を使用したメッセージの送信{#campaign-classic-use-case}

この使用例では、メールの送信に Adobe Campaign Classic v7 と Adobe Campaign v8 の統合を使用する手順を示します。

まず、Campaign でトランザクションメールのテンプレートを作成します。 次に、Journey Orchestration で、イベントとアクションを作成し、ジャーニーをデザインします。

Campaign の統合については、次のページを参照してください。

* [キャンペーンアクションの作成](../action/acc-action.md)
* [ジャーニーでのアクションの使用](../building-journeys/using-adobe-campaign-classic.md)

**Adobe Campaign**

Campaign インスタンスをこの統合用にプロビジョニングします。 トランザクションメッセージ機能を設定する必要があります。

1. Campaign コントロールインスタンスにログインします。

1. **管理**／**プラットフォーム**／**列挙**&#x200B;で、**イベントタイプ**（eventType）の列挙を選択します。新しいイベントタイプ（この例では「journey-event」）を作成します。イベントタイプの内部名は、後で JSON ファイルを書き込む際に使用します。

   ![](../assets/accintegration-uc-1.png)

1. インスタンスを切断してからもう一度接続し、作成を有効にします。

1. **Message Center**／**トランザクションメッセージテンプレート**&#x200B;の下に、前に作成したイベントタイプに基づいて、新しいメールテンプレートを作成します。

   ![](../assets/accintegration-uc-2.png)

1. テンプレートをデザインします。 この例では、プロファイルの名前と注文番号にパーソナライズ機能を使用します。 名前は Adobe Experience Platform データソースにあり、注文番号は Journey Orchestration イベントのフィールドにあります。 Campaign で正しいフィールド名を使用していることを確認します。

   ![](../assets/accintegration-uc-3.png)

1. トランザクションテンプレートを公開します。

   ![](../assets/accintegration-uc-4.png)

1. テンプレートに対応する JSON ペイロードを記述します。

```
{
     "channel": "email",
     "eventType": "journey-event",
     "email": "Email address",
     "ctx": {
          "firstName": "First name", "purchaseOrderNumber": "Purchase order number"
     }
}
```

* チャネルには、「email」と入力します。
* eventType には、前に作成したイベントタイプの内部名を使用します。
* メールアドレスは変数なので、任意のラベルを入力できます。
* ctx のパーソナライゼーションフィールドも変数です。

**Journey Orchestration**

1. 最初に、イベントを作成します。 「purchaseOrderNumber」フィールドを必ず含めてください。

   ![](../assets/accintegration-uc-5.png)

1. Journey Orchestration で、キャンペーンテンプレートに対応するアクションを作成します。 **アクションタイプ**&#x200B;ドロップダウンで、**Adobe Campaign Classic** を選択します。

   ![](../assets/accintegration-uc-6.png)

1. 「**ペイロードフィールド**」をクリックし、前に作成した JSON を貼り付けます。

   ![](../assets/accintegration-uc-7.png)

1. メールアドレスと 2 つのパーソナライゼーションフィールドを、**定数**&#x200B;から&#x200B;**変数**&#x200B;に変更します。

   ![](../assets/accintegration-uc-8.png)

1. 新しいジャーニーを作成し、以前に作成したイベントで開始します。

   ![](../assets/accintegration-uc-9.png)

1. アクションを追加し、各フィールドを Journey Orchestration の正しいフィールドにマッピングします。

   ![](../assets/accintegration-uc-10.png)

1. **終了**&#x200B;アクティビティを追加し、ジャーニーをテストします。

   ![](../assets/accintegration-uc-11.png)

1. これで、ジャーニーを公開できます。
