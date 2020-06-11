---
title: リリースノート
description: リリースノートについて説明します
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
source-git-commit: 556dbe88d2717a387e5f0ce8795c9fa02a45ac6f
workflow-type: tm+mt
source-wordcount: '1098'
ht-degree: 70%

---


# リリースノート{#release-notes}

このページでは、Journey Orchestration のすべての新機能と改善点をリストします。
[ドキュメントの更新](../release-notes/documentation-updates.md)も参照してください。

## 第2四半期リリース — 2020年6月 {#q2-release---june-2020}

<table>
<thead>
<tr>
<th><strong>Adobe Experience Platform統合の強化</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>プラットフォーム統合に関する次の機能強化が行われました。</p>
<ul>
<li><p>新しいアクティビティでは、プラットフォームのセグメントの入口/出口をリスニングして、訪問者が旅に出たり前に進んだりできるようになりました。 <a href="../building-journeys/event-activities.md#segment-qualification">詳細を表示</a></p>
<img src="../assets/rn-segment7.png"/>
</li>
<li><p>新しい「 <strong>セグメント</strong> 」タブにより、Journey Orchestrationインターフェイスを離れることなく、プラットフォームセグメントを作成および編集できるようになりました。<a href="../segment/about-segments.md">詳細を表示</a></p>
<img src="../assets/rn-segment1.png"/>
</li>
<li><p>シンプルな式エディターで、プラットフォームセグメントがナビゲーションツリーに直接表示され、「この人はセグメントAに属していますか？」などの条件を簡単に設定できます。<a href="../segment/using-a-segment.md">詳細を表示</a></p>
<img src="../assets/rn-segment4.png"/>
</li>
<li><p>Journey Orchestrationは、ジャーニーで実行される手順をAdobe Data Platformに自動的に渡すようになりました。 これには、発生する可能性のあるエラーも含まれます。 この情報は、特定のジャーニーまたはすべてのジャーニーに関して、ジャーニーステップイベントのクエリを実行することで、レポートとトラブルシューティングを達成するために使用できます。 <a href="../building-journeys/sharing-overview.md">詳細を表示</a></p>
<img src="../assets/rn-journeystepevent.png"/>
</li>
</li>
<li><p>Journey Orchestrationは、実稼働用および非実稼働用のプラットフォームサンドボックスに接続できるようになりました。 サンドボックスはベータ版機能です。 有効な可用性： 2020年6月30日。 <a href="../about/access-management.md#sandboxes">詳細を表示</a></p>
</li>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>ジャーニーデザイナーとテストモードの機能強化</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>ジャーニーデザイナーとテストモードが次のように強化されました。</p>
<ul>
<li><p>「1」または「N」のジャーニーアクティビティを選択して、1つのジャーニーから別のジャーニーにアクティビティをコピーできるようになりました。 <a href="../building-journeys/using-the-journey-designer.md#copy-paste">詳細を表示</a></p>
<img src="../assets/rn-copy-paste1.png"/>
</li>
<li><p>イベントを実行してテストプロファイルを旅行に出した後、色付きの視覚的な流れにより、その進行状況を見ることができます。 この旅でエラーが発生した場合は、エラーの詳細も表示されます。 <a href="../building-journeys/testing-the-journey.md#firing_events">詳細を表示</a></p>
<img src="../assets/rn-journeytest6.png"/>
</li>
<li>「 <strong>Finished</strong> jerny( <strong>旅の完了</strong> )」の状態は、この状態の意味をよりよく反映するため、「Closed(No Entrance)」に変更されました。</li>
</ul>
</td>
</tr>
</tbody>
</table>

**その他の機能強化**

サードパーティ製システムに対してAPI呼び出しが多すぎるのを防ぐために、新しいパブリックAPIが導入され、「制限」ルールが設定されました。 キャップルールを使用すると、APIエンドポイントへの最大呼び出し数をミリ秒単位で定義できます。 [詳細を表示](../api/capping.md)

