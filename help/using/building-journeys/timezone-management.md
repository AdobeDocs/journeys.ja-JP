---
product: adobe campaign
title: タイムゾーン管理
description: タイムゾーン管理について説明します。
feature: Journeys
role: User
level: Intermediate
exl-id: c0e67849-caa0-4045-94ed-38e483054e1d
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '322'
ht-degree: 86%

---

# タイムゾーン管理 {#timezone_management}


>[!CAUTION]
>
>**Adobe Journey Optimizerをお探しですか** Journey Optimizerのドキュメントについては、[&#x200B; こちら &#x200B;](https://experienceleague.adobe.com/ja/docs/journey-optimizer/using/ajo-home){target="_blank"} をクリックしてください。
>
>
>_このドキュメントでは、Journey Optimizerに置き換えられた従来のJourney Orchestration マテリアルについて説明します。 Journey OrchestrationやJourney Optimizerへのアクセスに関するご質問は、アカウントチームにお問い合わせください。_



タイムゾーンは、ジャーニーの[プロパティ](../building-journeys/changing-properties.md)で定義できます。

「プロパティ」にアクセスするには、画面の右上にある鉛筆アイコンをクリックします。

このタイムゾーンは、次のような時間要素を含むジャーニーのすべてのアクティビティで使用されます。

* [時間条件](../building-journeys/condition-activity.md#time_condition)
* [日付条件](../building-journeys/condition-activity.md#date_condition)
* [カスタム待機](../building-journeys/wait-activity.md#custom)

タイムゾーンを選択するか、ユーザープロファイルで定義されたタイムゾーンを使用するかを選択できます。

>[!NOTE]
>
>プロファイルタイムゾーンは、**環境設定詳細** フィールドグループにある **timeZone** フィールドと連携します。

## 固定タイムゾーンの定義 {#fixed-timezone}

タイムゾーンを固定することもできます。定義済みのタイムゾーンをクリアし、ドロップダウンリストからタイムゾーンを選択します。固定タイムゾーンを使用すると、ジャーニーにエントリするすべての個人のタイムゾーンは同じになります。

これをおこなうには、「**[!UICONTROL プロパティ]**」でタイムゾーンを選択します。

![](../assets/journey72.png)

## プロファイルを使用したジャーニータイムゾーンの定義 {#timezone-from-profiles}

ジャーニーのエントリイベントに名前空間がある（ジャーニーが Adobe Experience Platform のリアルタイム顧客プロファイルサービスにアクセスする）場合、プロファイルレベルで定義されたタイムゾーンを使用できます。 これを行うには、**プロパティ**&#x200B;で、「**タイマーと条件でプロファイルのタイムゾーンを使用する**」のチェックをオンにします。このオプションは、デフォルトではオンになっていません。

プロファイルのタイムゾーンが定義されている場合、そのタイムゾーンが取得され、ジャーニーで使用されます。タイムゾーンが定義されていない場合、使用されるタイムゾーンは、 タイムゾーンフィールドで定義されたタイムゾーンになります。

![](../assets/journey73.png)

## タイムゾーン式の使用 {#timezone-in-expressions}

ジャーニーの開始日と終了日を特定のタイムゾーンにリンクすることはできません。これらはインスタンスのタイムゾーンに自動的に関連付けられます。
