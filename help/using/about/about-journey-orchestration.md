---
product: adobe campaign
title: Journey Orchestration について
description: Journey Orchestration について詳しく知る
feature: Journeys
role: User
level: Beginner
exl-id: 430bac3a-06da-45a8-af90-1dcd1504d532
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '388'
ht-degree: 100%

---

# [!DNL Journey Orchestration] について{#concept_nd3_mqt_52b}

イベントやデータソースに保存されたコンテキストデータを活用して、リアルタイムオーケストレーションのユースケースを構築できます。

[!DNL Journey Orchestration] は、Adobe Experience Platform と統合されたアプリケーションサービスです。

![](../assets/journeydiagram.png)

[!DNL Journey Orchestration] を使用すると、イベントからのコンテキストデータ、Adobe Experience Platform からの情報、またはサードパーティの API サービスからのデータを利用したリアルタイムオーケストレーションが可能になります。サードパーティのシステムを使用してメッセージを送信する場合は、カスタムアクションを設定できます。Adobe Campaign Standard を利用している場合は、Adobe Campaign Standard の[トランザクションメッセージング機能](https://experienceleague.adobe.com/docs/campaign-standard/using/communication-channels/transactional-messaging/getting-started-with-transactional-msg.html?lang=ja)を使用して、E メール、プッシュ通知、SMS を送信できます。

「イベント設定」タブで、**技術ユーザー**&#x200B;がジャーニーで予想されるイベントを設定します。受信イベントのデータは、Adobe Experience Data Model（XDM）に従って正規化されます。イベントは、認証済みイベントと未認証イベント（Adobe Mobile SDK イベントなど）のストリーミング取り込み API から取り込みます。

「データソース設定」タブで、**技術ユーザー**&#x200B;は次の設定をおこないます。

* 条件の作成とパーソナライゼーションを目的として、ジャーニーデザイナーで Adobe Experience Platform から公開される様々なフィールド。
* ジャーニーデザイナーで使用する追加のカスタムデータソース。カスタムデータソースとは、[!DNL Journey Orchestration] と、サードパーティのシステムや API を介したサービスとの接続です。ロイヤルティシステムなどのサードパーティのシステムを接続できます。サードパーティのサービスには、天気予報 API などがあります。

ジャーニーデザイナーを使用すると、**ビジネスユーザー**&#x200B;は、エントリイベントのドラッグ＆ドロップ、条件の追加、実行するアクションの指定を容易におこなえます。

その後、次の条件に基づいて条件を作成します。

* 時間
* イベントペイロードからのデータ
* データソースからの情報：リアルタイム顧客プロファイルデータソースまたはカスタムデータソース

条件分岐を使用すると、ジャーニーの訪問者を別の方向に送ることができます。

アクションアクティビティを使用すると、サードパーティのシステムを介してメッセージを送信できます。Adobe Campaign Standard を使用している場合は、パーソナライズされたリアルタイムの SMS、プッシュ通知または E メールを送信します。

[!DNL Journey Orchestration] は多段階式なので、高度なシナリオを作成できます。例えば、最初のイベントとアクションの後に、他のイベントをドラッグできます。次に、2 つ目のアクションを追加し、待機アクティビティを設定してしばらく待機して、2 つの異なるパスにユーザーをプッシュする条件分岐を追加して、別々のメッセージを送信します。

>[!NOTE]
>
>このドキュメントは、製品の最近の変更を反映するために頻繁に更新されています。ただし、一部のスクリーンショットは、製品のインターフェイスと多少異なる場合があります。
