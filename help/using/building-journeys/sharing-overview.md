---
product: adobe campaign
title: ジャーニーステップ共有の概要
description: ジャーニーステップ共有の概要
feature: ジャーニー
role: User
level: Intermediate
exl-id: 95ca5fdb-38b7-47a0-b1a9-b1b26bf8e5f5
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '441'
ht-degree: 79%

---

# ジャーニーステップ共有の概要{#sharing-overview}

[!DNL Journey Orchestration] は、他のデータと組み合わせて分析目的に利用できるように　Adobe Experience Platform にジャーニーパフォーマンスのデータを自動送信します。


>[!NOTE]
>
>この機能は、ジャーニーステップのイベントの場合、すべてのインスタンスにおいてデフォルトで有効になっています。 ジャーニープロファイルステップのイベントの場合は、リクエストに応じて有効化されます。 この機能のプロビジョニング中に作成したスキーマとデータセットは変更しないでください。

たとえば、複数の メールを送信するジャーニーを設定したとします。この機能を使用すると、[!DNL Journey Orchestration] のデータをダウンストリームのイベントデータと組み合わせることができます。このようなイベントデータには、発生したコンバージョン数、Web サイトで発生したエンゲージメント、ストアで発生したトランザクション数などがあります。ジャーニー情報を、他のデジタルプロパティやオフラインプロパティのデータと組み合わせて、Adobe Experience Platform上のパフォーマンスをより包括的に把握できます。

[!DNL Journey Orchestration] は、ジャーニーで1回おこなう各手順に対して、必要なスキーマを自動的に作成し、データセットにストリームします。ステップイベントは、ジャーニーのあるノードから別のノードに移動する個人に対応します。例えば、イベント、条件およびアクションを含むジャーニーでは、3つのステップイベントがAdobe Experience Platformに送信されます。

渡される XDM フィールドのリストは多岐にわたります。システムで生成されたコードを含むものもあれば、人間が理解できるわかりやすい名前を持つものもあります。例えば、ジャーニーアクティビティやステップステータスのラベルがあります。アクションがタイムアウトした回数や、エラーで終了した回数などです。

>[!CAUTION]
>
>リアルタイムプロファイルサービスの場合は、データセットを有効にできません。**[!UICONTROL プロファイル]**&#x200B;の切り替えがオフになっていることを確認してください。

ジャーニーは、発生時にストリーミング方式でデータを送信します。このデータは、クエリサービスを使用してクエリできます。Customer Journey Analytics またはその他の BI ツールに接続して、これらのステップに関連するデータを表示できます。

次のスキーマが作成されます。

* [!DNL Journey Orchestration] のジャーニーステッププロファイルイベントスキーマ：ジャーニーで実行されるステップのエクスペリエンスイベントと、個々のジャーニー参加者へのマッピングに使用される ID マップ。
* [!DNL Journey Orchestration] のジャーニーステップイベントスキーマ：ジャーニーメタデータに関連付けられているジャーニーステップイベント。
* [!DNL Journey Orchestration] のジャーニーフィールドを含むジャーニースキーマ：ジャーニーを記述するジャーニーメタデータ。

![](../assets/sharing1.png)

![](../assets/sharing2.png)

次のデータセットが渡されます。

* [!DNL Journey Orchestration] のジャーニーステッププロファイルイベントスキーマ
* ジャーニーステップイベント
* ジャーニー

![](../assets/sharing3.png)

Adobe Experience Platformに渡されるXDMフィールドのリストについて詳しくは、次を参照してください。

* [journeySteps イベントの共通フィールド](../building-journeys/sharing-common-fields.md)
* [journeyStep イベントのアクション実行フィールド](../building-journeys/sharing-execution-fields.md)
* [journeyStep イベントのデータ取得フィールド](../building-journeys/sharing-fetch-fields.md)
* [journeyStep イベントの ID フィールド](../building-journeys/sharing-identity-fields.md)
* [ジャーニーのフィールド](../building-journeys/sharing-journey-fields.md)

Adobe Experience Platform にレポートするステップイベントの詳細については、この[チュートリアルビデオ](https://experienceleague.adobe.com/docs/journey-orchestration-learn/tutorials/reporting-step-events-to-adobe-experience-platform.html?lang=ja)をご覧ください。
