---
product: adobe campaign
title: ペイロードフィールドの定義
description: ペイロードフィールドの定義方法を学ぶ
feature: Journeys
role: User
level: Intermediate
exl-id: 9d385b64-46cd-489b-9c18-352fa2a2dbba
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '300'
ht-degree: 84%

---

# ペイロードフィールドの定義 {#concept_yrw_3qt_52b}

ペイロード定義を使用すると、ジャーニーのイベントからシステムが受け取ると想定される情報と、イベントに関連付けられている人を識別するためのキーを選択できます。ペイロードは Experience Cloud XDM フィールド定義に基づいています。XDM について詳しくは、[このページ](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=ja)を参照してください。

1. リストから XDM スキーマを選択し、「**[!UICONTROL ペイロード]**」フィールドまたは&#x200B;**[!UICONTROL 編集]**&#x200B;アイコンをクリックします。

   ![](../assets/journey8.png)

   スキーマで定義されているすべてのフィールドが表示されます。フィールドのリストは、スキーマによって異なります。特定のフィールドを検索し、フィルターを使用してすべてのノードとフィールドを表示、または選択したフィールドのみを表示できます。スキーマ定義によっては、一部のフィールドが必須となっており、事前に選択されている場合があります。選択を解除することはできません。Journey Orchestrationがイベントを適切に受け取るために必須のフィールドはすべて、デフォルトで選択されます。

   >[!NOTE]
   >
   >XDM スキーマに「オーケストレーション」Mixin が追加されていることを確認してください。これにより、[!DNL Journey Orchestration] と連携するために必要な情報がスキーマにすべて含まれるようになります。

   ![](../assets/journey9.png)

1. イベントから受け取るフィールドを選択します。これらは、ビジネスユーザーがジャーニーで活用するフィールドです。また、イベントに関連付けられた人物を識別するために使用するキーも含める必要があります（[ このページ ](../event/defining-the-event-key.md) を参照）。

   ![](../assets/journey10.png)

   >[!NOTE]
   >
   >システム生成イベントの場合は、[!DNL Journey Orchestration] がイベントを識別できるよう、選択されたフィールドのリストに **[!UICONTROL eventID]** フィールドが自動的に追加されます。イベントをプッシュするシステムでは ID を生成しないため、ペイロードプレビューにある ID を使用する必要があります。[このページ](../event/previewing-the-payload.md)を参照してください。

1. 必要なフィールドの選択が完了したら、「**[!UICONTROL 保存]**」をクリックするか、**[!UICONTROL Enter]** キーを押します。

   ![](../assets/journey11.png)

   選択したフィールドの数が「**[!UICONTROL ペイロード]**」フィールドに表示されます。

   ![](../assets/journey12.png)
