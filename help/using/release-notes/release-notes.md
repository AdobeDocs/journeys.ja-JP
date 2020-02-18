---
title: リリースノート
description: リリースノートについて
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
source-git-commit: 8023d7780d43f1de4447c63568f641ce204722c7

---


# リリースノート{#release-notes}

このページには、Jureny Orchestrationのすべての新機能と改善点が一覧表示されます。
また、ドキュメントの更新を参照す [ることもできます](../release-notes/documentation-updates.md)。

## 第1四半期のリリース — 2019年2月 {#q1-release---february-2019}

**タイムゾーン管理**

タイムゾーンは、現在、旅行レベルで管理されています。 次の2つのパラメーターがジャーニープロパティに追加されました。

* 「 **Timezone** 」ドロップダウンでは、特定のタイムゾーンを選択できます。 デフォルトでは、ブラウザーのタイムゾーンが使用されます。

* 「プロフ **ァイルタイムゾーン** 」チェックボックスを使用すると、旅行に参加した人のエクスペリエンスプラットフォームプロファイルタイムゾーン（利用可能な場合）を使用できます。 そうでない場合は、ドロップダウンで定義されたタイムゾーンが使用されます。 この機能は、名前空間のないジャーニーとは互換性がありません。

**コンテキストヘルプ**

コンテキストヘルプ機能が、様々なJargeny Orchestration画面で使用できるようになりました。 つまり、シングルクリックで、現在使用している機能に関するドキュメントに直接アクセスできます。

コンテキストヘルプを表示するには、画面の右上隅にある「i」アイコンをクリックします。

現時点では、この機能はホーム、データソース、イベントおよびアクションリスト画面で使用できます。

**その他の変更**

* テストモードでは、新しいパラメーターを使用してタイムピーナーを定義できます。  待機アクティビティが持続する可能性がある。 これにより、テスト結果にすばやくアクセスできます。

* テストモードで、遍歴のすべてのイベントをトリガーできるようになりました。


* 新しいパラメーターを使用して、タイムピーナーを定義できます。  待機アクティビティが持続する可能性がある。 これにより、テスト結果にすばやくアクセスできます。

* EMEAでJourneys Orchestrationを利用できるようになりました。

* パレットに新しいアイコンが追加され、利用可能な項目を表示または非表示にできます。 sans名前空間。 parのデフォルト。

* canvas, deconnection, petit icone, qui disconnected node.

* ショートカットCトレッツリスト

* パレットのUI（検索結果を表示しない）

* プーワール・キャッパーは、DES APISエクスターネス（データソースから行動）を呼び出す。 マルク・ニアクセプティ500コールパー秒、エル・プウラ・メタントル500コールをキャッピング解除サーチャージャシステムの忠誠度層

* テストログのログを記録します。 Avant status = error. quandを指定します。 ポシビリティエ・ド・ヴォワール・コード・エルル・フレーズ・クア・レンボワール・システムメ。 -> ds un test en cas d&#39;erreur，システム層，エラーコード，エラーレスポンス

* 削除の途中停止

* 旅行：バージョン1の場合、メットされたアイテムは最新

1er火星。


## GAリリース — 2019年12月 {#ga-release---december-2019}

Javerny Orchestrationは現在GAです。

イベントやデータソースに保存されたコンテキストデータを活用して、リアルタイムオーケストレーションの使用例を構築します。

Javerny Orchestrationを使用すると、イベントのコンテキストデータ、Adobe Experience Platformの情報、またはサードパーティのAPIサービスのデータを利用したリアルタイムオーケストレーションを実現できます。 アプリケーションは、「ジャーニー」と呼ばれる複数のステップのフローで、そのプロファイルと行動に基づいて、消費者に固有の次のベストアクションを決定します。 最適なタイミングと、Adobe Campaign Standardのトランザクションメッセージング機能（Adobe Campaign Standardが必要）を介したプッシュ通知や、サードパーティ製システムの通知など、ユーザーへのアクションのタイプが含まれます。 決めるのはルールと先生の点数です。

[Jargeny](../action/working-with-adobe-campaign.md) Orchestrationの詳細。

その他のリソース：

* [チュートリアル](https://docs.adobe.com/content/help/en/platform-learn/tutorials/journey-orchestration/introduction.html)
* [コミュニティ](https://www.adobe.com/go/journeyorchestrationcommunity)