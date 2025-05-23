---
product: adobe campaign
title: リリースノート
description: リリースノートについて説明します
feature: Journeys
role: User
level: Beginner
exl-id: b923f7e3-997b-483b-b6ac-eef62fc81a84
source-git-commit: 4f6c5f9326b4d1cc4a1a02a036b51e4ad1ae68c4
workflow-type: ht
source-wordcount: '4458'
ht-degree: 100%

---

# リリースノート {#release-notes}

>[!CAUTION]
>
>**Adobe Journey Optimizer をお探しですか**？Journey Optimizer のドキュメントについて詳しくは、[こちら](https://experienceleague.adobe.com/ja/docs/journey-optimizer/using/ajo-home){target="_blank"}をクリックしてください。
>
>
>_このドキュメントは、Journey Optimizer に置き換えられた従来の Journey Orchestration 資料を参照しています。Journey Orchestration または Journey Optimizer へのアクセスについてご質問がある場合は、アカウントチームにお問い合わせください。_

このページでは、Journey Orchestration のすべての新機能と改善点をリストします。Experience Platform の機能については、次の[リリースノート](https://experienceleague.adobe.com/docs/experience-platform/release-notes/latest.html?lang=ja)を参照してください。

2022年以降にリリースされた機能については、リンク先の [Adobe Journey Optimizer ドキュメント](https://experienceleague.adobe.com/ja/docs/journey-optimizer/using/ajo-home){target="_blank"}を参照してください。

## 2024年3月リリース {#mar-rn-2024}

### 機能強化 {#mar-2024-improvements}

新しい中間ステータスが次のジャーニーオーサリングライフサイクルに追加されました。

* **ドラフト**&#x200B;ステータスと&#x200B;**ライブ**&#x200B;ステータスの間の&#x200B;**公開**&#x200B;ステータス
* **ライブ**&#x200B;ステータスと&#x200B;**停止**&#x200B;ステータスの間の&#x200B;**停止**&#x200B;ステータス
* **ドラフト**&#x200B;ステータスと&#x200B;**ドラフト（テスト）**&#x200B;ステータスの間の&#x200B;**テストモードのアクティブ化**&#x200B;または&#x200B;**テストモードの非アクティブ化**

ジャーニーが中間の状態にある場合は、読み取り専用です。[詳細情報](https://experienceleague.adobe.com/ja/docs/journey-optimizer/using/orchestrate-journeys/create-journey/journey-gs#filter){target="_blank"}

## 2024年2月リリース {#feb-rn-2024}

### 機能強化 {#feb-2024-improvements}

* **ジャーニーをフィルタリング** - 既存の定義済み日付フィルターに加えて、**カスタム日付を使用してジャーニーインベントリをフィルタリング**&#x200B;できるようになりました。これにより、特定の日付、特定の月内、年間全体、指定した期間内に作成または公開されたジャーニーを表示することで、リストを絞り込むことができます。[詳細情報](https://experienceleague.adobe.com/docs/journey-optimizer/using/orchestrate-journeys/create-journey/journey-gs.html?lang=ja#filter){target="_blank"}
* **カスタムアクション** - **content-type** ヘッダーを更新できるようになりました。この新しい **content-type** は、JSON コンテンツを参照する必要があります。[詳細情報](https://experienceleague.adobe.com/docs/journey-optimizer/using/configuration/configure-journeys/action-journeys/about-custom-action-configuration.html?lang=ja#url-configuration){target="_blank"}
* **設定** - stepEvents のidentityMap 属性が事前に入力されるようになりました。プライマリ ID は「primary = true」として定義されます。[詳細情報](https://experienceleague.adobe.com/docs/journey-optimizer/using/reporting/reports/sharing-field-list.html?lang=ja){target="_blank"}
* **ユーザーインターフェイス** - エクスペリエンスを向上させるために、ジャーニー画面の上部バーが再編成されました。様々な更新が行われるなか、ジャーニーのプロパティにアクセスできる「鉛筆」アイコンが、上部バーの左側、ジャーニー名の横に表示されるようになりました。[詳細情報](https://experienceleague.adobe.com/docs/journey-optimizer/using/orchestrate-journeys/create-journey/journey-gs.html?lang=ja#change-properties){target="_blank"}

## 2024年1月リリース {#jan-rn-2024}

### 機能強化 {#jan-2024-improvements}

* **反応イベントの期間** - **反応イベント**&#x200B;で定義できる最大期間は、30 日ではなく 29 日になりました。[詳細情報](https://experienceleague.adobe.com/docs/journey-optimizer/using/orchestrate-journeys/about-journey-building/reaction-events.html?lang=ja){target="_blank"}
* **フィールドグループ** - このリリースでは、特定の場合にフィールドグループの保存がブロックされていた問題が修正されています。
* `<listObject>` のサポートは、複数の機能で変更されました。

## 2023年8月リリース {#aug-rn-2023}

### 機能強化 {#aug-2023-improvements}

* カスタムアクションで API 呼び出し応答を活用し、これらの応答に基づいてジャーニーを調整できるようになりました。この機能は現在、Private Beta として使用可能です。Journey Optimizer [ドキュメント](https://experienceleague.adobe.com/docs/journey-optimizer/using/configuration/configure-journeys/action-journeys/action-response.html?lang=ja){target="_blank"}を参照してください。

## 2023年4月リリース {#apr-rn-2023}

### 機能強化 {#april-2023-improvements}

* アクション、データソース、イベント、ジャーニーに表示される設定パネルのレイアウトが改善されました。
* カスタムアクションで静的クエリパラメーターまたは動的クエリパラメーターを定義できるようになりました。Journey Optimizer [ドキュメント](https://experienceleague.adobe.com/docs/journey-optimizer/using/configuration/configure-journeys/action-journeys/about-custom-action-configuration.html?lang=ja#url-configuration){target="_blank"}を参照してください。
* ジャーニーが提供するエクスペリエンスの増加を管理する新しいガードレールは次のとおりです。
   * ジャーニーのパフォーマンス、読みやすさ、QA、トラブルシューティングを維持するために、ノード数を 50 以下に制限することをお勧めします。アクティビティの数は、ジャーニーキャンバスの左上に表示されます。Journey Optimizer [ドキュメント](https://experienceleague.adobe.com/docs/journey-optimizer/using/get-started/guardrails.html?lang=ja#journeys-guardrails-journeys){target="_blank"}を参照してください
   * ジャーニーを開発して開始する際に、一度に 100 のライブジャーニーというマイルストーンに近づくと通知されます。プランで一度に 100 を超えるジャーニーが必要な場合は、通知を確認した後にサポート用のチケットを作成してください。アドビがお手伝いします。Journey Optimizer [ドキュメント](https://experienceleague.adobe.com/docs/journey-optimizer/using/get-started/guardrails.html?lang=ja#journeys-guardrails-journeys){target="_blank"}を参照してください

## 2023年3月リリース {#mar-2023}

### 機能強化 {#mar-2023-improvements}

* 新しい **Throttling API** では、1 秒あたりに送信されるイベントの数に制限を設定して、外部システムや API での過剰なトラフィックのスパイクを防ぐことができます。設定制限に達すると、以降のすべての API 呼び出しは、受け取った順序で、可能な限り早くキューに登録されて処理されます。この機能では、すべてのサンドボックスに対して 1 つのスロットル設定のみがサポートされることに注意してください。[詳細情報](../api/throttling.md)
* ジャーニーキャンバスが強化され、よりシンプルで改善されたユーザーエクスペリエンスが実現しました。キャンバスの各パスの最後に、空のプレースホルダーが削除されています。これで、パスの最後にあるアクティビティをドラッグするだけで、アクティビティを追加できます。
* ジャーニーキャンバスで、**終了**&#x200B;タグは、以前のアクティビティの名前で自動的に設定されなくなりました。必要に応じて、カスタムラベルを手動で追加できます。
* ジャーニープロパティのデフォルトのタイムアウトとエラーの時間が 5 秒から 30 秒に変更されました。Journey Optimizer [ドキュメント](https://experienceleague.adobe.com/docs/journey-optimizer/using/configuration/configure-journeys/external-systems/external-systems.html?lang=ja#timeout){target="_blank"}を参照してください。
* インターフェイスを通じて送信されたイベントのみをリッスンするガードレールが、テストモードに追加されました。 外部ツールから送信されたイベントは考慮されません。Journey Optimizer [ドキュメント](https://experienceleague.adobe.com/docs/journey-optimizer/using/orchestrate-journeys/create-journey/testing-the-journey.html?lang=ja){target="_blank"}を参照してください。

## 2023年2月リリース {#feb-2023}

### 機能強化 {#feb-2023-improvements}

* ジャーニープロパティに「**再エントリ待機期間**」フィールドが追加されました。このフィールドでは、（イベントまたはセグメントの資格で始まる）単一のジャーニーで、プロファイルがジャーニーに再度エントリできるようにするまでの待機時間を定義できます。これにより、ジャーニーが同じイベントに対して誤って複数回トリガーされるのを防ぎます。デフォルトでは、このフィールドは 5 分に設定されています。Journey Optimizer [ドキュメント](https://experienceleague.adobe.com/docs/journey-optimizer/using/orchestrate-journeys/create-journey/journey-gs.html?lang=ja#entrance){target="_blank"}を参照してください。
* **ジャーニーの開始日と終了日**&#x200B;が改善されました。開始日を指定していない場合は、公開時に自動的に追加されるようになりました。その日付に達したプロファイルを自動的に終了できます。Journey Optimizer [ドキュメント](https://experienceleague.adobe.com/docs/journey-optimizer/using/orchestrate-journeys/create-journey/journey-gs.html?lang=ja#dates){target="_blank"}を参照してください。

## 2023年1月リリース {#jan-2023-release}

### 機能強化 {#jan-2023-improvements}

* 「**セグメントの選定**」をジャーニーに追加すると、名前空間は、最後に使用した名前空間で、デフォルトで事前入力されるようになりました。Journey Optimizer [ドキュメント](https://experienceleague.adobe.com/docs/journey-optimizer/using/orchestrate-journeys/about-journey-building/segment-qualification-events.html?lang=ja#about-segment-qualification){target="_blank"}を参照してください。
* ジャーニーキャンバスのツールバーに新しいボタンが表示され、ジャーニーのスクリーンショットをダウンロードできます。

## 2022年9月リリース{#sept-2022-release}

### 新機能{#sept-2022-features}


<table>
<thead>
<tr>
<th><strong>データガバナンスとプライバシー</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Data Usage Labeling and Enforcement（DULE）ガバナンスフレームワークにより、Journey Orchestration では、Adobe Experience Platform ガバナンスポリシーを活用して、機密のフィールドがカスタムアクションを通じてサードパーティのシステムへと書き出されるのを防止できるようになりました。制限されたフィールドがカスタムアクションパラメーターで特定されると、エラーが表示され、ジャーニーの公開ができなくなります。</p>
<p>Data Usage Labeling and Enforcement（DULE）の使用は、現在、選択した顧客に限定されており、将来のリリースですべての環境にデプロイされます。</p>
<p>詳しくは、Journey Optimizer <a href="https://experienceleague.adobe.com/docs/journey-optimizer/using/privacy/action-privacy.html?lang=ja">ドキュメント</a>を参照してください。
</td>
</tr>
</tbody>
</table>

### 機能強化{#sept-2022-improvements}

* 同じイベントに対してジャーニーが誤って複数回トリガーされるのを防ぐために、新しいガードレールが（イベントまたはセグメントの選定で始まる）単一のジャーニーに追加されました。プロファイルの再エントリは、デフォルトで 5 分間一時的にブロックされるようになりました。Journey Optimizer [ドキュメント](https://experienceleague.adobe.com/docs/journey-optimizer/using/get-started/guardrails.html?lang=ja#events-g){target="_blank"}を参照してください。

### その他の変更{#sept-2022-other}

* パフォーマンスを向上させるために、セグメントの選定アクティビティで開始されるジャーニーでは、エクスペリエンスイベントフィールドグループを使用できなくなりました。この変更は、新しいジャーニーにのみ適用されます。既存のジャーニーは、現在の動作を維持します。Journey Optimizer [ドキュメント](https://experienceleague.adobe.com/docs/journey-optimizer/using/get-started/guardrails.html?lang=ja#expression-editor){target="_blank"}を参照してください。

### 機能強化

* **ジャーニーの終了** - ジャーニーキャンバスで、**終了**&#x200B;アクティビティがパレットから削除されました。デフォルトで終了タグが各パスの最後に追加され、削除できなくなりました。この機能強化により、どこで顧客がジャーニーから離脱したのか、ジャーニーの実務担当者が何もしなくても、より適切にレポートできるようになりました。Journey Optimizer [ドキュメント](https://experienceleague.adobe.com/docs/journey-optimizer/using/orchestrate-journeys/manage-journey/end-journey.html?lang=ja){target="_blank"}を参照してください。

* ジャーニープロパティで「**プロファイルのタイムゾーン**」オプションは、デフォルトではオフになっています。[詳細情報](https://experienceleague.adobe.com/docs/journey-optimizer/using/orchestrate-journeys/manage-journey/timezone-management.html?lang=ja#timezone-from-profiles){target="_blank"}。

## 2022年5月リリース {#may-2022-release}

### 機能強化

* **式エディター** - [limit](../functions/functionlimit.md) 関数が追加され、リストの項目数を制限できるようになりました。[sort](../functions/functionsort.md) 関数を使用して、リストオブジェクトを並べ替えることができるようになりました。また、listObject のサポートが [discint](../functions/functiondistinct.md) および [distinctWithNull](../functions/functiondistinctwithnull.md) 関数に追加されました。

## 2022年3月リリース {#feb-2022-release}

### 機能強化

* 統合プロファイルスキーマに不要なフィールドが含まれないようにするために、ジャーニーステップイベントスキーマはプロファイルに対してデフォルトでは有効にならなくなりました。必要に応じて、有効にすることができます。[詳細情報](../building-journeys/sharing-overview.md)
* エクスポートジョブに関連する新しいステップイベントが、Journey Optimizer から Adobe Experience Platform に送信されるようになりました。クエリの例がドキュメントに追加されました。[詳細情報](../building-journeys/query-examples.md)

## 2022年2月リリース {#february-2022-release}

### 機能強化

* パフォーマンスを最適化し、古くなったリソースの使用を防ぐために、1 週間トリガーされていないテストモードのすべてのジャーニーは、ドラフトステータスに戻ります。[詳細情報](../building-journeys/testing-the-journey.md#important_notes)

## 2022年1月リリース {#january-2022-release}

### 機能強化

* Journey Orchestration ステップイベントを、[Adobe Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-overview.html?lang=ja){target="_blank"} の他のデータセットにリンクできるようになりました。ビルトイン Journey Step Event スキーマの **profileID** フィールドが、ID フィールドとして定義されるようになりました。[詳細情報](../building-journeys/sharing-overview.md#integration-cja)
* Adobe Campaign Standard アクションのキャッピングルールが、5 分あたり 4000 件数の呼び出しに変更されました。[詳細情報](../action/working-with-adobe-campaign.md)

## 2021年10月リリース {#october-2021-release}

### 機能強化

* **式エディター** - パワーユーザーは、関数を使用してマップを操作できるようになりました。[詳細情報](../expression/field-references.md)
* **アクセシビリティ** - アクセシビリティ機能の強化が実装されました。Journey Orchestration は、アクセシビリティの点で完全に準拠するようになりました。
* **コレクション** - サブオブジェクトを含んだオブジェクトの配列がサポートされるようになりました。[詳細情報](../usecase/collections.md)
* **監視** - ライブジャーニーのステップイベントとテストモードが強化されました。プロファイルエクスポートジョブに関連する[新規フィールド](../building-journeys/sharing-field-list.md#serviceevents)が追加されました。ユーザーエクスペリエンスを向上させるために、ステップイベントのフィールドは、Journey Orchestration 用のジャーニーステップイベントスキーマの異なるカテゴリに整理されるようになりました。以前のステップイベントフィールドはすべて、引き続き [stepEvents](../building-journeys/sharing-legacy-fields.md) カテゴリで使用できます。

## 2021年9月リリース {#september-2021-release}

<table>
<thead>
<tr>
<th><strong>カスタムアクションを使用したデータリストの動的な受け渡し</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>実行時に動的に入力されるカスタムアクションパラメーターに、コレクションつまりデータのリストを渡すことができるようになりました。単純なコレクションとオブジェクトコレクションの 2 種類のコレクションがサポートされています。以前に作成したカスタムアクションは引き続き機能します。 </p>
<p>コレクションについて詳しくは、<a href="../usecase/collections.md">詳細なドキュメント</a>を参照してください。 </p>
<p>filter 関数と intersect 関数が、高度な式エディターで使用できる関数のリストに追加されました。これにより、コレクションのフィルタリングと比較でさらに多くのことを行えるようになります。</p>
<p><a href="../functions/functionfilter.md">filter</a> 関数と <a href="../functions/functionintersect.md">intersect</a> 関数のドキュメントを参照してください。</p>
</td>
</tr>
</tbody>
</table>

### 機能強化

* ステップイベントのプロビジョニング時に作成されたシステム生成スキーマおよびデータセットは、読み取り専用モードになり、重要なスキーマへの不用意な変更に対する保護が強化されました。[詳細情報](../building-journeys/sharing-overview.md)
* 「**待機**」アクティビティのラベルとして、キャンバスに表示されるラベルがはっきりと表示されます。このラベルは、レポートおよびテストモードのログでも使用され、実行内容がはっきりとわかるようになっています。[詳細情報](../building-journeys/using-the-journey-designer.md)
* 検索を使用して&#x200B;**イベント**&#x200B;および&#x200B;**アクション**&#x200B;カテゴリの要素をフィルタリングすることで、イベントとアクションをすばやく見つけることができます。オーケストレーションアクティビティがフィルタリングされなくなりました。[詳細情報](../building-journeys/using-the-journey-designer.md)
* ルールベースでイベントイベント ID 条件を定義する際に、文字列タイプのフィールドで「contains（次を含む）」演算子を使用できるようになりました。[詳細情報](../event/about-creating.md)

## 2021 年 8 月リリース {#august-2021-release}

### 機能強化

**ジャーニー**

* **動的ヘッダー** - HTTP ヘッダーパラメーターで動的データを渡せるようになりました。これらのパラメーターは、ジャーニーアクションの HTTP 呼び出し（タイムスタンプやトラッキング ID など）を受信する統合システムで使用できます。[詳細情報](../action/url-configuration.md)
* **動的 URL パス** - カスタムアクションの動的 URL パスをセットアップできるようになりました。[詳細情報](../action/url-configuration.md)

## 2021 年 7 月リリース {#july-2021-release}

<table>
<thead>
<tr>
<th><strong>スキーマ間の関係の活用</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Adobe Experience Platform では、あるデータセットを別のデータセットのルックアップテーブルとして使用するために、スキーマ間の関係を定義できます。Journey Orchestration は、リンクされたスキーマからのデータを活用できるようになりました。</p>
<p>これらのフィールドは、単一のイベント設定、ジャーニー条件、カスタムアクションのパーソナライゼーションで使用できます。
<p>詳しくは、 <a href="../event/experience-event-schema.md#leverage_schema_relationships">詳細なドキュメント</a>を参照してください。</p>
</td>
</tr>
</tbody>
</table>

### 機能強化

* **キャッシュ時間**&#x200B;フィールドがデータソース設定ペインから削除されました。[詳細を読む](../datasource/about-data-sources.md)

## 2021 年 6 月リリース {#june-2021-release}

<table>
<thead>
<tr>
<th><strong> Adobe Campaign Classic との統合</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Adobe Campaign Classic と統合できるようになりました。Adobe Campaign v7 または v8 のトランザクションメッセージ機能を使用して、メール、プッシュ通知、SMS を送信できます。</p>
<p>Journey Orchestration インスタンスと Campaign インスタンスの接続は、プロビジョニング時にアドビが設定します。</p>
<p>詳しくは、 <a href="../action/acc-action.md">詳細なドキュメント</a>を参照してください。</p>
</td>
</tr>
</tbody>
</table>

### 機能強化

* 外部データソースの場合、1 秒あたり 15 回というキャッピングルールが自動的に定義されるようになりました。 [詳細を読む](../about/external-systems.md#capping)
* シンプルな式エディターと高度な式エディターで、XDM 日付形式がサポートされるようになりました。
* ジャーニーリスト画面に新しいフィルターが追加されました。**[!UICONTROL 単一イベント]**&#x200B;または&#x200B;**[!UICONTROL セグメントの選定]**のジャーニータイプでフィルタリングできるようになりました。
[詳細を読む](../about/user-interface.md#section_lgm_hpz_pgb)
* ライブジャーニーの場合、ジャーニーのプロパティ画面に、ジャーニーの公開日と公開したユーザー名が表示されるようになりました。 この情報は、ジャーニーの技術的な詳細をコピーする際にも利用できます。 [詳細を読む](../building-journeys/changing-properties.md#section_lgm_hpz_pgb)

## 2021 年 4 月リリース {#april-2021-release}

### 機能強化

* テストモードの&#x200B;**イベント設定**&#x200B;画面で、定義済みリストのフィールドにドロップダウンが表示されるようになりました。表示される値の 1 つを選択するだけで設定できます。これにより、誤った値が定義されたことでイベントのトリガー時にエラーが発生するのを回避できます。[詳細を読む](../building-journeys/testing-the-journey.md#firing_events)

## 2021 年 3 月リリース {#march-2021-release}

### 機能強化

* ジャーニーに新しいステータスが追加されました。ジャーニーが終了または手動で閉じられると、閉じられてから 30 日後に、ジャーニーのステータスは&#x200B;**クローズド**&#x200B;から&#x200B;**完了**&#x200B;に切り替わります。これにより、非アクティブなジャーニーをより簡単に特定できる一方、ジャーニーにまだ参加しているすべての個人がジャーニーを完了する時間を確保できます。[詳細を読む](../building-journeys/journey.md#ending_a_journey)
* ドラフトジャーニーのアクティビティの右パネルで、読み取り専用フィールドがデフォルトで非表示になりました。こうしたインターフェイスの簡素化で、アクティビティをより簡単に設定できるようになります。これらのフィールドを表示するには、アクティビティ設定ペインの左上隅にある「**読み取り専用フィールドを表示**」アイコンをクリックします。[詳細を読む](../building-journeys/using-the-journey-designer.md#configuration_pane)
* テストモードの&#x200B;**イベント設定**&#x200B;画面で、テストプロファイルの ID を定義するために使用される「**キー**」フィールドは、ユーザーエクスペリエンスを向上させるために、名前が&#x200B;**プロファイル識別子**&#x200B;に変更されました。[詳細を読む](../building-journeys/testing-the-journey.md)。
* 反応イベントの場合、タイムアウト時間は 40 秒から 30 日の間でのみ設定できるようになりました。反応イベントを使用するジャーニーをテストする場合、テストモードの&#x200B;**[!UICONTROL 待機時間]**&#x200B;はデフォルトで最小値の 40 秒になりました。[詳細を読む](../building-journeys/reaction-events.md)。

## 2021 年 2 月リリース {#february-2021-release}

<table>
<thead>
<tr>
<th><strong>プロファイルアクティビティの更新</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>この新しいアクションアクティビティを使用すると、イベントやデータソースから得られた情報、または特定の値を使用して、既存の Adobe Experience Platform プロファイルを更新できます。</p>
<p>詳しくは、 <a href="../building-journeys/update-profiles.md">詳細なドキュメント</a>を参照してください。</p>
</td>
</tr>
</tbody>
</table>

### その他の機能強化

* 現在は、イベントを設定する場合、XDM 検証に必須のフィールドのみがデフォルトで事前に選択されています。これらのフィールドは選択解除できません。
* ジャーニーパレットに新しいフィルターが追加されました。標準搭載されたイベントに加えて、直近で使用した 5 つのイベントとアクションのみを表示できます。この機能は、各ユーザーに固有です。デフォルトでは、すべての項目が表示されます。[詳細を読む](../building-journeys/using-the-journey-designer.md#palette)
* 新しいジャーニーを開始するとき、最初の手順でキャンバスにドロップできない要素が非表示になりました。これは、すべてのアクション、条件のアクティビティ、待機、反応が対象です。
* 高度な式エディターの左側に表示されるリストの最後にある「**関数**」セクションの下に関数が再グループ化されるようになりました。

## 2021 年 1 月リリース {#january-2021-release}

イベント設定でスキーマを選択する場合、Journey Orchestration がイベントを適切に受け取るために必須のフィールドのみが選択されます。[詳細を読む](../event/defining-the-payload-fields.md)

ジャーニーのプロパティ属性は、シンプルな式エディターで使用できるようになりました。[詳細を読む](../expression/journey-properties.md)

2 つの新しいジャーニーのプロパティ属性（sandboxName と organizationId）が追加されました。[詳細を読む](../expression/journey-properties.md)

Adobe Campaign Standard の SLA に合わせるために、Adobe Campaign Standard 統合が設定されるとすぐに、Adobe Campaign Standard のアクションに対して 1 秒あたり 13 コールの制限ルールが自動的に定義されるようになりました。[詳細を読む](../action/working-with-adobe-campaign.md)

イベントのタイムアウト時間が、タイムアウトパスでより明確に指定されるようになりました。[詳細を読む](../building-journeys/event-activities.md#listening-to-events-during-a-specific-time)

[getListItem](../functions/functiongetlistitem.md) 関数と [split](../functions/functionsplit.md) 関数が、高度な式エディターで使用できる関数のリストに追加されました。これにより、文字列計算の使用例の自由度が向上します。

## 2020 年 11 月リリース {#november-release}

<table>
<thead>
<tr>
<th><strong>ジャーニー間でのジャンプ</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>新しいアクションアクティビティで、各個人をジャーニー間で移動させることができるようになりました。<strong>ジャンプ</strong>アクティビティを使用すると、次のことができます。
</p>
<ul>
<li>非常に複雑なジャーニーを複数のジャーニーに分けて設計を簡素化する </li>
<li>一般的で再利用可能なジャーニーパターンに基づいてジャーニーを作成する</li>
</ul>
<p>詳しくは、<a href="../building-journeys/jump.md">詳細なドキュメント</a>を参照してください。</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>式エディターでのジャーニープロパティの使用</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>高度な式エディターで、フィールドと関数のリストに新しいカテゴリを追加しました。これは、ジャーニー ID や発生した特定のエラーなど、システムがライブジャーニーから取得した情報です。これにより、ジャーニーを作成する際に、より多くのことができるようになります。例えば、条件やアクションでエラーが発生した場合に、サードパーティ製システムにアラートを出すことができます。
</p>
<p>詳しくは、<a href="../expression/journey-properties.md">詳細なドキュメント</a>を参照してください。</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>ルールベースのイベント（ベータ版）</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>イベント ID を使用せず、より簡単にイベントを設定できる新しい方法が追加されました。ルールベースのイベントは、一定の条件に従ってイベントをトリガーする必要があるかを評価します。既存のメソッド（現在は「システム生成」と呼ばれています）も引き続き使用できます。この機能は、アルファプログラムを使用して一部の顧客にてテストされていましたが、すべての顧客がベータ版で利用できるようになりました。
</p>
</td>
</tr>
</tbody>
</table>

### その他の機能強化

新しいバージョンのジャーニーを作成する場合の制限が追加されました。これらの制限により、ジャーニーの急激な変動が抑制され、バージョン間の一貫性が維持されます。[詳細を読む](../about/limitations.md#journey-versions-limitations)

**セグメントの選定**アクティビティは、Campaign Standard メッセージアクティビティを含むジャーニーでは使用できなくなりました。 この制限により、Adobe Campaign Standard インスタンスの整合性が維持されます。実際、セグメントの選定を使用すると、メッセージ送信が毎日のようにピークに達し、Campaign Standard のトランザクションメッセージに大きな負荷がかかる可能性があります。
[詳細を読む](../about/limitations.md#segment-qualification)

## 2020 年 10 月リリース {#october-release}

<table>
<thead>
<tr>
<th><strong>イベントタイムアウト</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>一定時間のみイベントをジャーニーでリッスンするように、イベントのタイムアウトを設定できるようになりました。これをおこなうために、イベントパスに並行して待機アクティビティを追加する必要がなくなりました。
</p>
<p>詳しくは、 <a href="../building-journeys/event-activities.md#listening-to-events-during-a-specific-time">詳細なドキュメント</a>を参照してください。</p>
</td>
</tr>
</tbody>
</table>

### その他の機能強化

* 新しいバージョンのジャーニーを公開すると、前のバージョンが自動的に終了し、クローズステータスに切り替わります。[詳細を読む](../building-journeys/journey-versions.md)

## 2020 年 9 月リリース {#september-release}

### 一般公開（GA）のアップデート{#september-ga-update}

<table>
<thead>
<tr>
<th><strong>条件アクティビティの改善</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>ジャーニーに条件を追加した際に、ラベルを定義できるようになりました。1 つのジャーニーで複数の条件を使用している場合は、それらの条件をより簡単に特定できます。
</p>
<p>詳しくは、 <a href="../building-journeys/condition-activity.md#about_condition">詳細なドキュメント</a>を参照してください。</p>
</td>
</tr>
</tbody>
</table>

### アルファ版のアップデート{#september-alpha-update}

<table>
<thead>
<tr>
<th><strong>「セグメントを読み取り」アクティビティの改善</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p><strong>セグメントを読み取り</strong>アクティビティに対して、次の機能が強化されました。
</p>
<ul>
<li><p>セグメントベースのジャーニーがキャンバスの上に表示されるようになりました。これは、ジャーニーのスケジュールタイプを知らせる役割を果たします。このリマインダーをクリックすると、スケジュール設定メニューにアクセスできます。</p>
</li>
<li><p>テストモードログの精度が向上し、セグメントエクスポートの進行状況ステータスが表示されるようになりました。</p>
</li>
</ul>
</td>
</tr>
</tbody>
</table>

## 2020 年 8 月リリース {#august-release}

### 一般公開（GA）のアップデート{#august-ga-update}

セグメントの選定イベントのペイロードには、行動（エントリ、離脱）、選定のタイムスタンプおよびセグメント ID のコンテキスト情報が含まれるようになりました。これらの情報は、条件およびアクションで使用できます。[詳細を読む](../building-journeys/segment-qualification-events.md)

### アルファ版のアップデート{#august-alpha-update}

<table>
<thead>
<tr>
<th><strong>セグメントトリガーアクティビティ</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>セグメントトリガーアクティビティに対して、次の機能が強化されました。
</p>
<ul>
<li><p>アクティビティの名前が「セグメントを読み取り」に変更されました。 </p>
</li>
<li><p>ジャーニースケジューラーの設定がアクティビティプロパティから削除されました。代わりに、「セグメントを読み取り」アクティビティがキャンバスにドロップされた場合に表示される専用のセクションで、ジャーニーのプロパティから直接アクセスできるようになりました。 </p>
</li>
<li><p>これにより、単一のプロファイルでジャーニーをテストし、視覚的なフローを使用して、ジャーニーの進行状況を追跡できるようになりました。</p>
</li>
</ul>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>ルールベースのイベント</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>ルールベースのイベントに対して、次の機能が強化されました。
</p>
<ul>
<li><p>既にキャプチャ済みで Platform へのストリーミングをおこなっている Adobe Analytics のあらゆる行動イベントデータを活用し、ジャーニーをトリガーして顧客向けのエクスペリエンスを自動化できるようになりました。<a href="../event/about-analytics.md">詳細を読む</a></p>
</li>
<li><p>テストモードでルールベースのイベントをトリガーする場合、イベント ID 条件を直接表示できるようになりました。また、ルール評価の一部である各フィールドの横にツールチップが追加されました。<a href="../building-journeys/testing-the-journey.md#test-rule-based">詳細を読む</a></p>
</li>
<li><p>ルールベースのイベント定義画面が再構成され、エクスペリエンスが向上しました。<a href="../event/about-creating.md">詳細を読む</a></p>
</li>
</ul>
</td>
</tr>
</tbody>
</table>

## アルファリリース - 2020 年 7 月 {#alpha-release---july-2020}

アルファプログラムオファー機能は、限られた顧客セットの中で現在テストされています。これにより、寄せられたフィードバックに基づいて製品の改善に役立てることができます。これらの機能は、すべての Journey Orchestration ユーザーにご利用いただけるわけではありません。

<table>
<thead>
<tr>
<th><strong>ユーザーインターフェイスの強化</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Adobe Experience Platform との一貫したインターフェイスを提供するため、Journey Orchestration メニュー内のナビゲーションが強化されました。
</p>
<ul>
<li><p>メニューがインターフェイスの上部から左側に移動しました。 </p>
</li>
<li><p>管理機能を 1 つのダッシュボードにグループ化しました。</p>
</li>
</ul>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>セグメントトリガーアクティビティ</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>セグメントトリガーアクティビティを使用すると、Adobe Experience Platform セグメントに属するすべての個人をジャーニーにエントリさせることができます。ジャーニーへのエントリは、1 回きりと定期的のいずれも可能です。 
</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>ルールベースのイベント</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>エクスペリエンスイベントの設定方法が簡略化されました。eventID を使用する必要のない新しいメソッドが導入されます。Journey Orchestration でイベントを設定する際に、ルールベースのイベントを定義できるようになりました。<a href="../event/about-events.md">詳細を読む</a>
</p>
</td>
</tr>
</tbody>
</table>


## 第 2 四半期リリース - 2020 年 6 月 {#q2-release---june-2020}

<table>
<thead>
<tr>
<th><strong>Adobe Experience Platform 統合の強化</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Adobe Experience Platform 統合に関する次の機能強化がおこなわれました。</p>
<ul>
<li><p>新しいアクティビティでは、Adobe Experience Platform セグメントのエントリ／離脱をリッスンして、ユーザーによるジャーニーへのエントリやジャーニーの進行を可能にします。<a href="../building-journeys/segment-qualification-events.md">詳細を読む</a></p>
<img src="../assets/rn-segment7.png"/>
</li>
<li><p>新しい「<strong>セグメント</strong>」タブにより、Journey Orchestration インターフェイスを離れることなく、Adobe Experience Platform セグメントを作成および編集できるようになりました。<a href="../segment/about-segments.md">詳細を読む</a></p>
<img src="../assets/rn-segment1.png"/>
</li>
<li><p>シンプルな式エディターに、Adobe Experience Platform セグメントがナビゲーションツリーに直接表示され、「この人はセグメント A に属しているか」などの条件を容易に設定できるようになりました。<a href="../segment/using-a-segment.md">詳細を読む</a></p>
<img src="../assets/rn-segment4.png"/>
</li>
<li><p>Journey Orchestration が、ジャーニーで実行される手順を Adobe Experience Platform に自動的に渡すようになりました。これには、発生する可能性のあるエラーも含まれます。この情報は、特定のジャーニーまたはすべてのジャーニーに対して、ジャーニーステップイベントのクエリを実行することで、レポートとトラブルシューティングを可能にするために使用できます。<a href="../building-journeys/sharing-overview.md">詳細を読む</a></p>
<img src="../assets/rn-journeystepevent.png"/>
</li>
<li><p>Journey Orchestration が、実稼動用および非実稼動用の Adobe Experience Platform サンドボックスに接続できるようになりました。サンドボックスはベータ版機能です。<a href="../about/access-management.md#sandboxes">詳細を読む</a></p>
</li>
</ul>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>ジャーニーデザイナーとテストモードの強化</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>ジャーニーデザイナーとテストモードが次のように強化されました。</p>
<ul>
<li><p>1 または N 個のジャーニーアクティビティを選択して、1 つのジャーニーから別のジャーニーにアクティビティをコピー＆ペーストできるようになりました。<a href="../building-journeys/using-the-journey-designer.md#copy-paste">詳細を読む</a></p>
<img src="../assets/rn-copy-paste1.png"/>
</li>
<li><p>イベントを実行してテストプロファイルをジャーニーにエントリした後、色付きのビジュアルフローにより、ジャーニーに沿って進行状況を確認できるようになりました。ジャーニーでエラーが発生した場合は、エラーの詳細も表示されます。<a href="../building-journeys/testing-the-journey.md#firing_events">詳細を読む</a></p>
<img src="../assets/rn-journeytest6.png"/>
</li>
<li>ジャーニーの「<strong>完了</strong>」ステータスが、ステータスの意味をより明確に反映するために、「<strong>クローズ済み (新規エントリなし)</strong>」に変更されました。</li>
</ul>
</td>
</tr>
</tbody>
</table>

**その他の機能強化**

サードパーティのシステムに対する過剰な API 呼び出しを防ぐために、新しいパブリック API が導入され、「キャッピング」ルールが設定されました。キャッピングルールを使用すると、API エンドポイントへの最大呼び出し数をミリ秒単位で定義できます。[詳細を読む](../api/capping.md)

アクセス制御によってユーザーアクセス管理の精度が高まりました。使用可能となる日付：2020 年 6 月 30 日。[詳細を読む](../about/access-management.md#create-product-profile)

Journey Orchestration が APAC（オーストラリアのデータセンター）で利用できるようになりました。使用可能となる日付：2020 年 6 月 30 日

Journey Orchestration インターフェイスは日本語で利用できます。

## 第 1 四半期リリース - 2020 年 3 月 {#q1-release---march-2020}

<table>
<thead>
<tr>
<th><strong>テストモードの強化</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>テストモードが次のように強化されました。</p>
<ul>
<li>1 つのジャーニーで複数のイベントを使用した場合、テストモードの<strong>イベント設定</strong>画面で、ドロップダウンリストからそれぞれのイベントを個別にトリガーできるようになりました。<a href="../building-journeys/testing-the-journey.md#firing_events">詳細を読む</a></p></li>
<li><p>1 つ以上の<strong>待機</strong>アクティビティを 1 つのジャーニーで使用した場合、それぞれのアクティビティがテストモードで持続する時間を定義できるようになりました。デフォルトの時間は 10 秒です。これを変更するには、左下隅にある <strong>Wait time in test</strong> パラメーターを使用します。<a href="../building-journeys/testing-the-journey.md">詳細を読む</a></p><img src="../assets/rn-test.png"/>
</li>
<li><strong>テストログ</strong>で、サードパーティシステムの呼び出し時にエラーが発生した場合（データソースまたはアクション）に、エラーコードとエラー応答が表示されるようになりました。<a href="../building-journeys/testing-the-journey.md#viewing_logs">詳細を読む</a>
</li>
</ul>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>一元化されたタイムゾーン管理</strong><br/></th>
</tr>
</thead>
<tbody>
<tr> 
<td>
<p>タイムゾーン管理をジャーニープロパティパネルで一元化しました。次の 2 つのパラメーターをジャーニープロパティに追加しました。</p>
<img src="../assets/rn-timezone.png"/>
<ul>
<li>「<strong>タイムゾーン</strong>」ドロップダウンリストを使用すると、特定のタイムゾーンを選択できます。デフォルトでは、ブラウザーのタイムゾーンが使用されます。 </li>
<li>「<strong>プロファイルタイムゾーン</strong>」チェックボックスを使用すると、ジャーニーにエントリする人の Adobe Experience Platform プロファイルタイムゾーン（ある場合）を使用できます。タイムゾーンがない場合は、ドロップダウンリストで定義されたタイムゾーンが使用されます。この機能は、名前空間を持たないイベントを使用するジャーニーには対応しません。</li>
</ul>
<p>詳しくは、<a href="../building-journeys/changing-properties.md#timezone">プロパティの変更</a>および<a href="../building-journeys/timezone-management.md">タイムゾーン管理</a>の節を参照してください。</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>ジャーニーデザイナーの機能強化</strong><br/></th>
</tr>
</thead>
<tbody>
<tr> 
<td>
<p>ジャーニーデザイナーの左側にあるジャーニー<strong>パレット</strong>機能が強化されました。</p>
<ul>
<li><strong>検索</strong>バーの横にある新しいアイコンを使用すると、パレット内の使用できない要素（例：ジャーニーで使用しているものとは異なる名前空間を使用するイベント）を表示または非表示にできます。デフォルトでは、使用できない項目は非表示になっています。</li>
<li>「<strong>検索</strong>」フィールドを使用した際に、キャンバスアクティビティカテゴリごとの結果数が表示されるようになりました。</li>
<li>異なるアクティビティカテゴリ間のナビゲーションを改善しました。</li>
</ul>
<p>ジャーニーデザイナーで、最新バージョンのジャーニーにアクセスしていることを確認できるようになりました。この情報は、バージョン番号の横に表示されます。</p>
<p>ジャーニー<strong>キャンバス</strong>で、2 つのアクティビティが切断された場合に、警告メッセージが表示されるようになりました。</p>
<img src="../assets/rn-canvas.png"/>
<p>詳しくは、 <a href="../building-journeys/using-the-journey-designer.md">詳細なドキュメント</a>を参照してください。</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>コンテキストヘルプ</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Journey Orchestration の様々なリスト画面（ジャーニー、イベント、アクション、データソース）で、コンテキストヘルプを利用できるようになりました。現在の機能の簡単な説明を表示し、関連記事やビデオにアクセスできます。</p>
<p>コンテキストヘルプを表示するには、画面の右上隅にある <img src="../assets/icon-context.png"/> アイコンをクリックします。 </p>
<img src="../assets/rn-context.png"/>
</td>
</tr>
</tbody>
</table>

**その他の機能強化**

* 米国に加えて、**EMEA** でも Journey Orchestration を利用できるようになりました。アプリケーションとドキュメントは、フランス語版とドイツ語版が用意されています。

* Experience League が製品に統合されました。関連コンテンツへのアクセスが簡素化され、Experience Cloud を最大限に活用できます。Journey Orchestration ドキュメントには「ヘルプ」タブの下部から直接アクセスできます。さらに、ヘルプ／フィードバックをクリックして問題を報告したり、Adobeとアイデアを共有したりします。

* 新しい項目を作成するための「**C**」キーボードショートカットを、すべてのリスト画面（ジャーニー、データソース、アクション、イベント）で使用できるようになりました。[詳細を読む](../about/user-interface.md#section_ksq_zr1_ffb)

* 停止済みジャーニーを&#x200B;**削除**&#x200B;できるようになりました。これらの削除されたジャーニーに関連付けられたレポートは使用できません。

* **Adobe Experience Platform フィールド**（XDM 形式）を参照する際、フィールド名に加えて表示名が表示されるようになりました。この情報は、エクスペリエンスデータモデルのスキーマ定義から取得されます。使用可能な場合は、代替の表示名が表示されます。内容がわかりやすいように付けられた代替の表示名によって、（特に eVar フィールドの場合は）フィールドをより簡単に識別することができます。[詳細を読む](../about/user-interface.md#friendly-names-display)

## 一般公開（GA）リリース - 2019 年 12 月 {#ga-release---december-2019}

Journey Orchestration は現在一般公開（GA）されています。

イベントやデータソースに保存されたコンテキストデータを活用して、リアルタイムオーケストレーションの使用例を構築できます。

Journey Orchestration を使用すると、イベントからのコンテキストデータ、Adobe Experience Platform からの情報、またはサードパーティの API サービスからのデータを利用したリアルタイムオーケストレーションが可能になります。アプリケーションは、ジャーニーと呼ばれる複数手順のフローで、ユーザーのプロファイルと行動に基づいて、ユーザーに特有の次のベストアクションを決定します。これには、最適なタイミングに加えて、Adobe Campaign Standard のトランザクションメッセージング機能（Adobe Campaign Standard が必要）を介した消費者へのプッシュ通知の送信、サードパーティシステムの通知などの、アクションタイプも含まれます。これらの決定は、ルールと Sensei のスコアに基づいておこなわれます。

Journey Orchestration の[詳細](../action/working-with-adobe-campaign.md)をご確認ください。
