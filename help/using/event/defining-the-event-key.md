---
title: イベントキーの定義
description: イベントキー
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
source-git-commit: e579936cfe5eb43caf72627004f98a5746c7abb1

---


# イベントキーの定義 {#concept_ond_hqt_52b}

キーは、フィールドまたはフィールドの組み合わせがイベントのペイロードデータの一部であり、システムがイベントに関連付けられた人物を識別できるようにします。 キーには、例えば、Experience Cloud ID、CRM ID、電子メールアドレスを使用できます。

リアルタイム顧客プロファイルデータベースに保存されたデータを活用する場合は、イベントキーとして、リアルタイム顧客プロファイルサービスでプロファイルのIDとして定義した情報を選択する必要があ [ります](https://docs.adobe.com/content/help/en/experience-platform/profile/home.html)。

これにより、システムはイベントと個人のプロファイルの調整を実行できます。 プライマリIDを持つスキーマを選択した場合は、フィールドとフ **[!UICONTROL Key]** ィール **[!UICONTROL Namespace]** ドに事前入力されます。 IDが定義されていない場合は、プライマリキー _としてidentityMap_ /idを選択します。 次に、名前空間を選択し、identityMap/idを使用して（フィールドの下の）キーが事 **[!UICONTROL Namespace]** 前入力さ _れます_。

フィールドを選択すると、プライマリIDフィールドにタグが付けられます。

![](../assets/primary-identity.png)

CRM IDや電子メールアドレスなど、別のキーを使用する必要がある場合は、手動で追加する必要があります。

1. フィールドの内側または **[!UICONTROL Key]** 鉛筆アイコンをクリックします。

   ![](../assets/journey16.png)

1. ペイロードフィールドのリストでキーとして選択したフィールドを選択します。 また、アドバンス式エディタに切り替えて、より複雑なキー(例えば、2つのフィールドを連結したイベント)を作成することもできます。 この節では、以下を参照してください。

   ![](../assets/journey20.png)

イベントを受け取ると、キーの値によって、システムがそのユーザーに関連付けられた人物を識別できるようになります。イベント 名前空間に関連付けられている( [](../event/selecting-the-namespace.md)参照)場合、キーを使用してAdobe Experience Platformでクエリを実行できます。 [](../building-journeys/about-orchestration-activities.md)を参照してください。人が旅に出ているかどうかを調べるのにも使われます。 同じ旅の中で2つの異なる場所にいる人はいないのです その結果、システムは、同じキー（例えば、CRMID=3224）を同じ遍歴の異なる場所に置くことを許可しません。

また、追加の操作を実行する場合は、高度な式&#x200B;**[!UICONTROL Advanced mode]**&#x200B;関数()にアクセスすることもできます。 これらの関数を使用すると、形式の変更、フィールドの連結の実行など、特定のクエリ（例えば、10文字の先頭文字）の実行に使用される値を操作できます。 [](../expression/expressionadvanced.md)を参照してください。
