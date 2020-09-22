---
title: Journey Orchestration について
description: Journey Orchestration について詳しく知る
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: ht
source-git-commit: eb4474313d3c0470448f9959ed757902ef0ecd2a
workflow-type: ht
source-wordcount: '390'
ht-degree: 100%

---


# [!DNL Journey Orchestration について]{#concept_nd3_mqt_52b}

イベントやデータソースに保存されたコンテキストデータを活用して、リアルタイムオーケストレーションの使用例を構築します。

[!DNL Journey Orchestration] は、Adobe Experience Platform と統合されたアプリケーションサービスです。

![](../assets/journeydiagram.png)

[!DNL Journey Orchestration] を使用すると、イベントからのコンテキストデータ、Adobe Experience Platform からの情報、またはサードパーティの API サービスからのデータを利用したリアルタイムオーケストレーションを実現できます。サードパーティのシステムを使用してメッセージを送信する場合は、カスタムアクションを設定できます。Adobe Campaign Standard を利用している場合は、Adobe Campaign Standard の[トランザクションメッセージング機能](https://docs.adobe.com/content/help/ja-JP/campaign-standard/using/communication-channels/transactional-messaging/about-transactional-messaging.html)を使用して、E メール、プッシュ通知、SMS を送信できます。

「イベント設定」タブで、**技術ユーザー**&#x200B;がジャーニーで予想されるイベントを設定します。受信イベントのデータは、Adobe Experience Data Model（XDM）に従って正規化されます。イベントは、認証済みイベントと未認証イベント（Adobe Mobile SDK イベントなど）のストリーミング取得 API から提供されます。

「データソース設定」タブで、**技術ユーザー**&#x200B;は次の設定をおこないます。

* 条件の作成とパーソナライゼーションを目的として、ジャーニーデザイナーで Adobe Experience Platform から公開される様々なフィールド。
* ジャーニーデザイナーで使用する追加のカスタムデータソース。カスタムデータソースとは、[!DNL Journey Orchestration] と、サードパーティのシステムや API を介したサービスとの接続です。ロイヤルティシステムなどのサードパーティのシステムを接続できます。サードパーティのサービスには、天気予報 API などがあります。

ジャーニーデザイナーを使用すると、**ビジネスユーザー**&#x200B;は、エントリイベントのドラッグ＆ドロップ、条件の追加、実行するアクションの指定を容易におこなえます。

その後、次の条件に基づいて条件を作成します。

* 時間
* イベントペイロードからのデータ
* データソースからの情報：リアルタイム顧客プロファイルデータソースまたはカスタムデータソース

分割条件を使用すると、ジャーニーの訪問者を別の方向に送ることができます。

アクションアクティビティを使用すると、サードパーティのシステムを介してメッセージを送信できます。Adobe Campaign Standard を使用している場合は、パーソナライズされたリアルタイムの SMS、プッシュ通知または E メールを送信します。

[!DNL Journey Orchestration] は多段階式なので、高度なシナリオを作成できます。例えば、最初のイベントとアクションの後に、他のイベントをドラッグできます。次に、2 つ目のアクションを追加し、待機アクティビティを設定してしばらく待機して、2 つの異なるパスにユーザーをプッシュする分割条件を追加して、別々のメッセージを送信します。

>[!NOTE]
>
>このドキュメントは、製品に対する最近の変更を反映するために頻繁に更新されています。ただし、一部のスクリーンショットは、製品のインターフェイスと多少異なる場合があります。
