---
product: adobe campaign
title: 待機アクティビティ
description: 待機アクティビティの詳細
feature: ジャーニー
role: Business Practitioner
level: Intermediate
exl-id: 819ff3c3-0e3e-4d86-b5d2-10c5b10d19e6
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '392'
ht-degree: 5%

---

# 待機アクティビティ{#section_rlm_nft_dgb}

パス内の次のアクティビティを実行する前に待機する場合は、**[!UICONTROL 待機]**&#x200B;アクティビティを使用できます。 次のアクティビティを実行するタイミングを定義できます。 次の 3 つのオプションを選択できます。

* [期間](#duration)
* [固定日](#fixed_date)
* [カスタム](#custom)

<!--* [Email send time optimization](#email_send_time_optimization)-->

## 待機アクティビティについて{#about_wait}

複数の待機を並行して使用する場合、待機の優先順位付けの方法を次に示します。 同じ時間設定で、重なり合う条件が異なる場合、上に配置された待機が優先順位付けされます。 例えば、最初の待機の条件は「女性」で、2番目の待機の条件は「VIP」です。 最初の待機アクティビティが優先順位付けされます

また、2つの異なる待機が並行している場合は、垂直方向の位置に関係なく、最初に発生した待機が優先されます。 例えば、1時間の待機が以上で30分の待機が未満の場合、30分後に30分の待機が処理されます。

待機を特定の母集団に制限する場合は、条件を定義できます。

>[!NOTE]
>
>最大待機時間は30日です。
>
>テストモードでは、**[!UICONTROL Wait time in test]**&#x200B;パラメーターを使用して、各待機アクティビティが持続する時間を定義できます。 デフォルト時間は 10 秒です。これにより、テスト結果を迅速に取得できます。 [このページ](../building-journeys/testing-the-journey.md)を参照

## 待機時間{#duration}

次のアクティビティが実行されるまでの待機時間を選択します。

![](../assets/journey55.png)

## 固定日の待機{#fixed_date}

次のアクティビティの実行日を選択します。

![](../assets/journey56.png)

## カスタム待機{#custom}

このオプションを使用すると、イベントやデータソースから取得したフィールドに基づく高度な式を使用して、2020年7月12日午後5時などのカスタム日付を定義できます。 カスタムの期間（例：7日）を定義することはできません。 式エディターの式は、 dateTimeOnly形式を指定する必要があります。 [このページ](../expression/expressionadvanced.md)を参照してください。dateTimeOnlyの形式について詳しくは、[このページ](../expression/data-types.md)を参照してください。

>[!NOTE]
>
>dateTimeOnly式を利用するか、関数を使用してdateTimeOnlyに変換することができます。 例：toDateTimeOnly(@{Event.offerOpened.activity.endTime})：イベントのフィールドの形式は2016-08-12T09:46:06Zです。
>
>ジャーニーのプロパティには、**タイムゾーン**&#x200B;が必要です。 その結果、現在のインターフェイスから、2016-08-12T09:46:06.982-05のような、完全なISO-8601タイムスタンプの混合時間とタイムゾーンのオフセットを直接指すことはできません。 [このページ](../building-journeys/timezone-management.md)を参照してください。

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
