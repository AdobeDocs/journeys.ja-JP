---
title: イベントキーの定義
description: イベントキーの定義方法を説明します。
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


# イベントキーの定義 {#concept_ond_hqt_52b}

キーは、フィールドまたはフィールドの組み合わせがイベントペイロードデータの一部であり、システムがイベントに関連付けられた人を識別できるようにします。 キーには、例えば、Experience Cloud ID、CRM ID、電子メールアドレスを使用できます。

リアルタイム顧客プロファイルデータベースに保存されたデータを活用する場合は、 [Real-time Customer Profile ServiceでプロファイルのIDとして定義した情報をイベントキーとして選択する必要があります](https://www.adobe.io/apis/cloudplatform/dataservices/profile-identity-segmentation/profile-identity-segmentation-services.html#!api-specification/markdown/narrative/technical_overview/unified_profile_architectural_overview/unified_profile_architectural_overview.md)。

これにより、イベントと個人のプロファイルの間の調整をシステムで実行できます。 プライマリIDを持つスキーマを選択した場合、およびのフィ **[!UICONTROL Key]**ールド**[!UICONTROL Namespace]** は事前入力されます。 IDが定義されていない場合は、プライマリキー _としてidentityMap_ /idを選択します。 その後、名前空間を選択する必要があります。この場合、identityMap/idを使用して、キーが（フィールドの下の） **[!UICONTROL Namespace]**事前入力&#x200B;_されます_。

CRM IDや電子メールアドレスなど、別のキーを使用する必要がある場合は、手動で追加する必要があります。

1. フィールドの内側または **[!UICONTROL Key]**鉛筆アイコンをクリックします。

   ![](../assets/journey16.png)

1. ペイロードフィールドのリストで、キーとして選択したフィールドを選択します。 高度な式エディターに切り替えて、より複雑なキー（例えば、イベントの2つのフィールドを連結したキー）を作成することもできます。 この節では、以下を参照してください。

   ![](../assets/journey20.png)

イベントを受け取ると、キーの値によって、イベントに関連付けられた人物をシステムで識別できます。 名前空間に関連付けられている場合( [](../event/selecting-the-namespace.md)参照)、Adobe Experience Platformに対するクエリーの実行にこのキーを使用できます。 [](../building-journeys/about-orchestration-activities.md)を参照してください。この鍵は、人が旅に出ているかどうかを調べるのにも使われます。 同じ旅の中で人が2つの異なる場所にいるのは無理です その結果、システムは、同じキー（例えば、キーCRMID=3224）を同じ遍歴の異なる場所に置くことを許可しません。

また、高度な式関数(**[!UICONTROL Advanced mode]**)を使用して、追加の操作を行うこともできます。 これらの関数を使用すると、形式の変更、フィールドの連結の実行など、特定のクエリを実行する際に使用する値を操作できます。これは、フィールドの一部（例えば、最初の10文字）のみを考慮に入れて行います。[](../expression/expressionadvanced.md)を参照してください。
