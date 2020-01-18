---
title: イベントの設定
description: 高度な使用例の遍歴に関するイベントの設定方法を説明します。
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


# イベントの設定 {#concept_sbp_5cy_w2b}

私たちのシナリオでは、人がマールトンホテルとレストランに入るたびにイベントを受け取る必要があります。 技術 **ユーザーは** 、システムが遍歴でリッスンする2つのイベントを設定する必要があります。

イベントの設定の詳細については、を参照してくださ [](../event/about-events.md)い。

1. 上部のメニューで、タブをクリックし、 **[!UICONTROL Events]**をクリックして新し**[!UICONTROL Add]** いイベントを作成します。

   ![](../assets/journeyuc1_1.png)

1. スペースや特殊文字を使用せずに名前を入力します。&quot;LobbyBeacon&quot;。

   ![](../assets/journeyuc2_1.png)

<!--li>Select the **[!UICONTROL Mobile - Streaming Ingestion APIs]** event type. Events are sent from the customers' mobile phone through the Mobile SDK.![](../assets/journeyuc2_3.png" placement="break" width="800" id="image_is5_2sn_z2b"/></li-->

1. 次に、スキーマを選択し、このイベントに必要なペイロードを定義します。 XDM正規化モデルから必要なフィールドを選択します。 リアルタイム顧客プロファイルデータベース内のユーザーを識別するには、Experience Cloud IDが必要です。&quot;endUserIDs > _experience > mcid > id&quot;。

   プッシュメッセージを送信するには、登録トークンも必要です。&quot;_experience > campaign > message > profile > pushNotificationTokens > token&quot;

   このイベントに対してIDが自動的に生成されます。 このIDは、フィールド(「_experience > campaign > **[!UICONTROL eventID]**orchestration > eventID」)に保存されます。 イベントをプッシュするシステムではIDを生成しないでください。ペイロードプレビューで使用できるIDを使用する必要があります。 使用事例では、このIDを使用してビーコンの場所を識別します。 人がロビービーコンの近くを歩くたびに、この特定のイベントIDを含むイベントが送信されます。 同じ原則がレストランのビーコンイベントにも当てはまります。 これにより、イベント送信をトリガーしたビーコンをシステムが知ることができます。

   ![](../assets/journeyuc2_2.png)

   >[!NOTE]
   >
   >フィールドのリストはスキーマによって異なります。 スキーマ定義によっては、一部のフィールドが必須であり、事前に選択されている場合があります。

1. 名前空間を選択する必要があります。 名前空間は、スキーマのプロパティに基づいて事前に選択されています。 事前に選択した状態を維持できます。 名前空間の詳細については、を参照してくださ [](../event/selecting-the-namespace.md)い。

   ![](../assets/journeyuc2_4.png)

1. キーは、スキーマのプロパティと選択した名前空間に基づいて事前に選択されます。 それを持っていい。

   ![](../assets/journeyuc2_4bis.png)

1. クリック **[!UICONTROL Save]**.

1. アイコンをク **[!UICONTROL View Payload]**リックして、システムが予期するペイロードをプレビューし、イベント送信の責任者と共有します。  このペイロードは、Mobile Services管理コンソールのポストバックで設定する必要があります。

   ![](../assets/journeyuc2_5.png)

同様に、「RestarantBeacon」イベントを作成します。 2つのビーコンイベントが作成され、これでアドビの旅行に使用できます。 これで、モバイルアプリケーションがStreaming Ingestion APIエンドポイントに必要なペイロードを送信できるように設定する必要があります。 [](../event/additional-steps-to-send-events-to-journey-orchestration.md)を参照してください。
