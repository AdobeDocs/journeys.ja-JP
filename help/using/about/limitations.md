---
title: Journey Orchestration制限
description: Journey Orchestration制限の詳細
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: tm+mt
source-git-commit: f45069225b284fe47e2acaccb4aa5d34fe171f35
workflow-type: tm+mt
source-wordcount: '268'
ht-degree: 2%

---


# 制限事項{#limitations}

Journey Orchestrationの使用に関する制限を以下に示します。

## 一般的なアクションの制限

* 送信ジョブ数の制限はありません。 
* 誤りの場合には、2つの再試行を系統的に行う。 受け取ったエラーメッセージに従って再試行数を調整することはできません。 
* 組み込みの **Reaction** イベントを使用すると、あらかじめ用意されているアクションに対応できます(この [ページを参照](../building-journeys/reaction-events.md))。 カスタムアクションを介して送信されたメッセージに反応する場合は、専用のイベントを設定する必要があります。 
* Adobe Campaign Classic製品の統合はありません。
 
## カスタムアクションの制限

* カスタムアクションURLは動的パラメーターをサポートしていません。 
* POSTとPUT呼び出しのメソッドのみがサポートされています。 
* クエリパラメーターまたはヘッダーの名前は、「。」で開始できません。 または &quot;$&quot;. 
* IPアドレスは使用できません。 
* 内部Adobeアドレス(.adobe.) は許可されません。
 

## Adobe Campaignアクションの制限

* Adobe Campaign Standardトランザクションメッセージングのスケールは、特定のインスタンスのチャネル全体で、1時間あたり最大50,000メッセージになります。 See [Adobe Campaign Standard Product Description](https://helpx.adobe.com/jp/legal/product-descriptions/campaign-standard.html). 
* スループットの制約により、 **セグメント認定** アクティビティをAdobe Campaign Standardトランザクションメッセージングと組み合わせて使用することは避けてください。
 
## イベントの制限

* 顧客の遍歴の開始に使用するストリーミングデータは、一意のオーケストレーションIDを取得するために、まずJourney Orchestration内で設定する必要があります。 このオーケストレーションIDは、Adobe Experience Platformに到達するストリーミングペイロードに追加する必要があります。
 

## データソースの制限事項

* 外部データソースは、顧客の遍歴の中でリアルタイムに外部データを参照できます。 これらのソースは、REST API経由で使用でき、JSONをサポートし、要求の量を処理できる必要があります。