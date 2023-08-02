---
product: adobe campaign
title: Journey Orchestrationの制限
description: Journey Orchestration制限の詳細
feature: Journeys
role: User
level: Beginner
exl-id: fef039ae-c04d-4198-a082-4be27710255f
source-git-commit: 861c6bd8ce65793b6009e220d88f105c75ea3008
workflow-type: tm+mt
source-wordcount: '567'
ht-degree: 82%

---

# 制限事項 {#limitations}

Journey Orchestrationの使用に関する制限を次に示します。

## 一般的なジャーニーのガードレール {#journeys-guardrails-journeys}

* ジャーニー 1 つあたりのアクティビティ数は 50 に制限されます。アクティビティの数は、ジャーニーキャンバスの左上に表示されます。
* 1 つの組織における&#x200B;**ライブジャーニー**&#x200B;の数は、サンドボックスあたり 100 に制限されます。この制限に達すると、新しいジャーニーを公開できなくなります。

## 一般的なアクションの制限

* エラーが発生した場合は、手順に従い再試行を 2 回実行します。受け取ったエラーメッセージに応じて、リトライ回数を調整することはできません。 
* ビルトインの&#x200B;**反応**&#x200B;イベントを使用すると、すぐに使えるアクションに反応できます（[このページ](../building-journeys/reaction-events.md)を参照してください）。
カスタムアクションを介して送信されたメッセージに反応する場合は、専用のイベントを設定する必要があります。 

## ジャーニーバージョンの制限 {#journey-versions-limitations}

* v1 でジャーニーをイベントアクティビティで開始した場合、それ以降のバージョンをイベント以外で開始することはできません。**セグメントの選定**&#x200B;イベントでジャーニーを開始することはできません。
* ジャーニーが v1 の&#x200B;**セグメントの選定**&#x200B;アクティビティで開始した場合、それ以降のバージョンも必ず&#x200B;**セグメントの選定**&#x200B;で開始する必要があります。
* **セグメントの選定**（最初のノード）で選択されたセグメントと名前空間を、新しいバージョンで変更することはできません。
* 再エントリのルールは、すべてのバージョンのジャーニーで同じである必要があります。

## セグメントの選定 {#segment-qualification}

* The **セグメントの選定** スループットの制約により、アクティビティは、Adobe Campaign Standardトランザクションメッセージと組み合わせて使用することはできません。 詳しくは、 [Adobe Campaign Standard Product Description](https://helpx.adobe.com/jp/legal/product-descriptions/campaign-standard.html). 
 
## カスタムアクションの制限

* カスタムアクションの URL は動的パラメーターをサポートしていません。 
* POST と PUT の呼び出しメソッドのみをサポートしています。 
* クエリパラメーターまたはヘッダーの名前を、「.」または「$」で開始することはできません。 
* IP アドレスは使用できません。 
* 内部 Adobe アドレス（.adobe.）は使用できません。
 
## Adobe Campaignアクションの制限

* Adobe Campaign Standard Transactional Messaging の規模は、特定のインスタンスのチャネル全体で 1 時間あたり最大 50,000 メッセージです。 詳しくは、 [Adobe Campaign Standard Product Description](https://helpx.adobe.com/jp/legal/product-descriptions/campaign-standard.html). 
 
## イベントの制限

* システム生成イベントの場合、カスタマージャーニーの開始に使用するストリーミングデータは、一意のオーケストレーション ID を取得するために、最初にJourney Orchestration内で設定する必要があります。このオーケストレーション ID は、Adobe Experience Platform に到達するストリーミングペイロードに追加する必要があります。この制限は、ルールベースのイベントには適用されません。
 
## データソースの制限

* 外部データソースは、カスタマージャーニー内でリアルタイムに外部データを参照するために利用できます。これらのソースは、REST API 経由で使用でき JSON をサポートし、リクエストのボリューム量を処理できる必要があります。

## プロファイルの作成と同時に開始するジャーニー {#journeys-limitation-profile-creation}

Adobe Experience Platform では、API ベースのプロファイルの作成や更新に関連して遅延が発生します。遅延に関するサービスレベルターゲット（SLT）は、毎秒 2 万件のリクエスト（RPS）のボリュームで、95 パーセンタイルのリクエストに対し、統合プロファイルへの取得から 1 分未満です。

ジャーニーがプロファイルの作成と同時にトリガーされ、プロファイルサービスからただちに情報を確認または取得すると、うまく機能しない可能性があります。

次の 2 つの解決策を選択できます。

* 最初のイベントの後に待機アクティビティを追加して、プロファイルサービスへの取得に必要な時間を Adobe Experience Platform に与えます。

* このプロファイルをすぐには活用しないジャーニーを設定します。例えば、アカウントの作成を確認するようにジャーニーをデザインしている場合、エクスペリエンスイベントには、最初の確認メッセージを送信するのに必要な情報（姓、名、メールアドレスなど）を含めることができます。
