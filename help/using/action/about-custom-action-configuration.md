---
title: カスタムアクション設定について
description: カスタムアクションの設定方法を学びます。
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: tm+mt
source-git-commit: 9fc7f0664afa19e3debe2ad4f37d6b794da0ed1f
workflow-type: tm+mt
source-wordcount: '266'
ht-degree: 14%

---


# カスタムアクション設定について {#concept_sxy_bzs_dgb}

サードパーティ製システムを使用してメッセージを送信する場合、またはAPI呼び出しをサードパーティ製システム [!DNL Journey Orchestration] に送信する場合は、ここでとの接続を設定し [!DNL Journey Orchestration]ます。 技術ユーザーが定義したカスタムアクションは、 **[!UICONTROL アクション]** カテゴリの旅の左側のパレットで使用できます( [このページを参照](../building-journeys/about-action-activities.md))。 次に、カスタムアクションを使用して接続できるシステムの例を示します。Epsilon、Facebook、Adobe.io、Firebaseなど
このページには制限事項 [が記載されています](../about/limitations.md)。

カスタムアクションを設定する際に必要な主な手順は次のとおりです。

1. 「 **[!UICONTROL アクション]** 」リストで、をクリックして新しいアクション **** 追加を作成します。 アクション設定ペインが画面の右側に開きます。

   ![](../assets/custom2.png)

1. アクションの名前を入力します。

   >[!NOTE]
   >
   >スペースや特殊文字は使用しないでください。30 文字以内にしてください。

1. ア追加クションの説明。 この手順はオプションです。
1. The number of journeys that use this action is displayed in the **[!UICONTROL Used in]** field. You can click the **[!UICONTROL View journeys]** button to display the list of  journeys using this action.
1. 様々な **[!UICONTROL URL設定パラメーターを定義します]** 。 [このページ](../action/url-configuration.md)を参照してください。
1. 「 **[!UICONTROL 認証]** 」セクションを設定します。 この設定は、データソースの場合と同じです。  [こちらの節](../datasource/external-data-sources.md#section_wjp_nl5_nhb)を参照してください。
1. **[!UICONTROL Messageパラメーターを定義します]**。 [このページ](../action/defining-the-message-parameters.md)を参照してください。
1. 「**[!UICONTROL 保存]**」をクリックします。

   これでカスタムアクションが設定され、ジャーニーで使用できる状態になりました。 [このページ](../building-journeys/about-action-activities.md)を参照してください。

   >[!NOTE]
   >
   >カスタムアクションを1つの遍歴で使用する場合、ほとんどのパラメーターは読み取り専用です。 「 **[!UICONTROL 名前]**」、「 **[!UICONTROL 説明]**」、「 **[!UICONTROL URL]** 」フィールドは、「 **** 認証」、「変更」セクションのみ使用できます。
