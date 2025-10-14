---
product: adobe campaign
title: カスタムアクション設定について
description: カスタムアクションの設定方法を学ぶ
feature: Journeys
role: User
level: Intermediate
exl-id: 8b24abef-700d-4f68-a921-d7299c939439
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '364'
ht-degree: 77%

---

# カスタムアクション設定について {#concept_sxy_bzs_dgb}


>[!CAUTION]
>
>**Adobe Journey Optimizerをお探しですか** Journey Optimizerのドキュメントについては、[&#x200B; こちら &#x200B;](https://experienceleague.adobe.com/ja/docs/journey-optimizer/using/ajo-home){target="_blank"} をクリックしてください。
>
>
>_このドキュメントでは、Journey Optimizerに置き換えられた従来のJourney Orchestration マテリアルについて説明します。 Journey OrchestrationやJourney Optimizerへのアクセスに関するご質問は、アカウントチームにお問い合わせください。_


サードパーティ製システムを使用してメッセージを送信する場合、または [!DNL Journey Orchestration] ーザーがサードパーティ製システムに API 呼び出しを送信する場合は、ここで [!DNL Journey Orchestration] への接続を設定します。 技術ユーザーが定義したカスタムアクションは、ジャーニーの左側のパレットの&#x200B;**[!UICONTROL アクション]**&#x200B;カテゴリーで利用できます（[このページ](../building-journeys/about-action-activities.md)を参照）。カスタムアクションを使用して接続できるシステムとしては、例えば、Epsilon、Facebook、Adobe.io、Firebase などが挙げられます。

制限事項については、[このページ](../about/limitations.md)を参照してください。

カスタムアクションパラメーターでは、単純なコレクションとオブジェクトのコレクションを渡すことができます。制限に関しては [&#x200B; こちらのページ &#x200B;](../usecase/collections.md#limitations) をご覧ください。 また、パラメーターは想定される形式（例：文字列、10 進数など）になっています。これらの想定される形式に従うように注意する必要があります。この[ユースケース](../usecase/collections.md)を参照してください。

カスタムアクションを設定する際に必要な主な手順は次のとおりです。

1. 「**[!UICONTROL アクション]**」リストで「**[!UICONTROL 追加]**」をクリックして、新しいアクションを作成します。画面右側にアクション設定ペインが開きます。


   ![](../assets/custom2.png)

1. アクションの名前を入力します。

   >[!NOTE]
   >
   >スペースや特殊文字は使用しないでください。30 文字以内にしてください。

1. アクションに説明を追加します。この手順はオプションです。
1. このアクションを使用しているジャーニーの数は、「**[!UICONTROL 使用されている場所]**」フィールドに表示されます。「**[!UICONTROL ジャーニーを表示]**」ボタンをクリックすると、このアクションを使用するジャーニーのリストを表示できます。
1. 様々な **[!UICONTROL URL 設定]**&#x200B;パラメーターを定義します。[このページ](../action/url-configuration.md)を参照してください。
1. 「**[!UICONTROL 認証]**」セクションを設定します。この設定はデータソースの場合と同じです。[この節](../datasource/external-data-sources.md#section_wjp_nl5_nhb)を参照してください。
1. **[!UICONTROL アクションパラメーター]**&#x200B;を定義します。[このページ](../action/defining-the-message-parameters.md)を参照してください。
1. 「**[!UICONTROL 保存]**」をクリックします。

   カスタムアクションが設定され、ジャーニーで使用できる状態になります。[このページ](../building-journeys/about-action-activities.md)を参照してください。

   >[!NOTE]
   >
   >ジャーニーでカスタムアクションを使用する場合、ほとんどのパラメーターは読み取り専用です。変更できるのは、**[!UICONTROL 名前]**、**[!UICONTROL 説明]**、**[!UICONTROL URL]** フィールド、および&#x200B;**[!UICONTROL 認証]**&#x200B;セクションのみです。
