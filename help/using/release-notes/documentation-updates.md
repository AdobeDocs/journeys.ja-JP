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
source-git-commit: 10d4fd57e9a801dab2310b2b511bf99cf1d9170a
workflow-type: tm+mt
source-wordcount: '735'
ht-degree: 85%

---


# ドキュメントの更新

このページでは、[!DNL Journey Orchestration] のドキュメントの更新をすべてリストします。
[!DNL Journey Orchestration] [リリースノート](../release-notes/release-notes.md)も参照してください。

## 2020 年 8 月 {#august-2020}

* セグメントリストで表示する列の並べ替えおよび選択方法に関する情報を追加しました。 [詳細を表示](../building-journeys/segment-qualification-events.md)
* セグメントの名前とIDを選択した後にコピーする方法に関する情報を追加しました。 [詳細を表示](../building-journeys/segment-qualification-events.md)
* 様々なページ間でExperience Platformの発生が調和されています。

## 2020 年 7 月 {#july-2020}

* Adobe Experience Platformへのステップイベントレポートに関する新しいチュートリアルビデオへのリンクを追加しました。 [詳細を表示](../building-journeys/sharing-overview.md)
* 「イベントアクティビティ」セクションは、イベントのタイプごとに専用のサブセクションに再編成されました。 [詳細を表示](../building-journeys/event-activities.md)
* セグメントの品質が過負荷になるのを回避するためのベストプラクティスを追加しました。 [詳細を表示](../building-journeys/segment-qualification-events.md#speed-segment-qualification)
* アクションまたは条件のエラーの後、ジャーニーを続行させる方法を説明する注記を追加しました。 [詳細を表示](../about/troubleshooting.md#section_h3q_kqk_fhb)
* 一部のユーザーに対してテストを実施するアルファ機能に関する新しい節を追加しました。[詳細を表示](../alpha/alpha-overview.md)
* インテリジェントサービスとの統合に関する新しい節を追加しました。[詳細を表示](../ai-services/ai-services-overview.md)
* テストプロファイルの作成に関する新しい節を追加しました。[詳細を表示](../building-journeys/testing-the-journey.md#create-test-profile)
* ジャーニー条件またはアクションでの **[!UICONTROL SegmentQualification]** ノードの使用方法に関する情報を追加しました。[詳細を表示](../building-journeys/segment-qualification-events.md)
* Campaign のトランザクションメッセージとイベントのパブリケーションにメモを追加しました。[Adobe Campaign の使用](../action/working-with-adobe-campaign.md)および [Adobe Campaign のアクションの使用](../building-journeys/using-adobe-campaign-actions.md)を参照してください。
* Campaign Standard インスタンス URL のテスト時に実行されるチェックに関する情報を追加しました。[詳細を表示](../action/working-with-adobe-campaign.md)
* AWS または Azure サーバーでホストされる Campaign Standard インスタンスと反応イベントの互換性に関する情報を追加しました。[詳細を表示](../building-journeys/reaction-events.md)
* Campaign Standard トランザクションメッセージングを使用する際にキャッピングルールを設定する必要性についてメモを追加しました。[詳細を表示](../action/working-with-adobe-campaign.md)
* テストモードを使用してイベントをトリガーする際の実イベントの生成に関するメモを追加しました。[詳細を表示](../building-journeys/testing-the-journey.md#firing_events)

## 2020 年 6 月{#june-2020}

* カスタム認証データソース用のトークンのキャッシュ期間を変更する方法に関する情報を追加しました。[詳細を表示](../datasource/external-data-sources.md#section_wjp_nl5_nhb)
* スクリーンショットとテキストを更新し、**[!UICONTROL 完了した]**&#x200B;ジャーニーの名前が「**[!UICONTROL クローズ済み (新規エントリなし)]**」に変更されたことを反映しました。
* インターフェイスの言語の定義方法に関する情報を追加しました。[詳細を表示](../about/user-interface.md)
* 個人のジャーニーステータスのリストは、[テストモードログ](../building-journeys/testing-the-journey.md#viewing_logs)の節に移動されました。

## 2020 年 4 月 {#april-2020}

* 初回イベントを設定できるように、エクスペリエンスイベントスキーマの定義に関する新しい節を追加しました。[詳細を表示](../event/experience-event-schema.md)
* [!DNL Journey Orchestration] ドキュメントのホームページを更新し、役立つリンクをさらに追加しました。[詳細を表示](../../journey-orchestration-home.md)

## 2020 年 3 月 {#march-2020}

* テストログの節に、_actionExecutionErrors_ および _fetchErrors_ パラメーターの説明を追加しました。[詳細を表示](../building-journeys/testing-the-journey.md#viewing_logs)
* ジャーナルで使用されるカスタムアクションの制限事項を更新しました。「**[!UICONTROL URL]**」フィールドと&#x200B;**[!UICONTROL 認証]**&#x200B;パラメーターも変更できます。[詳細を表示](../action/about-custom-action-configuration.md)
* 新しいコンテキストヘルプエントリを追加しました。カスタム認証ペイロードペイン（アクションおよびデータソース内）に、この[節](../datasource/external-data-sources.md#section_wjp_nl5_nhb)にリンクするヘルプアイコンが含まれるようになりました。
* クローズ済みジャーニーを停止できるようになりました。[詳細を表示](../building-journeys/using-the-journey-designer.md)
* インターフェイスを説明する節を再編成しました。[詳細を表示](../about/user-interface.md)
* テストモードの節に複数のイベントのトリガーを追加しました。[詳細を表示](../building-journeys/testing-the-journey.md#firing_events)
* テストモードの節を、新しい **[!UICONTROL Wait time in test]** パラメーターに関して更新しました。[詳細を表示](../building-journeys/testing-the-journey.md)
* テストログの節を更新し、外部呼び出しのエラーコードと応答を追加しました。[詳細を表示](../building-journeys/testing-the-journey.md#viewing_logs)
* タイムゾーン管理をジャーニープロパティパネルで一元化しました。詳しくは[こちら](../building-journeys/changing-properties.md#timezone)および[こちら](../building-journeys/timezone-management.md)を参照してください。
* ジャーニーデザイナーの節を更新して、最近の機能強化を反映しました。[詳細を表示](../building-journeys/using-the-journey-designer.md)
* インターフェイスの説明を、コンテキストヘルプに関する情報で更新しました。[詳細を表示](../about/user-interface.md#section_ksq_zr1_ffb)
* **XDM フィールド**&#x200B;を参照する際に、わかりやすい名前が表示されるようになりました。関連した節を更新しました。[詳細を表示](../about/user-interface.md#friendly-names-display)

## 2020 年 2 月 {#february-2020}

* ショートカットの節を更新しました。「**C**」キーボードショートカットを使用すると、すべてのリスト画面で新しいアイテムを作成できます。[詳細を表示](../about/user-interface.md#section_ksq_zr1_ffb)
* [データソース](../datasource/about-data-sources.md)と[アクション](../action/action.md)の概要ページを改善しました。

## 2020 年 1 月{#january-2020}

* [エクスペリエンスのイベント](../datasource/adobe-experience-platform-data-source.md)と[セグメント](../functions/functioninsegment.md)に対する取得の制限を追加しました。

<!--* The [getBestSendTime documentation](../functions/functiongetbestsendtime.md) has been updated.-->

## 2019 年 12 月 {#december-2019}

* インターフェイスの変更を反映するために、すべてのスクリーンショットを更新しました。
* テストモードの節を更新しました。[詳細を表示](../building-journeys/testing-the-journey.md)
<!--* A warning has been added in the [email send time optimization](../building-journeys/wait-activity.md) and [predictive fatigue scores](../ai-services/leveraging-fatigue-scores.md) sections. These capabilities are only available to customers who use the [Adobe Experience Platform Data Connector](https://docs.adobe.com/content/help/en/campaign-standard/using/developing/mapping-campaign-and-aep-data/aep-about-data-connector.html).-->
* 停止済みジャーニーを削除できるようになりました。関連ドキュメントページを更新しました。
* ジャーニーで問題が検出された場合、エラーの場合は赤、警告の場合はオレンジの 2 色が表示されるようになりました。[詳細を表示](../about/troubleshooting.md)
* 詳細式エディターの節を更新しました。[詳細を表示](../expression/expressionadvanced.md)。
* 「[条件命令](../expression/conditional-instruction.md)」および「[コレクション管理](../expression/collection-management-functions.md)」の節を移動し、更新しました。
* 「[関数](../expression/functions.md)」の節に新しい例を追加しました。
* [toDateTime 関数](../functions/functiontodatetime.md)ドキュメントを更新し、タイムゾーンの構文の変更を反映しました。
