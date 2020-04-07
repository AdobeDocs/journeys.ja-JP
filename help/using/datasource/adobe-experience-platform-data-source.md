---
title: 'Adobe Experience Platform データソース '
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
source-git-commit: e579936cfe5eb43caf72627004f98a5746c7abb1

---


# Adobe Experience Platform データソース {#concept_zrb_nqt_52b}

Experience Platformデータソースは、Real-time Customer Platform Serviceへの接続を定義します。プロファイルは、 このデータソースは組み込まれ、事前設定されています。 削除できません。 このデータソースは、Real-time Customer Customer Serviceからデータを取得し、使用するように設計されています（例えば、旅行に参加した人が女性であるかどうかを確認します）。 これにより、エクスペリエンスデータとプロファイルイベントデータを使用できます。 Real-time Customer Serviceの詳細については、このページを参照してく [ださい](https://docs.adobe.com/content/help/en/experience-platform/profile/home.html)。

>[!NOTE]
>
>1年未満で作成された最新の1,000件のエクスペリエンスイベントを取得できます。

Real-time Customer Conter Serviceへの接続を可能にするには、キーを使用して個人を特定し、キーを変換する名前空間を使用する必要があります。 その結果、このデータソースは、キーと名前空間を含むイベントを持つジャーニー開始の場合にのみ使用できます。 [](../building-journeys/journey.md)を参照してください。

「ProfileFieldGroup」という名前の事前設定済みのフィールドグループを編集し、新しいフィールドグループを追加し、ドラフトまたはライブジャーニーで使用されていないフィールドグループを削除できます。 [](../datasource/field-groups.md)を参照してください。

フィールドグループを組み込みデータソースに追加する主な手順は、次のとおりです。

1. データソースのリストから、組み込みのExperience Platformデータソースを選択します。

   画面の右側にデータソース設定ウィンドウが開きます。

   ![](../assets/journey23.png)

1. をクリック **[!UICONTROL Add a New Field Group]** して、取得する一連の新しいフィールドを定義します。 [](../datasource/field-groups.md)を参照してください。

   ![](../assets/journey24.png)

1. ドロップダウンからスキーマ **[!UICONTROL Schema]** を選択します。 このフィールドリストプロファイルおよびエクスペリエンスイベントスキーマは、プラットフォームで使用できます。 スキーマの作成は、Jureny Orchestrationでは実行されません。 データプラットフォームで実行されます。
1. 使用するフィールドを選択します。
1. キャッシュの期間を定義します。
1. をクリックしま **[!UICONTROL Save]**&#x200B;す。

フィールドグループの名前にカーソルを置くと、右側に2つのアイコンが表示されます。 フィールドグループの削除と重複が可能です。 アイコンは、フ **[!UICONTROL Delete]** ィールドグループがライブまたはドラフトのどの遍歴（フィールドに表示される情報）でも使用されていない場合にのみ使用 **[!UICONTROL Used in]** できます。
