---
product: adobe campaign
title: URL 設定
description: URL設定について説明します
feature: ジャーニー
role: User
level: Intermediate
exl-id: e7cba6c4-a231-44f9-927a-10115e7ab1dd
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '142'
ht-degree: 97%

---

# URL 設定 {#concept_gbg_1f1_2gb}

カスタムアクションを設定する場合、次の **[!UICONTROL URL 設定]**&#x200B;パラメーターを定義する必要があります。

![](../assets/journeyurlconfiguration.png)

1. 外部サービスの **[!UICONTROL URL]** を追加します。

   >[!NOTE]
   >
   >セキュリティ上の理由から、HTTPS の使用を強くお勧めします。また、一般公開されていないアドビのアドレスの使用および IP アドレスの使用は許可されていません。

1. 呼び出し&#x200B;**[!UICONTROL メソッド]**&#x200B;を選択します。**[!UICONTROL POST]** または **[!UICONTROL PUT]** を指定できます。
1. 「**[!UICONTROL ヘッダー]**」セクションで、「**[!UICONTROL ヘッダーフィールドを追加]**」をクリックして、新しいキーと値のペアを定義します。これらは、外部サービスに対しておこなわれたリクエストの HTTP ヘッダーに対応します。キーと値のペアを削除するには、「**[!UICONTROL ヘッダー]**」フィールドにカーソルを置き、**[!UICONTROL 削除]**&#x200B;アイコンをクリックします。

   **[!UICONTROL Content-Type]** と **[!UICONTROL Charset]** はデフォルトで設定され、削除または上書きすることはできません。

   >[!NOTE]
   >
   >以下の[解析ルール](https://tools.ietf.org/html/rfc7230#section-3.2.4)に従って、ヘッダーの検証が行われます。
