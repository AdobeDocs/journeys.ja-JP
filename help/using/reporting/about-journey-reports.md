---
title: ジャーニーレポートについて
description: 遍歴レポートの作成方法を学ぶ
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
source-git-commit: b5b3c8b6adafaedbdd80db3091300e7a26249a3e
workflow-type: tm+mt
source-wordcount: '828'
ht-degree: 0%

---


# ジャーニーレポートについて {#concept_rfj_wpt_52b}

>[!NOTE]
>
>配信データとセグメントコンポーネントは、Adobe Campaign Standardがいる場合にのみ入力されます。

このセクションでは、レポートにアクセスして使用し、ジャーニーの効果を測定する方法について説明します。

## レポートインターフェイス {#reporting-interface}

上部のツールバーを使用すると、レポートの変更、保存、印刷などを行うことができます。

![](../assets/dynamic_report_toolbar.png)

「 **[!UICONTROL プロジェクト]** 」タブを使用して、次の操作を行います。

* **[!UICONTROL 開く]**: 以前に作成したレポートまたはテンプレートを開きます。
* **[!UICONTROL 名前を付けて保存]**: 重複テンプレートを変更できるようにします。
* **[!UICONTROL プロジェクトを更新]**: 新しいデータとフィルターの変更に基づいてレポートを更新します。
* **[!UICONTROL CSVのダウンロード]**: レポートをCSVファイルにエクスポートします。
* **[!UICONTROL 印刷]**: レポートが印刷されます。

「 **[!UICONTROL 編集]** 」タブでは、次の操作を行うことができます。

* **[!UICONTROL 元に戻す]**: ダッシュボードの最後の操作をキャンセルします。
* **[!UICONTROL やり直し]**: ダッシュボードでの最後の **[!UICONTROL 取り消し]** (Undo)操作をキャンセルします。
* **[!UICONTROL すべてをクリア]**: ダッシュボード上のすべてのパネルを削除します。

「 **[!UICONTROL 挿入]** 」(Insert)テーブルを使用すると、ダッシュボードにグラフと表を追加してレポートをカスタマイズできます。

* **[!UICONTROL 新しい空のパネル]**: ダッシュボードに新しい空白のパネルを追加します。
* **[!UICONTROL 新しいフリーフォーム]**: ダッシュボードに新しいフリーフォームテーブルを追加します。
* **[!UICONTROL 改行]**: ダッシュボードに新しい折れ線グラフを追加します。
* **[!UICONTROL 新しいバー]**: ダッシュボードに新しい棒グラフを追加します。

左側のタブを使用すると、レポートを作成し、必要に応じてデータをフィルターできます。

![](../assets/dynamic_report_interface.png)

これらのタブからは、次の項目にアクセスできます。

