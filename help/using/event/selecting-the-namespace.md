---
product: adobe campaign
solution: Journey Orchestration
title: 名前空間の選択
description: 名前空間の選択方法を学ぶ
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '207'
ht-degree: 14%

---


# 名前空間の選択 {#concept_ckb_3qt_52b}

名前空間を使用すると、イベントに関連付けられた人物を識別するために使用するキーのタイプを定義できます。 設定はオプションです。 [リアルタイム顧客プロファイル](https://docs.adobe.com/content/help/ja-JP/experience-platform/profile/home.html)からの追加情報をジャーニーで取得する場合に必要です。 カスタムデータソースを介してサードパーティ製の名前空間からのデータのみを使用する場合は、システム定義は必要ありません。

事前定義済みのいずれかを使用するか、ID名前空間サービスを使用して新しいものを作成できます。 この[ページ](https://docs.adobe.com/content/help/ja-JP/experience-platform/identity/home.html)を参照してください。

プライマリIDを持つスキーマを選択した場合は、**[!UICONTROL キー]**&#x200B;と&#x200B;**[!UICONTROL 名前空間]**&#x200B;フィールドに事前入力されます。 IDが定義されていない場合は、_identityMap > id_&#x200B;を主キーとして選択します。 次に、名前空間を選択する必要があります。キーは、_identityMap > id_&#x200B;を使用して、(**[!UICONTROL 名前空間]**&#x200B;フィールドの下)事前入力されます。

フィールドを選択すると、主IDフィールドにタグが付けられます。

![](../assets/primary-identity.png)


ドロップダウンリストから名前空間を選択します。

![](../assets/journey17.png)

1つのジャーニーで許可される名前空間は1つだけです。 同じジャーニーで複数のイベントを使用する場合は、同じ名前空間を使用する必要があります。 [このページ](../building-journeys/journey.md)を参照してください。
