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

カスタムアクションを設定する場合、次の&#x200B;**[!UICONTROL URL Configuration]**&#x200B;パラメーターを定義する必要があります。

![](../assets/journeyurlconfiguration.png)

1. 追加外部サービスの&#x200B;**[!UICONTROL URL]**。

   >[!NOTE]
   >
   >セキュリティ上の理由から、HTTPS の使用を強くお勧めします。パブリックでないAdobeアドレスの使用とIPアドレスの使用は許可されません。

1. 呼び出し&#x200B;**[!UICONTROL メソッド]**&#x200B;を選択します。**[!UICONTROL POST]**&#x200B;または&#x200B;**[!UICONTROL PUT]**&#x200B;を指定できます。
1. 「**[!UICONTROL ヘッダー]**」セクションで、**[!UICONTROL ヘッダーフィールド追加]**&#x200B;をクリックして、新しいキーと値のペアを定義します。 これらは、外部サービスに対して行われた要求のHTTPヘッダーに対応します。 キーと値のペアを削除するには、**[!UICONTROL ヘッダー]**&#x200B;フィールドにカーソルを置き、**[!UICONTROL 削除]**&#x200B;アイコンをクリックします。

   **[!UICONTROL Content-]** Typeと **** Charsetはデフォルトで設定され、削除または上書きはできません。

   >[!NOTE]
   >
   >以下の[解析ルール](https://tools.ietf.org/html/rfc7230#section-3.2.4)に従って、ヘッダーの検証が行われます。
