---
title: 'Adobe Experience Platformデータソース '
description: 'Adobe Experience Platformデータソースの設定方法を説明します。 '
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
source-git-commit: 7e69b19f2b7099e5c015dd1052a58728cf143ffa

---


# Adobe Experience Platform data source {#concept_zrb_nqt_52b}

エクスペリエンスプラットフォームデータソースは、Real-time Customer Profile Serviceへの接続を定義します。 このデータソースは組み込みで、事前設定されています。 削除できません。 このデータソースは、Real-time Customer Profile Serviceからデータを取得して使用するように設計されています（例えば、旅行に参加した人が女性であるかどうかを確認します）。 プロファイルデータとエクスペリエンスイベントデータを使用できます。 Real-time Customer Profile Serviceの詳細については、このページを参照してく [ださい](https://www.adobe.io/apis/cloudplatform/dataservices/profile-identity-segmentation/profile-identity-segmentation-services.html#!api-specification/markdown/narrative/technical_overview/unified_profile_architectural_overview/unified_profile_architectural_overview.md)。

>[!NOTE]
>
>1年未満で作成された最新の1,000件のエクスペリエンスイベントを取得できます。

Real-time Customer Profile Serviceへの接続を許可するには、キーを使用して個人を識別し、キーを変換する名前空間を使用する必要があります。 その結果、このデータソースは、キーと名前空間を含むイベントでジャーニーが開始する場合にのみ使用できます。 [](../building-journeys/journey.md)を参照してください。

「ProfileFieldGroup」という名前の事前設定済みのフィールドグループを編集し、新しいフィールドグループを追加して、ドラフトまたはライブジャーニーで使用されていないフィールドグループを削除できます。 [](../datasource/field-groups.md)を参照してください。

フィールドグループを組み込みデータソースに追加する主な手順は次のとおりです。

1. データソースのリストから、組み込みのExperience Platformデータソースを選択します。

   画面の右側にデータソース設定ペインが開きます。

   ![](../assets/journey23.png)

1. をクリッ **[!UICONTROL Add a New Field Group]**クして、取得する一連の新しいフィールドを定義します。[](../datasource/field-groups.md)を参照してください。

   ![](../assets/journey24.png)

1. ドロップダウンからスキーマ **[!UICONTROL Schema]**を選択します。 このフィールドには、プラットフォームで使用可能なプロファイルおよびエクスペリエンスイベントのスキーマが表示されます。 スキーマの作成がJureny Orchestrationで実行されません。 データプラットフォームで実行されます。
1. 使用するフィールドを選択します。
1. キャッシュの時間を定義します。
1. をクリックしま **[!UICONTROL Save]**す。

フィールドグループ名にカーソルを置くと、右側に2つのアイコンが表示されます。 フィールドグループを削除および複製できます。 アイコンは、フ **[!UICONTROL Delete]**ィールドグループがライブまたはドラフトの遍歴（フィールドに表示される情報）で使用されていない場合にのみ使用で**[!UICONTROL Used in]** きます。
