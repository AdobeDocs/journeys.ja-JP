---
title: 高度なユースケースについて
description: ジャーニーの高度なユースケースの詳細を説明します
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: tm+mt
source-git-commit: bcb8a71a27e2b9e37af7d0260cec04ed0fda24ee
workflow-type: tm+mt
source-wordcount: '418'
ht-degree: 93%

---


# 高度なユースケースについて{#concept_vzy_ncy_w2b}

## 目的 {#purpose}

Marlton というホテルブランドの例を見てみましょう。彼らのホテルでは、ロビー、客室階、レストラン、ジム、プールなどの全戦略エリアの近くにビーコン装置を配置しています。

>[!NOTE]
>
>このユースケースでは、Adobe Campaign Standard を使用してメッセージを送信します。

このユースケースでは、ユーザーが特定のビーコンの近くを歩いたときに、リアルタイムでパーソナライズされたメッセージを送信する方法を見ていきます。

まず、ユーザーが Marlton ホテルに入ったらすぐにメッセージを送信します。メッセージは、この 24 時間以内にメッセージを送信しなかった場合に限って送信します。

次に、2 つの条件を確認します。

* このユーザーがロイヤリティメンバーでない場合は、ロイヤリティメンバーシップオファーに参加するための E メールを送信します。
* このユーザーが既にロイヤリティメンバーである場合は、部屋の予約があるかどうかを確認します。
   * ない場合、部屋料金のプッシュ通知を送信します。
   * ある場合、歓迎のプッシュ通知を送信します。そして、このユーザーが 6 時間以内にレストランに入った場合、食事の割引をプッシュ通知で送信します。

![](../assets/journeyuc2_29.png)

For this use case, we will need to create two events (see [this page](../usecase/configuring-the-events.md)):

* 客がホテルに入るとシステムにプッシュされるロビービーコンイベント。
* 顧客がレストランに入るとプッシュされるレストランビーコンイベント。

We will need to configure a connection to two data sources (see [this page](../usecase/configuring-the-data-sources.md)):

* 組み込みの Adobe Experience Platform データソース。2 つの条件（ロイヤリティメンバーシップと最終連絡の日付）の情報と、メッセージのパーソナライゼーション情報を取得します。
* ホテル予約システム。予約状況情報はここから取得されます。

## 前提条件 {#prerequisites}

このユースケースでは、Adobe Campaign Standard のトランザクションメッセージテンプレートを 3 つ設計しました。イベントのトランザクションメッセージテンプレートを使用しています。この[ページ](https://docs.adobe.com/content/help/ja-JP/campaign-standard/using/communication-channels/transactional-messaging/about-transactional-messaging.html)を参照してください。

Adobe Campaign Standard は、E メールおよびプッシュ通知を送信するように設定されています。

Experience Cloud ID は、ホテル予約システムで顧客を識別するためのキーとして使用されます。

ビーコンの近くで検出された顧客の携帯電話から、イベントが送信されます。顧客の携帯電話から Mobile SDK にイベントを送信するモバイルアプリをデザインする必要があります。

「ロイヤリティメンバー」フィールドは、カスタムフィールドで、特定の組織 ID に対して XDM に追加されました。
