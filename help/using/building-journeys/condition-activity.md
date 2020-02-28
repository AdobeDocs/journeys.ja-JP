---
title: 条件アクティビティ
description: 条件のアクティビティについて
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
source-git-commit: 538b350165365479caef499a74346381643033d5

---


# 条件アクティビティ{#section_e2n_pft_dgb}

次の4種類の条件を使用できます。

* [データソースの条件](#data_source_condition)
* [時間条件](#time_condition)
* [割合の分割](#percentage_split)
* [日付条件](#date_condition)

![](../assets/journey49.png)

## Conditionアクティビティについて {#about_condition}

複数の条 **[!UICONTROL Add a path]** 件を定義する場合は、をクリックします。 条件ごとに、アクティビティの後に新しいパスがキャンバスに追加されます。

![](../assets/journey47.png)

ジャーニーのデザインは機能的な影響を及ぼします 条件の後に複数のパスが定義された場合は、最初の有効なパスのみが実行されます。 つまり、パスを相互に上下に配置することで、パスの優先順位付けを変更できます。 例えば、最初のパスの条件が「The person is a VIP」で、2番目のパスの条件が「The person is a male」の場合、 両方の条件を満たす人（VIPの男性）がこの手順に合格した場合、最初のパスは、2番目のパスにも適格である場合でも選択されます。1番目のパスは「上」にあるためです。 この優先順位を変更するには、アクティビティを別の垂直順序に移動します。

![](../assets/journey48.png)

定義した条件に適合しないオーディエンスに対して、別のパスを作成するには、このオプションをオンにしま **[!UICONTROL Show path for other cases than the one(s) above]**&#x200B;す。 このオプションは、分割条件では使用できません。 割合分 [割を参照](#percentage_split)。

シンプルモードでは、フィールドの組み合わせに基づいて単純なクエリを実行できます。 使用可能なすべてのフィールドが画面の左側に表示されます。 フィールドをメインゾーンにドラッグ&amp;ドロップします。 異なる要素を組み合わせるには、それらを相互に連動させて異なるグループやグループレベルを作成します。 次に、論理演算子を選択して、同じレベルの要素を組み合わせることができます。

* AND:2つの条件の交差。 すべての条件に一致する要素のみが考慮されます。
* OR:2つの条件の和。 2つの条件の少なくとも1つに一致する要素が考慮されます。

![](../assets/journey64.png)

>[!NOTE]
>
>単純なエディターでは、時系列（購入のリスト、メッセージの過去のクリックなど）に対するクエリを実行できません。 このためには、アドバンスエディターを使用する必要があります。 [](../expression/expressionadvanced.md)を参照してください。

## データソースの条件 {#data_source_condition}

これにより、データソースのフィールドや、以前にジャーニーに配置されたイベントに基づいて条件を定義できます。 エクスプレッションエディタの使用方法については、を参照してくださ [](../expression/expressionadvanced.md)い。 高度な式エディターを使用して、コレクションを操作したり、パラメーターを渡す必要があるデータソースを使用したりする、より高度な条件を設定できます。 [](../datasource/external-data-sources.md)を参照してください。

![](../assets/journey50.png)

## 時間条件{#time_condition}

これにより、時間帯や曜日に応じて様々なアクションを実行できます。 例えば、昼間にSMSメッセージを送信し、平日の夜に電子メールを送信することができます。

>[!NOTE]
>
>タイムゾーンは、条件に固有のものではなくなり、ジャーニープロパティのジャーニーレベルで定義されるようになりました。 [](../building-journeys/timezone-management.md)を参照してください。

![](../assets/journey51.png)

## 割合の分割 {#percentage_split}

このオプションを使用すると、オーディエンスをランダムに分割して、各グループに異なるアクションを定義できます。 各パスの分割数と再分割数を定義します。 分割計算は統計的なもので、この旅行のアクティビティで何人の人がフローするかを予測できません。 その結果、分割のエラーマージンは非常に低くなります。 この関数は、Javaのランダムメカニズムに基づいています(このページ [を参照](https://docs.oracle.com/javase/7/docs/api/java/util/Random.html))。

>[!NOTE]
>
>割合分割条件では、パスを追加するボタンはありません。 パスの数は分割の数によって異なります。 分割条件では、他のケースのパスは発生しないので、追加できません。 ユーザーは常に、分割されたパスの1つに入ります。


![](../assets/journey52.png)

## 日付条件 {#date_condition}

これにより、日付に基づいて異なるフローを定義できます。 例えば、「sales」期間中にその人がステップに入った場合、その人に特定のメッセージを送信します。 残りの年は、別のメッセージを送ります。

>[!NOTE]
>
>タイムゾーンは、条件に固有のものではなくなり、ジャーニープロパティのジャーニーレベルで定義されるようになりました。 [](../building-journeys/timezone-management.md)を参照してください。

![](../assets/journey53.png)
