---
product: adobe campaign
title: 待機アクティビティ
description: 待機アクティビティについて説明します
feature: Journeys
role: User
level: Intermediate
exl-id: 819ff3c3-0e3e-4d86-b5d2-10c5b10d19e6
source-git-commit: 77fcc4ba02a855d4d584627625a08abb4af0da2f
workflow-type: ht
source-wordcount: '360'
ht-degree: 100%

---

# 待機アクティビティ{#section_rlm_nft_dgb}

パス内の次のアクティビティを実行するまで待機する場合は、「**[!UICONTROL 待機]**」アクティビティを使用できます。後に続くアクティビティを実行するタイミングを定義できます。選択肢は次の 3 つあります。

* [期間](#duration)
* [カスタム](#custom)
<!--* [Email send time optimization](#email_send_time_optimization)-->

## 待機アクティビティについて{#about_wait}

並行して複数の待機を使用する場合、待機の優先順位は次のように設定されます。時間設定が同じで、条件が異なるが重複している場合は、上位に配置した待機が優先されます。例えば、1 つ目の待機の条件が「女性である」で、並行する 2 つ目の待機の条件が「VIP である」といった場合です。この場合は、1 つ目の待機アクティビティが優先されます。。

また、2 つの異なる待機が並行している場合、上位か下位かに関係なく、最初に発生した待機が優先されます。例えば、1 時間の待機が上位にあり、30 分の待機が下位にある場合、30 分後には 30 分の待機が処理されます。

>[!NOTE]
>
>最大の待機期間は 30 日です。
>
>テストモードでは、「**[!UICONTROL テストの待機時間]**」パラメーターを使用すると、各待機アクティビティの持続時間を定義できます。デフォルト時間は 10 秒です。これにより、テスト結果を迅速に取得できます。[このページ](../building-journeys/testing-the-journey.md)を参照してください。

## 期間待機{#duration}

次のアクティビティを実行するまでの待機期間を選択します。

![](../assets/journey55.png)

## カスタム待機{#custom}

このオプションでは、イベントやデータソースのフィールドに基づく高度な式を使用して、カスタムの日付（例：2020 年 7 月 12 日午後 5 時）を定義できます。カスタムの期間（例えば 7 日など）を定義することはできません。式エディターでは、式を dateTimeOnly 形式にする必要があります。[このページ](../expression/expressionadvanced.md)を参照してください。dateTimeOnly 形式の詳細については、[このページ](../expression/data-types.md)を参照してください。

>[!NOTE]
>
>dateTimeOnly 式を利用するか、関数を使用して dateTimeOnly に変換することができます。例：「toDateTimeOnly(@{Event.offerOpened.activity.endTime})」の場合、イベント内のフィールドは「2016-08-12T09:46:06Z」の形式になります。
>
>ジャーニーのプロパティには&#x200B;**タイムゾーン**&#x200B;が必要です。そのため、今のところ、時刻とタイムゾーンのオフセットを組み合わせた、完全な ISO-8601 タイムスタンプ（2016-08-12T09:46:06.982-05 など）をインターフェイスから直接指定することはできません。[このページ](../building-journeys/timezone-management.md)を参照してください。

![](../assets/journey57.png)

<!--## Email send time optimization{#email_send_time_optimization}

>[!CAUTION]
>
>The email send time optimization capability is only available to customers who use the [Adobe Experience Platform Data Connector](https://docs.adobe.com/content/help/en/campaign-standard/using/developing/mapping-campaign-and-aep-data/aep-about-data-connector.html).

This type of wait uses a score calculated in the Adobe Experience Platform. The score calculates the propensity to click or open an email in the future based on past behavior. Note that the algorithm calculating the score needs a certain amount of data to work. As a result, when it does not have enough data, the default wait time will apply. At publication time, you’ll be notified that the default time applies.

>[!NOTE]
>
>The first event of your journey must have a namespace.
>
>This capability is only available after an **[!UICONTROL Email]** activity. You need to have Adobe Campaign Standard.

1. In the **[!UICONTROL Amount of time]** field, define the number of hours to consider to optimize email sending.
1. In the **[!UICONTROL Optimization type]** field, choose if the optimization should increase clicks or opens.
1. In the **[!UICONTROL Default time]** field, define the default time to wait if the predictive send time score is not available.

    >[!NOTE]
    >
    >Note that the send time score can be unavailable because there is not enough data to perform the calculation. In this case, you will be informed, at publication time, that the default time applies.

![](../assets/journey57bis.png)-->
