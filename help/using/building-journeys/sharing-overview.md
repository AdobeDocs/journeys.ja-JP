---
product: adobe campaign
solution: Journey Orchestration
title: ジャーニーステップの共有の概要
description: ジャーニーステップの共有の概要
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '421'
ht-degree: 12%

---


# ジャーニーステップの共有の概要{#sharing-overview}

[!DNL Journey Orchestration] は、他のデータと組み合わせて分析目的に利用できるように　Adobe Experience Platform にジャーニーパフォーマンスのデータを自動送信します。


>[!NOTE]
>
>この機能は、デフォルトでは、新しくデプロイされたすべてのインスタンスでアクティブ化されません。 アクティベーションは要求に応じている。

例えば、複数の電子メールを送信するジャーニーを設定したとします。 この機能を使用すると、[!DNL Journey Orchestration]データを、コンバージョン数、Webサイトで発生したアクション数、ストアで発生したトランザクション数など、ダウンストリームイベントデータと結合できます。 ジャーニー情報は、他のデジタルプロパティまたはオフラインプロパティから、Adobe Experience Platformのデータと組み合わせて、より包括的なパフォーマンス表示を提供できます。

[!DNL Journey Orchestration] 個々のジャーニーがステップごとに必要なスキーマとデータセットを自動的に作成し、Adobe Experience Platformにデータセットをストリームします。ステップイベントは、ジャーニー内であるノードから別のノードに移動する個々のノードに対応する。 例えば、イベント、条件、およびアクションを持つジャーニーでは、3つのステップイベントがAdobe Experience Platformに送信されます。

渡されるXDMフィールドのリストは包括的です。 システムで生成されたコードを含むコードもあれば、人間が解読可能なフレンドリ名を持つコードもあります。 例えば、ジャーニーアクティビティのラベルやステップステータスがあります。アクションがタイムアウトした、またはエラーが発生して終了した回数。

>[!CAUTION]
>
>リアルタイムプロファイルサービスでは、データセットを有効にできません。 **[!UICONTROL プロファイル]**&#x200B;の切り替えがオフになっていることを確認してください。

ジャーニーは、発生時にデータをストリーミング方式で送信します。 このデータは、クエリサービスを使用してクエリできます。 Customer Journey Analyticsまたは他のBIツールに接続して、これらの手順に関連する表示データを取得できます。

次のスキーマが作成されます。

* [!DNL Journey Orchestration]のジャーニーステッププロファイルイベントスキーマ — 個々のジャーニー参加者へのマッピングに使用するIDマップと共にジャーニーで実行される手順のエクスペリエンスイベント。
* [!DNL Journey Orchestration]のジャーニーステップイベントスキーマ-ジャーニーメタデータに関連付けられているジャーニーステップイベント。
* [!DNL Journey Orchestration]用のジャーニーフィールドのジャーニースキーマ-ジャーニーを説明するジャーニーメタデータ。

![](../assets/sharing1.png)

![](../assets/sharing2.png)

次のデータセットが渡されます。

* [!DNL Journey Orchestration]のジャーニーステッププロファイルイベントスキーマ
* ジャーニー手順のイベント
* ジャーニー

![](../assets/sharing3.png)

Adobe Experience Platformに渡されるXDMフィールドのリストについては、以下を参照してください。

* [journeySteps イベントの共通フィールド](../building-journeys/sharing-common-fields.md)
* [journeyStep イベントのアクション実行フィールド](../building-journeys/sharing-execution-fields.md)
* [journeyStep イベントのデータ取得フィールド](../building-journeys/sharing-fetch-fields.md)
* [journeyStep イベントの ID フィールド](../building-journeys/sharing-identity-fields.md)
* [ジャーニーのフィールド](../building-journeys/sharing-journey-fields.md)

Adobe Experience Platformへのステップイベントレポートの詳細については、この[チュートリアルビデオ](https://docs.adobe.com/content/help/en/journey-orchestration-learn/tutorials/reporting-step-events-to-adobe-experience-platform.html)をご覧ください。
