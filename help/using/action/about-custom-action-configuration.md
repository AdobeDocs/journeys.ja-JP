---
product: adobe campaign
title: カスタムアクション設定について
description: カスタムアクションの設定方法を説明します
feature: ジャーニー
role: Business Practitioner
level: Intermediate
exl-id: 8b24abef-700d-4f68-a921-d7299c939439
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '267'
ht-degree: 14%

---

# カスタムアクション設定について {#concept_sxy_bzs_dgb}

サードパーティシステムを使用してメッセージを送信する場合、または[!DNL Journey Orchestration]でサードパーティシステムにAPI呼び出しを送信する場合は、 [!DNL Journey Orchestration]への接続を設定します。 技術ユーザーが定義したカスタムアクションは、ジャーニーの左側のパレットの&#x200B;**[!UICONTROL アクション]**&#x200B;カテゴリで使用できます（[このページ](../building-journeys/about-action-activities.md)を参照）。 次に、カスタムアクションで接続できるシステムの例を示します。Epsilon、Facebook、Adobe.io、Firebaseなど
制限事項については、[このページ](../about/limitations.md)を参照してください。

カスタムアクションを設定するために必要な主な手順は次のとおりです。

1. 「**[!UICONTROL アクション]**」リストで、「**[!UICONTROL 追加]**」をクリックして、新しいアクションを作成します。 画面の右側にアクション設定ペインが開きます。

   ![](../assets/custom2.png)

1. アクションの名前を入力します。

   >[!NOTE]
   >
   >スペースや特殊文字は使用しないでください。30 文字以内にしてください。

1. アクションに説明を追加します。 この手順はオプションです。
1. このアクションを使用するジャーニーの数は、「**[!UICONTROL 使用場所]**」フィールドに表示されます。 「**[!UICONTROL ジャーニーを表示]**」ボタンをクリックすると、このアクションを使用するジャーニーのリストを表示できます。
1. 別の&#x200B;**[!UICONTROL URL設定]**&#x200B;パラメーターを定義します。 [このページ](../action/url-configuration.md)を参照してください。
1. **[!UICONTROL 認証]**&#x200B;セクションを設定します。 この設定は、データソースの場合と同じです。  詳しくは、[この節](../datasource/external-data-sources.md#section_wjp_nl5_nhb)を参照してください。
1. **[!UICONTROL メッセージパラメーター]**&#x200B;を定義します。 [このページ](../action/defining-the-message-parameters.md)を参照してください。
1. 「**[!UICONTROL 保存]**」をクリックします。

   これで、カスタムアクションが設定され、ジャーニーで使用できる状態になりました。 [このページ](../building-journeys/about-action-activities.md)を参照してください。

   >[!NOTE]
   >
   >カスタムアクションを1つのジャーニーで使用する場合、ほとんどのパラメーターは読み取り専用です。 **[!UICONTROL 名前]**、**[!UICONTROL 説明]**、**[!UICONTROL URL]**&#x200B;フィールドおよび&#x200B;**[!UICONTROL 認証]**&#x200B;セクションのみを変更できます。
