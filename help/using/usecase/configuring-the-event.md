---
product: adobe campaign
title: イベントの設定
description: ジャーニーのシンプルなユースケースでイベントを設定する方法を説明します
feature: Journeys
role: User
level: Intermediate
exl-id: 7423f4eb-005d-43a5-a403-97bee1e8d480
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: ht
source-wordcount: '408'
ht-degree: 100%

---

# イベントの設定{#concept_y44_hcy_w2b}


>[!CAUTION]
>
>**Adobe Journey Optimizer をお探しですか**？Journey Optimizer のドキュメントについて詳しくは、[こちら](https://experienceleague.adobe.com/ja/docs/journey-optimizer/using/ajo-home){target="_blank"}をクリックしてください。
>
>
>_このドキュメントは、Journey Optimizer に置き換えられた従来の Journey Orchestration 資料を参照しています。Journey Orchestration または Journey Optimizer へのアクセスについてご質問がある場合は、アカウントチームにお問い合わせください。_


このシナリオでは、ユーザーがスパの隣にあるビーコンの近くを歩くたびに、イベントを受け取るようにします。**技術ユーザー**&#x200B;は、ジャーニーでシステムがリッスンするイベントを設定する必要があります。

イベントの設定について詳しくは、[このページ](../event/about-events.md)を参照してください。

1. トップメニューで、「**[!UICONTROL イベント]**」タブをクリックし、「**[!UICONTROL 追加]**」をクリックして新しいイベントを作成します。

   ![](../assets/journeyuc1_1.png)

1. スペースや特殊文字を使用しない名前を入力します（例：SpaBeacon）。

   ![](../assets/journeyuc1_2.png)

1. 次に、スキーマを選択し、このイベントに必要なペイロードを定義します。必要なフィールドは、XDM 正規化モデルから選択します。リアルタイム顧客プロファイルデータベース内の個人を識別するには、Experience Cloud ID が必要です（_endUserIDs／エクスペリエンス／mcid／id_）。このイベントに対して ID が自動的に生成されます。この ID は、「**[!UICONTROL eventID]**」フィールド（_エクスペリエンス／キャンペーン／オーケストレーション／eventID_）に格納されます。イベントをプッシュするシステムでは ID を生成しないため、ペイロードプレビューにある ID を使用する必要があります。このユースケースでは、この ID を使用してビーコンの場所を識別します。ユーザーがスパビーコンの近くを歩くたびに、この特定のイベント ID を含むイベントが送信されます。これによってシステムが、イベント送信をトリガーしたビーコンを特定できるようになります。

   ![](../assets/journeyuc1_3.png)

   >[!NOTE]
   >
   >フィールドのリストは、スキーマによって異なります。スキーマ定義によっては、一部のフィールドが必須となっており、事前に選択されている場合があります。

1. 名前空間を選択する必要があります。名前空間は、スキーマのプロパティに基づいて事前に選択されます。あらかじめ選択されているものを、選択したままにすることができます。名前空間の詳細については、[このページ](../event/selecting-the-namespace.md)を参照してください。

   ![](../assets/journeyuc1_6.png)

1. キーは、スキーマのプロパティと選択された名前空間に基づいて事前に選択されます。そのままにしても構いません。

   ![](../assets/journeyuc1_5.png)

1. 「**[!UICONTROL 保存]**」をクリックします。

1. **[!UICONTROL ペイロードを表示]**&#x200B;アイコンをクリックして、システムが想定するペイロードをプレビューし、イベント送信の担当者と共有します。このペイロードは、Mobile Services 管理コンソールのポストバックで設定する必要があります。

   ![](../assets/journeyuc1_7.png)

   イベントは、ジャーニーで使用できる状態になっています。次に、想定されたペイロードをストリーミング取り込み API エンドポイントに送信できるように、モバイルアプリケーションを設定する必要があります。[このページ](../event/additional-steps-to-send-events-to-journey-orchestration.md)を参照してください。
