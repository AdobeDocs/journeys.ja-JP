---
product: adobe campaign
title: Journey Orchestration イベント用の ExperienceEvent スキーマについて
description: Journey Orchestration イベント用の ExperienceEvent スキーマについて学ぶ
feature: Journeys
role: User
level: Intermediate
exl-id: ffec0d42-8632-4806-97df-da2a2372ca53
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '762'
ht-degree: 70%

---

# [!DNL Journey Orchestration] イベントの ExperienceEvent スキーマについて


>[!CAUTION]
>
>**Adobe Journey Optimizerをお探しですか** Journey Optimizerのドキュメントについては、[&#x200B; こちら &#x200B;](https://experienceleague.adobe.com/ja/docs/journey-optimizer/using/ajo-home){target="_blank"} をクリックしてください。
>
>
>_このドキュメントでは、Journey Optimizerに置き換えられた従来のJourney Orchestration マテリアルについて説明します。 Journey OrchestrationやJourney Optimizerへのアクセスに関するご質問は、アカウントチームにお問い合わせください。_



[!DNL Journey Orchestration] イベントは、ストリーミング取得を介してAdobe Experience Platformに送信される XDM エクスペリエンスイベントです。

そのため、[!DNL Journey Orchestration] のイベントを設定するための重要な前提条件は、Adobe Experience Platformの Experience Data Model （または XDM）と XDM Experience Data スキーマの作成方法、および XDM 形式のデータをAdobe Experience Platformにストリーミングする方法に精通していることです。

## [!DNL Journey Orchestration] イベントのスキーマ要件

[!DNL Journey Orchestration] のイベントを設定する最初の手順は、イベントを表す XDM スキーマと、Adobe Experience Platformでイベントのインスタンスを記録するために作成されたデータセットを確実に用意することです。 イベント用データセットは必ずしも必要ではありませんが、特定のデータセットにイベントを送信すると、ユーザーのイベント履歴を保持して後から参照および分析できるので便利です。イベントに適したスキーマとデータセットがまだない場合は、これらのタスクの両方をAdobe Experience Platformの web インターフェイスで実行できます。

![](../assets/schema1.png)

[!DNL Journey Orchestration] イベントに使用される XDM スキーマは、以下の要件を満たす必要があります。

* スキーマは、XDM ExperienceEvent クラスである必要があります。

  ![](../assets/schema2.png)

* システム生成イベントの場合、スキーマにオーケストレーション eventID Mixin を含める必要があります。[!DNL Journey Orchestration] はこのフィールドを使用して、ジャーニーで使用されるイベントを識別します。

  ![](../assets/schema3.png)

* イベントの件名を識別するための ID フィールドを宣言します。ID が指定されていない場合は、ID マップを使用できます。この方法は推奨されません。

  ![](../assets/schema4.png)

* このデータを後からジャーニーで参照できるようにする場合は、プロファイルのスキーマとデータセットをマークします。

  ![](../assets/schema5.png)

  ![](../assets/schema6.png)

* ユーザーに関する情報、イベントの生成元のデバイス、場所、イベントに関連するその他の有意義な状況など、イベントに含めたいその他のコンテキストデータを取り込むためのデータフィールドを自由に含めることができます。

  ![](../assets/schema7.png)

  ![](../assets/schema8.png)

## スキーマ間の関係の活用{#leverage_schema_relationships}

Adobe Experience Platform では、あるデータセットを別のデータセットの参照テーブルとして使用するために、スキーマ間の関係を定義できます。

ブランドデータモデルに、購入をキャプチャするスキーマがあるとします。また、製品カタログのスキーマもあります。購入スキーマで製品 ID をキャプチャし、関係を使用して、製品カタログからより完全な製品詳細を検索できます。これにより、例えばノートパソコンを購入したすべての顧客を対象としたセグメントを作成することができます。その際、すべてのノートパソコン ID を明示的にリストアップしたり、トランザクションシステムで製品の詳細をすべてキャプチャしたりする必要はありません。

関係を定義するには、ソーススキーマに専用のフィールド（この場合は購入スキーマの製品 ID フィールド）が必要です。このフィールドは、宛先スキーマの製品 ID フィールドを参照している必要があります。プロファイルのソーステーブルと宛先テーブルを有効にし、宛先スキーマには、プライマリ ID として定義されたその共通フィールドが必要です。

ここでは、製品 ID をプライマリ ID として定義したプロファイルに有効な製品カタログスキーマを示します。

![](../assets/schema9.png)

ここでは、製品 ID フィールドで定義された関係を持つ購入スキーマを示します。

![](../assets/schema10.png)

>[!NOTE]
>
>スキーマ間の関係について詳しくは、[Experience Platform ドキュメント](https://experienceleague.adobe.com/docs/platform-learn/tutorials/schemas/configure-relationships-between-schemas.html?lang=ja)を参照してください。

Journey Orchestrationでは、リンクされたテーブルのすべてのフィールドを次の場合に活用できます。

* 単一イベントを設定する場合：[詳細情報](../event/experience-event-schema.md#unitary_event_configuration)
* ジャーニーで条件を使用する場合：[詳細情報](../event/experience-event-schema.md#journey_conditions_using_event_context)
* カスタムアクションをパーソナライズする場合：[詳細情報](../event/experience-event-schema.md#custom_action_personalization_with_journey_event_context)

### 単一イベントの設定{#unitary_event_configuration}

リンクされたスキーマフィールドは、次の場合に単一イベントの設定で使用できます。

* イベント設定画面でイベントスキーマフィールドを参照する場合
* システム生成イベントの条件を定義する場合

![](../assets/schema11.png)

リンクされたフィールドは次の場所では使用できません。

* イベントキー式
* イベント ID 条件（ルールベースのイベント）

単一イベントの設定方法については、この[ページ](../event/about-creating.md)を参照してください。

### イベントコンテキストを使用したジャーニー条件{#journey_conditions_using_event_context}

条件作成のジャーニー（式エディター）で使用するイベントにリンクした参照テーブルのデータを使用できます。

式エディターでジャーニーに条件を追加し、式を編集し、イベントノードを展開します。

![](../assets/schema12.png)

ジャーニー条件の定義方法については、この[ページ](../building-journeys/condition-activity.md)を参照してください。

### ジャーニーイベントコンテキストを使用したアクションのパーソナライズ機能{#custom_action_personalization_with_journey_event_context}

リンクされたフィールドは、ジャーニーのアクションアクティビティのアクションパラメーターを設定する際に使用できます。

![](../assets/schema13.png)

カスタムアクションの使用方法については、この[ページ](../building-journeys/using-custom-actions.md)を参照してください。

