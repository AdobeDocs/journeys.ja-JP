---
product: adobe campaign
title: 高度なユースケースについて
description: ジャーニーの高度なユースケースの詳細を説明します
feature: Journeys
role: User
level: Intermediate
exl-id: 43435aee-572d-4db2-88d5-6124ce074285
source-git-commit: 579e5a0dbdc11369248c2683c399b090130a7262
workflow-type: tm+mt
source-wordcount: '416'
ht-degree: 100%

---

# 高度なユースケースについて{#concept_vzy_ncy_w2b}

## 目的 {#purpose}

Marlton というホテルブランドの例を見てみましょう。彼らのホテルでは、ロビー、客室階、レストラン、ジム、プールなどの全戦略エリアの近くにビーコン装置を配置しています。

>[!NOTE]
>
>このユースケースでは、Adobe Campaign Standard を使用してメッセージを送信します。

このユースケースでは、ユーザーが特定のビーコンの近くを歩いたときに、リアルタイムでパーソナライズされたメッセージを送信する方法を見ていきます。

まず、ユーザーが Marlton ホテルに入ったらすぐにメッセージを送信します。メッセージは、この 24 時間以内にメッセージが送信されていない場合に限って送信します。

次に、2 つの条件を確認します。

* このユーザーがロイヤルティメンバーでない場合は、ロイヤルティメンバーシップに参加するためのオファーメールを送信します。
* このユーザーが既にロイヤルティメンバーである場合は、部屋の予約があるかどうかを確認します。
   * そうでない場合は、宿泊料金を記載したプッシュ通知を送信します。
   * その場合は、歓迎のプッシュ通知を送信します。そして、このユーザーが 6 時間以内にレストランに入った場合、食事が割引になるプッシュ通知を送信します。

![](../assets/journeyuc2_29.png)

この使用例では、2 つのイベントを作成する必要があります（ [このページ](../usecase/configuring-the-events.md)を参照）。

* 客がホテルに入るとシステムにプッシュされるロビービーコンイベント。
* 顧客がレストランに入るとプッシュされるレストランビーコンイベント。

2 つのデータソースへの接続を設定する必要があります（ [このページ](../usecase/configuring-the-data-sources.md)を参照）。

* ビルトインの Adobe Experience Platform データソース。2 つの条件（ロイヤルティメンバーシップと最終連絡の日付）の情報と、メッセージのパーソナライゼーション情報を取得します。
* ホテル予約システム。予約状況情報はここから取得されます。

## 前提条件 {#prerequisites}

このユースケースでは、Adobe Campaign Standard のトランザクションメッセージテンプレートを 3 つ設計しました。イベントのトランザクションメッセージテンプレートを使用しています。この[ページ](https://experienceleague.adobe.com/docs/campaign-standard/using/communication-channels/transactional-messaging/getting-started-with-transactional-msg.html?lang=ja)を参照してください。

Adobe Campaign Standard は、E メールおよびプッシュ通知を送信するように設定されています。

Experience Cloud ID は、ホテル予約システムで顧客を識別するためのキーとして使用されます。

ビーコンの近くで検出された顧客の携帯電話から、イベントが送信されます。このため、顧客の携帯電話から Mobile SDK にイベントを送信するモバイルアプリをデザインする必要があります。

この組織 ID に対して、カスタムの「ロイヤルティメンバー」フィールドが XDM に追加されています。
