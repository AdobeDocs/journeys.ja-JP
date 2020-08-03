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
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b8cfc9de56e879d8812cf3871067252937454e1d
workflow-type: tm+mt
source-wordcount: '404'
ht-degree: 0%

---


# ジャーニーステップの共有の概要{#sharing-overview}

[!DNL Journey Orchestration] は、旅行パフォーマンスデータをAdobe Experience Platformに自動的に送信し、分析のために他のデータと組み合わせることができます。

例えば、複数の電子メールを送信する遍歴が設定されているとします。 この機能を使用すると、コンバージョン数、Webサイトで発生したアクション数、ストアで発生したトランザクション数など、ダウンストリームイベントデータと [!DNL Journey Orchestration] データを組み合わせることができます。 この遍歴情報を他のデジタルプロパティやオフラインプロパティのデータと組み合わせて、Adobe Experience Platform上のデータと組み合わせることで、より包括的なパフォーマンス表示を実現できます。

[!DNL Journey Orchestration] は、個々の訪問者が旅行を行うたびに、必要なスキーマとデータセットに自動的にストリームします。 ステップイベントは、遍歴の中でノード間を移動する個々の要素に対応します。 例えば、イベント、条件、およびアクションを持つ遍歴では、3つのステップイベントがAdobe Experience Platformに送信されます。

渡されるXDMフィールドのリストは包括的です。 システムで生成されたコードを含むコードもあれば、人間が解読可能なフレンドリ名を持つコードもあります。 例としては、遍歴アクティビティのラベルやステップステータスがあります。 アクションがタイムアウトした、またはエラーが発生して終了した回数。

>[!CAUTION]
>
>リアルタイムプロファイルサービスでは、データセットを有効にできません。 **[!UICONTROL プロファイルの切り替えがオフになっていることを確認してください]** 。

ジャーニーは、発生したとおりにデータをストリーミング方式で送信します。 このデータは、クエリサービスを使用してクエリできます。 Customer Journey Analyticsまたは他のBIツールに接続して、これらの手順に関連する表示データを取得できます。

次のスキーマが作成されます。

* ジャーニーステッププロファイルイベントスキーマ( [!DNL Journey Orchestration] — エクスペリエンスイベント)：個々の遍歴参加者へのマッピングに使用するIDマップと共に、遍歴で行われる手順の例です。
* ジャーニーステップイベントスキーマ( [!DNL Journey Orchestration] — ジャーニーステップイベント)。これは、ジャーニーメタデータに結び付けられています。
* ジャーニースキーマとジャーニーフィールドとの連携 — ジャーニーメタデータ [!DNL Journey Orchestration] を参照してください。

![](../assets/sharing1.png)

![](../assets/sharing2.png)

次のデータセットが渡されます。

* ジャーニーステッププロファイルイベントスキーマ [!DNL Journey Orchestration]
* ジャーニーステップイベント
* ジャーニー

![](../assets/sharing3.png)

Adobe Experience Platformに渡すXDMフィールドのリストについては、以下を参照してください。

* [jeurneyStepsイベント共通フィールド](../building-journeys/sharing-common-fields.md)
* [jeurnyStepイベントアクション実行フィールド](../building-journeys/sharing-execution-fields.md)
* [jurneryStepイベントデータ取得フィールド](../building-journeys/sharing-fetch-fields.md)
* [jurneryStepイベントIDフィールド](../building-journeys/sharing-identity-fields.md)
* [旅の場](../building-journeys/sharing-journey-fields.md)

Adobe Experience Platformへのレポート手順の詳細については、この [チュートリアルビデオを参照してください](https://docs.adobe.com/content/help/en/journey-orchestration-learn/tutorials/reporting-step-events-to-adobe-experience-platform.html)。
