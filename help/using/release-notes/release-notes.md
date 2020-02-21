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
source-git-commit: 6274426ec04315149fb430b847498c0e20164bae

---


# リリースノート{#release-notes}

このページには、Jureny Orchestrationのすべての新機能と改善点が一覧表示されます。
また、ドキュメントの更新を参照す [ることもできます](../release-notes/documentation-updates.md)。

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
<li>1つの遍歴で複数のイベントを使用する場合、テストモードの <strong>Event configuration</strong> 画面で、ドロップダウンリストから各イベントを個別にトリガーできるようになりました。 <a href="../building-journeys/testing-the-journey.md#firing_events">詳細を表示</a></p></li>
<li><p>1つ以上の <strong>Wait</strong> アクティビティを1つの遍歴で使用する場合、これらの各アクティビティがテストモードで持続する時間を定義できます。 デフォルトの時間は10秒です。 この設定は、左下隅の <strong>Wait time in test</strong> パラメーターを使用して変更できます。 <a href="../building-journeys/testing-the-journey.md">詳細を表示</a></p><img src="../assets/rn-test.png"/>
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
<p>タイムゾーン管理がジャーニープロパティパネルに一元化されました。 次の2つのパラメーターがジャーニープロパティに追加されました。</p>
<img src="../assets/rn-timezone.png"/>
<ul>
<li>「 <strong>Timezone</strong> 」ドロップダウンリストを使用すると、特定のタイムゾーンを選択できます。 デフォルトでは、ブラウザーのタイムゾーンが使用されます。</li>
<li>「プロフ <strong>ァイルタイムゾーン</strong> 」チェックボックスを使用すると、旅行に参加した人のエクスペリエンスプラットフォームプロファイルタイムゾーン（利用可能な場合）を使用できます。 そうでない場合は、コンボボックスで定義されているタイムゾーンが使用されます。 この機能は、名前空間を持たないイベントを使用するジャーニーとは互換性がありません。</li>
</ul>
<p>詳しくは、「プロパティとタイムゾーンの <a href="../building-journeys/changing-properties.md#timezone">管理の変更</a> 」の節を <a href="../building-journeys/timezone-management.md">参照してください</a> 。</p>
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
<li>**Search**バーの横にある新しいアイコンを使用すると、使用できない要素（例えば、旅行で使用する名前空間とは異なる名前空間を使用するイベント）をパレットに表示または非表示にできます。 デフォルトでは、使用できない項目は非表示になっています。</li>
<li>「検索」フィールド <strong>を使用する場合</strong> 、各キャンバスアクティビティカテゴリの結果数が表示されるようになりました。</li>
<li>様々なアクティビティカテゴリ間のナビゲーションが改善されました。</li>
</ul>
<p>ジャーニーデザイナーで、最新バージョンの旅行にアクセスしていることを確認できます。 この情報は、バージョン番号の横に表示されます。</p>
<p>ジャーニーキャン <strong>バスで</strong>、2つのアクティビティが切断されると、警告メッセージが表示されるようになりました。</p>
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
<p>様々なJareny Orchestrationリスト画面（ジャーニー、イベント、アクション、データソース）で、コンテキストヘルプを利用できるようになりました。 これにより、現在の機能に関する簡単な説明を表示し、関連する記事やビデオにアクセスできます。</p>
<p>コンテキストヘルプを表示するには、画 <img src="../assets/icon-context.png"/> 面の右上隅にあるアイコンをクリックします。 </p>
<img src="../assets/rn-context.png"/>
</td>
</tr>
</tbody>
</table>

**その他の改善点**

* 米国に加え、EMEAでJourneys Orchestrationを利用できるようになり **ました**。 アプリケーションとドキュメントは、フランス語とドイツ語で入手できます。

* Experience Leagueが製品に統合されました。 これにより、関連コンテンツへのアクセスが簡素化され、Experience cloudを最大限に活用できます。 [ヘルプ]タブの下部で、Jargeny Orchestrationのドキュメントに直接アクセスできます。 さらに、ヘルプ/フィードバックをクリックして、問題を報告したり、アドビとアイデアを共有したりします。

* 新しいアイテムを作成できる **C** cキーボードショートカットが、すべてのリスト画面で使用できるようになりました。ジャーニー、データソース、アクションおよびイベント。 [詳細を表示](../about/user-interface.md#section_ksq_zr1_ffb)

* 停止したジャーニー **を削除で** きるようになりました。 これらの削除されたジャーニーに関連付けられたレポートは使用できません。

* Data Platformフィール **ド** （XDM形式）を参照する際に、フィールド名に加えて表示名が表示されるようになりました。 この情報は、エクスペリエンスデータモデルのスキーマ定義から取得されます。 使用可能な場合は、代替表示名が表示されます。 このわかりやすい説明は、特にeVarフィールドの場合に役立ち、フィールドをより簡単に識別できます。 [詳細を表示](../event/defining-the-payload-fields.md)

## GAリリース — 2019年12月 {#ga-release---december-2019}

Javerny Orchestrationは現在GAです。

イベントやデータソースに保存されたコンテキストデータを活用して、リアルタイムオーケストレーションの使用例を構築します。

Javerny Orchestrationを使用すると、イベントのコンテキストデータ、Adobe Experience Platformの情報、またはサードパーティのAPIサービスのデータを利用したリアルタイムオーケストレーションを実現できます。 アプリケーションは、「ジャーニー」と呼ばれる複数のステップのフローで、そのプロファイルと行動に基づいて、消費者に固有の次のベストアクションを決定します。 最適なタイミングと、Adobe Campaign Standardのトランザクションメッセージング機能（Adobe Campaign Standardが必要）を介したプッシュ通知や、サードパーティ製システムの通知など、ユーザーへのアクションのタイプが含まれます。 決めるのはルールと先生の点数です。

[Jargeny](../action/working-with-adobe-campaign.md) Orchestrationの詳細。

その他のリソース：

* [チュートリアル](https://docs.adobe.com/content/help/en/platform-learn/tutorials/journey-orchestration/introduction.html)
* [コミュニティ](https://www.adobe.com/go/journeyorchestrationcommunity)