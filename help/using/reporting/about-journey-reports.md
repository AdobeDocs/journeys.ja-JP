---
title: ジャーニーレポートについて
description: 旅行レポートの作成方法を説明します。
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

---


# ジャーニーレポートについて {#concept_rfj_wpt_52b}

>[!NOTE]
>
>配信データおよびセグメントコンポーネントは、Adobe Campaign Standardを使用している場合にのみ入力されます。

ここでは、レポートにアクセスして、ジャーニーの効果を測定する方法について説明します。

## レポートインターフェイス {#reporting-interface}

上部のツールバーを使用すると、例えば、レポートを変更、保存、印刷できます。

![](../assets/dynamic_report_toolbar.png)

タブを使用して、次 **[!UICONTROL Project]**の操作を行います。

* **[!UICONTROL Open]**:以前に作成したレポートまたはテンプレートを開きます。
* **[!UICONTROL Save As]**:テンプレートを複製して、変更できるようにします。
* **[!UICONTROL Refresh project]**:新しいデータとフィルターの変更に基づいてレポートを更新します。
* **[!UICONTROL Download CSV]**:レポートをCSVファイルにエクスポートします。
* **[!UICONTROL Print]**:レポートが印刷されます。

このタブ **[!UICONTROL Edit]**では、次の操作を行うことができます。

* **[!UICONTROL Undo]**:ダッシュボードでの最後の操作をキャンセルします。
* **[!UICONTROL Redo]**:ダッシュボードでの最後**[!UICONTROL Undo]** の操作をキャンセルします。
* **[!UICONTROL Clear all]**:ダッシュボードのすべてのパネルを削除します。

この表 **[!UICONTROL Insert]**では、ダッシュボードにグラフと表を追加して、レポートをカスタマイズできます。

* **[!UICONTROL New Blank Panel]**:ダッシュボードに新しい空のパネルを追加します。
* **[!UICONTROL New Freeform]**:新しいフリーフォームテーブルをダッシュボードに追加します。
* **[!UICONTROL New Line]**:ダッシュボードに新しい折れ線グラフを追加します。
* **[!UICONTROL New Bar]**:ダッシュボードに新しい棒グラフを追加します。

左のタブを使用すると、レポートを作成し、必要に応じてデータをフィルタリングできます。

![](../assets/dynamic_report_interface.png)

これらのタブを使用すると、次の項目にアクセスできます。

* **[!UICONTROL Panels]**:空白のパネルまたはフリーフォームをレポートに追加して、データのフィルタリングを開始します。 For more on this, refer to the[Adding panels](../reporting/creating-your-journey-reports.md#adding-panels)section
* **[!UICONTROL Visualizations]**:選択したビジュアライゼーション項目をドラッグ&amp;ドロップして、レポートにグラフィカルなディメンションを設定します。 For more on this, refer to the[Adding visualizations](../reporting/creating-your-journey-reports.md#adding-visualizations)section.
* **[!UICONTROL Components]**:様々なディメンション、指標、セグメントおよび期間を使用してレポートをカスタマイズします。 For more on this, refer to the[Adding components](../reporting/creating-your-journey-reports.md#adding-components)section.

## ジャーニーサマリテンプレート {#ootb-template}

レポートは2つのカテゴリに分かれています。標準のテンプレートとカスタムレポート。
標準搭載のテンプレートを使用すると、最も重要 **[!UICONTROL Journey summary]**なトラッキングデータを明確に表示できます。

![](../assets/dynamic_report_journey_8.png)

各表は、概要番号とグラフで表されます。 各ビジュアライゼーション設定での詳細の表示方法を変更できます。

レポートの上部では、次のKPIを使用できます。

* **[!UICONTROL Journey - Entered]**:旅の参加イベントに到達した人の総数。
* **[!UICONTROL Journey - Completion rate]**:旅の終わりに到達した人の総数（条件に合わない人の場合）と、旅に出た人の総数。
* **[!UICONTROL Journey - Current]**:現在旅行中の個人数の合計。
* **[!UICONTROL Journey - Failed rate]**:正常に実行されなかったジャーニーの合計数（走行ジャーニーの数と比較）。
* **[!UICONTROL Delivery - Messages sent]**:送信されたメッセージの合計数。
* **[!UICONTROL Delivery rate]**:送信されたメッセージと比較して正常に配信されたメッセージの合計数です。
* **[!UICONTROL Delivery - Bounce rate]**:送信されたメッセージと比較してバウンスしたメッセージの合計数です。
* **[!UICONTROL Delivery - Unsubscribed rate]**:配信されたメッセージと比較した、受信者による未購読の合計数です。
* **[!UICONTROL Delivery - Open rate]**:配信されたメッセージの数と比較した、開かれたメッセージの合計数。
* **[!UICONTROL Delivery - Click rate]**:配信されたメッセージの数と比較した、配信のクリック数の合計です。

ジャーニーフロービジュアライゼーションを使用すると、目的のプロファイルのパスを、旅程を1つずつ確認できます。 これは、1つの遍歴をターゲットにする場合にのみ使用できます。 自動的に生成され、変更できません。

![](../assets/dynamic_report_journey_10.png)

表に **[!UICONTROL Journey summary]**は、次のようなデータが含まれます。

* **[!UICONTROL Entered]**:旅の参加イベントに到達した人の総数。
* **[!UICONTROL Completion rate]**:旅の終了フロー制御に到達した人の総数と、旅に出た人の総数とを比較した値。
* **[!UICONTROL Current]**:現在旅行中の個人数の合計。
* **[!UICONTROL Failed]**:正常に実行されなかったジャーニーの合計数です。
* **[!UICONTROL Failed rate]**:正常に実行されなかったジャーニーの合計数（走行ジャーニーの数と比較）。

表に **[!UICONTROL Top events]**は、最も成功したイベントと、最も成功し**[!UICONTROL Top action]**&#x200B;たアクションがジャーニー内に表示されます。

![](../assets/dynamic_report_journey_11.png)

表に **[!UICONTROL Delivery - Sending summary]**は、次のような遍歴の配信に使用できるデータが含まれます。

* **[!UICONTROL Processed/sent]**:送信されたメッセージの合計数。
* **[!UICONTROL Delivered rate]**:送信されたメッセージと比較して正常に配信されたメッセージの合計数です。
* **[!UICONTROL Delivered]**:送信されたメッセージの合計数に関連して正常に送信されたメッセージの数。
* **[!UICONTROL Bounce + error rate]**:送信されたメッセージと比較してバウンスしたメッセージの合計数です。
* **[!UICONTROL Bounces + errors]**:送信されたメッセージの合計数に関して、配信および自動返信処理中に累積されたエラーの合計。

この表 **[!UICONTROL Delivery - Tracking summary]**には、次のようなジャーニー配信の成功を追跡するために使用できるデータが含まれています。

* **[!UICONTROL Open Rate]**:開封済みメッセージの割合。
* **[!UICONTROL Open]**:配信でメッセージが開かれた回数。
* **[!UICONTROL Click trough rate]**:配信されたメッセージの数と比較した、配信のクリック数の合計です。
* **[!UICONTROL Click]**:配信でコンテンツがクリックされた回数。
* **[!UICONTROL Unsubscribe rate]**:配信されたメッセージと比較した、受信者による購読解除の割合。
* **[!UICONTROL Unsubscribed]**:配信されたメッセージと比較した、受信者による未購読の合計数です。
