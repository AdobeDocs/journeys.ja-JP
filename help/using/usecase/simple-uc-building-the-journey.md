---
product: adobe campaign
title: ジャーニーの構築 - シンプル
description: シンプルなユースケースのジャーニーの構築方法を説明します
feature: Journeys
role: User
level: Intermediate
exl-id: 22bcd7f4-03ee-4e4c-b221-9f14aeadded6
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: ht
source-wordcount: '448'
ht-degree: 100%

---

# ジャーニーの構築{#concept_eyw_mcy_w2b}


>[!CAUTION]
>
>**Adobe Journey Optimizer をお探しですか**？Journey Optimizer のドキュメントについて詳しくは、[こちら](https://experienceleague.adobe.com/ja/docs/journey-optimizer/using/ajo-home){target="_blank"}をクリックしてください。
>
>
>_このドキュメントは、Journey Optimizer に置き換えられた従来の Journey Orchestration 資料を参照しています。Journey Orchestration または Journey Optimizer へのアクセスについてご質問がある場合は、アカウントチームにお問い合わせください。_


**ビジネスユーザー**&#x200B;はジャーニーを構築できるようになりました。ジャーニーに含まれるパスは 1 つだけで、以下のアクティビティが含まれます。

* 「SpaBeacon」**[!UICONTROL イベント]**：ユーザーがスパビーコンの近くを歩くと、イベントが送信され、そのユーザーのジャーニーが開始します。
* ユーザーが女性であるかを調べる&#x200B;**[!UICONTROL 条件]**&#x200B;アクティビティ
* **[!UICONTROL 電子メール]**アクティビティ（Adobe Campaign Standard を使用）

* **[!UICONTROL 終了]**&#x200B;アクティビティ

>[!NOTE]
>
>**[!UICONTROL プッシュ]**&#x200B;アクティビティと&#x200B;**[!UICONTROL 電子メール]**&#x200B;アクティビティは、Adobe Campaign Standard がある場合にのみパレットで使用できます。

ジャーニーの作成方法について詳しくは、[このページ](../building-journeys/journey.md)を参照してください。

1. トップメニューで、「**[!UICONTROL ホーム]**」タブをクリックし、「**[!UICONTROL 作成]**」をクリックして新しいジャーニーを作成します。

   ![](../assets/journey31.png)

1. 右側に表示される設定ペインで、ジャーニーのプロパティを編集します。「スパジャーニー」という名前を付け、12 月 1 日から 12 月 31 日まで、1 か月間継続するように設定します。

   ![](../assets/journeyuc1_8.png)

1. パレットから「SpaBeacon」イベントをキャンバスにドラッグ＆ドロップして、ジャーニーのデザインを開始します。パレット内のイベントをダブルクリックしてキャンバスに追加することもできます。

   ![](../assets/journeyuc1_9.png)

1. 次に、そのユーザーが女性であることを確認する条件を追加します。ジャーニーに条件アクティビティをドラッグ＆ドロップします。

   ![](../assets/journeyuc1_10.png)

1. 「**[!UICONTROL データソースの条件]**」タイプを選択し、「**[!UICONTROL 式]**」フィールドをクリックします。また、キャンバス上の矢印に表示される「条件」ラベルを定義することもできます。

   ![](../assets/journeyuc1_11.png)

1. シンプルな式エディターを使用して、性別フィールド（_ユーザー／性別_）を探し、右にドロップして「性別が「女性」と同じ」という条件を作成します。

   ![](../assets/journeyuc1_12.png)

1. **[!UICONTROL 電子メール]**&#x200B;アクティビティをドロップし、「Spa 割引」トランザクションメッセージテンプレートを選択します。このテンプレートは Adobe Campaign を使用して設計されています。この[ページ](https://experienceleague.adobe.com/docs/campaign-standard/using/communication-channels/transactional-messaging/getting-started-with-transactional-msg.html?lang=ja)を参照してください。

   ![](../assets/journeyuc1_13.png)

1. 「**[!UICONTROL 電子メール]**」フィールド内をクリックし、データソースからメールアドレスを選択します。


   ![](../assets/journeyuc1_14.png)

1. 同じように、データソースの姓と名のパーソナライゼーションフィールドを定義します。

   ![](../assets/journeyuc1_15.png)

1. **[!UICONTROL 終了]**&#x200B;アクティビティをドロップします。

   ![](../assets/journeyuc1_17.png)

1. 「**[!UICONTROL テスト]**」切替スイッチをクリックして、テストプロファイルを使用してジャーニーをテストします。エラーがある場合は、テストモードを無効にし、ジャーニーを修正してから再度テストします。テストモードについて詳しくは、[このページ](../building-journeys/testing-the-journey.md)を参照してください。

   ![](../assets/journeyuc1_18bis.png)

1. 最終的にテストに合格した後は、右上のドロップダウンメニューからジャーニーを公開できます。

   ![](../assets/journeyuc1_18.png)

次回、女性がスパビーコンの近くを歩くと、パーソナライズされた「スパ割引」メールがすぐに届きます。
