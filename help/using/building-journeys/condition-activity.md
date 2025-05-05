---
product: adobe campaign
title: 条件アクティビティ
description: 条件アクティビティについて学ぶ
feature: Journeys
role: User
level: Intermediate
exl-id: 7b44edbe-9d05-4d67-8a64-2a0a553fcb92
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '894'
ht-degree: 93%

---

# 条件アクティビティ{#section_e2n_pft_dgb}


>[!CAUTION]
>
>**Adobe Journey Optimizerをお探しですか** Journey Optimizerのドキュメントについては、[ こちら ](https://experienceleague.adobe.com/ja/docs/journey-optimizer/using/ajo-home){target="_blank"} をクリックしてください。
>
>
>_このドキュメントでは、Journey Optimizerに置き換えられた従来のJourney Orchestration マテリアルについて説明します。 Journey OrchestrationやJourney Optimizerへのアクセスに関するご質問は、アカウントチームにお問い合わせください。_



次の 4 種類の条件を使用できます。

* [データソースの条件](#data_source_condition)
* [時間条件](#time_condition)
* [パーセンテージ分割](#percentage_split)
* [日付条件](#date_condition)

![](../assets/journey49.png)

## 条件アクティビティについて {#about_condition}

ジャーニーで複数の条件を使用する場合は、わかりやすくするために、各条件にラベルを定義できます。

複数の条件を定義する場合は、「**[!UICONTROL パスを追加]**」をクリックします。条件ごとに、キャンバスのアクティビティの後に新しいパスが追加されます。

![](../assets/journey47.png)

ジャーニーの設計には、機能的な影響があることに注意してください。条件の後に複数のパスが定義された場合、最初の有効なパスのみが実行されます。つまり、パスを上下に配置することで、パスの優先順位を変更できます。

例えば、最初のパスの条件「この人物は VIP である」と2番目のパスの条件「この人物は男性である」を例にとってみましょう。両方の条件を満たす人物（VIP の男性）がこのステップを通過した場合、最初のパスが「上」に配置されているため、2 番目のパスに該当しても最初のパスが選択されます。この優先度を変更するには、アクティビティを別の垂直方向の順序に移動します。

![](../assets/journey48.png)

定義された条件に該当しないオーディエンス向けに、別のパスを作成するには、「**[!UICONTROL 上記以外の事例のパスを表示]**」をオンにします。このオプションは、条件分岐では使用できません。[分割された割合](#percentage_split)を参照してください。

シンプルモードでは、フィールドの組み合わせに基づいて単純なクエリを実行できます。使用可能なすべてのフィールドが画面の左側に表示されます。フィールドをメインゾーンにドラッグ＆ドロップします。異なる要素を組み合わせるには、それらを相互に連動させて異なるグループやグループレベルを作成します。次に、論理演算子を選択して、同じレベルの要素を組み合わせることができます。

* AND：2 つの基準の積集合（共通部分）。すべて条件に一致する要素のみが考慮されます。
* OR：2 つの基準の和集合。2 つの条件の少なくとも 1 つに一致する要素が考慮されます。

![](../assets/journey64.png)

[Adobe Experience Platform Segmentation Service](https://experienceleague.adobe.com/docs/experience-platform/segmentation/home.html?lang=ja) を使用してセグメントを作成している場合は、それらのセグメントをジャーニー条件で利用できます。[条件でのセグメントの使用](../segment/using-a-segment.md)を参照してください。


>[!NOTE]
>
>単純なエディターでは、時系列（購入のリスト、メッセージの過去のクリックなど）に対してクエリを実行できません。このためには、高度なエディターを使用する必要があります。[このページ](../expression/expressionadvanced.md)を参照してください。

アクションまたは条件でエラーが発生すると、個人のジャーニーが停止します。続行するには、「**[!UICONTROL タイムアウトまたはエラーの場合に代替パスを追加]**」チェックボックスをオンにするだけです。[この節](../building-journeys/using-the-journey-designer.md#paths)を参照してください。

シンプルなエディターでは、イベントカテゴリとデータソースカテゴリの下に、「ジャーニーのプロパティ」カテゴリも表示されます。このカテゴリには、特定のプロファイルのジャーニーに関連するテクニカルフィールドが含まれています。これは、ジャーニー ID や発生した特定のエラーなど、システムによってライブジャーニーから取得される情報です。詳しくは、[ このページ ](../expression/journey-properties.md) を参照してください

## データソースの条件 {#data_source_condition}

これにより、データソースのフィールドまたはジャーニー内で以前に配置されたイベントーに基づいて条件を定義できます。式エディターの使用方法については、[このページ](../expression/expressionadvanced.md)を参照してください。高度な式エディターを使用すると、コレクションを操作する、またはパラメーターを渡す必要があるデータソースを使用する、より高度な条件を設定できます。[このページ](../datasource/external-data-sources.md)を参照してください。

![](../assets/journey50.png)

## 時間条件{#time_condition}

これにより、時間帯や曜日に応じて異なるアクションを実行できます。例えば、日中に SMS メッセージを送信し、平日の夜にメールを送信するように指定できます。

>[!NOTE]
>
>タイムゾーンは条件に固有ではなくなり、ジャーニープロパティのジャーニーレベルで定義されるようになりました。[このページ](../building-journeys/timezone-management.md)を参照してください。

![](../assets/journey51.png)

## パーセンテージ分割 {#percentage_split}

このオプションを使用すると、オーディエンスをランダムに分割して、グループごとに異なるアクションを定義できます。各パスの分割数と再分割数を定義します。分割計算は統計的なもので、システムはジャーニーのこのアクティビティに流れる人数を予測することはできません。その結果、分割の許容誤差は非常に小さくなります。この関数は、Java のランダムメカニズムに基づいています（この[ページ](https://docs.oracle.com/javase/7/docs/api/java/util/Random.html)を参照）。

テストモードでは、分割に達すると、常に上位の分岐が選択されます。テストで別のパスを選択する場合は、分割された分岐の位置を再編成できます。[このページ](../building-journeys/testing-the-journey.md)を参照してください。

>[!NOTE]
>
>割合条件分岐には、パスを追加するボタンはありません。パスの数は、分割数によって異なります。条件分岐では、他のケースではパスは発生しないので、パスを追加できません。ユーザーは常に、分割されたパスの 1 つに入ります。

![](../assets/journey52.png)

## 日付条件 {#date_condition}

これにより、日付に基づいて異なるフローを定義できます。例えば、「セール」期間中にステップにエントリした人には、特定のメッセージが送信されます。残りの期間には、別のメッセージを送信します。

>[!NOTE]
>
>タイムゾーンは条件に固有ではなくなり、ジャーニープロパティのジャーニーレベルで定義されるようになりました。[このページ](../building-journeys/timezone-management.md)を参照してください。

![](../assets/journey53.png)

<!--
## Profile cap {#profile_cap}

Use this condition type to set a maximum number of profiles for a journey path. When this limit is reached, the selected profiles take a second path.

You can use this condition type to ramp up the volume of your deliveries. For example, you might have recently moved to another email service provider, IP address, or email domain or subdomain. Using this feature, you can establish your reputation as a sender and avoid that your deliveries be blocked or moved to the spam folder of the recipients' mailbox. Learn how to increase your email reputation with IP warming in the [Deliverability Best Practice Guide](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/generic-resources/increase-reputation-with-ip-warming.html?lang=ja){target="_blank"}.

The default cap is 1000. You must set an integer value that is greater than or equal to 1.

The counter applies only to the selected journey version. By default, the counter is reset to zero after 180 days. After a reset, the selected profiles take the first path again until the counter limit is reached. You can gradually increase this limit up to the total number of your subscribers. After your IP has warmed up, you can remove this condition.

The first path always has priority over the second path, even if you move the second path above the first path on the journey canvas.

![](../assets/profile-cap-condition.png)
-->