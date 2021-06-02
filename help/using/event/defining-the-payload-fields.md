---
product: adobe campaign
title: ペイロードフィールドの定義
description: ペイロードフィールドの定義方法について説明します
feature: ジャーニー
role: Business Practitioner
level: Intermediate
exl-id: 9d385b64-46cd-489b-9c18-352fa2a2dbba
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '308'
ht-degree: 20%

---

# ペイロードフィールドの定義 {#concept_yrw_3qt_52b}

ペイロード定義を使用すると、ジャーニーのイベントからシステムが受け取ると予想される情報と、イベントに関連付けられている人を識別するキーを選択できます。 ペイロードは、Experience CloudXDMフィールド定義に基づいています。 XDMについて詳しくは、[このページ](https://docs.adobe.com/content/help/ja-JP/experience-platform/xdm/home.html)を参照してください。

1. リストからXDMスキーマを選択し、「**[!UICONTROL ペイロード]**」フィールドまたは「**[!UICONTROL 編集]**」アイコンをクリックします。

   ![](../assets/journey8.png)

   スキーマで定義されたすべてのフィールドが表示されます。 フィールドのリストは、スキーマによって異なります。特定のフィールドを検索するか、フィルターを使用して、すべてのノードおよびフィールドを表示するか、選択したフィールドのみを表示できます。 スキーマ定義によって、一部のフィールドが必須で、事前に選択されている場合があります。選択を解除することはできません。 イベントがJourney Orchestrationで正しく受信されるために必須のフィールドは、すべてデフォルトで選択されます。

   >[!NOTE]
   >
   >「オーケストレーション」mixinがXDMスキーマに追加されていることを確認します。 これにより、[!DNL Journey Orchestration]で使用するために必要な情報がスキーマにすべて含まれるようになります。

   ![](../assets/journey9.png)

1. イベントから受け取るフィールドを選択します。 これらは、ビジネスユーザーがジャーニーで活用するフィールドです。 また、イベントに関連付けられた個人を識別するために使用するキーも含める必要があります（[このページ](../event/defining-the-event-key.md)を参照）。

   ![](../assets/journey10.png)

   >[!NOTE]
   >
   >システムで生成されたイベントの場合、**[!UICONTROL eventID]**&#x200B;フィールドが選択されたフィールドのリストに自動的に追加され、[!DNL Journey Orchestration]でイベントを識別できるようになります。 イベントをプッシュするシステムでは ID を生成せずに、ペイロードプレビューにある ID を使用する必要があります。[このページ](../event/previewing-the-payload.md)を参照してください。

1. 必要なフィールドの選択が完了したら、「**[!UICONTROL 保存]**」をクリックするか、**[!UICONTROL Enter]**&#x200B;キーを押します。

   ![](../assets/journey11.png)

   選択したフィールドの数が「**[!UICONTROL ペイロード]**」フィールドに表示されます。

   ![](../assets/journey12.png)