* **[!UICONTROL パネル]**: データをフィルターする開始に、レポートに空白のパネルまたはフリーフォームを追加します。 For more on this, refer to the [Adding panels](../reporting/creating-your-journey-reports.md#adding-panels) section
* **[!UICONTROL ビジュアライゼーション]**: 選択したビジュアライゼーション項目をドラッグ&amp;ドロップして、レポートにグラフィカルなディメンションを表示します。 For more on this, refer to the [Adding visualizations](../reporting/creating-your-journey-reports.md#adding-visualizations) section.
* **[!UICONTROL コンポーネント]**: 様々なディメンション、指標、セグメントおよび期間でレポートをカスタマイズできます。 For more on this, refer to the [Adding components](../reporting/creating-your-journey-reports.md#adding-components) section.

## ジャーニーサマリテンプレート {#ootb-template}

レポートは2つのカテゴリに分かれています。 標準のテンプレートおよびカスタムレポートです。
標準搭載のテンプレートである **[!UICONTROL 遍歴サマリ]**(Jurnery summary)には、最も重要なトラッキングデータの明確な表示が表示されます。

![](../assets/dynamic_report_journey_8.png)

各表は、数値の概要とグラフで表されます。 各ビジュアライゼーション設定での詳細の表示方法を変更できます。

レポートの上部で次のKPIを使用できます。

* **[!UICONTROL 遍歴 — 入口]**: 旅の入り口イベントに到達した人の総数。
* **[!UICONTROL 遍歴 — 完了率]**: 旅行の最後に到達した人の総数（条件に一致しない人の場合）と、旅に参加した人の合計数。
* **[!UICONTROL 遍歴 — 現在]**: 現在旅行中の人数の合計です。
* **[!UICONTROL ジャーニー — 失敗率]**: 正常に実行されなかったジャーニーの総数が、走るジャーニーの数と比較してわかります。
* **[!UICONTROL 配信 — 送信メッセージ]**: 送信されたメッセージの合計数。
* **[!UICONTROL 配信率]**: 送信されたメッセージと比較して、正常に配信されたメッセージの合計数です。
* **[!UICONTROL 配信 — 直帰率]**: 送信されたメッセージと比較してバウンスしたメッセージの合計数です。
* **[!UICONTROL 配信 — 登録解除率]**: 配信されたメッセージと比較した、受信者別の購読解除の合計数です。
* **[!UICONTROL 配信 — オープン率]**: 配信されたメッセージの数と比較した、開かれたメッセージの合計数。
* **[!UICONTROL 配信 — クリック率]**: 配信されたメッセージの数と比較した、配信内のクリック数の合計。

遍歴フロービジュアライゼーションを使用すると、ターゲットプロファイルのパスをステップバイステップで把握できます。 これは、1つの遍歴をターゲットにする場合にのみ使用できます。 この変数は自動的に生成され、変更できません。

![](../assets/dynamic_report_journey_10.png)

「 **[!UICONTROL 遍歴サマリ]** 」(Jurnery summary)テーブルには、以下のようなデータが含まれています。

* **[!UICONTROL 入力]**: 旅の入り口イベントに到達した人の総数。
* **[!UICONTROL 完了率]**: 移動の終了フロー制御に到達した人の合計数です。この人の合計数は、移動に参加した人の合計数と比較されます。
* **[!UICONTROL 現在]**: 現在旅行中の人数の合計です。
* **[!UICONTROL 失敗]**: 正常に実行されなかったジャーニーの合計数です。
* **[!UICONTROL 失敗率]**: 正常に実行されなかったジャーニーの総数が、走るジャーニーの数と比較してわかります。

「 **[!UICONTROL トップイベント]** 」( **[!UICONTROL Top Actions]**)テーブルには、最も成功したイベントと、最も成功したアクションであるジャーニー内で最も成功したアクションが表示されます。

![](../assets/dynamic_report_journey_11.png)

「 **[!UICONTROL 配信 — サマリの送信]** 」表には、次のような遍歴の配信に使用できるデータが含まれています。

* **[!UICONTROL 処理済み/送信済み]**: 送信されたメッセージの合計数。
* **[!UICONTROL 配信率]**: 送信されたメッセージと比較して、正常に配信されたメッセージの合計数です。
* **[!UICONTROL 配信済み]**: 正常に送信されたメッセージの数（送信されたメッセージの合計数に関連）。
* **[!UICONTROL バウンス+エラー率]**: 送信されたメッセージと比較してバウンスしたメッセージの合計数です。
* **[!UICONTROL バウンス+エラー]**: 配信および自動返信処理中に発生したエラーの合計（送信されたメッセージの合計数に関連）。

**[!UICONTROL 配信 — トラッキングの概要]** （表）には、次のようなジャーニーの配信の成功を追跡するために使用できるデータが含まれています。

* **[!UICONTROL オープン率]**: 開いているメッセージの割合。
* **[!UICONTROL 開く]**: 配信でメッセージが開かれた回数。
* **[!UICONTROL クリックトラフ率]**: 配信されたメッセージの数と比較した、配信内のクリック数の合計。
* **[!UICONTROL クリック]**: 配信内でコンテンツがクリックされた回数。
* **[!UICONTROL 登録解除率]**: 配信されたメッセージと比較した、受信者別の購読解除の割合。
* **[!UICONTROL 登録解除]**: 配信されたメッセージと比較した、受信者別の購読解除の合計数です。
