---
product: adobe campaign
title: ジャーニーの構築 — Advanced
description: '高度なユースケースのジャーニーの構築方法を説明します '
feature: Journeys
role: User
level: Intermediate
exl-id: cca6ed3c-e151-4494-9e2d-9ed504bfc54b
source-git-commit: 9db330405130b14d1d8a8cbed59f612fd1f6767b
workflow-type: tm+mt
source-wordcount: '914'
ht-degree: 99%

---

# ジャーニーの構築 {#concept_owm_kdy_w2b}

**ビジネスユーザー**&#x200B;はジャーニーを構築できるようになります。ジャーニーには以下のアクティビティが含まれます。

* 2 つの&#x200B;**[!UICONTROL イベント]**&#x200B;アクティビティ：「LobbyBeacon」および「RestaurantBeacon」
* 2 つの&#x200B;**[!UICONTROL 条件]**&#x200B;アクティビティ
* 3 つの&#x200B;**[!UICONTROL プッシュ]**&#x200B;アクティビティと 1 つの&#x200B;**[!UICONTROL 電子メール]**&#x200B;アクティビティ（Adobe Campaign Standard を使用）
* **[!UICONTROL 待機]**&#x200B;アクティビティ
* 4 つの&#x200B;**[!UICONTROL エンド]**&#x200B;アクティビティ

>[!NOTE]
>
>**[!UICONTROL プッシュ]**&#x200B;アクティビティと&#x200B;**[!UICONTROL 電子メール]**&#x200B;アクティビティは、Adobe Campaign Standard がある場合にのみパレットで使用できます。

ジャーニーの作成方法について詳しくは、[このページ](../building-journeys/journey.md)を参照してください。

## 最初の手順{#section_ntb_ws1_ffb}

1. 上部のメニューで、「**[!UICONTROL ホーム]**」タブをクリックし、「**[!UICONTROL 作成]**」をクリックして新しいジャーニーを作成します。

   ![](../assets/journey31.png)

1. 右側に表示される設定ペインで、ジャーニーのプロパティを編集します。名前を付け、12 月 1 日から 12 月 31 日まで、1 か月間継続するように設定します。

   ![](../assets/journeyuc2_12.png)

1. パレットから「LobbyBeacon」イベントをキャンバスにドラッグ&amp;ドロップして、ジャーニーのデザインを開始します。パレット内のイベントをダブルクリックしてキャンバスに追加することもできます。

   ![](../assets/journeyuc2_13.png)

1. ここで、その人が過去 24 時間以内に連絡を受けていないことを確認する条件を追加し、その人がロイヤルティメンバーかどうかも確認します。ジャーニーに条件アクティビティをドラッグ＆ドロップします。

   ![](../assets/journeyuc2_14.png)

1. 「**[!UICONTROL データソースの条件]**」タイプを選択し、「**[!UICONTROL 式]**」フィールドをクリックします。また、キャンバス上の矢印に表示される「条件」ラベルを定義することもできます。この例では、「条件 1」を「ロイヤルティメンバー」に置き換えます。

   ![](../assets/journeyuc2_15.png)

1. 「**[!UICONTROL 詳細設定モード]**」をクリックし、Adobe Experience Platform データソースから取得した「timestamp」フィールドと「directMarketing.sends.value」フィールドに基づいて、次の条件を定義します。式の構文は次のとおりです。

   ```
   count(#{ExperiencePlatformDataSource.MarltonExperience.experienceevent.all(
       currentDataPackField.directMarketing.sends.value > 0 and
       currentDataPackField.timestamp > nowWithDelta(-1, "days")).timestamp}) == 0
   and
       #{ExperiencePlatformDataSource.MarltonProfiles.Profile._customer.marlton.loyaltyMember}
   ```

   ![](../assets/journeyuc2_30.png)

1. 「**[!UICONTROL パスを追加]**」ボタンをクリックし、過去 24 時間以内に連絡を受けておらず、ロイヤルティメンバーではない顧客の 2 番目のパスを作成します。パスに「非ロイヤルティメンバー」という名前を付けます。式の構文は次のとおりです。

   ```
   count(#{ExperiencePlatformDataSource.MarltonExperience.experienceevent.all(
       currentDataPackField.directMarketing.sends.value > 0 and
       currentDataPackField.timestamp > nowWithDelta(-1, "days").timestamp}) == 0
   and not
       #{ExperiencePlatformDataSource.MarltonProfiles.Profile._customer.marlton.loyaltyMember}
   ```

   >[!NOTE]
   >
   >式の 2 番目の部分の「Profile」は任意に指定します。

1. 名前空間を選択する必要があります。名前空間は、スキーマのプロパティに基づいて事前に選択されます。あらかじめ選択されているものを、選択したままにすることができます。名前空間の詳細については、[このページ](../event/selecting-the-namespace.md)を参照してください。

このユースケースでは、この 2 つの条件にのみ反応したいので、「**[!UICONTROL 上記以外の他の事例のパスを表示]**」チェックボックスはオフにします。

条件の後に 2 つのパスが作成されます。

* _過去 24 時間に連絡を受けていない、ロイヤルティメンバーの顧客。_
* _過去 24 時間に連絡を受けていない、ロイヤルティメンバーではない顧客。_

![](../assets/journeyuc2_16.png)

