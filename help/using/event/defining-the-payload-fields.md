---
product: adobe campaign
solution: Journey Orchestration
title: ペイロードフィールドの定義
description: ペイロードフィールドの定義方法について説明します
translation-type: tm+mt
source-git-commit: 81bb0b5da38217f9290214901c64e90d7ec2ba0e
workflow-type: tm+mt
source-wordcount: '288'
ht-degree: 21%

---


# ペイロードフィールドの定義 {#concept_yrw_3qt_52b}

ペイロード定義を使用すると、遍歴の中でイベントから受け取ると予想される情報と、イベントに関連付けられている人を識別する鍵を選択できます。 ペイロードは、Experience CloudXDMフィールド定義に基づきます。 For more information on XDM, refer to [this page](https://docs.adobe.com/content/help/ja-JP/experience-platform/xdm/home.html).

1. リストからXDMスキーマを選択し、「 **[!UICONTROL Payload]** 」フィールドまたは **[!UICONTROL 「Edit]** 」アイコンをクリックします。

   ![](../assets/journey8.png)

   スキーマで定義されているすべてのフィールドが表示されます。 フィールドのリストは、スキーマによって異なります。特定のフィールドを検索するか、フィルターを使用してすべてのノードとフィールドを表示するか、選択したフィールドのみを表示するかを指定できます。 スキーマ定義によって、一部のフィールドが必須で、事前に選択されている場合があります。選択を解除することはできません。

   >[!NOTE]
   >
   >XDMスキーマに「オーケストレーション」ミックスインが追加されていることを確認してください。 これにより、使用するスキーマに、使用する必要のあるすべての情報が確実に含まれ [!DNL Journey Orchestration]ます。

   ![](../assets/journey9.png)

1. イベントから受け取るフィールドを選択します。 これらはビジネスユーザーがこの遍歴で活用するフィールドです。 また、イベントに関連付けられた人物を識別するために使用されるキーも含める必要があります( [このページを参照](../event/defining-the-event-key.md))。

   ![](../assets/journey10.png)

   >[!NOTE]
   >
   >システム生成イベントの場合、 **[!UICONTROL eventID]** ( [!DNL Journey Orchestration] eventID)フィールドが選択したフィールドのリストに自動的に追加され、イベントを識別できるようになります。 イベントをプッシュするシステムでは ID を生成せずに、ペイロードプレビューにある ID を使用する必要があります。[このページ](../event/previewing-the-payload.md)を参照してください。

1. 必要なフィールドの選択が完了したら、「 **[!UICONTROL 保存]** 」をクリックするか、 **[!UICONTROL Enterキーを押します]**。

   ![](../assets/journey11.png)

   選択したフィールドの数が「 **[!UICONTROL ペイロード]** 」フィールドに表示されます。

   ![](../assets/journey12.png)
