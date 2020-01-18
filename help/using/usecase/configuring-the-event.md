---
title: イベントの設定
description: ジャーニーシンプルな使用事例のためのイベントの設定方法を説明します。
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


# イベントの設定{#concept_y44_hcy_w2b}

このシナリオでは、人がスパの隣にあるビーコンの近くを歩くたびに、イベントを受け取る必要があります。 技術ユ **ーザーは** 、システムがアドビの遍歴でリッスンするイベントを設定する必要があります。

イベントの設定の詳細については、を参照してくださ [](../event/about-events.md)い。

1. 上部のメニューで、タブをクリックし、 **[!UICONTROL Events]**をクリックして新し**[!UICONTROL Add]** いイベントを作成します。

   ![](../assets/journeyuc1_1.png)

1. スペースや特殊文字を含まない名前を入力します。「SpaBeacon」。

   ![](../assets/journeyuc1_2.png)

   <!--li>Select the **[!UICONTROL Mobile - Streaming Ingestion APIs]** event type. Events are sent from the customers' mobile phone through the Mobile SDK.![](../assets/journeyuc1_4.png" placement="break" width="800" id="image_qgr_2mn_z2b"/></li-->

1. 次に、スキーマを選択し、このイベントに必要なペイロードを定義します。 XDM正規化モデルから必要なフィールドを選択します。 リアルタイム顧客プロファイルデータベース内のユーザーを識別するには、Experience Cloud IDが必要です。 _endUserIDs > experience > mcid > id_。 このイベントに対してIDが自動的に生成されます。 このIDは、フィールドに保存さ **[!UICONTROL eventID]**れます(_エクスペリエンス/キャンペーン/オーケストレーション/eventID_)。 イベントをプッシュするシステムではIDを生成しないでください。ペイロードプレビューで使用できるIDを使用する必要があります。 使用事例では、このIDを使用してビーコンの場所を識別します。 訪問者がスパビーコンの近くを歩くたびに、この特定のイベントIDを含むイベントが送信されます。 これにより、イベント送信をトリガーしたビーコンをシステムが知ることができます。

   ![](../assets/journeyuc1_3.png)

   >[!NOTE]
   >
   >フィールドのリストはスキーマによって異なります。 スキーマ定義によっては、一部のフィールドが必須であり、事前に選択されている場合があります。

1. 名前空間を選択する必要があります。 名前空間は、スキーマのプロパティに基づいて事前に選択されています。 事前に選択した状態を維持できます。 名前空間の詳細については、を参照してくださ [](../event/selecting-the-namespace.md)い。

   ![](../assets/journeyuc1_6.png)

1. キーは、スキーマのプロパティと選択した名前空間に基づいて事前に選択されます。 それを持っていい。

   ![](../assets/journeyuc1_5.png)

1. クリック **[!UICONTROL Save]**.

1. アイコンをク **[!UICONTROL View Payload]**リックして、システムが予期するペイロードをプレビューし、イベント送信の責任者と共有します。 このペイロードは、Mobile Services管理コンソールのポストバックで設定する必要があります。

   ![](../assets/journeyuc1_7.png)

   このイベントを旅に出す準備が整いました。 これで、モバイルアプリケーションがStreaming Ingestion APIエンドポイントに必要なペイロードを送信できるように設定する必要があります。 [](../event/additional-steps-to-send-events-to-journey-orchestration.md)を参照してください。