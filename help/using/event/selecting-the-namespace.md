---
title: 名前空間の選択
description: 名前空間の選択方法を学ぶ
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
workflow-type: tm+mt
source-wordcount: '205'
ht-degree: 5%

---


# 名前空間の選択 {#concept_ckb_3qt_52b}

名前空間を使用すると、イベントに関連付けられた人物を識別するために使用するキーのタイプを定義できます。 設定はオプションです。 リアルタイム顧客プロファイルからの追加情報をジャーニーで取得する場合は、 [この情報が必要です](https://docs.adobe.com/content/help/en/experience-platform/profile/home.html)。 カスタムデータソースを介してサードパーティ製の名前空間からのデータのみを使用する場合は、システム定義は必要ありません。

事前定義済みのいずれかを使用するか、ID名前空間サービスを使用して新しいものを作成できます。 この[ページ](https://docs.adobe.com/content/help/en/experience-platform/identity/home.html)を参照してください。

主IDを持つスキーマを選択した場合は、「 **[!UICONTROL キー]** 」フィールドと「 **[!UICONTROL 名前空間]** 」フィールドに事前入力されます。 IDが定義されていない場合は、主キーとして _identityMap/id_ を選択します。 次に、名前空間を選択する必要があります。この場合、identityMap/idを使用して、( **[!UICONTROL 名前空間]** フィールドの下の _)キーが事前入力されます_。

フィールドを選択すると、主IDフィールドにタグが付けられます。

![](../assets/primary-identity.png)


ドロップダウンリストから名前空間を選択します。

![](../assets/journey17.png)

1回の旅行で許可される名前空間は1つだけです。 同じ遍歴で複数のイベントを使用する場合は、同じ名前空間を使用する必要があります。 [](../building-journeys/journey.md)を参照してください。
