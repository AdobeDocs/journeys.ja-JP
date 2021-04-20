---
product: adobe campaign
solution: Journey Orchestration
title: カスタムアクション設定について
description: カスタムアクションの設定方法を学びます。
feature: Journeys
role: Business Practitioner
level: Intermediate
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '270'
ht-degree: 15%

---


# カスタムアクション設定について {#concept_sxy_bzs_dgb}

サードパーティ製システムを使用してメッセージを送信する場合、または[!DNL Journey Orchestration]からサードパーティ製システムにAPI呼び出しを送信する場合は、[!DNL Journey Orchestration]への接続を設定します。 技術ユーザーが定義したカスタムアクションは、ジャーニーの左側のパレットの&#x200B;**[!UICONTROL アクション]**&#x200B;カテゴリーで利用できます（[このページ](../building-journeys/about-action-activities.md)を参照）。 次に、カスタムアクションを使用して接続できるシステムの例を示します。Epsilon、Facebook、Adobe.io、Firebaseなど
[このページ](../about/limitations.md)には制限が記載されています。

カスタムアクションを設定する際に必要な主な手順は次のとおりです。

1. **[!UICONTROL アクション]**&#x200B;リストで、**[!UICONTROL 追加]**&#x200B;をクリックして、新しいアクションを作成します。 アクション設定ペインが画面の右側に開きます。

   ![](../assets/custom2.png)

1. アクションの名前を入力します。

   >[!NOTE]
   >
   >スペースや特殊文字は使用しないでください。30 文字以内にしてください。

1. ア追加クションの説明。 この手順はオプションです。
1. このアクションを使用するジャーニーの数は、「**[!UICONTROL 使用場所]**」フィールドに表示されます。 「**[!UICONTROL 表示ジャーニー]**」ボタンをクリックすると、このアクションを使用するジャーニーのリストを表示できます。
1. 様々な&#x200B;**[!UICONTROL URL設定]**&#x200B;パラメーターを定義します。 [このページ](../action/url-configuration.md)を参照してください。
1. **[!UICONTROL 認証]**&#x200B;セクションを設定します。 この設定は、データソースの場合と同じです。  [この節](../datasource/external-data-sources.md#section_wjp_nl5_nhb)を参照してください。
1. **[!UICONTROL メッセージパラメーター]**&#x200B;を定義します。 [このページ](../action/defining-the-message-parameters.md)を参照してください。
1. 「**[!UICONTROL 保存]**」をクリックします。

   これで、カスタムアクションが設定され、ジャーニーで使用できる状態になりました。 [このページ](../building-journeys/about-action-activities.md)を参照してください。

   >[!NOTE]
   >
   >ジャーニーでカスタムアクションを使用する場合、ほとんどのパラメーターは読み取り専用です。 **[!UICONTROL 名前]**、**[!UICONTROL 説明]**、**[!UICONTROL URL]**&#x200B;フィールド、および&#x200B;**[!UICONTROL 認証]**&#x200B;セクションのみを変更できます。
