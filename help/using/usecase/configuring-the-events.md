---
product: adobe campaign
solution: Journey Orchestration
title: イベントの設定
description: ジャーニーの高度なユースケースでイベントを設定する方法を説明します
feature: ジャーニー
role: 開業医
level: 中級
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '406'
ht-degree: 99%

---


# イベントの設定 {#concept_sbp_5cy_w2b}

このシナリオでは、ユーザーが Marlton のホテルやレストランに入るたびにイベントを受け取る必要があります。**技術ユーザー**&#x200B;は、ジャーニーでシステムがリッスンする 2 つのイベントを設定する必要があります。

イベントの設定について詳しくは、[このページ](../event/about-events.md)を参照してください。

1. 上部のメニューで、「**[!UICONTROL イベント]**」タブをクリックし、「**[!UICONTROL 追加]**」をクリックして新しいイベントを作成します。

   ![](../assets/journeyuc1_1.png)

1. スペースや特殊文字を使用しない名前を入力します（例：LobbyBeacon）。

   ![](../assets/journeyuc2_1.png)

1. 次に、スキーマを選択し、このイベントに必要なペイロードを定義します。必要なフィールドは、XDM 正規化モデルから選択します。リアルタイム顧客プロファイルデータベース内の個人を識別するには、Experience Cloud ID が必要です（endUserIDs／_experience／mcid／id）。

   プッシュメッセージを送信するには、登録トークンも必要です（_experience／キャンペーン／メッセージ／プロファイル／pushNotificationTokens／トークン）。

   このイベントに対して ID が自動的に生成されます。この ID は、「**[!UICONTROL eventID]**」フィールド（_experience／キャンペーン／オーケストレーション／eventID）に格納されています。イベントをプッシュするシステムでは ID を生成せずに、ペイロードプレビューにある ID を使用する必要があります。このユースケースでは、この ID を使用してビーコンの場所を識別します。ユーザーがロビービーコンの近くを歩くたびに、この特定のイベント ID を含むイベントが送信されます。同じ原則がレストランビーコンのイベントにも当てはまります。これにより、イベント送信をトリガーしたビーコンを特定できます。

   ![](../assets/journeyuc2_2.png)

   >[!NOTE]
   >
   >フィールドのリストは、スキーマによって異なります。スキーマ定義によって、一部のフィールドが必須で、事前に選択されている場合があります。

1. 名前空間を選択する必要があります。名前空間は、スキーマのプロパティに基づいて事前に選択されます。あらかじめ選択されているものを、選択したままにすることができます。名前空間の詳細については、[このページ](../event/selecting-the-namespace.md)を参照してください。

   ![](../assets/journeyuc2_4.png)

1. キーは、スキーマのプロパティと選択された名前空間に基づいて事前に選択されます。そのままでよいです。

   ![](../assets/journeyuc2_4bis.png)

1. 「**[!UICONTROL 保存]**」をクリックします。

1. **[!UICONTROL ペイロードを表示]**&#x200B;アイコンをクリックして、イベントが予想するペイロードをプレビューし、ペイロード送信の担当者と共有します。このペイロードは、Mobile Services 管理コンソールのポストバックで設定する必要があります。

   ![](../assets/journeyuc2_5.png)

同様に、「RestaurantBeacon」イベントを作成します。2 つのビーコンイベントが作成され、ジャーニーで使用できるようになりました。次に、期待されたペイロードをストリーミング取得 API エンドポイントに送信できるように、モバイルアプリケーションを設定する必要があります。[このページ](../event/additional-steps-to-send-events-to-journey-orchestration.md)を参照してください。
