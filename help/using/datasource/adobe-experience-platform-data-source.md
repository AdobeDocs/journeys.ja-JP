---
product: adobe campaign
title: Adobe Experience Platform のデータソース
description: Adobe Experience Platform データソースの設定方法を学ぶ
feature: Journeys
role: User
level: Intermediate
exl-id: 847fa819-2b92-49e5-8a5e-4f3f0acd5e35
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '401'
ht-degree: 66%

---

# Adobe Experience Platform のデータソース {#concept_zrb_nqt_52b}


>[!CAUTION]
>
>**Adobe Journey Optimizerをお探しですか** Journey Optimizerのドキュメントについては、[ こちら ](https://experienceleague.adobe.com/ja/docs/journey-optimizer/using/ajo-home){target="_blank"} をクリックしてください。
>
>
>_このドキュメントでは、Journey Optimizerに置き換えられた従来のJourney Orchestration マテリアルについて説明します。 Journey OrchestrationやJourney Optimizerへのアクセスに関するご質問は、アカウントチームにお問い合わせください。_


Adobe Experience Platform データソースは、リアルタイム顧客プロファイルサービスへの接続を定義します。 このデータソースは組み込み済みで、事前に設定されているので、削除できません。このデータソースは、リアルタイム顧客プロファイルサービスからデータを取得して使用するように設計されています（例えば、ジャーニーにエントリした人物が女性かどうかを確認します）。プロファイルデータとエクスペリエンスイベントデータを使用できます。リアルタイム顧客プロファイルサービスの詳細については、この[ページ](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=ja)を参照してください。

>[!NOTE]
>
>1 年以内に作成された最の 1,000 件のエクスペリエンスイベントを取得できます。

リアルタイム顧客プロファイルサービスへの接続を可能にするには、人物を特定するキーと、キーを説明する名前空間前を使用する必要があります。その結果、このデータソースは、ジャーニーが、キーと名前空間を含むイベントで開始する場合にのみ使用できます。[このページ](../building-journeys/journey.md)を参照してください。

「ProfileFieldGroup」という名前の事前設定済みフィールドグループを編集し、新しいグループを追加して、ドラフトまたはライブジャーニーで使用されていないフィールドグループを削除できます。 [このページ](../datasource/field-groups.md)を参照してください。

ビルトインデータソースにフィールドグループを追加する主な手順は次のとおりです。

1. データソースのリストから、ビルトインの Adobe Experience Platform データソースを選択します。

   画面の右側にデータソース設定ペインが開きます。


   ![](../assets/journey23.png)

1. 「**[!UICONTROL 新しいフィールドグループを追加]**」をクリックして、新しく取得する一連のフィールドを定義します。[このページ](../datasource/field-groups.md)を参照してください。

   ![](../assets/journey24.png)

1. **[!UICONTROL スキーマ]**&#x200B;ドロップダウンからスキーマを選択します。このフィールドには、Adobe Experience Platformで使用できるプロファイルイベントとエクスペリエンスイベントスキーマが一覧表示されます。 [!DNL Journey Orchestration] ではスキーマの作成は実行されません。Adobe Experience Platformで上演されます。
1. 使用するフィールドを選択します。
1. 「**[!UICONTROL 保存]**」をクリックします。

フィールドグループの名前にカーソルを置くと、右側に 2 つのアイコンが表示されます。 これらのアイコンを使用すると、フィールドグループを削除および複製できます。**[!UICONTROL 削除]**&#x200B;アイコンは、フィールドグループがライブジャーニーまたはドラフトジャーニー（「**[!UICONTROL 使用されている場所]**」フィールドに表示される情報）で使用されていない場合にのみ使用できます。
