---
product: adobe campaign
solution: Journey Orchestration
title: URL 設定
description: URLの設定について説明します
feature: ジャーニー
role: Business Practitioner
level: Intermediate
exl-id: e7cba6c4-a231-44f9-927a-10115e7ab1dd
translation-type: tm+mt
source-git-commit: 8ab3951f9c97a0a964f5c123978ed256d3aedc45
workflow-type: tm+mt
source-wordcount: '142'
ht-degree: 9%

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
