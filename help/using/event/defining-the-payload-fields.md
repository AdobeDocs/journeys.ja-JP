---
title: ペイロードフィールドの定義
description: ペイロードフィールドの定義方法について説明します
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


# ペイロードフィールドの定義 {#concept_yrw_3qt_52b}

ペイロード定義を使用すると、遍歴の中でシステムがイベントから受け取ると予想される情報を選択し、イベントに関連付けられている人を識別するキーを選択できます。 ペイロードは、Experience Cloud XDMフィールドの定義に基づいています。 For more information on XDM, refer to this [page](https://www.adobe.io/apis/cloudplatform/dataservices/xdm.html).

1. リストからXDMスキーマを選択し、フィールドまたはアイコ **[!UICONTROL Payload]**ンをクリック**[!UICONTROL Edit]** します。

   ![](../assets/journey8.png)

   スキーマに定義されているすべてのフィールドが表示されます。 フィールドのリストはスキーマによって異なります。 特定のフィールドを検索したり、フィルターを使用してすべてのノードとフィールドを表示したり、選択したフィールドのみを表示したりできます。 スキーマ定義によっては、一部のフィールドが必須であり、事前に選択されている場合があります。 選択を解除することはできません。

   >[!NOTE]
   >
   >XDMスキーマに「オーケストレーション」ミックスインが追加されていることを確認します。 これにより、スキーマにJargeny Orchestrationを使用するために必要なすべての情報が含まれるようになります。

   ![](../assets/journey9.png)

1. イベントから受け取る予定のフィールドを選択します。 これらは、ビジネス・ユーザーが遍歴で活用するフィールドです。 また、イベントに関連付けられた個人を識別するために使用されるキーを含める必要があります(を参照 [](../event/defining-the-event-key.md))。

   ![](../assets/journey10.png)

   >[!NOTE]
   >
   >このフ **[!UICONTROL eventID]**ィールドは、Jargeny Orchestrationがイベントを識別できるように、選択したフィールドのリストに自動的に追加されます。 イベントをプッシュするシステムではIDを生成しないでください。ペイロードプレビューで使用できるIDを使用する必要があります。[](../event/previewing-the-payload.md)を参照してください。

1. 必要なフィールドの選択が完了したら、をクリックするか、を **[!UICONTROL Save]**押しま**[!UICONTROL Enter]**&#x200B;す。

   ![](../assets/journey11.png)

   選択したフィールドの数がフィールドに表示さ **[!UICONTROL Payload]**れます。

   ![](../assets/journey12.png)
