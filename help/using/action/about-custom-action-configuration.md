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
source-git-commit: 1bc8d845716044671a11c200e4bab92302841994

---


# カスタムアクション設定について {#concept_sxy_bzs_dgb}

サードパーティ製のシステムを使用してメッセージを送信する場合、またはJareny Orchestrationでサードパーティ製のシステムにAPI呼び出しを送信する場合は、Jareny Orchestrationへの接続を設定します。 技術ユーザーが定義したカスタムアクションは、旅の左側のパレットのカテゴリで使用で **[!UICONTROL Action]**きます(を参照[](../building-journeys/about-action-activities.md))。 カスタムアクションを使用して接続できるシステムの例を以下に示します。Epsilon、Facebook、Adobe.io、Firebaseなど
制限事項は次のとおりです。[](../action/custom-action-limitations.md).

カスタムアクションを設定する際に必要な主な手順は次のとおりです。

1. リストから、 **[!UICONTROL Actions]**をクリックして新**[!UICONTROL Add]** しいアクションを作成します。 画面の右側にアクション設定ペインが開きます。

   ![](../assets/custom2.png)

1. アクションの名前を入力します。

   >[!NOTE]
   >
   >スペースや特殊文字は使用しないでください。 30文字以内にする必要があります。

1. アクションに説明を追加します。 この手順はオプションです。
1. このアクションを使用するジャーニーの数がフィールドに表示さ **[!UICONTROL Used in]**れます。 このボタンをクリックす**[!UICONTROL View journeys]** ると、このアクションを使用したジャーニーのリストを表示できます。
1. 様々なパラメーターを定 **[!UICONTROL URL Configuration]**義します。[](../action/url-configuration.md)を参照してください。
1. セクションを設 **[!UICONTROL Authentication]**定します。 この設定は、データソースの場合と同じです。[](../datasource/external-data-sources.md#section_wjp_nl5_nhb)を参照してください。
1. を定義しま **[!UICONTROL Message parameters]**す。[](../action/defining-the-message-parameters.md)を参照してください。
1. クリック **[!UICONTROL Save]**.

   これでカスタムアクションが設定され、ジャーニーで使用できる状態になりました。 [](../building-journeys/about-action-activities.md)を参照してください。

   >[!NOTE]
   >
   >ジャーニーバージョンでカスタムアクションを使用する場合、ほとんどのパラメーターは読み取り専用です。 「名前」フィールドと「説明」フィールドのみを変更できます。
