---
product: adobe campaign
title: Journey Orchestrationの制限
description: Journey Orchestration制限の詳細
feature: ジャーニー
role: Business Practitioner
level: Beginner
exl-id: 27859689-dc61-4f7a-b942-431cdf244455
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '527'
ht-degree: 2%

---

# 制限事項 {#limitations}

Journey Orchestrationの使用に関する制限を以下に示します。

## 一般的なアクションの制限

* 送信スロットリングはありません。 
* エラーが発生した場合は、2回の再試行が体系的に実行されます。 受信したエラーメッセージに従って再試行の回数を調整することはできません。 
* 組み込みの&#x200B;**Reaction**&#x200B;イベントを使用すると、すぐに使用できるアクションに反応できます（この[page](../building-journeys/reaction-events.md)を参照）。 カスタムアクションで送信されたメッセージに反応する場合は、専用のイベントを設定する必要があります。 
* Adobe Campaign Classic製品化された統合はありません。

## ジャーニーバージョンの制限{#journey-versions-limitations}

* v1のイベントアクティビティで始まるジャーニーは、それ以降のバージョンのイベント以外で開始することはできません。 **セグメントの選定**&#x200B;イベントを使用してジャーニーを開始することはできません。
* v1の&#x200B;**セグメント認定**&#x200B;アクティビティで始まるジャーニーは、必ず以降のバージョンで&#x200B;**セグメント認定**&#x200B;で始める必要があります。
* **Segment qualification**（最初のノード）で選択したセグメントと名前空間は、新しいバージョンでは変更できません。
* 再入口ルールは、すべてのジャーニーバージョンで同じにする必要があります。

## セグメントの適性 {#segment-qualification}

* スループットの制約により、**セグメント認定**&#x200B;アクティビティをAdobe Campaign Standardトランザクションメッセージと組み合わせて使用することはできません。 [Adobe Campaign Standard製品の説明](https://helpx.adobe.com/jp/legal/product-descriptions/campaign-standard.html)を参照してください。 
 

## カスタムアクションの制限

* カスタムアクションURLは動的パラメーターをサポートしていません。 
* POST呼び出しメソッドとPUT呼び出しメソッドのみがサポートされます。 
* クエリパラメーターまたはヘッダーの名前は、「。」で始めることはできません。 または &quot;$&quot;. 
* IPアドレスは許可されません。 
* 内部Adobeアドレス(.adobe.) は許可されていません。
 

## Adobe Campaignアクションの制限

* Adobe Campaign Standardトランザクションメッセージの規模は、特定のインスタンスのチャネル全体で1時間あたり最大50,000件です。 [Adobe Campaign Standard製品の説明](https://helpx.adobe.com/legal/product-descriptions/campaign-standard.html)を参照してください。 
 

## イベントの制限

* システム生成イベントの場合、カスタマージャーニーの開始に使用するストリーミングデータは、一意のオーケストレーションIDを取得するために、まずJourney Orchestration内で設定する必要があります。 このオーケストレーションIDは、Adobe Experience Platformに送られるストリーミングペイロードに追加する必要があります。 この制限は、ルールベースのイベントには適用されません。
 

## データソースの制限

* 外部データソースは、カスタマージャーニー内で利用して、外部データをリアルタイムで検索できます。 これらのソースは、REST APIを介して使用でき、JSONをサポートし、リクエストの量を処理できる必要があります。

## ジャーニーの作成{#journeys-limitation-profile-creation}と同時に開始するプロファイル

Adobe Experience Platformでは、APIベースのプロファイルの作成/更新に関連して遅延が生じます。 待ち時間に関するサービスレベルターゲット(SLT)は、要求の95番目の百分位数（ボリュームは1秒あたり20,000個の要求）に対して、取り込みから統合プロファイルまで1分未満です。

ジャーニーの作成に同時にトリガーされ、即座にプロファイルサービスから情報を確認/取得する場合は、正しく機能しない可能性があります。

次の2つのソリューションのいずれかを選択できます。

* 最初のイベントの後に待機アクティビティを追加して、Adobe Experience Platformがプロファイルサービスへのインジェストを実行するのに必要な時間を確保します。

* プロファイルをすぐに活用しないジャーニーを設定します。 例えば、ジャーニーがアカウントの作成を確認するように設計されている場合、エクスペリエンスイベントには、最初の確認メッセージ（名、姓、Eメールアドレスなど）の送信に必要な情報を含めることができます。
