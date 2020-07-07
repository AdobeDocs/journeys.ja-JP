---
title: ドキュメントの更新
description: ドキュメントの更新について説明します
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
source-git-commit: 5d92b9d70a70700026a4715c6cb6a6c4ba565ba5
workflow-type: tm+mt
source-wordcount: '649'
ht-degree: 59%

---


# ドキュメントの更新

This page lists all the documentation updates for [!DNL Journey Orchestration].
You can also consult the [!DNL Journey Orchestration] [Release Notes](../release-notes/release-notes.md).

## 2020 年 7 月 {#july-2020}

* 制限された一連のお客様でテストされるAlpha機能に関する新しい節を追加しました。 [詳細を表示](../alpha/alpha-overview.md)
* インテリジェントサービスとの統合に関する新しい節を追加しました。 [詳細を表示](../ai-services/ai-services-overview.md)
* テストプロファイルの作成に関する新しい節を追加しました。 [詳細を表示](../building-journeys/testing-the-journey.md#create-test-profile)。
* 遍歴条件またはアクションでの **SegmentQuolification** ノードの使用方法に関する情報を追加しました。 [詳細を表示](../building-journeys/event-activities.md#segment-qualification)。
* キャンペーンのトランザクションメッセージとイベントのパブリケーションにメモが追加されました。 [](../action/working-with-adobe-campaign.md)および[](../building-journeys/using-adobe-campaign-actions.md)を参照してください。
* Campaign StandardインスタンスURLのテスト時に実行されるチェックに関する情報が追加されました。 [詳細を表示](../action/working-with-adobe-campaign.md)
* AWSまたはAzureサーバーでホストされるCampaign Standardインスタンスとのイベントの互換性に関する情報が追加されました。 [詳細を表示](../building-journeys/event-activities.md#section_dhx_gss_dgb)
* Campaign Standardトランザクションメッセージングを扱う際にキャッピング規則を設定する必要があることについての注意を追加しました。 [詳細を表示](../action/working-with-adobe-campaign.md)
* テストモードを使用してイベントをトリガーする場合の実イベントの生成に関する注意事項が追加されました。 [詳細を表示](../building-journeys/testing-the-journey.md#firing_events)

## 2020 年 6 月{#june-2020}

* カスタム認証データソース用のトークンのキャッシュ期間を変更する方法に関する情報を追加しました。 [詳細を表示](../datasource/external-data-sources.md#section_wjp_nl5_nhb)
* スクリーンショットとテキストを更新し、「 **Finished** jerny」の名前が「 **Closed（入口なし）」に変更されたことを反映しました**。
* インターフェイスでの言語の定義方法に関する情報を追加しました。 [詳細を表示](../about/user-interface.md)
* 個人の遍歴のステータスのリストは、「 [テストモードログ](../building-journeys/testing-the-journey.md#viewing_logs) 」セクションに移動されました。

## 2020 年 4 月 {#april-2020}

* エクスペリエンスイベントスキーマの定義に関する新しい節を追加し、初回イベントの設定に役立ちました。 [詳細を表示](../event/experience-event-schema.md)
* ドキュメントのホームページ [!DNL Journey Orchestration] が更新され、さらに役立つリンクが追加されました。 [詳細を表示](../../journey-orchestration-home.md)

## 2020 年 3 月 {#march-2020}

* テストログの節に、_actionExecutionErrors_ および _fetchErrors_ パラメーターの説明を追加しました。[詳細を表示](../building-journeys/testing-the-journey.md#viewing_logs)
* ジャーナルで使用されるカスタムアクションの制限事項を更新しました。「**URL**」フィールドと&#x200B;**認証**&#x200B;パラメーターも変更できます。[詳細を表示](../action/about-custom-action-configuration.md)
* 新しいコンテキストヘルプエントリを追加しました。カスタム認証ペイロードペイン（アクションおよびデータソース内）に、この[節](../datasource/external-data-sources.md#section_wjp_nl5_nhb)にリンクするヘルプアイコンが含まれるようになりました。
* 閉まった旅行は今や止められる。 [詳細を表示](../building-journeys/using-the-journey-designer.md)
* インターフェイスを説明する節を再編成しました。[詳細を表示](../about/user-interface.md)
* テストモードの節に複数のイベントのトリガーを追加しました。[詳細を表示](../building-journeys/testing-the-journey.md#firing_events)
* テストモードの節を、新しい **Wait time in test** パラメーターに関して更新しました。[詳細を表示](../building-journeys/testing-the-journey.md)
* テストログの節を更新し、外部呼び出しのエラーコードと応答を追加しました。[詳細を表示](../building-journeys/testing-the-journey.md#viewing_logs)
* タイムゾーン管理をジャーニープロパティパネルで一元化しました。詳しくは[こちら](../building-journeys/changing-properties.md#timezone)および[こちら](../building-journeys/timezone-management.md)を参照してください。
* ジャーニーデザイナーの節を更新して、最近の機能強化を反映しました。[詳細を表示](../building-journeys/using-the-journey-designer.md)
* インターフェイスの説明を、コンテキストヘルプに関する情報で更新しました。[詳細を表示](../about/user-interface.md#section_ksq_zr1_ffb)
* **XDM フィールド**&#x200B;を参照する際に、わかりやすい名前が表示されるようになりました。関連した節を更新しました。[詳細を表示](../about/user-interface.md#friendly-names-display)

## 2020 年 2 月 {#february-2020}

* ショートカットの節を更新しました。「**C**」キーボードショートカットを使用すると、すべてのリスト画面で新しいアイテムを作成できます。[詳細を表示](../about/user-interface.md#section_ksq_zr1_ffb)
* デ [ータソース](../datasource/about-data-sources.md) と [](../action/action.md) アクションの概要ページが改善されました。

## 2020 年 1 月{#january-2020}

* [エクスペリエンスのイベント](../datasource/adobe-experience-platform-data-source.md)と[セグメント](../functions/functioninsegment.md)に対する取得の制限を追加しました。
* [getBestSendTime ドキュメント](../functions/functiongetbestsendtime.md)を更新しました。

## 2019 年 12 月 {#december-2019}

* インターフェイスの変更を反映するために、すべてのスクリーンショットを更新しました。
* テストモードの節を更新しました。[詳細を表示](../building-journeys/testing-the-journey.md)
* 「[E メール送信時間の最適化](../building-journeys/wait-activity.md)」の節と「[予測疲労スコア](../ai-services/leveraging-fatigue-scores.md)」の節に警告を追加しました。これらの機能は、Adobe Campaign Standard データサービス機能を使用するお客様のみが利用できます。
* 停止済みジャーニーを削除できるようになりました。関連ドキュメントページを更新しました。
* ジャーニーで問題が検出された場合、エラーの場合は赤、警告の場合はオレンジの 2 色が表示されるようになりました。[詳細を表示](../about/troubleshooting.md)
* 詳細式エディターの節を更新しました。[詳細を表示](../expression/expressionadvanced.md)。
* 「[条件命令](../expression/conditional-instruction.md)」および「[コレクション管理](../expression/collection-management-functions.md)」の節を移動し、更新しました。
* 「[関数](../expression/functions.md)」の節に新しい例を追加しました。
* [toDateTime 関数](../functions/functiontodatetime.md)ドキュメントを更新し、タイムゾーンの構文の変更を反映しました。
