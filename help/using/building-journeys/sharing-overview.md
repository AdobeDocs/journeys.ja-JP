---
product: adobe campaign
title: ジャーニーステップの共有の概要
description: ジャーニーステップの共有の概要
feature: ジャーニー
role: Business Practitioner
level: Intermediate
exl-id: 95ca5fdb-38b7-47a0-b1a9-b1b26bf8e5f5
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '422'
ht-degree: 13%

---

# ジャーニーステップの共有の概要{#sharing-overview}

[!DNL Journey Orchestration] は、他のデータと組み合わせて分析目的に利用できるように　Adobe Experience Platform にジャーニーパフォーマンスのデータを自動送信します。


>[!NOTE]
>
>この機能は、新しくデプロイされたすべてのインスタンスで、デフォルトでは有効化されません。 アクティベーションはリクエストに応じて実行します。

例えば、複数のEメールを送信するジャーニーを設定したとします。 この機能を使用すると、コンバージョン数、Webサイトで発生したエンゲージメント数、ストアで発生したトランザクション数など、[!DNL Journey Orchestration]データをダウンストリームイベントデータと組み合わせることができます。 ジャーニー情報を、他のデジタルプロパティやオフラインプロパティのデータと組み合わせて、Adobe Experience Platform上のパフォーマンスをより包括的に把握できます。

[!DNL Journey Orchestration] は、ジャーニーで1回おこなう各手順に対して、必要なスキーマを自動的に作成し、データセットにストリームします。ステップイベントは、ジャーニー内のノード間の個々の移動に対応します。 例えば、イベント、条件およびアクションを含むジャーニーでは、3つのステップイベントがAdobe Experience Platformに送信されます。

渡されるXDMフィールドのリストは包括的です。 システムで生成されたコードを含むものや、人間が読み取り可能なわかりやすい名前を持つものもあります。 例としては、ジャーニーアクティビティのラベルやステップのステータスなどがあります。アクションがタイムアウトした、またはエラーで終了した回数。

>[!CAUTION]
>
>リアルタイムプロファイルサービスのデータセットを有効にすることはできません。 **[!UICONTROL プロファイル]**&#x200B;の切り替えがオフになっていることを確認してください。

ジャーニーは、発生したとおりにストリーミング方法でデータを送信します。 クエリサービスを使用して、このデータに対してクエリを実行できます。 Customer Journey Analyticsや他のBIツールに接続して、これらの手順に関連するデータを表示できます。

次のスキーマが作成されます。

* [!DNL Journey Orchestration]のジャーニーステッププロファイルイベントスキーマ —ジャーニーで実行される手順と、個々のジャーニー参加者へのマッピングに使用するIDマップ用のエクスペリエンスイベント。
* [!DNL Journey Orchestration]のジャーニーステップのイベントスキーマ —ジャーニーメタデータに結び付けられたジャーニーステップのイベント。
* [!DNL Journey Orchestration]のジャーニーフィールドを含むジャーニースキーマ —ジャーニーを記述するジャーニーメタデータ。

![](../assets/sharing1.png)

![](../assets/sharing2.png)

次のデータセットが渡されます。

* [!DNL Journey Orchestration]のジャーニーステッププロファイルイベントスキーマ
* ジャーニーステップイベント
* ジャーニー

![](../assets/sharing3.png)

Adobe Experience Platformに渡されるXDMフィールドのリストについて詳しくは、次を参照してください。

* [journeySteps イベントの共通フィールド](../building-journeys/sharing-common-fields.md)
* [journeyStep イベントのアクション実行フィールド](../building-journeys/sharing-execution-fields.md)
* [journeyStep イベントのデータ取得フィールド](../building-journeys/sharing-fetch-fields.md)
* [journeyStep イベントの ID フィールド](../building-journeys/sharing-identity-fields.md)
* [ジャーニーのフィールド](../building-journeys/sharing-journey-fields.md)

Adobe Experience Platformにレポートする手順イベントについて詳しくは、この[チュートリアルビデオ](https://docs.adobe.com/content/help/en/journey-orchestration-learn/tutorials/reporting-step-events-to-adobe-experience-platform.html)をご覧ください。
