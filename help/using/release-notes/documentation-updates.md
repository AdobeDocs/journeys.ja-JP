---
title: ドキュメントの更新
description: ドキュメントの更新について
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
source-git-commit: 0bf8ce5974b7be684a156d5c5445dca122213237
workflow-type: tm+mt
source-wordcount: '383'
ht-degree: 8%

---


# ドキュメントの更新

このページでは、Journey Orchestrationに関するドキュメントのすべての更新をリストします。
また、Journey Orchestration [リリースノートを参照することもできます](../release-notes/release-notes.md)。

## 2020 年 3 月 {#march-2020}

* テストログの節に、 _actionExecutionErrors_ と _fetchErrors_ のパラメーターの説明を追加しました。 [詳細を表示](../building-journeys/testing-the-journey.md#viewing_logs)
* 遍歴で使用されるカスタムアクションの制限事項が更新されました。 「 **URL** 」フィールドと「 **認証** 」パラメーターも変更できます。 [詳細を表示](../action/about-custom-action-configuration.md)
* 新しいコンテキストヘルプエントリが追加されました。 （アクションおよびデータソース内の）カスタム認証ペイロードペインに、この [セクションにリンクするヘルプアイコンが含まれるようになりました](../datasource/external-data-sources.md#section_wjp_nl5_nhb)。
* 終わったジャーニーは今や止められる。 [詳細を表示](../building-journeys/using-the-journey-designer.md)
* インターフェイスの説明セクションが再編成されました。 [詳細を表示](../about/user-interface.md)
* 複数のイベントのトリガがテストモードの節に追加されました。 [詳細情報](../building-journeys/testing-the-journey.md#firing_events)
* テストモードの節が、testパラメーターの新しい **待ち時間に関して更新されました** 。 [詳細を表示](../building-journeys/testing-the-journey.md)
* 「テストログ」セクションが更新され、外部呼び出しのエラーコードと応答が追加されました。 [詳細を表示](../building-journeys/testing-the-journey.md#viewing_logs)
* タイムゾーン管理は、ジャーニープロパティパネルで一元化されました。 詳し [くは](../building-journeys/changing-properties.md#timezone) 、こちらを [参照](../building-journeys/timezone-management.md)
* 「遍歴デザイナー」セクションが更新され、最近の機能強化が反映されました。 [詳細を表示](../building-journeys/using-the-journey-designer.md)
* インターフェイスの説明は、コンテキストヘルプに関する情報で更新されました。 [詳細を表示](../about/user-interface.md#section_ksq_zr1_ffb)
* XDMフィールドを参照する際に ****、わかりやすい名前が表示されるようになりました。 関連セクションが更新されました。 [詳細を表示](../about/user-interface.md#friendly-names-display)


## 2020 年 2 月 {#february-2020}

* ショートカットセクションが更新されました。 「 **C** 」キーボードショートカットを使用すると、すべてのリスト画面で新しいアイテムを作成できます。 [詳細を表示](../about/user-interface.md#section_ksq_zr1_ffb)

## 2020 年 1 月{#january-2020}

* エクスペリ [エンスのイベント](../datasource/adobe-experience-platform-data-source.md) と [セグメントに、取得の制限が追加されました](../functions/functioninsegment.md)。
* The [getBestSendTime documentation](../functions/functiongetbestsendtime.md) has been updated.

## 2019 年 12 月 {#december-2019}

* すべてのスクリーンショットが更新され、インターフェイスの変更が反映されました。
* テストモードのセクションが更新されました。 [詳細を表示](../building-journeys/testing-the-journey.md)
* 電子 [メール送信時間の最適化](../building-journeys/wait-activity.md) 、および [予測疲労スコアのセクションに警告が追加されました](../usecase/leveraging-fatigue-scores.md) 。 これらの機能は、Adobe Campaign標準データサービス機能を使用するお客様のみが利用できます。
* 停止したジャーニーを削除できるようになりました。 関連ドキュメントページが更新されました。
* 遍歴で問題が検出された場合、2色が表示されるようになりました。 エラーの場合は赤、警告の場合はオレンジです。 [詳細を表示](../about/troubleshooting.md)
* アドバンス式エディタセクションが更新されました。 [詳細を表示](../expression/expressionadvanced.md)。
* [条件付き命令](../expression/conditional-instruction.md) 、 [](../expression/collection-management-functions.md) コレクション管理の各セクションが移動および更新されました。
* 「 [関数](../expression/functions.md) 」の節では、新しい例を追加しました。
* toDateTime関数 [のドキュメントが更新され](../functions/functiontodatetime.md) 、タイムゾーンの構文の変更が反映されました。
