---
product: adobe campaign
solution: Journey Orchestration
title: Journey Orchestration制限
description: Journey Orchestration制限の詳細
translation-type: tm+mt
source-git-commit: 6ebedad2cb8e78b4dd953bc7a2993cebbeefabcc
workflow-type: tm+mt
source-wordcount: '361'
ht-degree: 3%

---


# 制限事項{#limitations}

Journey Orchestrationの使用に関する制限を以下に示します。

## 一般的なアクションの制限

* 送信ジョブ数の制限はありません。 
* 誤りの場合には、2つの再試行を系統的に行う。 受け取ったエラーメッセージに従って再試行数を調整することはできません。 
* 組み込みの **Reaction** イベントを使用すると、あらかじめ用意されているアクションに対応できます(この [ページを参照](../building-journeys/reaction-events.md))。 カスタムアクションを介して送信されたメッセージに反応する場合は、専用のイベントを設定する必要があります。 
* Adobe Campaign Classic製品の統合はありません。

## ジャーニーバージョンの制限 {#journey-versions-limitations}

* v1のイベントアクティビティで始まる遍歴は、それ以降のバージョンではイベント以外のものと開始できません。 セグメントクオリフィケーション **** イベントを使用して旅行を開始することはできません。
* v1の **セグメント資格** アクティビティから始まる遍歴は、必ず、それ以降のバージョンで **セグメント資格と開始する必要があります** 。
* セグメントクオリフィケーション **** （最初のノード）で選択したセグメントと名前空間は、新しいバージョンでは変更できません。
* 再入場規則は、すべてのジャーニーバージョンで同じにする必要があります。

## セグメントの適性 {#segment-qualification}

* スループットの制約により、 **セグメント認定** アクティビティは、Adobe Campaign Standardトランザクションメッセージングと組み合わせて使用できません。 See [Adobe Campaign Standard Product Description](https://helpx.adobe.com/jp/legal/product-descriptions/campaign-standard.html). 
 

## カスタムアクションの制限

* カスタムアクションURLは動的パラメーターをサポートしていません。 
* POSTとPUT呼び出しのメソッドのみがサポートされています。 
* クエリパラメーターまたはヘッダーの名前は、「。」で開始できません。 または &quot;$&quot;. 
* IPアドレスは使用できません。 
* 内部Adobeアドレス(.adobe.) は許可されません。
 

## Adobe Campaignアクションの制限

* Adobe Campaign Standardトランザクションメッセージングのスケールは、特定のインスタンスのチャネル全体で、1時間あたり最大50,000メッセージになります。 See [Adobe Campaign Standard Product Description](https://helpx.adobe.com/jp/legal/product-descriptions/campaign-standard.html). 
 

## イベントの制限

* 顧客の遍歴の開始に使用するストリーミングデータは、一意のオーケストレーションIDを取得するために、まずJourney Orchestration内で設定する必要があります。 このオーケストレーションIDは、Adobe Experience Platformに到達するストリーミングペイロードに追加する必要があります。
 

## データソースの制限事項

* 外部データソースは、顧客の遍歴の中でリアルタイムに外部データを参照できます。 これらのソースは、REST API経由で使用でき、JSONをサポートし、要求の量を処理できる必要があります。