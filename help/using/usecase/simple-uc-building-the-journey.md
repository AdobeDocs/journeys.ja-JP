---
product: adobe campaign
solution: Journey Orchestration
title: ジャーニーの構築
description: シンプルなユースケースのジャーニーの構築方法を説明します
feature: Journeys
role: Business Practitioner
level: Intermediate
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '415'
ht-degree: 100%

---


# ジャーニーの構築{#concept_eyw_mcy_w2b}

**ビジネスユーザー**&#x200B;はジャーニーを構築できるようになりました。ジャーニーに含まれるパスは 1 つだけで、アクティビティは以下です。

* 「SpaBeacon」**[!UICONTROL イベント]**：ユーザーがスパビーコンの近くを歩くと、イベントが送信され、そのユーザーのジャーニーが開始します。
* ユーザーが女性であるかを調べる&#x200B;**[!UICONTROL 条件]**&#x200B;アクティビティ
* **[!UICONTROL E メール]**&#x200B;アクティビティ（Adobe Campaign Standard を使用）
* **[!UICONTROL 終了]**&#x200B;アクティビティ

>[!NOTE]
>
>**[!UICONTROL プッシュ]**&#x200B;アクティビティと **[!UICONTROL E メール]**&#x200B;アクティビティは、Adobe Campaign Standard がある場合にのみパレットで使用できます。

ジャーニーの作成方法について詳しくは、[このページ](../building-journeys/journey.md)を参照してください。

1. 上部のメニューで、「**[!UICONTROL ホーム]**」タブをクリックし、「**[!UICONTROL 作成]**」をクリックして新しいジャーニーを作成します。

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

1. **[!UICONTROL E メール]**&#x200B;アクティビティをドロップし、「Spa 割引」トランザクションメッセージテンプレートを選択します。このテンプレートは Adobe Campaign を使用して設計されています。この[ページ](https://docs.adobe.com/content/help/ja-JP/campaign-standard/using/communication-channels/transactional-messaging/about-transactional-messaging.html)を参照してください。

   ![](../assets/journeyuc1_13.png)

1. 「**[!UICONTROL E メール]**」フィールド内をクリックし、データソースから E メールアドレスを選択します。

   ![](../assets/journeyuc1_14.png)

1. 同じように、データソースの姓と名のパーソナライゼーションフィールドを定義します。

   ![](../assets/journeyuc1_15.png)

1. **[!UICONTROL 終了]**&#x200B;アクティビティをドロップします。

   ![](../assets/journeyuc1_17.png)

1. 「**[!UICONTROL テスト]**」トグルをクリックして、テストプロファイルを使用してジャーニーをテストします。エラーが発生した場合は、テストモードを非アクティブ化し、ジャーニーを変更して再度テストします。テストモードについて詳しくは、[このページ](../building-journeys/testing-the-journey.md)を参照してください。

   ![](../assets/journeyuc1_18bis.png)

1. テストの最終的な結果が得られたら、右上のドロップダウンメニューからジャーニーを公開できます。

   ![](../assets/journeyuc1_18.png)

次回、女性がスパビーコンの近くを歩くと、パーソナライズされた「スパ割引」メールがすぐに届きます。
