---
title: データソースの設定
description: 高度な使用例の遍歴に使用するデータソースの設定方法を学びます。
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: tm+mt
source-git-commit: b852c08a488a1bec02b8b31a1fccf1a8773b99af
workflow-type: tm+mt
source-wordcount: '493'
ht-degree: 15%

---


# データソースの設定 {#concept_vml_hdy_w2b}

アドビの使用事例では、メッセージに対してパーソナライゼーションデータを使用します。 また、その人が忠誠度のメンバーで、過去24時間に連絡がなかったかどうかも確認する必要があります。 この情報は、リアルタイム顧客プロファイルデータベースに保存されます。 **技術ユーザーは** 、Adobe Experience Platformのデータソースを設定してこれらのフィールドを取得する必要があります。

データソースの設定の詳細については、を参照してください [](../datasource/about-data-sources.md)。

1. 上部のメニューで、「 **[!UICONTROL データソース]** 」タブをクリックし、組み込みのAdobe Experience Platformデータソースを選択します。

   ![](../assets/journey23.png)

1. 事前設定済みのグループフィールドで、次のフィールドが選択されていることを確認します。

   * _人物/名前/名_
   * _人物/名前/lastName_
   * _personalEmail > address_

1. 「新しいフィ **[!UICONTROL ールドグループ]**」をクリックし、 **[!UICONTROL プロファイル]** スキーマを選択して、条件に「 **忠誠度メンバ** 」フィールドを追加します。 Loyaltyメンバ **ー** ・フィールドはカスタム・フィールドで、XDMに追加されました。&quot;_customer > marlton > loyaltyMember&quot;

   ![](../assets/journeyuc2_6.png)

1. 「新しいフィ **[!UICONTROL ールドグループ]**」をクリックし **[!UICONTROL 、ExperienceEvent]** スキーマを選択し、指定した期間に送信されるメッセージの数に関して、条件に応じて必要なフィールドを選択します。 _日付のタイムスタンプ_ 、および _directMarketing/送信日/送信日_ ：送信されたメッセージ数の値。

   ![](../assets/journeyuc2_7.png)

1. 「**[!UICONTROL 保存]**」をクリックします。

ホテルの予約システムに予約が入っているかどうかも確認する必要があります。 **技術ユーザーは** 、このフィールドを取得するために2つ目のデータソースを設定する必要があります。

1. データソースのリストで、をクリックし **** 追加、新しい外部データソースを追加してホテル予約システムへの接続を定義します。

   ![](../assets/journeyuc2_9.png)

1. データソースの名前と外部サービスのURLを入力します。次に例を示します。 _https://marlton.com/reservation_

   >[!CAUTION]
   >
   >セキュリティ上の理由から、HTTPS の使用を強くお勧めします。

1. 外部サービスの設定に応じて認証を&#x200B;**[!UICONTROL 認証なし]**、**[!UICONTROL 基本]**、**[!UICONTROL カスタム]**、**[!UICONTROL API キー]**&#x200B;に設定します。この例では、タイプに「基本」を選択し、API呼び出しのユーザー名とパスワードを指定します。

   ![](../assets/journeyuc2_10.png)

1. 「 **[!UICONTROL 追加New Field Group]** 」をクリックして、取得する情報とAPIパラメーターを定義します。 この例では、パラメーター(id)は1つだけなので、次の情報を含む1つのフィールドグループを作成する必要があります。

   * **[!UICONTROL メソッド]**：POST または GET メソッドを選択します。ここでは GET メソッドを選択します。
   * **[!UICONTROL キャッシュ期間]**:これは、API呼び出しの頻度に応じて変わります。 当社の場合、予約制度は10分ごとに更新されます。
   * **[!UICONTROL 応答ペイロード]**:「 **[!UICONTROL ペイロード]** 」フィールド内をクリックし、ペイロードの例を貼り付けます。 フィールドタイプが正しいことを確認します。API が呼び出されるたびに、ペイロードの例に含まれるすべてのフィールドが取得されます。この例では、ペイロードには予約ステータスのみが含まれます。

   ```
   {
       "reservation" : true
   }
   ```

   * **[!UICONTROL 動的値]**:例では、各顧客の識別に使用するキーに対応するパラメータ(「id」)を入力します。 このパラメーターの値は、遍歴で定義されます。

   ![](../assets/journeyuc2_11.png)

1. 「**[!UICONTROL 保存]**」をクリックします。

   これで、データソースが設定され、遍歴で使用できる状態になります。
