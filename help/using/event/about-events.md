---
title: イベントについて
description: イベント
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
source-git-commit: e579936cfe5eb43caf72627004f98a5746c7abb1

---


# イベントについて {#concept_gfj_fqt_52b}

>[!CONTEXTUALHELP]
>id="jo_events"
>title="イベントについて"
>abstract="イベントは人にリンクされます。 人の行動（例えば、人が製品を購入した、店に行った、Webサイトを退出したなど）に関連します。または、人にリンクされた何か（例えば、人が10,000の忠誠度ポイントに到達した）が発生した場合。 これは、次に最良の行動を調整するために、Jurney Orchestrationが旅でリッスンするものです。"

イベントは人にリンクされます。 人の行動（例えば、人が製品を購入した、店に行った、Webサイトを退出したなど）に関連します。または、人にリンクされた何か（例えば、人が10,000の忠誠度ポイントに到達した）が発生した場合。 これは、次に最良の行動を調整するために、Jurney Orchestrationが旅でリッスンするものです。

この設定は必須で **す**。これは、Jargeny Orchestrationがイベントをリッスンし、常に技術ユーザーが実行するように設計されているた **めです**。

イベント構成を使用すると、Jurney Orchestrationが受け取る情報をイベントとして定義できます。 複数のイベント（旅の異なるステップ）を使用でき、複数のジャーニーで同じイベントを使用できます。

ドラフトまたはライブのイベントで使用されるペイロードを編集する場合は、名前、説明、またはペイロードフィールドの追加のみ可能です。 私たちは、旅を中断しないように、草案や旅行を生き延びることを厳しく制限する。

## 一般原則 {#section_r1f_xqt_pgb}

イベントはPOST API呼び出しです。 イベントは、Streaming Ingestion APIを通じてAdobe Experience Cloud Data Platformに送信されます。 トランザクションイベントAPIを通じて送信されるメッセージのURL宛先は、「インレット」と呼ばれます。 ペイロードのイベントはXDM形式に従います。

ペイロードには、Streaming Ingestion APIで機能するために（ヘッダー内で）必要な情報と、Jargeny Orchestrationで機能するために必要な情報（ペイロード本体の一部）と、ジャーニーで使用される情報（例えば、放棄された買い物かごの量）が含まれます。 ストリーミング取り込みには、認証済みと非認証の2つのモードがあります。 ストリーミングインジェストAPIの詳細については、このリンクを [参照してくださ](https://docs.adobe.com/content/help/en/experience-platform/xdm/api/getting-started.html)い。

Streaming Ingestion APIを通じて到達した後、イベントはパイプラインと呼ばれる内部サービスに流れ込み、次にデータプラットフォームに流れ込みます。 イベントスキーマでReal-time Customer Commenter Serviceフラグが有効になっており、Real-time Customer Commenterプロファイルフラグも持つデータセットIDを使用すると、Real-time Customerプロファイルサービスにフローします。

パイプラインフィルターイベントは、Jurenry Orchestrationによって提供されるJaverny OrchestrationイベントID(以下のイベント作成プロセスを参照)を含むペイロードを持ち、イベントペイロードに含まれています。 これらのイベントは、Jurney Orchestrationによってリッスンされ、対応するジャーニーがトリガーされます。

## Creating a new event {#section_tbk_5qt_pgb}

次に、新しい設定を行う主な手順を示します。イベント

1. 上部のメニューで、タブをクリック **[!UICONTROL Events]** します。 リストのイベントが表示されます。 インターフ [](../about/user-interface.md) ェイスの詳細については、を参照してください。

   ![](../assets/journey5.png)

1. をクリック **[!UICONTROL Add]** して、新しいイベントを作成します。 イベント設定ペインが画面の右側に開きます。

   ![](../assets/journey6.png)

1. イベント名

   >[!NOTE]
   >
   >スペースや特殊文字は使用しないでください。 30文字以内にする必要があります。

1. 追加イベントの説明。 この手順はオプションです。
1. ペイロードフィールドとスキーマフィールドの定義：ここでは、Jurney Orchestrationが受信するイベント情報（通常はペイロード）を選択します。 その後、この情報を旅に使うことができます。 [](../event/defining-the-payload-fields.md)を参照してください。
1. このイベントを使用するジャーニーの数がフィールドに表示さ **[!UICONTROL Used in]** れます。 このアイコンをクリックす **[!UICONTROL View journeys]** ると、このアイコンを使用してジャーニーのリストを表示できます。イベント
1. 追加名前空間 この手順はオプションですが、名前空間を追加することで、リアルタイム顧客プロファイルサービスに保存された情報を活用できるようにすることをお勧めします。 キーのタイプを定義します。イベントのキー [](../event/selecting-the-namespace.md)を参照してください。
1. キーの定義：ペイロードフィールドからフィールドを選択するか、式を定義して、ペイロードに関連付けられた個人を識別します。イベント。 このキーは、オプションを選択した場合に自動的に設定されます（ただし、編集は可能です）。名前空間 実際に、Jureny Orchestrationは、名前空間に対応する必要のあるキーを選択します(例えば、電子メール名前空間を選択した場合、電子メールキーが選択されます)。 [](../event/defining-the-event-key.md)を参照してください。
1. 条追加件。 この手順はオプションです。 これにより、条件を満たすイベントのみを処理できます。 条件は、その条件に含まれる情報に基づく場合にのみイベントします。 [](../event/adding-a-condition.md)を参照してください。
1. クリック **[!UICONTROL Save]** .

   ![](../assets/journey7.png)

   これでイベントが設定され、旅に出る準備が整いました。 追加の設定手順は、ユーザーを受け取るために必要なイベントです。 [](../event/additional-steps-to-send-events-to-journey-orchestration.md)を参照してください。
