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
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 017d502e21605b3e0b8c61e5fea0b4f6a65d4470
workflow-type: tm+mt
source-wordcount: '407'
ht-degree: 5%

---


# ジャーニーの構築{#concept_eyw_mcy_w2b}

これで **ビジネスユーザー** はこの旅を作成できます。 以下のアクティビティを含むパスは1つだけです。

* 「SpaBeacon」 **[!UICONTROL イベント]**: 人がspaビーコンの近くを歩くと、イベントが送られ、その人の開始が送られます。
* 人が **[!UICONTROL 女性であるかを調べるアクティビティ]** 。
* 電子 **[!UICONTROL メール]** アクティビティ(Adobe Campaign標準を使用)
* **[!UICONTROL 終了]**&#x200B;アクティビティ

>[!NOTE]
>
>「 **[!UICONTROL プッシュ]** 」および「 **[!UICONTROL 電子メール]** 」アクティビティは、Adobe Campaign標準を使用している場合にのみ、パレットで使用できます。

遍歴の作り方の詳細については、を参照してください [](../building-journeys/journey.md)。

1. 上部のメニューで、「 **[!UICONTROL ホーム]** 」タブをクリックし、「 **[!UICONTROL 作成]** 」をクリックして新しいジャーニーを作成します。

   ![](../assets/journey31.png)

1. 右側に表示される設定ペインで、ジャーニーのプロパティを編集します。 12月1日から12月31日まで1か月間「スパジャーニー」と名付けました。

   ![](../assets/journeyuc1_8.png)

1. 「SpaBeacon」イベントをパレットからキャンバスにドラッグ&amp;ドロップして、旅のデザインに開始が発生しました。 パレット内のイベントを重複クリックして、キャンバスに追加することもできます。

   ![](../assets/journeyuc1_9.png)

1. 次に、その人が女性であることを確認する条件を追加します。 条件アクティビティをジャーニーにドラッグ&amp;ドロップします。

   ![](../assets/journeyuc1_10.png)

1. 「 **[!UICONTROL Data Source Condition]** 」タイプを選択し、「 **[!UICONTROL 式]** 」フィールドをクリックします。 また、キャンバス上の矢印に表示される条件ラベルを定義することもできます。

   ![](../assets/journeyuc1_11.png)

1. シンプルな式エディターを使用して、性別フィールド(_人/性別_)を探し、右にドロップして次の条件を作成します。 「性別は「女性」と同等です。

   ![](../assets/journeyuc1_12.png)

1. 「 **[!UICONTROL 電子メール]** 」アクティビティを削除し、「Spa割引」トランザクションメッセージングテンプレートを選択します。 このテンプレートはAdobe Campaignを使用して設計されています。 この[ページ](https://docs.adobe.com/content/help/ja-JP/campaign-standard/using/communication-channels/transactional-messaging/about-transactional-messaging.html)を参照してください。

   ![](../assets/journeyuc1_13.png)

1. 「 **[!UICONTROL 電子メール]** 」フィールド内をクリックし、データソースから電子メールアドレスを選択します。

   ![](../assets/journeyuc1_14.png)

1. 同様に、データソースの名と姓のパーソナライゼーションフィールドーを定義します。

   ![](../assets/journeyuc1_15.png)

1. Drop an **[!UICONTROL End]** activity.

   ![](../assets/journeyuc1_17.png)

1. 「 **[!UICONTROL テスト]** 」トグルをクリックし、テストプロファイルを使用して遍歴をテストします。 エラーが発生した場合は、テストモードを非アクティブ化し、遍歴を変更して再度テストします。 For more information on the test mode, refer to [](../building-journeys/testing-the-journey.md).

   ![](../assets/journeyuc1_18bis.png)

1. テストが最終的な結果を得られたら、右上のドロップダウンメニューからジャーニーを公開できます。

   ![](../assets/journeyuc1_18.png)

次回、女性がスパビーコンの近くを歩くと、「スパディスカウント」のパーソナライズされたメールがすぐに届きます。
