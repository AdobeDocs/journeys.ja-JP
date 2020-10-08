---
title: ジャーニーステップの共有の概要
description: ジャーニーステップの共有の概要
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: tm+mt
source-git-commit: b852c08a488a1bec02b8b31a1fccf1a8773b99af
workflow-type: tm+mt
source-wordcount: '404'
ht-degree: 13%

---


# ジャーニーステップの共有の概要{#sharing-overview}

[!DNL Journey Orchestration] は、他のデータと組み合わせて分析目的に利用できるように　Adobe Experience Platform にジャーニーパフォーマンスのデータを自動送信します。


例えば、複数の電子メールを送信する遍歴が設定されているとします。 この機能を使用すると、コンバージョン数、Webサイトで発生したアクション数、ストアで発生したトランザクション数など、ダウンストリームイベントデータと [!DNL Journey Orchestration] データを組み合わせることができます。 この旅行に関する情報は、他のデジタルプロパティやオフラインプロパティのデータと組み合わせて、より包括的なパフォーマンス表示を提供することができます。

[!DNL Journey Orchestration] は、個々の人が旅を行うたびに、必要なスキーマを自動的に作成し、データセットにデータセットをストリーミングします。 ステップイベントは、遍歴の中で1つのノードから別のノードに移動する個々の要素に対応します。 例えば、イベント、条件、およびアクションを持つ遍歴では、3つのステップイベントがAdobe Experience Platformに送信されます。

渡されるXDMフィールドのリストは包括的です。 システムで生成されたコードを含むコードもあれば、人間が解読可能なフレンドリ名を持つコードもあります。 例としては、遍歴アクティビティのラベルやステップステータスがあります。アクションがタイムアウトした、またはエラーが発生して終了した回数。

>[!CAUTION]
>
>リアルタイムプロファイルサービスでは、データセットを有効にできません。 **[!UICONTROL プロファイルの切り替えがオフになっていることを確認してください]** 。

ジャーニーは、発生したとおりにデータをストリーミング方式で送信します。 このデータは、クエリサービスを使用してクエリできます。 Customer Journey Analyticsまたは他のBIツールに接続して、これらの手順に関連する表示データを取得できます。

次のスキーマが作成されます。

* ジャーニーステッププロファイルイベントスキーマ( [!DNL Journey Orchestration] — エクスペリエンスイベント)：個々の遍歴参加者へのマッピングに使用するIDマップと共に、遍歴で行われる手順を示します。
* ジャーニーステップイベントスキーマ( [!DNL Journey Orchestration] — ジャーニーステップイベント)。これは、ジャーニーメタデータに結び付けられています。
* ジャーニースキーマとジャーニーフィールドとの連携 — ジャーニーメタデータ [!DNL Journey Orchestration] を参照してください。

![](../assets/sharing1.png)

![](../assets/sharing2.png)

次のデータセットが渡されます。

* ジャーニーステッププロファイルイベントスキーマ [!DNL Journey Orchestration]
* ジャーニーステップイベント
* ジャーニー

![](../assets/sharing3.png)

Adobe Experience Platformに渡されるXDMフィールドのリストについては、以下を参照してください。

* [journeySteps イベントの共通フィールド](../building-journeys/sharing-common-fields.md)
* [journeyStep イベントのアクション実行フィールド](../building-journeys/sharing-execution-fields.md)
* [journeyStep イベントのデータ取得フィールド](../building-journeys/sharing-fetch-fields.md)
* [journeyStep イベントの ID フィールド](../building-journeys/sharing-identity-fields.md)
* [ジャーニーのフィールド](../building-journeys/sharing-journey-fields.md)

Adobe Experience Platformへのステップイベントレポートの詳細については、この [チュートリアルビデオをご覧ください](https://docs.adobe.com/content/help/en/journey-orchestration-learn/tutorials/reporting-step-events-to-adobe-experience-platform.html)。
