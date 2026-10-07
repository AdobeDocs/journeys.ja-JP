---
product: adobe campaign
title: 名前空間の選択
description: 名前空間を選択する方法を説明します
feature: Journeys
role: User
level: Intermediate
exl-id: 976c6353-797e-40cc-bb90-5d82381bb903
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
source-wordcount: '263'
ht-degree: 97%
---
# 名前空間の選択 {#concept_ckb_3qt_52b}


>[!CAUTION]
>
>**Adobe Journey Optimizer をお探しですか**？ Journey Optimizer のドキュメントについて詳しくは、[こちら](https://experienceleague.adobe.com/ja/docs/journey-optimizer/using/ajo-home){target="_blank"}をクリックしてください。
>
>
>_このドキュメントは、Journey Optimizer に置き換えられた従来の Journey Orchestration 資料を参照しています。 Journey Orchestration または Journey Optimizer へのアクセスについてご質問がある場合は、アカウントチームにお問い合わせください。_


名前空間を使用すると、イベントに関連付けられた人物の識別に使用するキーのタイプを定義できます。 設定は必須ではありません。 [リアルタイム顧客プロファイル](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=ja)からの追加情報をジャーニーで取得する場合に必要です。 カスタムデータソースを介したサードパーティシステムのデータのみを使用する場合は、名前空間は必要ありません。

事前定義済みのものを使用するか、ID 名前空間サービスを使用して新しく作成できます。 この[ページ](https://experienceleague.adobe.com/docs/experience-platform/identity/home.html?lang=ja)を参照してください。

プライマリ ID を持つスキーマを選択した場合は、「**[!UICONTROL キー]**」および「**[!UICONTROL 名前空間]** 」フィールドに事前入力されます。 ID を定義していない場合は、_identityMap > id_ がプライマリキーとして選択されます。 次に、名前空間を選択する必要があります。キーは、_identityMap > id_ を使用して（**[!UICONTROL 名前空間]**&#x200B;フィールドの下に）事前入力されます。

フィールドを選択すると、プライマリ ID フィールドにタグ付けされます。

![](../assets/primary-identity.png)


ドロップダウンリストから名前空間を選択します。

![](../assets/journey17.png)

1 つのジャーニーで使用できる名前空間は 1 つだけです。 同じジャーニーで複数のイベントを使用する場合は、同じ名前空間を使用する必要があります。 [このページ](../building-journeys/journey.md)を参照してください。
