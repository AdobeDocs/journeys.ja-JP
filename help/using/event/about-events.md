---
title: イベントについて
description: イベントの設定方法
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
source-git-commit: 017d502e21605b3e0b8c61e5fea0b4f6a65d4470

---


# イベントについて {#concept_gfj_fqt_52b}

イベントは人にリンクされます。 人の行動（例えば、人が製品を購入した、店に行った、Webサイトを退出したなど）に関連します。または、人に関連付けられた何か（例えば、人が10,000の忠誠度ポイントに達した）が発生した場合。 これは、次に最も良い行動を調整するために、旅行オーケストレーションがジャーニーでリッスンするものです。

この設定は必須で **す**。これは、Jargeny Orchestrationがイベントをリッスンするように設計されており、常に技術ユーザーが実行するように設 **計されています**。

イベント設定を使用すると、Jargeny Orchestrationがイベントとして受け取る情報を定義できます。 複数のイベントを（旅の異なるステップで）使用でき、同じイベントを使用できるジャーニーもいくつかあります。

ドラフトまたはライブジャーニーで使用されるイベントを編集する場合は、名前、説明、ペイロードフィールドの追加のみ可能です。 旅の途中での中断を避けるため、草案や旅のライブを厳しく制限します。

## 一般原則 {#section_r1f_xqt_pgb}

イベントはPOST API呼び出しです。 イベントは、Streaming Ingestion APIを使用してAdobe Experience Cloud Data Platformに送信されます。 トランザクションメッセージングAPIを介して送信されるイベントのURL宛先は「インレット」と呼ばれます。 イベントのペイロードはXDMの形式に従います。

ペイロードには、ストリーミングインジェストAPIが機能するために必要な情報（ヘッダー内）と、ジャーニーオーケストレーションが機能するために必要な情報（ペイロード本体の一部）と、ジャーニーで使用する情報（例えば、破棄された買い物かごの量）が含まれます。 ストリーミング取り込みには、認証済みと非認証の2つのモードがあります。 ストリーミングインジェストAPIの詳細については、このリンクを [参照してくださ](https://www.adobe.io/apis/experienceplatform/home/data-ingestion/data-ingestion-services.html#!api-specification/markdown/narrative/technical_overview/streaming_ingest/getting_started_with_platform_streaming_ingestion.md)い。

ストリーミングインジェストAPIを通じて到着したイベントは、パイプラインと呼ばれる内部サービスに送られ、次にデータプラットフォームに送られます。 イベントスキーマでReal-time Customer Profile Serviceフラグが有効になっており、Real-time Customer Profileフラグも持つデータセットIDがある場合、Real-time Customer Profile Serviceにフローします。

パイプラインは、Jargenry Orchestrationによって提供され、イベントペイロードに含まれる、Jargeny OrchestrationイベントIDを含むペイロード（以下のイベント作成プロセスを参照）を持つイベントをフィルタリングします。 これらのイベントは、Jareny Orchestrationによってリッスンされ、対応するジャーニーがトリガーされます。

## Creating a new event {#section_tbk_5qt_pgb}

新しいイベントを設定する主な手順は次のとおりです。

1. 上部のメニューで、タブをクリックし **[!UICONTROL Events]**ます。 イベントのリストが表示されます。 インターフ[](../about/user-interface.md)ェイスの詳細については、を参照してください。

   ![](../assets/journey5.png)

1. をクリック **[!UICONTROL Add]**して、新しいイベントを作成します。 イベント設定ペインが画面の右側に開きます。

   ![](../assets/journey6.png)

1. イベントの名前を入力します。

   >[!NOTE]
   >
   >スペースや特殊文字は使用しないでください。 30文字以内にする必要があります。

1. イベントに説明を追加します。 この手順はオプションです。
1. スキーマフィールドとペイロードフィールドの定義：ここでは、Jargeny Orchestrationが受信する必要のあるイベント情報（通常はペイロードと呼ばれます）を選択します。 その後、この情報を旅に使うことができます。 [](../event/defining-the-payload-fields.md)を参照してください。
1. このイベントを使用するジャーニーの数がフィールドに表示され **[!UICONTROL Used in]**ます。 このアイコンをクリックす**[!UICONTROL View journeys]** ると、このイベントを使用するジャーニーのリストを表示できます。
1. 名前空間を追加します。 この手順はオプションですが、名前空間を追加すると、Real-time Customer Profile Serviceに保存された情報を活用できるので、推奨されます。 イベントのキーのタイプを定義します。 [](../event/selecting-the-namespace.md)を参照してください。
1. キーの定義：ペイロードフィールドからフィールドを選択するか、イベントに関連付けられた個人を識別する式を定義します。 名前空間を選択した場合、このキーは自動的に設定されます（ただし、編集は可能です）。 実際、Jarney Orchestrationは、名前空間に対応する必要のあるキーを選択します（例えば、電子メール名前空間を選択した場合、電子メールキーが選択されます）。 [](../event/defining-the-event-key.md)を参照してください。
1. 条件を追加します。 この手順はオプションです。 これにより、条件を満たすイベントのみを処理できます。 条件は、イベントに含まれる情報に基づいてのみ指定できます。 [](../event/adding-a-condition.md)を参照してください。
1. クリック **[!UICONTROL Save]**.

   ![](../assets/journey7.png)

   これでイベントが設定され、旅に出る準備が整いました。 イベントを受け取るには、追加の設定手順が必要です。 [](../event/additional-steps-to-send-events-to-journey-orchestration.md)を参照してください。
