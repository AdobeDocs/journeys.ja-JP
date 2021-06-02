---
product: adobe campaign
title: URL 設定
description: URL設定について説明します
feature: ジャーニー
role: Business Practitioner
level: Intermediate
exl-id: e7cba6c4-a231-44f9-927a-10115e7ab1dd
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '142'
ht-degree: 9%

---

# URL 設定 {#concept_gbg_1f1_2gb}

カスタムアクションを設定する場合、次の&#x200B;**[!UICONTROL URL Configuration]**&#x200B;パラメーターを定義する必要があります。

![](../assets/journeyurlconfiguration.png)

1. 外部サービスの&#x200B;**[!UICONTROL URL]**&#x200B;を追加します。

   >[!NOTE]
   >
   >セキュリティ上の理由から、HTTPS の使用を強くお勧めします。パブリックでないAdobeアドレスの使用とIPアドレスの使用は許可されていません。

1. 呼び出し&#x200B;**[!UICONTROL メソッド]**&#x200B;を選択します。**[!UICONTROL POST]**&#x200B;または&#x200B;**[!UICONTROL PUT]**&#x200B;を指定できます。
1. 「**[!UICONTROL Headers]**」セクションで、「**[!UICONTROL Add a header field]**」をクリックして、新しいキーと値のペアを定義します。 これらは、外部サービスに対しておこなわれた要求のHTTPヘッダーに対応します。 キーと値のペアを削除するには、**[!UICONTROL Headers]**&#x200B;フィールドにカーソルを置き、**[!UICONTROL 削除]**&#x200B;アイコンをクリックします。

   **[!UICONTROL Content-TypeとCharset]** はデ **** フォルトで設定され、削除または上書きできません。

   >[!NOTE]
   >
   >ヘッダーは、以下の[解析ルール](https://tools.ietf.org/html/rfc7230#section-3.2.4)に従って検証されます。
