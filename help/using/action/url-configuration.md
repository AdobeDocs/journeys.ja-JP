---
product: adobe campaign
solution: Journey Orchestration
title: URL 設定
description: URLの設定について説明します
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
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
   >セキュリティ上の理由から、HTTPS の使用を強くお勧めします。パブリックでないAdobeアドレスとIPアドレスの使用は許可されていません。

1. 呼び出し **[!UICONTROL 方法]**: **[!UICONTROL POST]** 、 **** PUTのいずれかです。
1. 「 **[!UICONTROL ヘッダー]** 」セクションで、ヘッダーフィールド **[!UICONTROL 追加をクリックして]** 、新しいキーと値のペアを定義します。 これらは、外部サービスに対して行われた要求のHTTPヘッダーに対応します。 キー/値のペアを削除するには、「 **[!UICONTROL ヘッダ]** 」フィールドにカーソルを置き、 **[!UICONTROL 削除]** アイコンをクリックします。

   **[!UICONTROL Content-Type]** と **** Charsetはデフォルトで設定され、削除または上書きはできません。

   >[!NOTE]
   >
   >ヘッダーは、次の [解析ルールに従って検証されます](https://tools.ietf.org/html/rfc7230#section-3.2.4)。