## 1 番目のパス：ロイヤルティメンバーの顧客 {#section_otb_ws1_ffb}

1. 最初のパスに、予約があるかどうかを確認する条件を追加します。ジャーニーに条件アクティビティをドラッグ＆ドロップします。

   ![](../assets/journeyuc2_17.png)

1. 「**[!UICONTROL データソースの条件]**」タイプを選択し、予約システムから取得した予約ステータス情報に基づいて条件を定義します。

   ```
   #{MarltonReservation.MarltonFieldGroup.reservation} == true
   ```

   ![](../assets/journeyuc2_18.png)

1. 外部データソースからのフィールドを選択すると、画面の右側に外部データソースの設定時に定義したパラメーターのリストが表示されます（[このページ](../usecase/configuring-the-data-sources.md)を参照）。パラメーター名をクリックし、予約システムキーの値（この例では Experience Cloud ID）を定義します。

   ```
   @{LobbyBeacon.endUserIDs._experience.mcid.id}
   ```

   ![](../assets/journeyuc2_19.png)

1. また、予約をしていない顧客にも反応したいので、「**[!UICONTROL 上記以外の他の事例のパスを表示]**」チェックボックスをオンにする必要があります。

   ![](../assets/journeyuc2_20.png)

   次の 2 つのパスが作成されます。

   * _部屋を予約してある顧客_
   * _部屋を予約していない顧客_

   ![](../assets/journeyuc2_21.png)

1. 最初のパス（部屋を予約済み）に、**[!UICONTROL プッシュ]**&#x200B;アクティビティをドロップし、モバイルアプリと「ウェルカム」テンプレートを選択します。

   ![](../assets/journeyuc2_22.png)

1. プッシュを送信するためにシステムで必要な「**[!UICONTROL ターゲット]**」フィールドを定義します。

   * **[!UICONTROL プッシュプラットフォーム]**：**[!UICONTROL Apple Push Notification Server]**（Apple）または **[!UICONTROL Firebase Cloud Messaging]**（Android）、いずれかのプラットフォームを選択します。
   * **[!UICONTROL 登録トークン]**：詳細設定モードを使用して、（設定済みのイベントに基づいて）以下の式を追加します。

      ```
      @{LobbyBeacon._experience.campaign.message.profileSnapshot.pushNotificationTokens.first().token}
      ```

1. プッシュ通知パーソナライゼーションフィールドを定義します。この例では、姓と名です。

1. 「RestaurantBeacon」イベントを追加します。

   ![](../assets/journeyuc2_23.png)

1. 新しい&#x200B;**[!UICONTROL プッシュ]**&#x200B;アクティビティを追加して、「食事割引」テンプレートを選択し、「**[!UICONTROL アドレス]**」フィールドと「**[!UICONTROL パーソナライゼーション]**」フィールドを定義します。**[!UICONTROL 終了]**&#x200B;アクティビティを追加します。

   ![](../assets/journeyuc2_24.png)

1. 「ウェルカム」プッシュから 6 時間以内にレストランに入った場合にのみ「食事割引」プッシュ通知を送信します。これをおこなうには、待機アクティビティを使用する必要があります。「ウェルカム」プッシュアクティビティにポインターを合わせ、「+」記号をクリックします。新しいパスに待機アクティビティを追加し、期間を 6 時間に定義します。最初の有効なアクティビティが選択されます。「ウェルカム」プッシュから 6 時間未満にレストランのイベントが受信された場合は、プッシュアクティビティが送信されます。さらに次の 6 時間以内にレストランのイベントが受信されない場合は、待機が選択されます。待機アクティビティの後に、**[!UICONTROL 終了]**&#x200B;アクティビティを配置します。

   ![](../assets/journeyuc2_31.png)

1. 予約条件に従う 2 番目のパス（部屋を予約していない）に、**[!UICONTROL プッシュ]**&#x200B;アクティビティを追加し、「客室レート」テンプレートを選択します。**[!UICONTROL 終了]**&#x200B;アクティビティを追加します。

   ![](../assets/journeyuc2_25.png)

## 2 番目のパス：ロイヤルティメンバーではない顧客{#section_ptb_ws1_ffb}

1. 最初の条件に続く 2 番目のパス（顧客がロイヤルティメンバーではない）で、**[!UICONTROL 電子メール]**アクティビティを追加し、「ロイヤルティメンバーシップ」テンプレートを選択します。


   ![](../assets/journeyuc2_26.png)

1. 「**[!UICONTROL アドレス]**」フィールドで、データソースからメールアドレスを選択します。


   ![](../assets/journeyuc2_27.png)

1. データソースの姓と名のパーソナライゼーションフィールドを定義します。

   ![](../assets/journeyuc2_28.png)

1. **[!UICONTROL 終了]**&#x200B;アクティビティを追加します。

「**[!UICONTROL テスト]**」切替スイッチをクリックして、ジャーニーをテストします。エラーがある場合は、テストモードを無効にし、ジャーニーを修正してから再度テストします。テストモードについて詳しくは、[このページ](../building-journeys/testing-the-journey.md)を参照してください。

![](../assets/journeyuc2_32bis.png)

最終的にテストに合格した後は、右上のドロップダウンメニューからジャーニーを公開できます。

![](../assets/journeyuc2_32.png)
