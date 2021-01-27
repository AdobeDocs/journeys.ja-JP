---
product: adobe campaign
solution: Journey Orchestration
title: イベントキーの定義
description: イベントキーの定義方法を学びます
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '405'
ht-degree: 5%

---


# イベントキーの定義 {#concept_ond_hqt_52b}

キーは、フィールドまたはフィールドの組み合わせが、イベントのペイロードデータの一部であり、イベントに関連付けられた人を識別できるようにします。 キーには、Experience CloudID、CRM ID、電子メールアドレスなどがあります。

リアルタイム顧客プロファイルデータベースに保存されたデータを活用する場合は、イベントキーとして[リアルタイム顧客プロファイルサービス](https://docs.adobe.com/content/help/ja-JP/experience-platform/profile/home.html)でプロファイルのIDとして定義した情報を選択する必要があります。

これにより、イベントと個人のプロファイルの間の調整を実行できます。 プライマリIDを持つスキーマを選択した場合は、**[!UICONTROL キー]**&#x200B;と&#x200B;**[!UICONTROL 名前空間]**&#x200B;フィールドに事前入力されます。 IDが定義されていない場合は、_identityMap > id_&#x200B;を主キーとして選択します。 次に、名前空間を選択する必要があります。キーは、_identityMap > id_&#x200B;を使用して、(**[!UICONTROL 名前空間]**&#x200B;フィールドの下)事前入力されます。

フィールドを選択すると、主IDフィールドにタグが付けられます。

![](../assets/primary-identity.png)

CRM IDや電子メールアドレスなど、別のキーを使用する必要がある場合は、キーを手動で追加する必要があります。

1. **[!UICONTROL キー]**&#x200B;フィールド内または鉛筆アイコン上をクリックします。

   ![](../assets/journey16.png)

1. ペイロードフィールドのリストでキーとして選択したフィールドを選択します。 高度な式エディタに切り替えて、より複雑なキーを作成することもできます(例えば、2つのフィールドのイベントを連結したキー)。 この節では、以下を参照してください。

   ![](../assets/journey20.png)

イベントを受け取ると、キーの値によって、イベントに関連付けられた人物を識別できます。 名前空間に関連付けられている（[このページ](../event/selecting-the-namespace.md)を参照）。このキーはAdobe Experience Platformでクエリを行うのに使用できます。 [このページ](../building-journeys/about-orchestration-activities.md)を参照してください。この鍵は、人がジャーニーにいるかどうかを確認するためにも使用されます。 同じジャーニーの2つの異なる場所にいる人はいない。 その結果、同じキー（例えば、キーCRMID=3224）を同じジャーニー内の異なる場所に置くことはできません。

また、追加の操作を実行する場合は、高度な式関数（**[!UICONTROL 高度なモード]**）にアクセスできます。 これらの関数を使用すると、形式の変更、フィールドの連結など、特定のクエリ（先頭の10文字など）を実行する際に使用する値を操作できます。ただし、フィールドの一部のみを考慮に入れます。 [このページ](../expression/expressionadvanced.md)を参照してください。
