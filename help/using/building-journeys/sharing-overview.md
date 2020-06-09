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
source-git-commit: a6a98eca551bf5fc46ebd3a6d0d11486e3fbe06b
workflow-type: tm+mt
source-wordcount: '442'
ht-degree: 0%

---


# ジャーニーステップの共有の概要{#sharing-overview}

Journey Orchestrationは、旅行パフォーマンスデータをAdobe Experience Platformに自動的に送信するので、他のデータと組み合わせて分析を目的とすることができます。

例えば、複数の電子メールを送信する遍歴が設定されているとします。 この機能を使用すると、Journey Orchestrationデータを、コンバージョン数、Webサイトで発生したエンゲージメントの数、ストアで発生したトランザクションの数など、ダウンストリームイベントデータと組み合わせることができます。 この遍歴情報は、他のデジタルプロパティやオフラインプロパティのデータと組み合わせて、より包括的なパフォーマンス表示を提供することができます。

Journey Orchestrationは、個々のステップが進むたびに、必要なスキーマとデータセットを自動的に作成し、プラットフォームにストリーミングします。 ステップイベントは、遍歴の中でノード間を移動する個々の要素に対応します。 例えば、イベント、条件およびアクションを持つ遍歴では、3つのステップイベントがプラットフォームに送信されます。

渡されるXDMフィールドのリストは包括的です。 システムで生成されたコードを含むコードもあれば、人間が解読可能なフレンドリ名を持つコードもあります。 例としては、遍歴アクティビティのラベルやステップステータスがあります。 アクションがタイムアウトした、またはエラーが発生して終了した回数。

>[!CAUTION]
>
>デフォルトでは、リアルタイムプロファイルサービスではデータセットは有効になりません。 プロファイルサービスでデータセットを使用する場合は、データセットをオンにする(**プロファイル** の切り替え)必要があります。 大量のイベントが割り当てのストレージを引き上げることに注意してください。 プロファイルのデータセットをアクティブ化する前に、注意して操作を進めてください
>
>![](../assets/sharing4.png)

>[!]
>
>Journeysには、Journey Stepプロファイルイベントをプラットフォームに送信するかどうかの機能もあります。  ジャーニーは、これを決めるテクノロジーを維持している。
>
>![](../assets/techtoggle.png)

ジャーニーは、発生したとおりにデータをストリーミング方式で送信します。 このデータは、クエリサービスを使用してクエリできます。 これらの手順に関連する表示データには、Customer Jeurney Analyticsまたは他のBIツールに接続できます。

次のスキーマが作成されます。

* Journey Orchestrationの遍歴ステッププロファイルイベントスキーマ — 個々の遍歴参加者へのマッピングに使用するIDマップと共に遍歴で行われる手順のエクスペリエンスイベント。
* Journey Orchestrationのジャーニーステップイベントスキーマ — ジャーニーステップイベント。この情報は、ジャーニーメタデータに結び付けられています。
* ジャーニースキーマとJourney Orchestrationのためのジャーニーフィールド — ジャーニーメタデータ」を参照してください。

![](../assets/sharing1.png)

![](../assets/sharing2.png)

次のデータセットが渡されます。

* Journey Orchestrationの遍歴ステッププロファイルイベントスキーマ
* ジャーニーステップイベント
* ジャーニー

![](../assets/sharing3.png)

プラットフォームに渡されるXDMフィールドのリストについて詳しくは、以下を参照してください。

* [jeurneyStepsイベント共通フィールド](../building-journeys/sharing-common-fields.md)
* [jeurnyStepイベントアクション実行フィールド](../building-journeys/sharing-execution-fields.md)
* [jurneryStepイベントデータ取得フィールド](../building-journeys/sharing-fetch-fields.md)
* [jurneryStepイベントIDフィールド](../building-journeys/sharing-identity-fields.md)
* [旅の場](../building-journeys/sharing-journey-fields.md)

