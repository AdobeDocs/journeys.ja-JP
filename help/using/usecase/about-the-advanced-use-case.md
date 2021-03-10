---
product: adobe campaign
solution: Journey Orchestration
title: 高度なユースケースについて
description: ジャーニーの高度なユースケースの詳細を説明します
feature: ジャーニー
role: 開業医
level: 中級
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '422'
ht-degree: 99%

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

この使用例では、2 つのイベントを作成する必要があります（ [このページ](../usecase/configuring-the-events.md)を参照）。

* 客がホテルに入るとシステムにプッシュされるロビービーコンイベント。
* 顧客がレストランに入るとプッシュされるレストランビーコンイベント。

2 つのデータソースへの接続を設定する必要があります（ [このページ](../usecase/configuring-the-data-sources.md)を参照）。

* 組み込みの Adobe Experience Platform データソース。2 つの条件（ロイヤリティメンバーシップと最終連絡の日付）の情報と、メッセージのパーソナライゼーション情報を取得します。
* ホテル予約システム。予約状況情報はここから取得されます。

## 前提条件 {#prerequisites}

このユースケースでは、Adobe Campaign Standard のトランザクションメッセージテンプレートを 3 つ設計しました。イベントのトランザクションメッセージテンプレートを使用しています。この[ページ](https://docs.adobe.com/content/help/ja-JP/campaign-standard/using/communication-channels/transactional-messaging/about-transactional-messaging.html)を参照してください。

Adobe Campaign Standard は、E メールおよびプッシュ通知を送信するように設定されています。

Experience Cloud ID は、ホテル予約システムで顧客を識別するためのキーとして使用されます。

ビーコンの近くで検出された顧客の携帯電話から、イベントが送信されます。顧客の携帯電話から Mobile SDK にイベントを送信するモバイルアプリをデザインする必要があります。

「ロイヤリティメンバー」フィールドは、カスタムフィールドで、特定の組織 ID に対して XDM に追加されました。
