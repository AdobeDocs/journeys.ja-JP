---
product: adobe campaign
title: カスタムアクション設定について
description: カスタムアクションの設定方法を学ぶ
feature: Journeys
role: User
level: Intermediate
exl-id: 8b24abef-700d-4f68-a921-d7299c939439
product_v2:
  - id: cf67d108-ecf9-4fde-af49-3a3c39083bc8
    internal-label: Journey Orchestration
feature_v2:
  - id: 7de3230f-9523-5ba5-8d5c-2313288b27ef
    internal-label: Journeys
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
source-git-commit: 255cd6677e7c9ebff63ea9a1028a042c19e63ecc
workflow-type: tm+mt
source-wordcount: '375'
ht-degree: 89%
---
# カスタムアクション設定について {#concept_sxy_bzs_dgb}


>[!CAUTION]
>
>**Adobe Journey Optimizer をお探しですか**？ Journey Optimizer のドキュメントについて詳しくは、[こちら](https://experienceleague.adobe.com/ja/docs/journey-optimizer/using/ajo-home){target="_blank"}をクリックしてください。
>
>
>_このドキュメントは、Journey Optimizer に置き換えられた従来の Journey Orchestration 資料を参照しています。 Journey Orchestration または Journey Optimizer へのアクセスについてご質問がある場合は、アカウントチームにお問い合わせください。_


サードパーティシステムを使用してメッセージを送信する場合、または[!DNL Journey Orchestration]がサードパーティシステムにAPI呼び出しを送信する場合は、ここで[!DNL Journey Orchestration]への接続を設定します。 技術ユーザーが定義したカスタムアクションは、ジャーニーの左側のパレットの&#x200B;**[!UICONTROL アクション]**&#x200B;カテゴリーで利用できます（[このページ](../building-journeys/about-action-activities.md)を参照）。 カスタムアクションを使用して接続できるシステムとしては、例えば、Epsilon、Facebook、Adobe.io、Firebase などが挙げられます。

制限事項については、[このページ](../about/limitations.md)を参照してください。

カスタムアクションパラメーターでは、単純なコレクションとオブジェクトのコレクションを渡すことができます。 制限については、[このページ &#x200B;](../usecase/collections.md#limitations)を参照してください。 また、パラメーターは想定される形式（例：文字列、10 進数など）になっています。 これらの想定される形式に従うように注意する必要があります。 この[ユースケース](../usecase/collections.md)を参照してください。

カスタムアクションを設定する際に必要な主な手順は次のとおりです。

1. 「**[!UICONTROL アクション]**」リストで「**[!UICONTROL 追加]**」をクリックして、新しいアクションを作成します。 画面右側にアクション設定ペインが開きます。

   ![](../assets/custom2.png)

1. アクションの名前を入力します。

   >[!NOTE]
   >
   >スペースや特殊文字は使用しないでください。 30 文字以内にしてください。

1. アクションに説明を追加します。 この手順はオプションです。
1. このアクションを使用しているジャーニーの数は、「**[!UICONTROL 使用されている場所]**」フィールドに表示されます。 「**[!UICONTROL ジャーニーを表示]**」ボタンをクリックすると、このアクションを使用するジャーニーのリストを表示できます。
1. 様々な **[!UICONTROL URL 設定]**&#x200B;パラメーターを定義します。 [このページ](../action/url-configuration.md)を参照してください。
1. 「**[!UICONTROL 認証]**」セクションを設定します。 この設定はデータソースの場合と同じです。  [この節](../datasource/external-data-sources.md#section_wjp_nl5_nhb)を参照してください。
1. **[!UICONTROL アクションパラメーター]**&#x200B;を定義します。 [このページ](../action/defining-the-message-parameters.md)を参照してください。
1. 「**[!UICONTROL 保存]**」をクリックします。

   カスタムアクションが設定され、ジャーニーで使用できる状態になります。 [このページ](../building-journeys/about-action-activities.md)を参照してください。

   >[!NOTE]
   >
   >ジャーニーでカスタムアクションを使用する場合、ほとんどのパラメーターは読み取り専用です。 変更できるのは、**[!UICONTROL 名前]**、**[!UICONTROL 説明]**、**[!UICONTROL URL]** フィールド、および&#x200B;**[!UICONTROL 認証]**&#x200B;セクションのみです。
