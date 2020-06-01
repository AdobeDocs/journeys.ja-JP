---
title: Journey Orchestration について
description: Journey Orchestrationの詳細情報
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: tm+mt
source-git-commit: 891216a489b79fe4b168ecdb6120f5d9f3e107d0
workflow-type: tm+mt
source-wordcount: '399'
ht-degree: 19%

---


# Journey Orchestration について{#concept_nd3_mqt_52b}

イベントやデータソースに保存されたコンテキストデータを活用して、リアルタイムオーケストレーションの使用例を構築します。

Journey Orchestrationは、Experience Platformと統合されたアプリケーションサービスです。

![](../assets/journeydiagram.png)

Journey Orchestration を使用すると、イベントからのコンテキストデータ、Adobe Experience Platform からの情報、またはサードパーティの API サービスからのデータを利用したリアルタイムオーケストレーションを実現できます。サードパーティ製システムを使用してメッセージを送信する場合は、カスタムアクションを設定できます。 Adobe Campaign標準をお持ちの場合は、Adobe Campaign標準の [トランザクションメッセージ機能を使用して、電子メール、プッシュ通知、およびSMSを送信できます](https://docs.adobe.com/content/help/ja-JP/campaign-standard/using/communication-channels/transactional-messaging/about-transactional-messaging.html)。

「イベントの設定」タブで、 **技術ユーザーがジャーニーで予想されるイベントを設定します** 。 受信イベントのデータは、Adobe Experience Data Model(XDM)に従って正規化されます。 イベントは、認証済みユーザーと未認証イベント(Adobe Mobile SDKイベントなど)のストリーミング取り込みAPIから提供されます。

「data source configuration」タブで、 **技術ユーザーが次の設定を行います** 。

* 条件の作成とパーソナライゼーションのために、遍歴デザイナーでAdobe Experience Platformから公開された様々なフィールド。
* 遍歴デザイナーで活用する追加のカスタムデータソース。 カスタムデータソースは、Journey Orchestrationとサードパーティ製システム、またはAPIを介したサービスとの間の接続です。 ロイヤルティシステムなどのサードパーティ製システムを接続できます。 サードパーティのサービスには、天気予報APIなどがあります。

このジャーニーデザイナーを使用すると、 **ビジネスユーザーは** 、入口イベントのドラッグ&amp;ドロップ、条件の追加、実行するアクションの指定を簡単に行うことができます。

その後、次の条件に基づいて条件を作成します。

* 時間
* イベントペイロードからのデータ
* データソースからの情報： リアルタイム顧客プロファイルデータソースまたはカスタムデータソース

分割条件を使用すると、遍歴の訪問者を別の方向に送信できます。

アクションアクティビティを使用すると、サードパーティのシステムを介してメッセージを送信できます。 Adobe Campaign標準をお持ちの場合は、パーソナライズされたリアルタイムのSMS、プッシュ通知、または電子メールを送信します。

Journey Orchestrationは複数の手順を行うので、高度なシナリオを作成できます。 例えば、最初のイベントと操作の後に、他のイベントをドラッグできます。 次に、2つ目のアクションを追加し、待機アクティビティを設定してしばらく待機し、2つの異なるパスにユーザーを移動させ、別のメッセージを送信するための分割条件を追加します。

>[!NOTE]
>
>このドキュメントは、製品に対する最近の変更を反映するために頻繁に更新されています。ただし、一部のスクリーンショットは、製品のインターフェイスと多少異なる場合があります。
