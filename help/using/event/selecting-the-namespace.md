---
product: adobe campaign
title: 名前空間の選択
description: 名前空間の選択方法を学ぶ
feature: Journeys
role: User
level: Intermediate
exl-id: 976c6353-797e-40cc-bb90-5d82381bb903
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '238'
ht-degree: 78%

---

# 名前空間の選択 {#concept_ckb_3qt_52b}


>[!CAUTION]
>
>**Adobe Journey Optimizerをお探しですか** Journey Optimizerのドキュメントについては、[ こちら ](https://experienceleague.adobe.com/ja/docs/journey-optimizer/using/ajo-home){target="_blank"} をクリックしてください。
>
>
>_このドキュメントでは、Journey Optimizerに置き換えられた従来のJourney Orchestration マテリアルについて説明します。 Journey OrchestrationやJourney Optimizerへのアクセスに関するご質問は、アカウントチームにお問い合わせください。_


名前空間を使用すると、イベントに関連付けられた人物の識別に使用するキーのタイプを定義できます。設定は必須ではありません。[リアルタイム顧客プロファイル](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=ja)からの追加情報をジャーニーで取得する場合に必要です。カスタムデータソースを介したサードパーティシステムのデータのみを使用する場合は、名前空間は必要ありません。

事前定義済みのものを使用するか、ID 名前空間サービスを使用して新しく作成できます。この[ページ](https://experienceleague.adobe.com/docs/experience-platform/identity/home.html?lang=ja)を参照してください。

プライマリ ID を持つスキーマを選択した場合は、「**[!UICONTROL キー]**」および「**[!UICONTROL 名前空間]** 」フィールドに事前入力されます。ID を定義していない場合は、_identityMap > id_ がプライマリキーとして選択されます。次に、名前空間を選択する必要があります。キーは、_identityMap > id_ を使用して（**[!UICONTROL 名前空間]**&#x200B;フィールドの下に）事前入力されます。

フィールドを選択すると、プライマリ ID フィールドにタグ付けされます。

![](../assets/primary-identity.png)


ドロップダウンリストから名前空間を選択します。

![](../assets/journey17.png)

1 つのジャーニーで使用できる名前空間は 1 つだけです。同じジャーニーで複数のイベントを使用する場合は、同じ名前空間を使用する必要があります。[このページ](../building-journeys/journey.md)を参照してください。
