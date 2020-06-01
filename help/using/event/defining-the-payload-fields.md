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
workflow-type: tm+mt
source-wordcount: '285'
ht-degree: 5%

---


# ペイロードフィールドの定義 {#concept_yrw_3qt_52b}

ペイロード定義を使用すると、遍歴の中でイベントから受け取ると予想される情報と、イベントに関連付けられている人を識別する鍵を選択できます。 ペイロードは、Experience Cloud XDMフィールドの定義に基づいています。 For more information on XDM, refer to this [page](https://docs.adobe.com/content/help/ja-JP/experience-platform/xdm/home.html).

1. リストからXDMスキーマを選択し、「 **[!UICONTROL Payload]** 」フィールドまたは **[!UICONTROL 「Edit]** 」アイコンをクリックします。

   ![](../assets/journey8.png)

   スキーマで定義されているすべてのフィールドが表示されます。 フィールドのリストは、スキーマによって異なります。 特定のフィールドを検索するか、フィルターを使用してすべてのノードとフィールドを表示するか、選択したフィールドのみを表示するかを指定できます。 スキーマ定義によると、一部のフィールドが必須で、事前に選択されている場合があります。 選択を解除することはできません。

   >[!NOTE]
   >
   >XDMスキーマに「オーケストレーション」ミックスインが追加されていることを確認してください。 これにより、Journey Orchestrationで作業するために必要な情報がスキーマにすべて含まれるようになります。

   ![](../assets/journey9.png)

1. イベントから受け取るフィールドを選択します。 これらはビジネスユーザーがこの遍歴で活用するフィールドです。 また、イベントに関連付けられた人物を識別するために使用されるキーを含める必要があります(を参照 [](../event/defining-the-event-key.md))。

   ![](../assets/journey10.png)

   >[!NOTE]
   >
   >Journey Orchestrationが **[!UICONTROL イベントを識別できるように、選択したフィールドのリストに]** eventID（イベントID）フィールドが自動的に追加されます。 イベントをプッシュするシステムではIDを生成しない。ペイロードプレビューで使用できるIDを使用する必要がある。 [](../event/previewing-the-payload.md)を参照してください。

1. 必要なフィールドの選択が完了したら、「 **[!UICONTROL 保存]** 」をクリックするか、 **[!UICONTROL Enterキーを押します]**。

   ![](../assets/journey11.png)

   選択したフィールドの数が「 **[!UICONTROL ペイロード]** 」フィールドに表示されます。

   ![](../assets/journey12.png)
