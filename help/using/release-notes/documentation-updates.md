---
product: adobe campaign
title: ドキュメントの更新
description: ドキュメントの更新について説明します
feature: Journeys
role: User
level: Beginner
hide: true
hidefromtoc: true
exl-id: ac5d2cec-0b48-4863-afe3-19ac5f61c9fd
source-git-commit: 4f6c5f9326b4d1cc4a1a02a036b51e4ad1ae68c4
workflow-type: ht
source-wordcount: '1003'
ht-degree: 100%

---

# ドキュメントの更新

このページでは、[!DNL Journey Orchestration] のドキュメントの更新点がすべてリストアップされています。
[!DNL Journey Orchestration] [リリースノート](../release-notes/release-notes.md)も参照してください。

## 2022年7月 {#july-2022}

* ジャーニーのプロパティの「**プロファイルのタイムゾーン**」オプションが、デフォルトで無効になりました。 [詳細情報](../building-journeys/timezone-management.md#timezone-from-profiles)
* **待機**&#x200B;アクティビティで、「**固定日付**」オプションは使用できなくなりました。 [詳細情報](../building-journeys/wait-activity.md)

## 2022年6月 {#june-2022}

* この[ページ](../building-journeys/query-examples.md)に新しいクエリの例が追加されました

## 2022年3月 {#march-2022}

* 式エディターで式をデフォルト値として追加する方法の例を追加しました。[詳細情報](../expression/field-references.md#default-value)

## 2022年2月 {#feb-2022}

* この [replace](../functions/functionreplace.md#example_2) および [replaceAll](../functions/functionreplaceall.md#example) 関数のドキュメントページを更新し、ターゲットパラメーターに関する追加情報と例を追加しました。
* [演算子](../expression/operators.md#important-notes)ページにベストプラクティスが追加されました。

## 2021年9月

* [sethours](../functions/functionsethours.md)、[getListItem](../functions/functiongetlistitem.md)、[inSegment](../functions/functioninsegment.md) の各関数のページが更新されました。

* [filter](../functions/functionfilter.md)、[intersect](../functions/functionintersect.md)、[toDateOnly](../functions/functiontodateonly.md) の各関数が追加されました。

* dateOnly 日付タイプが式エディターのドキュメントに追加されました。[詳細情報](../expression/data-types.md)

* カスタムアクションのキャッシュ時間の詳細を追加しました。[詳細情報](../datasource/external-data-sources.md#section_wjp_nl5_nhb)

* カスタムアクションのデフォルトポートに関する情報を追加しました。[詳細情報](../action/url-configuration.md)

* データレイクのジャーニーステップイベントをクエリする一般的な例を追加しました。[詳細情報](../building-journeys/query-examples.md)

## 2021 年 8 月

* カスタムアクションの設定手順に動的 URL パスと動的ヘッダーを反映しました。[詳細情報](../action/url-configuration.md)
* アクセシビリティ機能に関する節を追加しました。[詳細情報](../about/user-interface.md#accessibility)
* セグメント評価方法に関する節を追加しました。[詳細情報](../segment/about-segments.md#evaluation-method-in-journey-orchestration)

## 2021 年 3 月 {#march-2021}

* Adobe Experience Platformでテストプロファイルを作成するための完全な手順を詳しく説明しました。 [詳細を読む](../building-journeys/creating-test-profiles.md)。

## 2021 年 1 月 {#january-2021}

* プロファイルの作成と同時にジャーニーをトリガーする際のベストプラクティスを追加しました。[詳細を読む](../about/limitations.md#journeys-limitation-profile-creation)。

## 2020 年 10 月 {#october-2020}

* イベントのタイムアウトの設定方法に関する情報が追加されました。[詳細を読む](../building-journeys/event-activities.md#listening-to-events-during-a-specific-time)。

## 2020 年 9 月 {#september-2020}

* インターフェイスの説明の節が更新され、新しい「**すべてのセレクター**」メニューが反映されました。[詳細を読む](../about/user-interface.md)
* セグメントベースのジャーニーの新しいバージョンのうち、反復されないものに関するメモを追加しました。

## 2020 年 8 月 {#august-2020}

* セグメントリストで表示する列の並べ替えおよび選択方法に関する情報を追加しました。[詳細を読む](../building-journeys/segment-qualification-events.md)
* セグメントの名前と ID を選択した後にコピーする方法に関する情報を追加しました。[詳細を読む](../building-journeys/segment-qualification-events.md)
* Experience Platform の発生回数は、様々なページ間で調整されています。

## 2020 年 7 月 {#july-2020}

* 「イベントアクティビティ」セクションは、イベントのタイプごとに専用のサブセクションに再編成されました。[詳細を読む](../building-journeys/event-activities.md)
* セグメントの選定が過負荷になるのを回避するため、ベストプラクティスを追加しました。[詳細を読む](../building-journeys/segment-qualification-events.md#speed-segment-qualification)
* アクションエラーまたは条件エラーの後、ジャーニーを続行させる方法を説明する注記を追加しました。[詳細を読む](../about/troubleshooting.md#section_h3q_kqk_fhb)
* 一部の顧客によるテストの対象となるアルファ機能に関する新しい節を追加しました。
* インテリジェントサービスとの統合に関する新しい節を追加しました。[詳細を読む](../ai-services/ai-services-overview.md)
* テストプロファイルの作成に関する新しい節を追加しました。[詳細を読む](../building-journeys/testing-the-journey.md)
* ジャーニー条件またはアクションでの **[!UICONTROL SegmentQualification]** ノードの使用方法に関する情報を追加しました。[詳細を読む](../building-journeys/segment-qualification-events.md)
* Campaign のトランザクションメッセージとイベントのパブリケーションにメモを追加しました。[Adobe Campaign の使用](../action/working-with-adobe-campaign.md)および [Adobe Campaign のアクションの使用](../building-journeys/using-adobe-campaign-actions.md)を参照してください。
* Campaign Standard インスタンス URL のテスト時に実行されるチェックに関する情報を追加しました。[詳細を読む](../action/working-with-adobe-campaign.md)
* AWS または Azure サーバーでホストされる Campaign Standard インスタンスと反応イベントの互換性に関する情報を追加しました。[詳細を読む](../building-journeys/reaction-events.md)
* Campaign Standard トランザクションメッセージングを使用する際にキャッピングルールを設定する必要性についてメモを追加しました。[詳細を読む](../action/working-with-adobe-campaign.md)
* テストモードを使用してイベントをトリガーする際の実イベントの生成に関するメモを追加しました。[詳細を読む](../building-journeys/testing-the-journey.md#firing_events)

## 2020 年 6 月 {#june-2020}

* カスタム認証データソース用のトークンのキャッシュ時間を変更する方法に関する情報を追加しました。[詳細を読む](../datasource/external-data-sources.md#section_wjp_nl5_nhb)
* スクリーンショットとテキストを更新し、**[!UICONTROL 完了した]**&#x200B;ジャーニーの名前が「**[!UICONTROL クローズ済み (新規エントリなし)]**」に変更されたことを反映しました。
* インターフェイスの言語の定義方法に関する情報を追加しました。[詳細を読む](../about/user-interface.md)
* 個人のジャーニーステータスのリストは、[テストモードログ](../building-journeys/testing-the-journey.md#viewing_logs)の節に移動されました。

## 2020 年 4 月 {#april-2020}

* 初回イベントを設定できるように、エクスペリエンスイベントスキーマの定義に関する新しい節を追加しました。[詳細を読む](../event/experience-event-schema.md)
* [!DNL Journey Orchestration]ドキュメントのホームページを更新し、便利なリンクをさらに追加しました。[詳細を読む](../../journey-orchestration-home.md)

## 2020 年 3 月 {#march-2020}

* テストログの節に、_actionExecutionErrors_ および _fetchErrors_ パラメーターの説明を追加しました。[詳細を読む](../building-journeys/testing-the-journey.md#viewing_logs)
* ジャーニーで使用されるカスタムアクションの制限事項を更新しました。「**[!UICONTROL URL]**」フィールドと&#x200B;**[!UICONTROL 認証]**&#x200B;パラメーターも変更できます。[詳細を読む](../action/about-custom-action-configuration.md)
* 新しいコンテキストヘルプエントリを追加しました。カスタム認証ペイロードペイン（アクションおよびデータソース内）に、この[節](../datasource/external-data-sources.md#section_wjp_nl5_nhb)にリンクするヘルプアイコンが含まれるようになりました。
* クローズ済みジャーニーを停止できるようになりました。[詳細を読む](../building-journeys/using-the-journey-designer.md)
* インターフェイスを説明する節を再編成しました。[詳細を読む](../about/user-interface.md)
* テストモードの節に複数のイベントのトリガーを追加しました。[詳細を表示](../building-journeys/testing-the-journey.md#firing_events)
* テストモードの節を、新しい **[!UICONTROL Wait time in test]** パラメーターに関して更新しました。[詳細を読む](../building-journeys/testing-the-journey.md)
* テストログの節を更新し、外部呼び出しのエラーコードと応答を追加しました。[詳細を読む](../building-journeys/testing-the-journey.md#viewing_logs)
* タイムゾーン管理をジャーニープロパティパネルで一元化しました。詳しくは[こちら](../building-journeys/changing-properties.md#timezone)および[こちら](../building-journeys/timezone-management.md)を参照してください。
* ジャーニーデザイナーの節を更新して、最近の機能強化を反映しました。[詳細を読む](../building-journeys/using-the-journey-designer.md)
* インターフェイスの説明を、コンテキストヘルプに関する情報で更新しました。[詳細を読む](../about/user-interface.md#section_ksq_zr1_ffb)
* **XDM フィールド**&#x200B;を参照する際に、わかりやすい名前が表示されるようになりました。関連した節を更新しました。[詳細を読む](../about/user-interface.md#friendly-names-display)

## 2020 年 2 月 {#february-2020}

* ショートカットのセクションを更新しました。「**C**」キーボードショートカットを使用すると、すべてのリスト画面で新しいアイテムを作成できます。[詳細を読む](../about/user-interface.md#section_ksq_zr1_ffb)
* [データソース](../datasource/about-data-sources.md)と[アクション](../action/action.md)の概要ページを改善しました。

## 2020 年 1 月 {#january-2020}

* [エクスペリエンスのイベント](../datasource/adobe-experience-platform-data-source.md)と[セグメント](../functions/functioninsegment.md)に対する取得の制限を追加しました。
  <!--* The [getBestSendTime documentation](../functions/functiongetbestsendtime.md) has been updated.-->

## 2019 年 12 月 {#december-2019}

* インターフェイスの変更を反映するために、すべてのスクリーンショットを更新しました。
* テストモードの節を更新しました。[詳細を読む](../building-journeys/testing-the-journey.md)
  <!--* A warning has been added in the [email send time optimization](../building-journeys/wait-activity.md) and [predictive fatigue scores](../ai-services/leveraging-fatigue-scores.md) sections. These capabilities are only available to customers who use the [Adobe Experience Platform Data Connector](https://experienceleague.adobe.com/docs/campaign-standard/using/integrating-with-adobe-cloud/adobe-experience-platform/data-connector/aep-about-data-connector.html).-->
* 停止済みジャーニーを削除できるようになりました。関連ドキュメントページを更新しました。
* ジャーニーで問題が検出された場合、エラーの場合は赤、警告の場合はオレンジの 2 色が表示されるようになりました。[詳細を読む](../about/troubleshooting.md)
* 高度な式エディターの節を更新しました。[詳細を読む](../expression/expressionadvanced.md)。
* 「[条件命令](../expression/conditional-instruction.md)」および「[コレクション管理](../expression/collection-management-functions.md)」の節を移動し、更新しました。
* 「[関数](../expression/functions.md)」の節に新しい例を追加しました。
* [toDateTime 関数](../functions/functiontodatetime.md)ドキュメントを更新し、タイムゾーンの構文の変更を反映しました。
