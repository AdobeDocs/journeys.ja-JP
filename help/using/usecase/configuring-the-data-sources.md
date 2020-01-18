---
title: データソースの設定
description: 高度なジャーニー用のデータソースの設定方法を説明します。
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


# データソースの設定 {#concept_vml_hdy_w2b}

使用事例では、メッセージに対してパーソナライゼーションデータを使用します。 また、その人が忠誠度のメンバーで、過去24時間以内に連絡がないかどうかを確認する必要があります。 この情報は、リアルタイム顧客プロファイルデータベースに保存されます。 技術ユ **ーザーは** 、Experience Platformのデータソースを設定して、これらのフィールドを取得する必要があります。

データソースの設定の詳細については、を参照してくださ [](../datasource/about-data-sources.md)い。

1. 上部のメニューで、タブをクリック **[!UICONTROL Data Sources]**し、組み込みのExperience Platformデータソースを選択します。

   ![](../assets/journey23.png)

1. 事前設定済みのグループフィールドで、以下のフィールドが選択されていることを確認します。

   * _人物/名前/名_
   * _人物/名前/lastName_
   * _personalEmail > address_

1. をクリック **[!UICONTROL Add a New Field Group]**し、スキーマを選**[!UICONTROL Profiles]** 択して、条件の「忠 **誠度メンバー** 」フィールドを追加します。 Loyalty **member** （忠誠度メンバ）フィールドはカスタムフィールドで、XDMに追加されました。&quot;_customer > marlton > loyaltyMember&quot;

   ![](../assets/journeyuc2_6.png)

1. をクリ **[!UICONTROL Add a New Field Group]**ックし、スキ**[!UICONTROL ExperienceEvent]** ーマを選択し、指定した期間に送信されたメッセージ数に関する条件に必要なフィールドを選択します。日付の _タイムスタンプ_ 、および _directMarketing/送信日_ /送信メッセージ数の値。

   ![](../assets/journeyuc2_7.png)

1. クリック **[!UICONTROL Save]**.

また、その人がホテルの予約システムに予約が入っているかどうかも確認する必要があります。 技術ユ **ーザーは** 、このフィールドを取得するために2つ目のデータソースを設定する必要があります。

1. データソースの一覧で、をクリックして新 **[!UICONTROL Add]**しい外部データソースを追加し、ホテルの予約システムへの接続を定義します。

   ![](../assets/journeyuc2_9.png)

1. データソースの名前と外部サービスのURLを入力します。例：https://marlton.com/reservation __

   >[!CAUTION]
   >
   >セキュリティ上の理由から、HTTPSの使用を強くお勧めします。

1. 外部サービス設定に応じて認証を設定します。 **[!UICONTROL No authentication]**、**[!UICONTROL Basic]**、ま **[!UICONTROL Custom]**たは**[!UICONTROL API key]**。 この例では、タイプに「Basic」を選択し、API呼び出しのユーザー名とパスワードを指定します。

   ![](../assets/journeyuc2_10.png)

1. 取得す **[!UICONTROL Add a New Field Group]**る情報とAPIパラメーターを定義する場合にクリックします。 例えば、パラメーター(ID)は1つだけなので、次の情報を含む1つのフィールドグループを作成する必要があります。

   * **[!UICONTROL Method]**:postメソッドまたはGETメソッドを選択します。 この例では、GETメソッドを選択します。
   * **[!UICONTROL Cache duration]**:これは、API呼び出しの頻度に応じて異なります。 私たちの場合は10分毎に予約制度が更新されます。
   * **[!UICONTROL Response Payload]**:フィールド内をク**[!UICONTROL Payload]** リックし、ペイロードの例を貼り付けます。 フィールドタイプが正しいことを確認します。 APIが呼び出されるたびに、システムはペイロード例に含まれるすべてのフィールドを取得します。 この例では、ペイロードには予約ステータスのみが含まれます。

   ```
   {
       "reservation" : true
   }
   ```

   * **[!UICONTROL Dynamic Values]**:例では、各顧客の識別に使用するキーに対応するパラメーター「id」を入力します。 このパラメーターの値は、遍歴で定義されます。
   ![](../assets/journeyuc2_11.png)

1. クリック **[!UICONTROL Save]**.

   これで、データソースが設定され、遍歴で使用できる状態になりました。
