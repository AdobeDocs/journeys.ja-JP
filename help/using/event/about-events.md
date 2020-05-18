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
source-git-commit: e579936cfe5eb43caf72627004f98a5746c7abb1
workflow-type: tm+mt
source-wordcount: '742'
ht-degree: 2%

---


# イベントについて {#concept_gfj_fqt_52b}

>[!CONTEXTUALHELP]
>id="jo_events"
>title="イベントについて"
>abstract="イベントは人と結び付いている。 訪問者の行動（例えば、製品の購入、訪問、Webサイトの退出など）に関連します。 または、人にリンクされた何か（例えば、1人が10,000個の忠誠度に到達した）が発生した場合にも発生します。 これが、Javerny Orchestrationが次の最良の行動を調整するための遍歴でリッスンするものです。"

イベントは人と結び付いている。 訪問者の行動（例えば、製品の購入、訪問、Webサイトの退出など）に関連します。 または、人にリンクされた何か（例えば、1人が10,000個の忠誠度に到達した）が発生した場合にも発生します。 これが、Javerny Orchestrationが次の最良の行動を調整するための遍歴でリッスンするものです。

この設定は **必須です**。Jureny Orchestrationはイベントをリッスンするように設計されており、常に **技術ユーザーが実行します**。

イベントの構成を使用すると、Jurnery Orchestrationが受け取るイベントを定義できます。 複数のイベント（旅の異なるステップ）を使用でき、複数のジャーニーで同じイベントを使用できます。

ドラフトまたはライブ遍歴で使用されるイベントを編集する場合、名前、説明、またはペイロードフィールドの追加のみ可能です。 旅の途中を切り裂くのを避けるために、草案の編集もしくは生の旅行も厳しく制限する。

## 一般原則 {#section_r1f_xqt_pgb}

イベントはPOST API呼び出しです。 イベントは、Streaming Ingest APIを使用してAdobe Experience Cloud Data Platformに送信されます。 トランザクションメッセージングAPIを通じて送信されるイベントのURL宛先は「入口」と呼ばれます。 イベントのペイロードは、XDMフォーマットに従います。

ペイロードには、Streaming Ingestion APIが（ヘッダー内で）機能するために必要とする情報と、Jarney Orchestrationが(イベントID、ペイロード本体の一部)機能させるために必要とする情報と、ジャーニー内で使用する情報（例えば、本体内、放棄された買い物かごの量）が含まれます。 ストリーミング取り込みには、認証済みと非認証の2つのモードがあります。 Streaming Ingest APIの詳細については、 [このリンクを参照してください](https://docs.adobe.com/content/help/en/experience-platform/xdm/api/getting-started.html)。

ストリーミング取り込みAPIを通じて到着したイベントは、パイプラインと呼ばれる内部サービスに送られ、その後データプラットフォームに送られます。 イベントスキーマでReal-time Customer Customer Serviceフラグが有効になっていて、Real-time Customer Customer Serviceフラグも持つデータセットIDが設定されている場合は、Real-time Customer Customer Serviceにプロファイルされます。

パイプラインフィルターイベントは、Jurenry Orchestrationによって提供されるJorgeny OrchestrationイベントIDを含むペイロード(以下のイベント作成プロセスを参照)を持ち、イベントペイロードに含まれます。 これらのイベントは、Jureny Orchestrationによってリッスンされ、対応する遍歴がトリガーされます。

## Creating a new event {#section_tbk_5qt_pgb}

新しいイベントを設定する主な手順は次のとおりです。

1. 上部のメニューで、「 **[!UICONTROL イベント]** 」タブをクリックします。 イベントのリストが表示されます。 インターフェイス [](../about/user-interface.md) の詳細については、を参照してください。

   ![](../assets/journey5.png)

1. Click **[!UICONTROL Add]** to create a new event. 画面の右側にイベント設定ペインが開きます。

   ![](../assets/journey6.png)

1. イベントの名前を入力します。

   >[!NOTE]
   >
   >スペースや特殊文字は使用しないでください。 30文字以内にしてください。

1. イベント追加の説明。 この手順はオプションです。
1. スキーマフィールドとペイロードフィールドの定義： ここで、Jurnery Orchestrationが受信するイベント情報（通常はペイロード）を選択します。 その後、この情報を旅に使うことができます。 [](../event/defining-the-payload-fields.md)を参照してください。
1. このイベントを使用するジャーニーの数は、「 **[!UICONTROL 使用対象]** 」フィールドに表示されます。 表示ジャーニー **** アイコンをクリックすると、このイベントを使用してジャーニーのリストを表示できます。
1. 名前空間追加。 この手順はオプションですが、名前空間を追加すると、リアルタイムプロファイルサービスに保存された情報を活用できるので、お勧めします。 イベントのキーのタイプを定義します。 [](../event/selecting-the-namespace.md)を参照してください。
1. キーの定義： ペイロードフィールドからフィールドを選択するか、イベントに関連付けられた個人を識別する数式を定義します。 このキーは、名前空間を選択した場合に自動的に設定されます（ただし、編集は可能です）。 実際に、Jureny Orchestrationは、名前空間に対応する必要のあるキーを選択します(例えば、電子メール名前空間を選択した場合、電子メールキーが選択されます)。 [](../event/defining-the-event-key.md)を参照してください。
1. 条件を追加. この手順はオプションです。 これにより、条件を満たすイベントのみを処理できます。 条件は、イベントに含まれる情報に基づく場合にのみ指定できます。 [](../event/adding-a-condition.md)を参照してください。
1. 「**[!UICONTROL 保存]**」をクリックします。

   ![](../assets/journey7.png)

   これでイベントが設定され、遍歴に含まれる準備が整いました。 イベントを受け取るには、追加の設定手順が必要です。 [](../event/additional-steps-to-send-events-to-journey-orchestration.md)を参照してください。
