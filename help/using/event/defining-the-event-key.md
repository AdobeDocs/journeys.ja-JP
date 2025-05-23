---
product: adobe campaign
title: イベントキーの定義
description: イベントキーの定義方法を学ぶ
feature: Journeys
role: User
level: Intermediate
exl-id: 79bcf562-f971-42f1-a607-94a2510c4a07
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '445'
ht-degree: 84%

---

# イベントキーの定義 {#concept_ond_hqt_52b}


>[!CAUTION]
>
>**Adobe Journey Optimizerをお探しですか** Journey Optimizerのドキュメントについては、[ こちら ](https://experienceleague.adobe.com/ja/docs/journey-optimizer/using/ajo-home){target="_blank"} をクリックしてください。
>
>
>_このドキュメントでは、Journey Optimizerに置き換えられた従来のJourney Orchestration マテリアルについて説明します。 Journey OrchestrationやJourney Optimizerへのアクセスに関するご質問は、アカウントチームにお問い合わせください。_


キーは、イベントのペイロードデータの一部とするフィールドまたはフィールドの組み合わせです。システムはキーを使用することでイベントに関連付けられた人を識別できます。キーには、Experience Cloud ID、CRM ID、メールアドレスなどを使用できます。

リアルタイム顧客プロファイルデータベースに保存されたデータを活用する場合は、[リアルタイム顧客プロファイルサービス](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=ja)でプロファイルの ID として定義した情報をイベントキーとして選択する必要があります。

これにより、システムはイベントと個人プロファイルの間で紐付けを実行できます。プライマリ ID を持つスキーマを選択した場合は、「**[!UICONTROL キー]**」および「**[!UICONTROL 名前空間]** 」フィールドに事前入力されます。ID を定義していない場合は、_identityMap > id_ がプライマリキーとして選択されます。次に、名前空間を選択する必要があります。キーは、_identityMap > id_ を使用して（**[!UICONTROL 名前空間]**&#x200B;フィールドの下に）事前入力されます。

フィールドを選択すると、メイン ID フィールドにタグ付けされます。

![](../assets/primary-identity.png)

CRM ID やメールアドレスなど、別のキーを使用する必要がある場合は、キーを手動で追加する必要があります。

1. 「**[!UICONTROL キー]** 」フィールド内または鉛筆アイコン上をクリックします。

   ![](../assets/journey16.png)

1. 「ペイロード」フィールドのリストでキーとして指定したフィールドを選択します。高度な式エディターに切り替えて、より複雑なキーを作成することもできます（例えば、イベントの 2 つのフィールドを連結）。この節では、以下を参照してください。

   ![](../assets/journey20.png)

イベントを受け取ると、キーの値によって、イベントに関連付けられた人物を識別できます。キーは名前空間に関連付けられ（[ このページ ](../event/selecting-the-namespace.md) を参照）、Adobe Experience Platformでクエリの実行に使用できます。 [このページ](../building-journeys/about-orchestration-activities.md)を参照してください。
このキーは、ある人物がジャーニーにエントリしているかどうかを確認するためにも使用されます。1 人の人物が同じジャーニーの 2 つの異なる場所に存在することはできません。その結果、同じキー（キー CRMID=3224 など）を同じジャーニー内の異なる場所に配置することはできません。

また、より高度な操作を実行する場合は、高度な式関数（**[!UICONTROL 詳細設定モード]**）にアクセスできます。これらの関数を使用すると、形式の変更、フィールドの連結、フィールドの一部のみを考慮する（先頭の 10 文字など）など、特定のクエリの実行に用いる値を操作できます。[このページ](../expression/expressionadvanced.md)を参照してください。
