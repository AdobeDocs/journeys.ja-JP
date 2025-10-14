---
product: adobe campaign
title: カスタムアクションの使用
description: アクションアクティビティについて学ぶ
feature: Journeys
role: User
level: Intermediate
exl-id: 9996d1eb-ddef-46dd-aaa9-c37fa9deb2f9
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '306'
ht-degree: 84%

---

# カスタムアクションの使用 {#section_f2c_hbg_nhb}


>[!CAUTION]
>
>**Adobe Journey Optimizerをお探しですか** Journey Optimizerのドキュメントについては、[&#x200B; こちら &#x200B;](https://experienceleague.adobe.com/ja/docs/journey-optimizer/using/ajo-home){target="_blank"} をクリックしてください。
>
>
>_このドキュメントでは、Journey Optimizerに置き換えられた従来のJourney Orchestration マテリアルについて説明します。 Journey OrchestrationやJourney Optimizerへのアクセスに関するご質問は、アカウントチームにお問い合わせください。_


アクティビティ設定ペインには、URL 設定パラメーターと、カスタムアクション用に設定された認証パラメーターが表示されます。[詳細情報](../action/about-custom-action-configuration.md)。

## URL 設定

### 動的パス

URL に動的パスが含まれる場合は、「**[!UICONTROL パス]**」フィールドでパスを指定します。

>[!NOTE]
>
>ジャーニーでは URL の静的な部分を設定できませんが、カスタムアクションのグローバル設定では設定できます。[詳細情報](../action/about-custom-action-configuration.md)。

フィールドとプレーンテキスト文字列を連結するには、高度な式エディターで文字列関数またはプラス記号（+）を使用します。プレーンテキスト文字列を一重引用符（&#39;）または二重引用符（&quot;）で囲みます。[詳細情報](../expression/expressionadvanced.md)。

この表は、設定の例を示しています

| フィールド | 値 |
| --- | --- |
| URL | `https://xxx.yyy.com:8080/somethingstatic/` |
| パス | `The id of marketingCampaign + '/messages'` |

連結された URL の形式は次のとおりです。

`https://xxx.yyy.com:8080/somethingstatic/`\&lt;キャンペーン ID\>`/messages`

![](../assets/journey-custom-action-url.png)

### ヘッダー

「**[!UICONTROL URL 設定]**」セクションには、動的ヘッダーフィールドが表示されますが、定数ヘッダーフィールドは表示されません。動的ヘッダーフィールドは、値が変数として設定される HTTP ヘッダーフィールドです。[詳細情報](../action/about-custom-action-configuration.md)。

必要に応じて、動的ヘッダーフィールドの値を指定します。

1. ジャーニーのカスタムアクションを選択します。
1. 設定ペインで、「**[!UICONTROL URL 設定]**」セクションのヘッダーフィールドの横にある鉛筆アイコンをクリックします。

   ![](../assets/journey-dynamicheaderfield.png)

1. フィールドを選択し、「**[!UICONTROL OK]**」をクリックします。

## アクションパラメーター

「**[!UICONTROL アクションパラメーター]**」セクションには、_「変数」_&#x200B;として定義されたメッセージパラメーターが表示されます。これらのパラメーターについては、この情報の取得先（例：イベント、データソース）を定義したり、値を手動で渡したり、高度なユースケースに高度な式エディターを使用したりできます。高度なユースケースとしては、データ操作などの関数の使用が考えられます。[詳細情報](../expression/expressionadvanced.md)

**関連トピック**

[アクションの設定](../action/about-custom-action-configuration.md)
