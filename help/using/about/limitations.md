---
product: adobe campaign
solution: Journey Orchestration
title: Journey Orchestration制限
description: Journey Orchestration制限の詳細
feature: ジャーニー
role: Business Practitioner
level: Beginner
exl-id: 27859689-dc61-4f7a-b942-431cdf244455
translation-type: tm+mt
source-git-commit: 8ab3951f9c97a0a964f5c123978ed256d3aedc45
workflow-type: tm+mt
source-wordcount: '527'
ht-degree: 2%

---

# 制限事項{#limitations}

Journey Orchestrationの使用に関する制限を以下に示します。

## 一般的なアクションの制限

* 送信ジョブ数の制限はありません。 
* 誤りの場合には、2つの再試行を系統的に行う。 受け取ったエラーメッセージに従って再試行数を調整することはできません。 
* 組み込みの&#x200B;**Reaction**&#x200B;イベントを使用すると、すぐに使えるアクションに対応できます（この[ページ](../building-journeys/reaction-events.md)を参照）。 カスタムアクションを介して送信されたメッセージに反応する場合は、専用のイベントを設定する必要があります。 
* Adobe Campaign Classic製品の統合はありません。

## ジャーニーバージョンの制限{#journey-versions-limitations}

* v1のイベントアクティビティで始まるジャーニーは、それ以降のバージョンではイベント以外のものと開始できません。 **セグメントクオリフィケーション**&#x200B;イベントとのジャーニーの開始はできません。
* v1の&#x200B;**セグメント資格**&#x200B;アクティビティで始まるジャーニーは、必ず、それ以降のバージョンの&#x200B;**セグメント資格**&#x200B;と開始する必要があります。
* **セグメントクオリフィケーション**（最初のノード）で選択されたセグメントと名前空間は、新しいバージョンでは変更できません。
* 再入口ルールは、すべてのジャーニーバージョンで同じである必要があります。

## セグメントの適性 {#segment-qualification}

* **セグメント条件**&#x200B;アクティビティは、スループットの制約により、Adobe Campaign Standardトランザクションメッセージと組み合わせて使用できません。 「[Adobe Campaign Standard製品の説明](https://helpx.adobe.com/jp/legal/product-descriptions/campaign-standard.html)」を参照してください。 
 

## カスタムアクションの制限

* カスタムアクションURLは動的パラメーターをサポートしていません。 
* POSTとPUT呼び出しのメソッドのみがサポートされています。 
* クエリパラメーターまたはヘッダーの名前は、「。」で開始できません。 または &quot;$&quot;. 
* IPアドレスは使用できません。 
* 内部Adobeアドレス(.adobe.) は許可されません。
 

## Adobe Campaignアクションの制限

* Adobe Campaign Standardトランザクションメッセージングのスケールは、特定のインスタンスのチャネル全体で、1時間あたり最大50,000メッセージになります。 「[Adobe Campaign Standard製品の説明](https://helpx.adobe.com/legal/product-descriptions/campaign-standard.html)」を参照してください。 
 

## イベントの制限

* システム生成イベントの場合、顧客ジャーニーの開始に使用するストリーミングデータは、一意のオーケストレーションIDを取得するために、Journey Orchestration内で最初に設定する必要があります。 このオーケストレーションIDは、Adobe Experience Platformに到達するストリーミングペイロードに追加する必要があります。 この制限は、ルールベースのイベントには適用されません。
 

## データソースの制限事項

* 外部データソースは、顧客ジャーニー内でリアルタイムに外部データを参照するために利用できます。 これらのソースは、REST API経由で使用でき、JSONをサポートし、要求の量を処理できる必要があります。

## プロファイルの作成と同時に開始するジャーニー{#journeys-limitation-profile-creation}

Adobe Experience Platformでは、APIベースのプロファイルの作成/更新に関連する遅延があります。 待ち時間の観点から見ると、サービスレベルターゲット(SLT)は、95パーセンタイルのリクエストに対して、統合プロファイルへの取り込みから1分未満で、1秒あたり20Kのリクエスト数(RPS)です。

ジャーニーがプロファイルの作成時に同時にトリガーされ、すぐにプロファイルサービスから情報を確認/取得する場合、正しく機能しない可能性があります。

次の2つのソリューションのいずれかを選択できます。

* 最初の追加イベントの後の待機アクティビティ。Adobe Experience Platformがプロファイルサービスへの取り込みを行うのに必要な時間を与えるためです。

* このプロファイルをすぐには活用しないジャーニーを設定します。 例えば、ジャーニーがアカウントの作成を確認するように設計されている場合、エクスペリエンスイベントには、最初の確認メッセージ（名、姓、電子メールアドレスなど）の送信に必要な情報を含めることができます。
