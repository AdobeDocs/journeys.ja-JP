---
product: adobe campaign
solution: Journey Orchestration
title: ペイロードフィールドの定義
description: ペイロードフィールドの定義方法について説明します
translation-type: tm+mt
source-git-commit: a515e052a5bc1359632a1829df70a206614a5bb2
workflow-type: tm+mt
source-wordcount: '307'
ht-degree: 19%

---


# ペイロードフィールドの定義 {#concept_yrw_3qt_52b}

ペイロード定義を使用すると、ジャーニー内のイベントからシステムが受け取ると想定する情報と、イベントに関連付けられている人を識別するためのキーを選択できます。 ペイロードは、Experience CloudXDMフィールド定義に基づきます。 XDMの詳細は、[このページ](https://docs.adobe.com/content/help/ja-JP/experience-platform/xdm/home.html)を参照してください。

1. リストからXDMスキーマを選択し、「**[!UICONTROL Payload]**」フィールドまたは&#x200B;**[!UICONTROL Edit]**&#x200B;アイコンをクリックします。

   ![](../assets/journey8.png)

   スキーマで定義されているすべてのフィールドが表示されます。 フィールドのリストは、スキーマによって異なります。特定のフィールドを検索するか、フィルターを使用してすべてのノードとフィールドを表示するか、選択したフィールドのみを表示するかを指定できます。 スキーマ定義によって、一部のフィールドが必須で、事前に選択されている場合があります。選択を解除することはできません。 Journey Orchestrationがイベントを適切に受け取るために必須のフィールドはすべて、デフォルトで選択されます。

   >[!NOTE]
   >
   >XDMスキーマに「オーケストレーション」ミックスインが追加されていることを確認してください。 これにより、[!DNL Journey Orchestration]と連携するために必要な情報がスキーマにすべて含まれるようになります。

   ![](../assets/journey9.png)

1. イベントから受け取るフィールドを選択します。 これらは、ビジネスユーザーがジャーニーで活用するフィールドです。 また、イベントに関連付けられた人物を識別するために使用されるキーも含める必要があります（[このページ](../event/defining-the-event-key.md)を参照）。

   ![](../assets/journey10.png)

   >[!NOTE]
   >
   >システム生成イベントの場合、**[!UICONTROL eventID]**&#x200B;フィールドが選択されたフィールドのリストに自動的に追加され、[!DNL Journey Orchestration]がイベントを識別できるようになります。 イベントをプッシュするシステムでは ID を生成せずに、ペイロードプレビューにある ID を使用する必要があります。[このページ](../event/previewing-the-payload.md)を参照してください。

1. 必要なフィールドの選択が完了したら、「**[!UICONTROL 保存]**」をクリックするか、**[!UICONTROL Enter]**&#x200B;キーを押します。

   ![](../assets/journey11.png)

   選択したフィールドの数が&#x200B;**[!UICONTROL ペイロード]**&#x200B;フィールドに表示されます。

   ![](../assets/journey12.png)
