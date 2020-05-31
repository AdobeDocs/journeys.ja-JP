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
source-git-commit: 66e4acb339e9190cf2877c0ab1824ca5f41c8a6d
workflow-type: tm+mt
source-wordcount: '758'
ht-degree: 4%

---


# リリースノート{#release-notes}

このページでは、Journey Orchestrationのすべての新機能と改善点をリストしています。
また、 [ドキュメントの更新情報を参照することもできます](../release-notes/documentation-updates.md)。

## 第1四半期のリリース — 2020年3月 {#q1-release---march-2020}

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
<li>1つの遍歴で複数のイベントを使用する場合、テストモードの <strong>イベント設定</strong> 画面で、ドロップダウンリストからそれぞれ個別にトリガーできるようになりました。 <a href="../building-journeys/testing-the-journey.md#firing_events">詳細を表示</a></p></li>
<li><p>1つ以上の <strong>Wait</strong> アクティビティを1つの遍歴で使用する場合、これらの各アクティビティがテストモードで持続する時間を定義できるようになりました。 デフォルトの時間は10秒です。 これを変更するには、左下隅にある <strong>Wait time in test</strong> （テストの待機時間）パラメーターを使用します。 <a href="../building-journeys/testing-the-journey.md">詳細を表示</a></p><img src="../assets/rn-test.png"/>
</li>
<li>テ <strong>ストログで</strong>、サードパーティのシステム（データソースまたはアクション）の呼び出し時にエラーが発生した場合に、エラーコードとエラー応答が表示されるようになりました。 <a href="../building-journeys/testing-the-journey.md#viewing_logs">詳細を表示</a>
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
<p>タイムゾーン管理は、ジャーニープロパティパネルで一元化されました。 次の2つのパラメーターがジャーニープロパティに追加されました。</p>
<img src="../assets/rn-timezone.png"/>
<ul>
<li>「 <strong>Timezone</strong> 」ドロップダウンリストを使用すると、特定のタイムゾーンを選択できます。 デフォルトでは、ブラウザーのタイムゾーンが使用されます。 </li>
<li>「 <strong>プロファイルタイムゾーン</strong> 」チェックボックスを使用すると、遍歴に参加した人のエクスペリエンスプラットフォームプロファイルタイムゾーン（ある場合）を使用できます。 タイムゾーンでない場合は、ドロップダウンリストで定義されたタイムゾーンが使用されます。 この機能は、名前空間を持たないイベントを使用するジャーニーとは互換性がありません。</li>
</ul>
<p>詳しくは、「プロパティの <a href="../building-journeys/changing-properties.md#timezone">変更</a> 」および「 <a href="../building-journeys/timezone-management.md">タイムゾーン管理</a> 」の節を参照してください。</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>遍歴デザイナーの機能強化</strong><br/></th>
</tr>
</thead>
<tbody>
<tr> 
<td>
<p>ジャーニー <strong>パレット</strong>、ジャーニーデザイナーの左側の機能が強化されました。</p>
<ul>
<li>新しいアイコン( <strong>検索</strong> バーの横)を使用すると、パレット内の使用できない要素(例えば、遍歴で使用しているものとは異なる名前空間を使用するイベント)を表示または非表示にできます。 デフォルトでは、使用できない項目は非表示になります。</li>
<li>「 <strong>検索</strong> 」フィールドを使用する場合、キャンバスアクティビティカテゴリごとの結果数が表示されるようになりました。</li>
<li>異なるアクティビティカテゴリ間のナビゲーションが改善されました。</li>
</ul>
<p>ジャーニーデザイナーで、最新バージョンの旅行にアクセスしていることを確認できます。 この情報は、バージョン番号の横に表示されます。</p>
<p>ジャーニー <strong>キャンバスで</strong>、2つのアクティビティが切断された場合に、警告メッセージが表示されるようになりました。</p>
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
<p>様々なJourney Orchestrationリスト画面(ジャーニー、イベント、アクションおよびデータソース)で、コンテキストヘルプを利用できるようになりました。 これにより、現在の機能の簡単な説明を表示し、関連記事やビデオにアクセスできます。</p>
<p>コンテキストヘルプを表示するには、画面の右上隅にある <img src="../assets/icon-context.png"/> アイコンをクリックします。 </p>
<img src="../assets/rn-context.png"/>
</td>
</tr>
</tbody>
</table>

**その他の機能強化**

* 米国に加えて、 **EMEAでJourneys Orchestrationを利用できるようになりました**。 アプリケーションとドキュメントは、フランス語とドイツ語で入手できます。

* Experience Leagueが製品に統合されました。 これにより、関連コンテンツへのアクセスが簡素化され、Experience Cloudを最大限に活用できます。 [ヘルプ]タブの下部で、Journey Orchestrationのドキュメントに直接アクセスできます。 さらに、ヘルプ/フィードバックをクリックして、問題を報告したり、アドビとアイデアを共有したりします。

* 新しいリストを作成できる **C** Keyboard Shortcutは、すべての項目画面で使用できるようになりました。 ジャーニー、データソース、アクションおよびイベント。 [詳細を表示](../about/user-interface.md#section_ksq_zr1_ffb)

* 停止したジャーニーを **削除できるようになりました** 。 これらの削除されたジャーニーに関連付けられたレポートは使用できません。

* 「 **Data Platform fields** （XDM形式）」を参照すると、フィールド名に加えて表示名が表示されるようになりました。 この情報は、エクスペリエンスデータモデルのスキーマ定義から取得されます。 使用可能な場合は、代替表示名が表示されます。 このわかりやすい説明は、特にeVarフィールドの場合に役立ち、フィールドをより簡単に識別できます。 [詳細を表示](../about/user-interface.md#friendly-names-display)

## GAリリース — 2019年12月 {#ga-release---december-2019}

Journey Orchestrationは現在GAです。

イベントやデータソースに保存されたコンテキストデータを活用して、リアルタイムオーケストレーションの使用例を構築します。

Journey Orchestrationにより、イベントのコンテキストデータ、Adobe Experience Platformの情報またはサードパーティのAPIサービスのデータを利用したリアルタイムオーケストレーションを実現できます。 アプリケーションは、ジャーニーと呼ばれる複数のステップフローで、ユーザーのプロファイルと行動に基づいて、ユーザーに特有の次のベストアクションを決定します。 最適なタイミングに加えて、Adobe Campaign標準のトランザクションメッセージング機能(Adobe Campaign標準が必要)を介して消費者にプッシュ通知を送信する、サードパーティ製システムの通知など、アクションのタイプも含まれます。 決めるのはルールと先生の得点です。

[](../action/working-with-adobe-campaign.md)
Journey Orchestration の詳細を説明します。

その他のリソース：

* [チュートリアル](https://docs.adobe.com/content/help/en/platform-learn/tutorials/journey-orchestration/introduction.html)
* [コミュニティ](https://www.adobe.com/go/journeyorchestrationcommunity)
