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
source-git-commit: e579936cfe5eb43caf72627004f98a5746c7abb1

---


# ペイロードフィールドの定義 {#concept_yrw_3qt_52b}

ペイロード定義を使用すると、イベントが遍歴の中でシステムから受け取ると予想される情報と、イベントに関連付けられている人を識別するキーを選択できます。 ペイロードは、Experience Cloud XDMフィールドの定義に基づきます。 For more information on XDM, refer to this [page](https://docs.adobe.com/content/help/en/experience-platform/xdm/home.html).

1. XDMスキーマをリストし、フィールドまたは **[!UICONTROL Payload]** アイコンをクリック **[!UICONTROL Edit]** します。

   ![](../assets/journey8.png)

   スキーマで定義されたすべてのフィールドが表示されます。 フィールドのリストは、スキーマによって異なります。 特定のフィールドを検索したり、フィルターを使用してすべてのノードとフィールドを表示したり、選択したフィールドのみを表示したりできます。 スキーマの定義によると、一部のフィールドが必須で、事前に選択されている場合があります。 選択を解除することはできません。

   >[!NOTE]
   >
   >XDMスキーマに「オーケストレーション」ミックスインが追加されていることを確認します。 これにより、スキーマに、Jureny Orchestrationを使用するために必要な情報がすべて含まれます。

   ![](../assets/journey9.png)

1. イベントから受け取るフィールドを選択します。 これらのフィールドは、ビジネスユーザーがこの遍歴で活用するフィールドです。 また、ユーザーに関連付けられた個人を識別するために使用されるキーを含める必要があります(「 [](../event/defining-the-event-key.md)」を参照)。

   ![](../assets/journey10.png)

   >[!NOTE]
   >
   >このフィ **[!UICONTROL eventID]** ールドは、Jeurney Orchestrationがリストを識別できるように、選択したフィールドのイベントに自動的に追加されます。 システムがイベントをプッシュしてもIDは生成されず、ペイロードシステムで使用可能なIDを使用する必要があります。プレビュー [](../event/previewing-the-payload.md)を参照してください。

1. 必要なフィールドの選択が完了したら、をクリックするか、を **[!UICONTROL Save]** 押しま **[!UICONTROL Enter]**&#x200B;す。

   ![](../assets/journey11.png)

   選択したフィールドの数がフィールドに表示さ **[!UICONTROL Payload]** れます。

   ![](../assets/journey12.png)