アクセス制御のアクセス管理で細分性を高めることができるようになりました。 有効な可用性： 2020年6月30日。 [詳細を表示](../about/access-management.md#create-product-profile)

Journey OrchestrationがAPAC（オーストラリアのデータセンター）で利用できるようになりました。 有効な可用性： 2020年6月30日

Journey Orchestrationインターフェースは日本語で利用できます。

## 第 1 四半期のリリース - 2020 年 3 月 {#q1-release---march-2020}

**新機能**

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
<li>1 つのジャーニーで複数のイベントを使用する場合、テストモードの<strong>イベント設定</strong>画面で、ドロップダウンリストからそれぞれのイベントを個別にトリガーできるようになりました。<a href="../building-journeys/testing-the-journey.md#firing_events">詳細を表示</a></p></li>
<li><p>1 つ以上の<strong>待機</strong>アクティビティを 1 つのジャーニーで使用する場合、それぞれのアクティビティがテストモードで持続する時間を定義できるようになりました。デフォルト時間は 10 秒です。これを変更するには、左下隅にある <strong>Wait time in test</strong> パラメーターを使用します。<a href="../building-journeys/testing-the-journey.md">詳細を表示</a></p><img src="../assets/rn-test.png"/>
</li>
<li><strong>テストログ</strong>で、サードパーティシステムの呼び出し時にエラーが発生した場合（データソースまたはアクション）に、エラーコードとエラー応答が表示されるようになりました。<a href="../building-journeys/testing-the-journey.md#viewing_logs">詳細を表示</a>
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
<li>「<strong>プロファイルタイムゾーン</strong>」チェックボックスを使用すると、ジャーニーを始める人の Experience Platform プロファイルタイムゾーン（ある場合）を使用できます。タイムゾーンがない場合は、ドロップダウンリストで定義されたタイムゾーンが使用されます。この機能は、名前空間を持たないイベントを使用するジャーニーとは互換性がありません。</li>
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
<li><strong>検索</strong>バーの横にある新しいアイコンを使用すると、パレット内の使用できない要素（例：ジャーニーで使用しているものとは異なる名前空間を使用するイベント）を表示または非表示にできます。デフォルトでは、使用できない項目は非表示になります。</li>
<li>「<strong>検索</strong>」フィールドを使用する場合、キャンバスアクティビティカテゴリごとの結果数が表示されるようになりました。</li>
<li>異なるアクティビティカテゴリ間のナビゲーションを改善しました。</li>
</ul>
<p>ジャーニーデザイナーで、最新バージョンのジャーニーにアクセスしていることを確認できるようになりました。この情報は、バージョン番号の横に表示されます。</p>
<p>ジャーニー<strong>キャンバス</strong>で、2 つのアクティビティが切断された場合に、警告メッセージが表示されるようになりました。</p>
<img src="../assets/rn-canvas.png"/>
<p>詳しくは、<a href="../building-journeys/using-the-journey-designer.md">詳細ドキュメント</a>を参照してください。</p>
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

* 米国に加えて、**EMEA** で Journey Orchestration を利用できるようになりました。アプリケーションとドキュメントは、フランス語とドイツ語で入手できます。

* Experience League が製品に統合されました。関連コンテンツへのアクセスが簡素化され、Experience Cloud を最大限に活用できます。Journey Orchestration ドキュメントには「ヘルプ」タブの下部から直接アクセスできます。さらに、ヘルプ／フィードバックをクリックして、問題を報告したり、アドビとアイデアを共有したりできます。

* 新しい項目を作成するための「**C**」キーボードショートカットを、すべてのリスト画面（ジャーニー、データソース、アクション、イベント）で使用できるようになりました。[詳細を表示](../about/user-interface.md#section_ksq_zr1_ffb)

* 停止済みジャーニーを&#x200B;**削除**&#x200B;できるようになりました。これらの削除されたジャーニーに関連付けられたレポートは使用できません。

* **データプラットフォームフィールド**（XDM 形式）を参照する際、フィールド名に加えて表示名が表示されるようになりました。この情報は、エクスペリエンスデータモデルのスキーマ定義から取得されます。使用可能な場合は、代替の表示名が表示されます。内容がわかりやすいように付けられた代替の表示名によって、（特に eVar フィールドの場合は）フィールドをより簡単に識別することができます。[詳細を表示](../about/user-interface.md#friendly-names-display)

## 一般公開（GA）リリース - 2019 年 12 月 {#ga-release---december-2019}

Journey Orchestration が一般公開されました。

イベントやデータソースに保存されたコンテキストデータを活用して、リアルタイムオーケストレーションの使用例を構築します。

Journey Orchestration を使用すると、イベントからのコンテキストデータ、Adobe Experience Platform からの情報、またはサードパーティの API サービスからのデータを利用したリアルタイムオーケストレーションを実現できます。アプリケーションは、ジャーニーと呼ばれる複数手順のフローで、ユーザーのプロファイルと行動に基づいて、ユーザーに特有の次のベストアクションを決定します。これには、最適なタイミングに加えて、Adobe Campaign Standard のトランザクションメッセージング機能（Adobe Campaign Standard が必要）を介した消費者へのプッシュ通知の送信、サードパーティシステムの通知など、アクションのタイプも含まれます。これらの決定は、ルールと Sensei のスコアに基づいておこなわれます。

Journey Orchestration の[詳細](../action/working-with-adobe-campaign.md)をご確認ください。

その他のリソース：

* [チュートリアル](https://docs.adobe.com/content/help/en/platform-learn/tutorials/journey-orchestration/introduction.html)
* [コミュニティ](https://www.adobe.com/go/journeyorchestrationcommunity_jp)
