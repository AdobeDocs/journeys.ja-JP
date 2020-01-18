---
title: URL設定
description: URLの設定について
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

---


# URL configuration {#concept_gbg_1f1_2gb}

カスタムアクションを設定する場合は、次のパラメーターを定義する必要があ **[!UICONTROL URL Configuration]**ります。

![](../assets/journeyurlconfiguration.png)

1. 外部サービ **[!UICONTROL URL]**スのを追加します。

   >[!NOTE]
   >
   >セキュリティ上の理由から、HTTPSの使用を強くお勧めします。 パブリックでないアドビのアドレスおよびIPアドレスの使用は許可されません。

1. 呼び出しを選択しま **[!UICONTROL Method]**す。またはのいずれか**[!UICONTROL POST]** です **[!UICONTROL PUT]**。
1. セクション **[!UICONTROL Headers]**で、をクリックし**[!UICONTROL Add a header field]** て新しいキー/値のペアを定義します。 これらは、外部サービスに対して行われた要求のHTTPヘッダーに対応します。 キーと値のペアを削除するには、フィールドにカーソルを置 **[!UICONTROL Headers]**き、アイコンをクリック**[!UICONTROL Delete]** します。

   **[!UICONTROL Content-Type]**とは、デ**[!UICONTROL Charset]** フォルトで設定され、削除または上書きはできません。

   >[!NOTE]
   >
   >ヘッダーは、次の解析ルールに従って検 [証されます](https://tools.ietf.org/html/rfc7230#section-3.2.4)。
