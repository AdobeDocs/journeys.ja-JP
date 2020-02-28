---
title: 名前空間の選択
description: 名前空間を選択する方法を説明します。
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
source-git-commit: 411ecf0ec4dc6a87c4e129b40f2918799bef54bf

---


# 名前空間の選択 {#concept_ckb_3qt_52b}

名前空間を使用すると、イベントに関連付けられた人を識別するために使用するキーのタイプを定義できます。 設定はオプションです。 リアルタイム顧客プロファイルからの追加情報をジャーニー内で取得する [場合は必須です](https://www.adobe.io/apis/cloudplatform/dataservices/profile-identity-segmentation/profile-identity-segmentation-services.html#!api-specification/markdown/narrative/technical_overview/unified_profile_architectural_overview/unified_profile_architectural_overview.md)。 カスタムデータソースを介してサードパーティのシステムから取得したデータのみを使用する場合は、名前空間の定義は不要です。

定義済みの名前空間の1つを使用するか、ID名前空間サービスを使用して新しい名前空間を作成できます。 この[ページ](https://www.adobe.io/apis/cloudplatform/dataservices/profile-identity-segmentation/profile-identity-segmentation-services.html#!api-specification/markdown/narrative/technical_overview/identity_namespace_overview/identity_namespace_overview.md)を参照してください。

プライマリIDを持つスキーマを選択した場合、およびのフィ **[!UICONTROL Key]** ールド **[!UICONTROL Namespace]** は事前入力されます。 IDが定義されていない場合は、プライマリキー _としてidentityMap_ /idを選択します。 その後、名前空間を選択する必要があります。この場合、identityMap/idを使用して、キーが（フィールドの下の） **[!UICONTROL Namespace]** 事前入力 _されます_。

フィールドを選択すると、プライマリIDフィールドにタグが付けられます。

![](../assets/primary-identity.png)


ドロップダウンリストから名前空間を選択します。

![](../assets/journey17.png)

1回の遍歴で許可される名前空間は1つだけです。 同じ遍歴で複数のイベントを使用する場合は、同じ名前空間を使用する必要があります。 [](../building-journeys/journey.md)を参照してください。
