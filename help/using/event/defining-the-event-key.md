---
product: adobe campaign
title: イベントキーの定義
description: イベントキーの定義方法を説明します
feature: ジャーニー
role: Business Practitioner
level: Intermediate
exl-id: 79bcf562-f971-42f1-a607-94a2510c4a07
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '406'
ht-degree: 5%

---

# イベントキーの定義 {#concept_ond_hqt_52b}

キーは、フィールドまたはフィールドの組み合わせがイベントペイロードデータの一部であり、イベントに関連付けられた人をシステムが識別できるようにします。 キーには、例えば、Experience CloudID、CRM IDまたは電子メールアドレスを使用できます。

リアルタイム顧客プロファイルデータベースに格納されたデータを活用する予定がある場合は、[リアルタイム顧客プロファイルサービス](https://docs.adobe.com/content/help/ja-JP/experience-platform/profile/home.html)でプロファイルのIDとして定義した情報をイベントキーとして選択する必要があります。

これにより、イベントと個人のプロファイルの間の紐付けがシステムで実行できます。 プライマリIDを持つスキーマを選択した場合、**[!UICONTROL キー]**&#x200B;と&#x200B;**[!UICONTROL 名前空間]**&#x200B;のフィールドは事前入力されます。 IDが定義されていない場合は、_identityMap > id_&#x200B;をプライマリキーとして選択します。 次に、名前空間を選択し、_identityMap/id_&#x200B;を使用して、キーが（**[!UICONTROL Namespace]**&#x200B;フィールドの下に）事前入力されます。

フィールドを選択すると、プライマリIDフィールドにタグが付けられます。

![](../assets/primary-identity.png)

CRM IDや電子メールアドレスなど、別のキーを使用する必要がある場合は、手動で追加する必要があります。

1. **[!UICONTROL キー]**&#x200B;フィールド内または鉛筆アイコンの内側をクリックします。

   ![](../assets/journey16.png)

1. ペイロードフィールドのリストで、キーとして選択したフィールドを選択します。 高度な式エディターに切り替えて、より複雑なキーを作成することもできます（例えば、イベントの2つのフィールドを連結するなど）。 この節の以下を参照してください。

   ![](../assets/journey20.png)

イベントを受け取ると、キーの値によってイベントに関連付けられた人物を識別できます。 名前空間（[このページ](../event/selecting-the-namespace.md)を参照）に関連付けられている場合、キーを使用してAdobe Experience Platformでクエリを実行できます。 [このページ](../building-journeys/about-orchestration-activities.md)を参照してください。キーは、人がジャーニーに出ているかどうかを確認するためにも使用されます。 実際、人は同じ旅の2つの異なる場所にいることはできません。 その結果、システムでは、同じキー（例えば、キーCRMID=3224）を同じジャーニー内の別の場所に配置することは許可されません。

また、追加の操作を実行する場合は、高度な式関数（**[!UICONTROL 詳細設定モード]**）にアクセスできます。 これらの関数を使用すると、形式の変更、フィールドの連結の実行など、特定のクエリの実行に使用する値を操作し、フィールドの一部（例えば、最初の10文字）のみを考慮に入れることができます。 [このページ](../expression/expressionadvanced.md)を参照してください。
