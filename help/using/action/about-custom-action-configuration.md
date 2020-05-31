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
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e53ecd96bbb308fe109843de6f64cde4cba5e246
workflow-type: tm+mt
source-wordcount: '258'
ht-degree: 5%

---


# カスタムアクション設定について {#concept_sxy_bzs_dgb}

サードパーティ製システムを使用してメッセージを送信する場合、またはJourney Orchestrationがサードパーティ製システムにAPI呼び出しを送信する場合は、Journey Orchestrationへの接続を設定します。 技術ユーザーが定義したカスタムアクションは、遍歴の左側のパレットの **[!UICONTROL アクション]** カテゴリで使用できます（を参照） [](../building-journeys/about-action-activities.md)。 次に、カスタムアクションを使用して接続できるシステムの例を示します。 Epsilon、Facebook、Adobe.io、Firebaseなど
制限事項は次のとおりです。 [](../action/custom-action-limitations.md).

カスタムアクションを設定する際に必要な主な手順は次のとおりです。

1. 「 **[!UICONTROL アクション]** 」リストで、をクリックして新しいアクション **** 追加を作成します。 アクション設定ペインが画面の右側に開きます。

   ![](../assets/custom2.png)

1. アクションの名前を入力します。

   >[!NOTE]
   >
   >スペースや特殊文字は使用しないでください。 30文字以内にしてください。

1. ア追加クションの説明。 この手順はオプションです。
1. このアクションを使用するジャーニーの数は、「 **[!UICONTROL 使用場所]** 」フィールドに表示されます。 「 **[!UICONTROL 表示ジャーニー]** 」ボタンをクリックすると、このアクションを使用してジャーニーのリストを表示できます。
1. 様々な **[!UICONTROL URL設定パラメーターを定義します]** 。 [](../action/url-configuration.md)を参照してください。
1. 「 **[!UICONTROL 認証]** 」セクションを設定します。 この設定は、データソースの場合と同じです。  [](../datasource/external-data-sources.md#section_wjp_nl5_nhb)を参照してください。
1. **[!UICONTROL Messageパラメーターを定義します]**。 [](../action/defining-the-message-parameters.md)を参照してください。
1. 「**[!UICONTROL 保存]**」をクリックします。

   これでカスタムアクションが設定され、ジャーニーで使用できる状態になりました。 [](../building-journeys/about-action-activities.md)を参照してください。

   >[!NOTE]
   >
   >カスタムアクションを1つの遍歴で使用する場合、ほとんどのパラメーターは読み取り専用です。 「 **[!UICONTROL 名前]**」、「 **[!UICONTROL 説明]**」、「 **[!UICONTROL URL]** 」フィールドは、「 **** 認証」、「変更」セクションのみ使用できます。
