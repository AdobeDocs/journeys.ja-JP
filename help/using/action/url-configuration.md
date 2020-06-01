---
title: URL 設定
description: URLの設定について説明します
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
source-git-commit: 1bc8d845716044671a11c200e4bab92302841994
workflow-type: tm+mt
source-wordcount: '141'
ht-degree: 8%

---


# URL 設定 {#concept_gbg_1f1_2gb}

カスタムアクションを設定する場合、次の **[!UICONTROL URL設定]** パラメーターを定義する必要があります。

![](../assets/journeyurlconfiguration.png)

1. Add the **[!UICONTROL URL]** of the external service.

   >[!NOTE]
   >
   >セキュリティ上の理由から、HTTPS の使用を強くお勧めします。パブリックでないアドビのアドレスの使用およびIPアドレスの使用は許可されていません。

1. 呼び出し **[!UICONTROL 方法]**: POST **[!UICONTROL または]** PUTのいずれかです ****。
1. 「 **[!UICONTROL ヘッダー]** 」セクションで、ヘッダーフィールド **[!UICONTROL 追加をクリックして]** 、新しいキーと値のペアを定義します。 これらは、外部サービスに対して行われた要求のHTTPヘッダーに対応します。 キー/値のペアを削除するには、「 **[!UICONTROL ヘッダ]** 」フィールドにカーソルを置き、 **[!UICONTROL 削除]** アイコンをクリックします。

   **[!UICONTROL Content-Type]** と **** Charsetはデフォルトで設定され、削除または上書きはできません。

   >[!NOTE]
   >
   >ヘッダーは、次の [解析ルールに従って検証されます](https://tools.ietf.org/html/rfc7230#section-3.2.4)。
