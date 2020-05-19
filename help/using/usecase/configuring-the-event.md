---
title: イベントの設定
description: ジャーニーシンプルな使用例のためのイベントの設定方法を学びます。
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
workflow-type: tm+mt
source-wordcount: '357'
ht-degree: 2%

---


# イベントの設定{#concept_y44_hcy_w2b}

このシナリオでは、人がスパの隣にあるビーコンの近くを歩くたびに、イベントを受け取る必要があります。 テク **ニカルユーザー** は、アドビの遍歴でシステムがリッスンするイベントを設定する必要があります。

イベント設定の詳細については、を参照してくだ [](../event/about-events.md)さい。

1. 上部のメニューで、「 **[!UICONTROL イベント]** 」タブをクリックし、をクリックして新しいイベントを作成し **** 追加ます。

   ![](../assets/journeyuc1_1.png)

1. 名前にスペースや特殊文字を使用しないで入力します。 &quot;SpaBeacon&quot;。

   ![](../assets/journeyuc1_2.png)

   <!--li>Select the **[!UICONTROL Mobile - Streaming Ingestion APIs]** event type. Events are sent from the customers' mobile phone through the Mobile SDK.![](../assets/journeyuc1_4.png" placement="break" width="800" id="image_qgr_2mn_z2b"/></li-->

1. 次に、スキーマを選択し、このイベントに必要なペイロードを定義します。 必要なフィールドは、XDM正規化モデルから選択します。 リアルタイム顧客プロファイルデータベース内のユーザーを識別するには、Experience Cloud IDが必要です。 _endUserIDs > experience > mcid > id_。 このイベントに対してIDが自動的に生成されます。 このIDは、 **[!UICONTROL eventID]** フィールド(_エクスペリエンス/キャンペーン/オーケストレーション/eventID_)に格納されます。 イベントをプッシュするシステムではIDを生成しない。ペイロードプレビューで使用できるIDを使用する必要がある。 使用事例では、このIDを使用してビーコンの場所を識別します。 訪問者がspaビーコンの近くを歩くたびに、この特定のイベントIDを含むイベントが送信されます。 これにより、イベント送信をトリガーしたビーコンを特定できます。

   ![](../assets/journeyuc1_3.png)

   >[!NOTE]
   >
   >フィールドのリストは、スキーマによって異なります。 スキーマ定義によると、一部のフィールドが必須で、事前に選択されている場合があります。

1. 名前空間を選択する必要があります。 名前空間は、スキーマのプロパティに基づいて事前に選択されます。 あらかじめ選択されているものを選択したままにすることができます。 名前空間の詳細については、を参照してください [](../event/selecting-the-namespace.md)。

   ![](../assets/journeyuc1_6.png)

1. キーは、スキーマのプロパティと選択した名前空間に基づいて事前に選択されます。 それは持って行けます。

   ![](../assets/journeyuc1_5.png)

1. 「**[!UICONTROL 保存]**」をクリックします。

1. 「 **[!UICONTROL 表示ペイロード]** 」アイコンをクリックして、イベントが予想するペイロードをプレビューし、ペイロード送信の担当者と共有します。 このペイロードは、Mobile Services管理コンソールのポストバックで設定する必要があります。

   ![](../assets/journeyuc1_7.png)

   イベントは、今すぐお使いいただけます。 次に、期待されたペイロードをストリーミング取り込みAPIエンドポイントに送信できるように、モバイルアプリケーションを設定する必要があります。 [](../event/additional-steps-to-send-events-to-journey-orchestration.md)を参照してください。