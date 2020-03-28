---
title: カスタムアクション設定について
description: カスタムアクションの設定方法を説明します。
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

---


# カスタムアクション設定について {#concept_sxy_bzs_dgb}

サードパーティのシステムを使用してメッセージを送信する場合や、Jeurney OrchestrationでサードパーティのシステムにAPI呼び出しを送信する場合は、Jeurney Orchestrationへの接続をここで設定します。 技術ユーザが定義したカスタムアクションは、旅の左側のパレットのカテゴリで使用で **[!UICONTROL Action]** きます(を参照 [](../building-journeys/about-action-activities.md))。 次に、カスタムアクションを使用して接続できるシステムの例を示します。Epsilon、Facebook、Adobe.io、Firebaseなど
次に制限を示します。 [](../action/custom-action-limitations.md).

カスタムアクションを設定するために必要な主な手順は、次のとおりです。

1. リストで、をク **[!UICONTROL Actions]** リックし **[!UICONTROL Add]** て新しいアクションを作成します。 画面の右側にアクション設定ペインが開きます。

   ![](../assets/custom2.png)

1. アクションの名前を入力します。

   >[!NOTE]
   >
   >スペースや特殊文字は使用しないでください。 30文字以内にする必要があります。

1. アク追加ションの説明。 この手順はオプションです。
1. このアクションを使用するジャーニーの数がフィールドに表示さ **[!UICONTROL Used in]** れます。 このボタンをクリックす **[!UICONTROL View journeys]** ると、このアクションを使用したジャーニーのリストを表示できます。
1. 様々なパラメーターを定 **[!UICONTROL URL Configuration]** 義します。 [](../action/url-configuration.md)を参照してください。
1. セクションを設 **[!UICONTROL Authentication]** 定します。 この設定は、データソースの場合と同じです。  [](../datasource/external-data-sources.md#section_wjp_nl5_nhb)を参照してください。
1. を定義しま **[!UICONTROL Message parameters]**&#x200B;す。 [](../action/defining-the-message-parameters.md)を参照してください。
1. クリック **[!UICONTROL Save]**.

   これで、カスタムアクションが設定され、ジャーニーで使用できる状態になりました。 [](../building-journeys/about-action-activities.md)を参照してください。

   >[!NOTE]
   >
   >カスタムアクションを遍歴で使用する場合、ほとんどのパラメーターは読み取り専用です。 、、、、の各フィールド **[!UICONTROL Name]**&#x200B;とセク **[!UICONTROL Description]**&#x200B;ション **[!UICONTROL URL]** のみ変更でき **[!UICONTROL Authentication]** ます。
