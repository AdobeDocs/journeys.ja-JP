---
title: 旅の構築
description: シンプルなユースケースの遍歴を構築する方法を説明します。
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

---


# 旅の構築{#concept_eyw_mcy_w2b}

ビジネ **スユーザーは** 、これで旅行を作成できます。 以下のアクティビティを含むパスは1つだけです。

* 「SpaBeacon」 **[!UICONTROL Event]**:人がスパビーコンの近くを歩くと、システムはイベントを受け取り、その人のために旅を始めます。
* その **[!UICONTROL Condition]**人が女性であることを確認する活動
* アクテ **[!UICONTROL Email]**ィビティ（Adobe Campaign Standardを使用）
* 活 **[!UICONTROL End]**動

>[!NOTE]
>
>とアク **[!UICONTROL Push]**ティビテ**[!UICONTROL Email]** ィは、Adobe Campaign Standardを使用している場合にのみパレットで使用できます。

旅の作り方に関する詳細は、を参照してください [](../building-journeys/journey.md)。

1. 上部のメニューで、タブをクリック **[!UICONTROL Home]**し、新しい**[!UICONTROL Create]** ジャーニーを作成します。

   ![](../assets/journey31.png)

1. 右側に表示される設定ペインで、ジャーニーのプロパティを編集します。 「スパジャーニー」と名付け、12月1日から31日まで1ヶ月続けます。

   ![](../assets/journeyuc1_8.png)

1. 「SpaBeacon」イベントをパレットからキャンバスにドラッグ&amp;ドロップして、旅のデザインを開始します。 また、パレットでイベントをダブルクリックして、キャンバスに追加することもできます。

   ![](../assets/journeyuc1_9.png)

1. 次に、その人が女性であることを確認する条件を追加します。 条件アクティビティをドラッグ&amp;ドロップして、旅に出ます。

   ![](../assets/journeyuc1_10.png)

1. タイプを選択 **[!UICONTROL Data Source Condition]**し、フィールド内をクリック**[!UICONTROL Expression]** します。 また、キャンバスの矢印に表示する条件ラベルを定義することもできます。

   ![](../assets/journeyuc1_11.png)

1. シンプルな式エディターで、性別フィールド(_人/性別_)を探し、右にドロップして次の条件を作成します。「性別は「女性」と同じです。

   ![](../assets/journeyuc1_12.png)

1. アクティビティを **[!UICONTROL Email]**削除し、「Spa割引」トランザクションメッセージングテンプレートを選択します。 このテンプレートは、Adobe Campaignを使用して設計されています。 この[ページ](https://docs.adobe.com/content/help/en/campaign-standard/using/communication-channels/transactional-messaging/about-transactional-messaging.html)を参照してください。

   ![](../assets/journeyuc1_13.png)

1. フィールド内をクリ **[!UICONTROL Email]**ックし、データソースから電子メールアドレスを選択します。

   ![](../assets/journeyuc1_14.png)

1. 同様に、データソースの姓と名のパーソナライゼーションフィールドを定義します。

   ![](../assets/journeyuc1_15.png)

1. アクティビティを削 **[!UICONTROL End]**除します。

   ![](../assets/journeyuc1_17.png)

1. 切り替えボタンをクリ **[!UICONTROL Test]**ックし、テストプロファイルを使用して遍歴をテストします。 エラーが発生した場合は、テストモードを非アクティブ化し、ジャーニーを変更して、もう一度テストします。 For more information on the test mode, refer to[](../building-journeys/testing-the-journey.md).

   ![](../assets/journeyuc1_18bis.png)

1. テストが決定的な場合は、右上のドロップダウンメニューからジャーニーを公開できます。

   ![](../assets/journeyuc1_18.png)

次回、女性がスパビーコンの近くを歩くと、「スパディスカウント」のパーソナライズされたメールがすぐに届きます。
