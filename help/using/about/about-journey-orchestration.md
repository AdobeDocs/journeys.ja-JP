---
title: Jargeny Orchestrationについて
description: Jargeny Orchestrationの詳細
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: tm+mt
source-git-commit: fed6fd8d8ee497ec47727f7297dc72f319fabe27

---


# Jargeny Orchestrationについて{#concept_nd3_mqt_52b}

イベントやデータソースに保存されたコンテキストデータを活用して、リアルタイムオーケストレーションの使用例を構築します。

Jargeny Orchestrationは、Experience Platformと統合されたアプリケーションサービスです。

![](../assets/journeydiagram.png)

Javerny Orchestrationを使用すると、イベントのコンテキストデータ、Adobe Experience Platformの情報、またはサードパーティのAPIサービスのデータを利用したリアルタイムオーケストレーションを実現できます。 サードパーティ製システムを使用してメッセージを送信する場合は、カスタムアクションを設定できます。 Adobe Campaign Standardをお持ちの場合は、Adobe Campaign Standardのトランザクションメッセージング機能を使用して、電子メール、プッシュ通知およびSMSを送信 [できます](https://docs.adobe.com/content/help/en/campaign-standard/using/communication-channels/transactional-messaging/about-transactional-messaging.html)。

「event configuration」タブで、技術ユーザーがジ **ャーニー** に必要なイベントを設定します。 受信イベントのデータは、Adobe Experience Data Model(XDM)に従って正規化されます。 イベントは、認証済みおよび未認証のイベント（Adobe Mobile SDKイベントなど）のストリーミングインジェストAPIから取得されます。

「Data source configuration」タブで、技術ユーザーは次の設定 **を行いま** す。

* 条件の作成とパーソナライゼーションのために、旅行デザイナーでAdobe Experience Platformから公開された様々なフィールドです。
* ジャーニーデザイナーで利用する追加のカスタムデータソース。 カスタムデータソースは、Jareny Orchestrationと、APIを介したサードパーティのシステムまたはサービスとの間の接続です。 忠誠度システムなどのサードパーティ製システムに接続できます。 サードパーティのサービスは、例えば天気予報APIのようになります。

このジャーニーデザイナーを使用す **ると** 、ビジネスユーザーはエントリイベントのドラッグ&amp;ドロップ、条件の追加、実行するアクションの指定を簡単に行うことができます。

その後、次の条件を基に条件を作成します。

* 時間
* イベントペイロードからのデータ
* データソースからの情報：リアルタイム顧客プロファイルデータソースまたはカスタムデータソース

分割条件を使用して、遍歴の中の人々を別の方向に送ることができます。

アクションアクティビティを使用して、サードパーティのシステムを介してメッセージを送信できます。 Adobe Campaign Standardをお持ちの場合は、パーソナライズされたSMS、プッシュ通知または電子メールをリアルタイムで送信します。

Jargeny Orchestrationは複数の手順で構成されるので、高度なシナリオを作成できます。 例えば、最初のイベントとアクションの後に、他のイベントをドラッグできます。 次に、2つ目のアクションを追加し、待機アクティビティを設定してしばらく待機し、分割条件を追加して2つの異なるパスにユーザーをプッシュし、異なるメッセージを送信します。

>[!NOTE]
>
>このドキュメントは、製品の最新の変更を反映して頻繁に更新されています。 ただし、一部のスクリーンショットは、製品のインターフェイスと少し異なる場合があります。

