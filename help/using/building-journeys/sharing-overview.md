---
product: adobe campaign
title: ジャーニーステップ共有の概要
description: ジャーニーステップ共有の概要
feature: Journeys
role: User
level: Intermediate
exl-id: 95ca5fdb-38b7-47a0-b1a9-b1b26bf8e5f5
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '519'
ht-degree: 67%

---

# ジャーニーステップ共有の概要{#sharing-overview}


>[!CAUTION]
>
>**Adobe Journey Optimizerをお探しですか** Journey Optimizerのドキュメントについては、[&#x200B; こちら &#x200B;](https://experienceleague.adobe.com/ja/docs/journey-optimizer/using/ajo-home){target="_blank"} をクリックしてください。
>
>
>_このドキュメントでは、Journey Optimizerに置き換えられた従来のJourney Orchestration マテリアルについて説明します。 Journey OrchestrationやJourney Optimizerへのアクセスに関するご質問は、アカウントチームにお問い合わせください。_


[!DNL Journey Orchestration] は、ジャーニーのパフォーマンスデータをAdobe Experience Platformに自動的に送信し、他のデータと組み合わせて分析できるようにします。

>[!NOTE]
>
>この機能は、ジャーニーステップのイベントの場合、すべてのインスタンスにおいてデフォルトで有効になっています。ステップイベントのプロビジョニング時に作成されたスキーマやデータセットは、変更も更新もできません。デフォルトでは、これらのスキーマとデータセットは読み取り専用モードです。

例えば、複数のメールを送信するジャーニーを設定したとします。この機能を使用すると、[!DNL Journey Orchestration] のデータをダウンストリームのイベントデータと組み合わせることができます。このようなイベントデータには、発生したコンバージョン数、Web サイトで発生したエンゲージメント、ストアで発生したトランザクション数などがあります。ジャーニー情報をAdobe Experience Platformのデータ（他のデジタルプロパティのデータまたはオフラインプロパティのデータ）と組み合わせて、パフォーマンスをより包括的に把握することができます。

[!DNL Journey Orchestration] は、個人がジャーニーで実行するステップごとに、必要なスキーマとデータセットへのストリームをAdobe Experience Platformに対して自動的に作成します。 ステップイベントは、ジャーニーのあるノードから別のノードに移動する個人に対応します。例えば、イベント、条件およびアクションを備えたジャーニーでは、3 つのステップイベントがAdobe Experience Platformに送信されます。

渡される XDM フィールドのリストは多岐にわたります。システムで生成されたコードを含むものもあれば、人間が理解できるわかりやすい名前を持つものもあります。例えば、ジャーニーアクティビティやステップステータスのラベルがあります。アクションがタイムアウトした回数や、エラーで終了した回数などです。

>[!CAUTION]
>
>リアルタイムプロファイルサービスの場合は、データセットを有効にできません。**[!UICONTROL プロファイル]**&#x200B;の切り替えがオフになっていることを確認してください。

ジャーニーは、発生時にストリーミング方式でデータを送信します。このデータは、クエリサービスを使用してクエリできます。Customer Journey Analytics またはその他の BI ツールに接続して、これらのステップに関連するデータを表示できます。

次のスキーマが作成されます。

* [!DNL Journey Orchestration] のジャーニーステップイベントスキーマ：ジャーニーメタデータに関連付けられているジャーニーステップイベント。
* [!DNL Journey Orchestration] のジャーニーフィールドを含むジャーニースキーマ：ジャーニーを記述するジャーニーメタデータ。

![](../assets/sharing1.png)

![](../assets/sharing2.png)

次のデータセットが渡されます。

* ジャーニーステップイベント
* ジャーニー

![](../assets/sharing3.png)

Adobe Experience Platformに渡される XDM フィールドのリストについて詳しくは、以下を参照してください。

* [ステップイベントフィールドの一覧](../building-journeys/sharing-field-list.md)
* [従来のステップイベントフィールド](../building-journeys/sharing-legacy-fields.md)


## Customer Journey Analytics との統合{#integration-cja}

Journey Orchestrationのステップイベントは、[Adobe Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-overview.html?lang=ja) の他のデータセットにリンクできます。 次に一般的なワークフローを示します。

* Customer Journey Analytics は、「ジャーニーステップイベント」データセットを取り込みます。
* 関連する「Journey Orchestration のジャーニーステップイベントスキーマ」の **profileID** フィールドは、ID フィールドとして定義されています。 Customer Journey Analytics では、このデータセットを、ユーザーベースの識別子と同じ値を持つ他のデータセットにリンクできます。
* Customer Journey Analytics でこのデータセットを使用する場合、クロスチャネルジャーニー分析については、この[ドキュメント](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/cross-channel.html?lang=ja)を参照してください。
