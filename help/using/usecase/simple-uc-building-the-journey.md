---
title: ジャーニーの構築
description: シンプルなユースケースの遍歴を構築する方法を学ぶ
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: tm+mt
source-git-commit: bcb8a71a27e2b9e37af7d0260cec04ed0fda24ee
workflow-type: tm+mt
source-wordcount: '411'
ht-degree: 39%

---


# ジャーニーの構築{#concept_eyw_mcy_w2b}

**ビジネスユーザー**&#x200B;はジャーニーを構築できるようになります。以下のアクティビティを含むパスは1つだけです。

* 「SpaBeacon」 **[!UICONTROL イベント]**:人がspaビーコンの近くを歩くと、イベントが送られ、その人の開始が送られます。
* 人が **[!UICONTROL 女性であるかを調べるアクティビティ]** 。
* 電子 **[!UICONTROL メール]** アクティビティ(Adobe Campaign Standardを使用)
* **[!UICONTROL 終了]**&#x200B;アクティビティ

>[!NOTE]
>
>**[!UICONTROL プッシュ]**&#x200B;アクティビティと **[!UICONTROL E メール]**&#x200B;アクティビティは、Adobe Campaign Standard がある場合にのみパレットで使用できます。

For additional information on how to build a journey, refer to [this page](../building-journeys/journey.md).

1. 上部のメニューで、「**[!UICONTROL ホーム]**」タブをクリックし、「**[!UICONTROL 作成]**」をクリックして新しいジャーニーを作成します。

   ![](../assets/journey31.png)

1. 右側に表示される設定ペインで、ジャーニーのプロパティを編集します。12月1日から12月31日まで1か月間「スパジャーニー」と名付けました。

   ![](../assets/journeyuc1_8.png)

1. 「SpaBeacon」イベントをパレットからキャンバスにドラッグ&amp;ドロップして、旅のデザインに開始が発生しました。 パレット内のイベントをダブルクリックしてキャンバスに追加することもできます。

   ![](../assets/journeyuc1_9.png)

1. 次に、その人が女性であることを確認する条件を追加します。 ジャーニーに条件アクティビティをドラッグ＆ドロップします。

   ![](../assets/journeyuc1_10.png)

1. 「**[!UICONTROL データソースの条件]**」タイプを選択し、「**[!UICONTROL 式]**」フィールドをクリックします。また、キャンバス上の矢印に表示される「条件」ラベルを定義することもできます。

   ![](../assets/journeyuc1_11.png)

1. シンプルな式エディターを使用して、性別フィールド(_人/性別_)を探し、右にドロップして次の条件を作成します。「性別は「女性」と同じです。

   ![](../assets/journeyuc1_12.png)

1. 「 **[!UICONTROL 電子メール]** 」アクティビティを削除し、「Spa割引」トランザクションメッセージングテンプレートを選択します。 このテンプレートはAdobe Campaignを使用して設計されています。 この[ページ](https://docs.adobe.com/content/help/ja-JP/campaign-standard/using/communication-channels/transactional-messaging/about-transactional-messaging.html)を参照してください。

   ![](../assets/journeyuc1_13.png)

1. 「 **[!UICONTROL 電子メール]** 」フィールド内をクリックし、データソースから電子メールアドレスを選択します。

   ![](../assets/journeyuc1_14.png)

1. 同様に、データソースの名と姓のパーソナライゼーションフィールドーを定義します。

   ![](../assets/journeyuc1_15.png)

1. Drop an **[!UICONTROL End]** activity.

   ![](../assets/journeyuc1_17.png)

1. Click on the **[!UICONTROL Test]** toggle and test your journey using test profiles. エラーが発生した場合は、テストモードを非アクティブ化し、ジャーニーを変更して再度テストします。For more information on the test mode, refer to [this page](../building-journeys/testing-the-journey.md).

   ![](../assets/journeyuc1_18bis.png)

1. テストの最終的な結果が得られたら、右上のドロップダウンメニューからジャーニーを公開できます。

   ![](../assets/journeyuc1_18.png)

次回、女性がスパビーコンの近くを歩くと、「スパディスカウント」のパーソナライズされたメールがすぐに届きます。
