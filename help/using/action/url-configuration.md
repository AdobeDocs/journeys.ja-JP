---
product: adobe campaign
title: URL 設定
description: URL設定について詳しく見る
feature: Journeys
role: User
level: Intermediate
exl-id: e7cba6c4-a231-44f9-927a-10115e7ab1dd
product_v2:
  - id: cf67d108-ecf9-4fde-af49-3a3c39083bc8
    internal-label: Journey Orchestration
feature_v2:
  - id: 7de3230f-9523-5ba5-8d5c-2313288b27ef
    internal-label: Journeys
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
source-git-commit: 255cd6677e7c9ebff63ea9a1028a042c19e63ecc
workflow-type: tm+mt
source-wordcount: '404'
ht-degree: 99%
---
# URL 設定 {#concept_gbg_1f1_2gb}



>[!CAUTION]
>
>**Adobe Journey Optimizer をお探しですか**？ Journey Optimizer のドキュメントについて詳しくは、[こちら](https://experienceleague.adobe.com/ja/docs/journey-optimizer/using/ajo-home){target="_blank"}をクリックしてください。
>
>
>_このドキュメントは、Journey Optimizer に置き換えられた従来の Journey Orchestration 資料を参照しています。 Journey Orchestration または Journey Optimizer へのアクセスについてご質問がある場合は、アカウントチームにお問い合わせください。_


カスタムアクションを設定する場合、次の **[!UICONTROL URL 設定]**&#x200B;パラメーターを定義する必要があります。

![](../assets/journeyurlconfiguration.png)

1. 「**[!UICONTROL URL]**」フィールドに、外部サービスの URL を指定します。

   * URL が静的な場合は、このフィールドに URL を入力します。

   * URL に動的パスが含まれる場合は、URL の静的な部分（スキーム、ホスト、ポート、オプションでパスの静的な部分）のみを入力します。

     例：`https://xxx.yyy.com/somethingstatic/`

     URL の動的パスは、カスタムアクションをジャーニーに追加する際に指定します。 [学習を増やす](../building-journeys/using-custom-actions.md)。

   >[!NOTE]
   >
   >セキュリティ上の理由から、URL には HTTPS スキームを使用することを強くお勧めします。 また、アドビの非公開アドレスや IP アドレスの使用は許可されていません。
   >
   >カスタムアクションを定義する場合は、デフォルトのポートのみ使用できます。http の場合は 80、https の場合は 443 です。

1. 呼び出し&#x200B;**[!UICONTROL メソッド]**&#x200B;を選択します。**[!UICONTROL POST]** または **[!UICONTROL PUT]** を指定できます。
1. 「**[!UICONTROL ヘッダー]**」セクションでは、外部サービスに送信されるリクエストメッセージの HTTP ヘッダーを定義します。
   1. ヘッダーフィールドを追加するには、「**[!UICONTROL ヘッダーフィールドを追加]**」をクリックします。
   1. ヘッダーフィールドのキーを入力します。
   1. キーと値のペアに動的な値を設定するには、「**[!UICONTROL 変数]**」を選択します。 それ以外の場合は、「**[!UICONTROL 定数]**」を選択します。

      例えば、タイムスタンプの場合、動的値を設定できます。

   1. 「**[!UICONTROL 定数]**」を選択した場合は、定数値を入力します。

      「**[!UICONTROL 変数]**」を選択した場合は、カスタムアクションをジャーニーに追加する際に、この変数を指定します。 [詳細情報](../building-journeys/using-custom-actions.md)

      ![](../assets/journeyurlconfiguration2.png)

   1. ヘッダーフィールドを削除するには、ヘッダーフィールドをポイントし、「**[!UICONTROL 削除]**」アイコンをクリックします。

   **[!UICONTROL Content-Type]** および **[!UICONTROL Charset]** ヘッダーフィールドは、デフォルトで設定されます。 これらのフィールドは変更または削除できません。

   カスタムアクションをジャーニーに追加した後でも、ジャーニーがドラフトステータスの場合は、ヘッダーフィールドを追加できます。 設定変更によってジャーニーに影響を与えたくない場合は、カスタムアクションを複製し、ヘッダーフィールドを新しいカスタムアクションに追加します。

   >[!NOTE]
   >
   >ヘッダーは、フィールド解析ルールに従って検証されます。 [学習を増やす](https://tools.ietf.org/html/rfc7230#section-3.2.4)。
