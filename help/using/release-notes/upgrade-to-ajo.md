---
title: Adobe Journey Optimizerへのアップグレード
description: Adobe Journey Optimizerへのアップグレード方法を説明します
hide: true
hidefromtoc: true
source-git-commit: 8591ed266f5a360dbc7bea8dd8a6d7a089aa346f
workflow-type: tm+mt
source-wordcount: '777'
ht-degree: 3%

---


# Journey Orchestration環境をAdobe Journey Optimizerにアップグレード{#ugrade-ajo}

## Adobe Journey Optimizerとは

Adobe Journey Optimizerは、任意のアプリ、デバイス、画面、チャネルにわたって、パーソナライズされ、接続されたタイムリーなカスタマージャーニーを統合し、提供するために、Adobe Experience Platform上でネイティブに構築された機敏で拡張性の高いアプリケーションで&#x200B;す。

## Journey Orchestration とは

Journey Orchestrationは、Adobe Experience Platformを基に構築されたサービスで、以前の行動と好みに基づいて顧客ごとに個別のジャーニーをカスタマイズできます。 Journey Orchestrationは、Journey Optimizerへの前駆的な適用です。

## なぜ私はAdobe Journey Optimizerに引っ越す必要があるのですか？

**合理化されたインターフェイスへのアクセス** を使用すると、ジャーニー、データセット、プロファイル、アラートなどにすばやくアクセスできます。 Adobe Experience PlatformとJourney Orchestration間でやり取りをしてスキーマやデータセットにアクセスする必要がなくなり、すべてAdobe Journey Optimizerから直接使用できます。 詳しくは、[このページ](https://experienceleague.adobe.com/docs/journey-optimizer/using/get-started/user-interface.html)を参照してください。

<table>
<tr>
<th>前</th>
<th>後</th>
</tr>
<tr>
<td><img src="../assets/migration-ajo-1.png"><p>「 」Journey Orchestrationで、ジャーニー、セグメントおよび管理者セクション（データソース、イベント、アクション）にアクセスできる。 セグメントとデータセットには、Adobe Experience Platformでアクセスできます。 </p></td>
<td><img src="../assets/migration-ajo-2.png"><p>ジャーニー、セグメント、管理者、セグメントおよびデータセットへのアクセス <strong>Adobe Journey Optimizer内</strong>. <strong>その他のAdobe Experience Platform機能</strong> は、こちらからもアクセスできます。</p></td>
</tr>
</table>

**新しいレポートインターフェイス** 新しいレポート機能にアクセスするには：

<table>
<tr>
<th>前</th>
<th>後</th>
</tr>
<tr>
<td><img src="../assets/migration-ajo-5.png"></td>
<td><img src="../assets/migration-ajo-6.png"><p><strong>グローバル表示</strong> を使用すると、選択した期間におけるジャーニーと配信の影響を測定できます。 よりリアルタイムの指標については、 <strong>ライブ表示</strong>. ジャーニーで使用されている各配信チャネル（E メール、SMS、プッシュ）に対して、 <strong>専用セクション</strong> は、指標を表示するためのレポートで使用できます。 これは、標準搭載のを使用する場合にのみ適用されます <strong>Adobe Journey Optimizerのメッセージ機能</strong>. 詳しくは、アカウントチームにお問い合わせください。</p></td>
</tr>
</table>

レポートエクスペリエンスを向上させたり、新しい機能リリースに従って強化したりするように変化した場合は、新しいレポートインターフェイスでのみ使用できます。 これを使用して、より完全なAdobe Journey Optimizerエクスペリエンスを得ます。

他の最新の機能を活用 **Adobe Journey Optimizerの機能** フィールドレベルのアクセス制御やオブジェクトレベルのアクセス制御など、新しいものが出てきます。 詳しくは、アカウントチームにお問い合わせください。

## Journey Orchestration環境をアップグレードする方法

1. アカウントチームに連絡して、無料でAdobeとの契約を更新してください。

1. 変更が完了するまで、エンジニアリングチームがお待ちください。

1. Journey Optimizerの製品プロファイルを使用して権限を更新します。 この[ページ](https://experienceleague.adobe.com/docs/journey-optimizer/using/administration/ootb-product-profiles.html?lang=ja)を参照してください。

1. Adobe Journey Optimizerにアクセスできます。

## よくある質問

### Journey OrchestrationからAdobe Journey Optimizerに移行するためには、何か計画が必要ですか？

移行は不要で、作業は不要で、ダウンタイムも不要で、追加投資も不要です。 お客様はAdobeとの契約を更新するだけで、残りの作業を行います。 このプロセスの開始方法については、アカウント担当者にお問い合わせください。

### 変更後に何か失う？

いいえ。既存のJourney OrchestrationとAdobe Experience Platformオブジェクトはすべて保持されます。スキーマ、データセット、ジャーニー、イベント、データソース、アクション。 何も失われず、すべてのライブジャーニーは、中断なしで引き続き機能します。

<table>
<tr>
<th>前</th>
<th>後</th>
</tr>
<tr>
<td><img src="../assets/migration-ajo-7.png"></td>
<td><img src="../assets/migration-ajo-8.png"></td>
</tr>
</table>

### アプリケーションスイッチャーにJourney Orchestrationが表示されますが、正常ですか？

![](../assets/migration-ajo-9.png)

はい、正常です。 アップグレード後 1 か月間、Journey Orchestrationへのアクセスを保持します。 これにより、すべてのユーザー権限を更新し、Adobe Journey Optimizerをより深く理解するのに十分な時間を確保できます。 1 ヶ月後に、アクセス権が削除されます。

### 今日Adobe Campaign StandardでJourney Orchestrationを使用するとどうなりますか？

Adobe Journey Optimizerに移行しても、Adobe Journey Optimizerでカスタマージャーニーを設計し、Adobe Campaign Standardに配信を送信させることで、ジャーニーとAdobe Campaign Standardの統合を引き続き使用できます。

ただし、Adobe Journey Optimizerのレポートスタックの動作により、レポートはジャーニーとCampaign Standardのデータを組み合わせません。 ジャーニー情報は、Adobe Campaign StandardのAdobe Journey Optimizerレポートおよび配信情報で使用できます。 Experience Platformの設定を行って、Adobe Campaign StandardデータをAdobe Experience Platformに取り込み、Customer Journey Analyticsで使用できるようにすることができます ([詳細情報](https://business.adobe.com/products/experience-platform/customer-journey-analytics.html)) や、Tableau や PowerBI などのその他のサードパーティのレポートツール。

Adobe Journey Optimizerのレポートは、Adobe Journey Optimizerの標準のメッセージング機能 ( 専用のAdobe Journey Optimizer製品で利用可能 ) を使用する場合に最適です。 ジャーニーキャンバスでのメッセージの作成方法について詳しくは、この [ページ](https://experienceleague.adobe.com/docs/journey-optimizer/using/messages/messages-in-journeys.html).

詳しくは、アカウントチームにお問い合わせください。