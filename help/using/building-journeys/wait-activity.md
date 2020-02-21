---
title: 待機アクティビティ
description: 待機アクティビティについて
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
source-git-commit: 6274426ec04315149fb430b847498c0e20164bae

---


# 待機アクティビティ{#section_rlm_nft_dgb}

パス内の次のアクティビティを実行する前に待機する場合は、アクティビティを使用で **[!UICONTROL Wait]** きます。 次のアクティビティを実行するタイミングを定義できます。 次の4つのオプションを使用できます。

* [期間](#duration)
* [固定日](#fixed_date)
* [カスタム](#custom)
* [電子メール送信時間の最適化](#email_send_time_optimization)

## Waitアクティビティについて{#about_wait}

複数の待機を並行して使用する場合、待機の優先順位は次のようになります。 同じ時間設定で、異なる重複する条件を持つ場合、上に配置した待機が優先されます。 例えば、最初の待機の条件は「女性」で、2番目の待機の条件は「VIP」です。 最初の待機アクティビティが優先されます

また、2つの異なる待機が並行して行われる場合、最初に行われた待機が、垂直位置に関係なく優先順位付けされます。 例えば、1時間以上の待機が30分未満の場合、30分後の待機が処理されます。

特定の母集団に対して待機を制限する場合は、条件を定義できます。

>[!NOTE]
>
>最大待機時間は30日です。
>
>テストモードでは、 **Wait time in test** （テストモードでの待機時間）パラメーターを使用して、各待機アクティビティが持続する時間を定義できます。 デフォルトの時間は10秒です。 これにより、テスト結果を迅速に取得できます。 [](../building-journeys/testing-the-journey.md)を参照してください。

## 待機時間{#duration}

次のアクティビティが実行されるまでの待機時間を選択します。

![](../assets/journey55.png)

## 固定日の待機{#fixed_date}

次のアクティビティの実行日を選択します。 固定日付を定義する場合は、タイムゾーンを指定する必要があります。 [](../building-journeys/timezone-management.md)を参照してください。

![](../assets/journey56.png)

## カスタム待機{#custom}

このオプションを使用すると、イベントやデータソースからのフィールドに基づく高度な式を使用して、2020年7月12日午後5時などのカスタム日付を定義できます。 カスタム期間（例：7日）は定義できません。 式エディターの式は、dateTimeOnly形式を指定する必要があります。 [](../expression/expressionadvanced.md)を参照してください。dateTimeOnly形式について詳しくは、 [](../expression/data-types.md)

>[!NOTE]
>
>dateTimeOnly式を使用するか、関数を使用してdateTimeOnlyに変換できます。 例：toDateTimeOnly(@{Event.offerOpened.activity.endTime})。このイベント内のフィールドの形式は2016-08-12T09:46:06です。
>
>タイ **ムゾーンは** 、カスタム待機設定ウィンドウの別の場所に必要です。 その結果、インターフェイスから、2016-08-12T09:46:06.982-05のような完全なISO-8601タイムスタンプの混合時間とタイムゾーンのオフセットを直接指定することはできません。 [](../building-journeys/timezone-management.md)を参照してください。

![](../assets/journey57.png)

## 電子メール送信時間の最適化{#email_send_time_optimization}

>[!CAUTION]
>
>電子メール送信時間最適化機能は、Adobe Campaign Standard Data Service機能を使用するお客様のみ利用できます。

このタイプの待機では、プラットフォームで計算されたスコアが使用されます。 スコアは、過去の行動に基づいて、将来的に電子メールをクリックまたは開く傾向を計算します。 スコアを計算するアルゴリズムは、動作する特定の量のデータを必要とします。 その結果、十分なデータがない場合は、デフォルトの待機時間が適用されます。 公開時には、デフォルトの時間が適用されることが通知されます。

>[!NOTE]
>
>旅の最初のイベントは名前空間を持つ必要があります。
>
>この機能は、アクティビティの後でのみ使用で **[!UICONTROL Email]** きます。 Adobe Campaign Standardが必要です。

1. このフィー **[!UICONTROL Amount of time]** ルドで、電子メール送信の最適化を検討する時間数を定義します。
1. このフィールド **[!UICONTROL Optimization type]** で、最適化によってクリック数を増やすか、開くかを選択します。
1. 「デフォルト **の時間** 」フィールドで、予測送信時間スコアが使用できない場合に待機するデフォルトの時間を定義します。

   >[!NOTE]
   >
   >計算を実行するのに十分なデータがないので、送信時間スコアを使用できない場合があります。 この場合、発行時に、デフォルトの時刻が適用されることが通知されます。

![](../assets/journey57bis.png)
