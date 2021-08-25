---
product: adobe campaign
title: URL 設定
description: URL設定について説明します
feature: Journeys
role: User
level: Intermediate
exl-id: e7cba6c4-a231-44f9-927a-10115e7ab1dd
source-git-commit: e71d641888caa9385d078d9c85e073b5f1ed743f
workflow-type: tm+mt
source-wordcount: '330'
ht-degree: 17%

---

# URL 設定 {#concept_gbg_1f1_2gb}

カスタムアクションを設定する場合、次の **[!UICONTROL URL 設定]**&#x200B;パラメーターを定義する必要があります。

![](../assets/journeyurlconfiguration.png)

1. 「**[!UICONTROL URL]**」フィールドに、外部サービスのURLを指定します。

   * URLが静的な場合は、このフィールドにURLを入力します。

   * URLに動的パスが含まれる場合は、URLの静的な部分（スキーム、ホスト、ポート、オプションでパスの静的な部分）のみを入力します。

      例：`https://xxx.yyy.com:8080/somethingstatic/`

      カスタムアクションをジャーニーに追加する際に、URLの動的パスを指定します。 [詳細情報](../building-journeys/using-custom-actions.md)。
   >[!NOTE]
   >
   >セキュリティ上の理由から、URLにはHTTPSスキームを使用することを強くお勧めします。 また、一般公開されていないアドビのアドレスの使用および IP アドレスの使用は許可されていません。

1. 呼び出し&#x200B;**[!UICONTROL メソッド]**&#x200B;を選択します。**[!UICONTROL POST]** または **[!UICONTROL PUT]** を指定できます。
1. **[!UICONTROL Headers]**&#x200B;セクションで、外部サービスに送信する要求メッセージのHTTPヘッダーを定義します。
   1. ヘッダーフィールドを追加するには、「**[!UICONTROL ヘッダーフィールドを追加]**」をクリックします。
   1. ヘッダーフィールドのキーを入力します。
   1. キーと値のペアに動的な値を設定するには、**[!UICONTROL Variable]**&#x200B;を選択します。 それ以外の場合は、「**[!UICONTROL 定数]**」を選択します。

      例えば、タイムスタンプの場合、動的値を設定できます。

   1. 「**[!UICONTROL 定数]**」を選択した場合は、定数値を入力します。

      **[!UICONTROL 変数]**&#x200B;を選択した場合、カスタムアクションをジャーニーに追加する際にこの変数を指定します。 [詳細情報](../building-journeys/using-custom-actions.md)。

      ![](../assets/journeyurlconfiguration2.png)

   1. ヘッダーフィールドを削除するには、ヘッダーフィールドをポイントし、**[!UICONTROL 削除]**&#x200B;アイコンをクリックします。
   **[!UICONTROL Content-Type]**&#x200B;および&#x200B;**[!UICONTROL Charset]**&#x200B;ヘッダーフィールドは、デフォルトで設定されます。 これらのフィールドは変更または削除できません。

   カスタムアクションをジャーニーに追加した後も、ジャーニーがドラフトステータスの場合は、ヘッダーフィールドを追加できます。 設定の変更によるジャーニーの影響を受けない場合は、カスタムアクションを複製し、新しいカスタムアクションにヘッダーフィールドを追加します。

   >[!NOTE]
   >
   >ヘッダーは、フィールド解析ルールに従って検証されます。 [詳細情報](https://tools.ietf.org/html/rfc7230#section-3.2.4)。
