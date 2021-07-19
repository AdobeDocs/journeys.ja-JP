---
product: adobe campaign
solution: Journey Orchestration
title: Campaign v7／v8 を使用したメッセージの送信
description: Campaign v7／v8 を使用したメッセージの送信
exl-id: 8832d306-5842-4be5-9fb9-509050fcbb01
source-git-commit: 3e78e429bbdfc95bfef74e0f2e2b92f8ff17cfdb
workflow-type: tm+mt
source-wordcount: '394'
ht-degree: 100%

---

# Campaign v7／v8 を使用したメッセージの送信 {#campaign-classic-use-case}

この使用例では、Adobe Campaign Classic v7 および Adobe Campaign v8 との統合を使用して電子メールを送信するために必要なすべての手順を示します。

まず、Campaign でトランザクションメールテンプレートを作成します。次に、Journey Orchestration で、イベントとアクションを作成し、ジャーニーをデザインします。

Campaign の統合について詳しくは、次のページを参照してください。

* [Campaign アクションの作成](../action/acc-action.md)
* [ジャーニーでのアクションの使用](../building-journeys/using-adobe-campaign-classic.md)。

**Adobe Campaign**

Campaign インスタンスをこの統合用にプロビジョニングする必要があります。トランザクションメッセージ機能を設定する必要があります。

1. Campaign コントロールインスタンスにログインします。

1. **管理**／**プラットフォーム**／**列挙**&#x200B;で、**イベントタイプ**（eventType）列挙を選択します。 新しいイベントタイプ（この例では「journey-event」）を作成します。 後で JSON ファイルを書き込む際には、イベントタイプの内部名を使用する必要があります。

   ![](../assets/accintegration-uc-1.png)

1. 作成を有効にするには、インスタンスを切断して、再接続します。

1. **Message Center**／**トランザクションメッセージテンプレート**&#x200B;で、以前に作成したイベントタイプに基づいて新しいメールテンプレートを作成します。

   ![](../assets/accintegration-uc-2.png)

1. テンプレートをデザインします。この例では、プロファイルの名と注文番号にパーソナライゼーションを使用します。名前は Adobe Experience Platform データソースにあり、注文番号は Journey Orchestration イベントのフィールドにあります。 Campaign で正しいフィールド名を使用していることを確認します。

   ![](../assets/accintegration-uc-3.png)

1. トランザクションテンプレートを公開します。

   ![](../assets/accintegration-uc-4.png)

1. 次に、テンプレートに対応する JSON ペイロードを記述する必要があります。

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

* チャネルには、「email」と入力する必要があります。
* eventType には、以前に作成したイベントタイプの内部名を使用します。
* メールアドレスは変数なので、任意のラベルを入力できます。
* ctx では、パーソナライゼーションフィールドも変数です。

**Journey Orchestration**

1. まず、イベントを作成する必要があります。「purchaseOrderNumber」フィールドを必ず含めてください。

   ![](../assets/accintegration-uc-5.png)

1. Journey Orchestration で、キャンペーンテンプレートに対応するアクションを作成します。 「**アクションタイプ**」ドロップダウンで、**Adobe Campaign Classic** を選択します。

   ![](../assets/accintegration-uc-6.png)

1. 「**ペイロードフィールド**」をクリックし、以前に作成した JSON を貼り付けます。

   ![](../assets/accintegration-uc-7.png)

1. メールアドレスと 2 つのパーソナライゼーションフィールドで、「**定数**」を「**変数**」に変更します。

   ![](../assets/accintegration-uc-8.png)

1. 次に、新しいジャーニーを作成し、以前に作成したイベントから開始します。

   ![](../assets/accintegration-uc-9.png)

1. アクションを追加し、各フィールドを Journey Orchestration の正しいフィールドにマッピングします。

   ![](../assets/accintegration-uc-10.png)

1. **終了**&#x200B;アクティビティを追加し、ジャーニーをテストします。

   ![](../assets/accintegration-uc-11.png)

1. これで、ジャーニーを公開できます。
