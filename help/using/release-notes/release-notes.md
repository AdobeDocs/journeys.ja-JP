---
title: リリースノート
description: リリースノートの詳細
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
source-git-commit: 66e4acb339e9190cf2877c0ab1824ca5f41c8a6d

---


# リリースノート{#release-notes}

このページでは、Jureny Orchestrationの新機能と改善点をすべてリストしています。
ドキュメントの更新を参照す [ることもできます](../release-notes/documentation-updates.md)。

## 第1四半期のリリース — 2020年3月 {#q1-release---march-2020}

**新機能?**

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
<li>複数のイベントを使用する遍歴では、テストモードのリスト設定画面で、ドロップダウンイベントから各モードを個別にトリガ <strong>ーで</strong> きるようになりました。 <a href="../building-journeys/testing-the-journey.md#firing_events">詳細を表示</a></p></li>
<li><p>1つ以上の <strong>Wait</strong> アクティビティが1つの遍歴で使用される場合、これらの各アクティビティがテストモードで持続する時間を定義できるようになりました。 デフォルトの時間は10秒です。 これは、左下隅の <strong>Wait time in test</strong> （テストの待機時間）パラメーターを使用して変更できます。 <a href="../building-journeys/testing-the-journey.md">詳細を表示</a></p><img src="../assets/rn-test.png"/>
</li>
<li>テストロ <strong>グで</strong>、サードパーティのシステム（データソースまたはアクション）を呼び出す際にエラーが発生した場合に、エラーコードとエラー応答が表示されるようになりました。 <a href="../building-journeys/testing-the-journey.md#viewing_logs">詳細を表示</a>
</li>
</ul>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>タイムゾーンの一元管理</strong><br/></th>
</tr>
</thead>
<tbody>
<tr> 
<td>
<p>タイムゾーンの管理がジャーニープロパティパネルに一元化されました。 次の2つのパラメーターがジャーニープロパティに追加されました。</p>
<img src="../assets/rn-timezone.png"/>
<ul>
<li>「 <strong>Timezone</strong> 」ドロップダウンリストを使用すると、特定のタイムゾーンを選択できます。 デフォルトでは、ブラウザーのタイムゾーンが使用されます。 </li>
<li>「 <strong>プロファイルタイムゾーン</strong> 」チェックボックスを使用すると、旅行に参加する人のエクスペリエンスプラットフォームのプロファイルタイムゾーン（利用可能な場合）を使用できます。 タイムゾーンが存在しない場合は、ドロップダウンリストで定義されたタイムゾーンが使用されます。 この機能は、ジャーニーを使用するイベントと互換性がありません。名前空間。</li>
</ul>
<p>詳しくは、「プロパティの変更」および「タ <a href="../building-journeys/changing-properties.md#timezone">イムゾーン管理</a> 」の節を <a href="../building-journeys/timezone-management.md">参照してください</a> 。</p>
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
<p>ジャーニー <strong>デザイナーの</strong>左側にあるジャーニーパレットが強化されました。</p>
<ul>
<li>検索バーの横にある新しいアイコンを使用すると <strong></strong> 、使用できないイベント(例えば、旅行で使用した名前空間とは異なる要素を使用する要素)をパレットで表示または非表示にできます。 デフォルトでは、使用できない項目は非表示になっています。</li>
<li>「検索」フィールド <strong>を使用すると</strong> 、各キャンバスアクティビティカテゴリの結果数が表示されます。</li>
<li>様々なナビゲーションのアクティビティカテゴリが改善されました。</li>
</ul>
<p>ジャーニーデザイナーで、最新バージョンのジャーニーにアクセスしていることを確認できます。 この情報は、バージョン番号の横に表示されます。</p>
<p>ジャーニーキャンバス <strong>で</strong>、2つのアクティビティが切断されると、警告メッセージが表示されるようになりました。</p>
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
<p>様々なジャーニーオーケストレーションリスト画面(ジャーニー、イベント、アクション、データソース)で、コンテキストヘルプを利用できるようになりました。 これにより、現在の機能の表示を簡単に説明し、関連する記事やビデオにアクセスできます。</p>
<p>コンテキストヘルプを表示するには、 <img src="../assets/icon-context.png"/> 画面の右上隅にあるアイコンをクリックします。 </p>
<img src="../assets/rn-context.png"/>
</td>
</tr>
</tbody>
</table>

**その他の改善点**

* 米国に加えて、Journeys Orchestrationは現在、 **EMEAで利用できます**。 アプリケーションとドキュメントは、フランス語とドイツ語で入手できます。

* Experience Leagueが製品に統合されました。 これにより、関連コンテンツへのアクセスが簡素化され、Experience Cloudを最大限に活用できます。 「ヘルプ」タブの下部で、Jurenery Orchestrationのドキュメントに直接アクセスできます。 さらに、ヘルプ/フィードバックをクリックして、問題を報告したり、アドビとアイデアを共有したりします。

* 新しい項目を作成できる **C** Keyboard Shortcutが、すべてのキーボード画面で使用できるようになりました。リスト:ジャーニー、データソース、アクションおよびイベント [詳細を表示](../about/user-interface.md#section_ksq_zr1_ffb)

* 停止したジャーニーを削 **除できる** ようになりました。 これらの削除されたジャーニーに関連付けられたレポートは使用できません。

* データプラット **フォーム** （XDM形式）フィールドを参照する際に、フィールド名に加えて表示名が表示されるようになりました。 この情報は、エクスペリエンスデータモデルのスキーマ定義から取得されます。 使用可能な場合は、代替表示名が表示されます。 このわかりやすい説明は、特にeVarフィールドの場合に役立ち、フィールドをより簡単に識別できます。 [詳細を表示](../about/user-interface.md#friendly-names-display)

## GAリリース — 2019年12月 {#ga-release---december-2019}

Javerny Orchestrationは現在GAです。

リアルタイムオーケストレーションの使用例を構築し、イベントやデータソースに保存されたコンテキストデータを活用します。

Jureny Orchestrationを使用すると、イベントのコンテキストデータ、Adobe Experience Platformの情報、またはサードパーティのAPIサービスのデータを利用したリアルタイムオーケストレーションを実現できます。 アプリケーションは、「ジャーニー」と呼ばれる複数のステップフローで、消費者のプロファイルと行動に基づいて、次に最適なアクションを決定します。 これは、最適なタイミングと、Adobe Campaign Standardのトランザクションメッセージング機能（Adobe Campaign Standardが必要）やサードパーティシステムの通知を通じて消費者にプッシュ通知を送信するなど、アクションのタイプの両方で構成されます。 この決定はルールと先生の得点に基づいて行われます。

[](../action/working-with-adobe-campaign.md)
Journey Orchestration の詳細を説明します。

その他のリソース:

* [チュートリアル](https://docs.adobe.com/content/help/en/platform-learn/tutorials/journey-orchestration/introduction.html)
* [コミュニティ](https://www.adobe.com/go/journeyorchestrationcommunity)
