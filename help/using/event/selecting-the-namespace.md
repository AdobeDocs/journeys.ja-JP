---
title: 名前空間の選択
description: オプションの選択名前空間
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


# 名前空間の選択 {#concept_ckb_3qt_52b}

この名前空間では、ユーザーに関連付けられた個人を識別するために使用するキーのタイプを定義できます。イベント 設定はオプションです。 リアルタイム顧客プロファイルからの追加情報を、ジャーニー内で取得する場合 [に必要です](https://docs.adobe.com/content/help/en/experience-platform/profile/home.html)。 名前空間定義は、カスタムデータソースを通じてサードパーティのシステムからのデータのみを使用する場合は不要です。

事前定義済みのいずれかを使用するか、ID名前空間サービスを使用して新しいIDを作成できます。 この[ページ](https://docs.adobe.com/content/help/en/experience-platform/identity/home.html)を参照してください。

プライマリIDを持つスキーマを選択した場合は、フィールドとフ **[!UICONTROL Key]** ィール **[!UICONTROL Namespace]** ドに事前入力されます。 IDが定義されていない場合は、プライマリキー _としてidentityMap_ /idを選択します。 次に、名前空間を選択し、identityMap/idを使用して（フィールドの下の）キーが事 **[!UICONTROL Namespace]** 前入力さ _れます_。

フィールドを選択すると、プライマリIDフィールドにタグが付けられます。

![](../assets/primary-identity.png)


ドロップダウン名前空間からオプションをリストします。

![](../assets/journey17.png)

1回の旅行で許可される名前空間は1つだけです。 同じ遍歴で複数のイベントを使用する場合は、同じ名前空間を使用します。 [](../building-journeys/journey.md)を参照してください。
