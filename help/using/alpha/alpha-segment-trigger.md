---
title: 「セグメントを読み取り」アクティビティ
description: セグメントの読み取りアクティビティの詳細を表示します。
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: tm+mt
source-git-commit: b852c08a488a1bec02b8b31a1fccf1a8773b99af
workflow-type: tm+mt
source-wordcount: '661'
ht-degree: 4%

---


# 「セグメントを読み取り」アクティビティ{#segment-trigger-activity}

## セグメントの読み取りアクティビティについて {#about-segment-trigger-actvitiy}

>[!NOTE]
>
>発行時またはテストモードのアクティベーション時に、標準搭載のアクションアクティビティAdobe Campaign Standardがキャンバスに存在する場合は、その移動は1秒あたり13回の参加で制限されます。 そうしないと、1秒あたり1000イベントに制限されます。

セグメントを読み取りアクティビティを使用すると、Adobe Experience Platformセグメントに属するすべての個人を旅行に参加させることができます。 ジャーニーへのエントリは、1 回きりでも定期的にでもおこなえます。

例えば、Adobe Experience Platformにゴールド顧客セグメントがあるとします。 セグメントを読み取りアクティビティを使用すると、ゴールド顧客セグメントに属するすべての個人を遍歴に加え、個々のジャーニーに流れ込ませて、すべての遍歴機能を活用できます。条件、タイマー、イベント、アクション。

## Configuring the activity {#configuring-segment-trigger-activity}

>[!NOTE]
>
>セグメントエクスポートの待ち時間が長いので、1時間より短い時間枠でセグメントベースの遍歴をトリガーすることはできません。

1. オーケストレーション **[!UICONTROL カテゴリを展開し、キャンバスに「セグメント]****[!UICONTROL 読み取り]** 」アクティビティをドロップします。

   このアクティビティは、旅の最初のステップとして位置づけられなければなりません。

1. アクティビティ追加の **[!UICONTROL ラベル]** （オプション）。

1. 「 **[!UICONTROL セグメント]** 」フィールドで、遍歴に入るAdobe Experience Platformセグメントを選択し、「 **[!UICONTROL 保存]**」をクリックします。

   >[!NOTE]
   >
   >リストに表示される列はカスタマイズして並べ替えることができます。

   ![](../assets/segment-trigger-segment-selection.png)

   セグメントが追加されると、「 **[!UICONTROL Copy]** 」ボタンを使用して、セグメントの名前とIDをコピーできます。

   `{"name":"Gold customers,”id":"8597c5dc-70e3-4b05-8fb9-7e938f5c07a3"}`

   ![](../assets/segment-trigger-copy.png)

1. 「 **[!UICONTROL 名前空間]** 」フィールドで、個人を識別するために使用する名前空間を選択します。 For more on namespaces, refer to [this section](../event/selecting-the-namespace.md).

   >[!NOTE]
   >
   >異なるIDの中から選択したID(名前空間)を持たないセグメントに属する個人は、この遍歴に参加できません。

1. セグメント **[!UICONTROL を読み取り]** アクティビティを使用すると、セグメントが旅行に参加する時間を指定できます。 これを行うには、「 **[!UICONTROL Edit jeurney schedule]** （ジャーニースケジュールを編集）」リンクをクリックしてジャーニーのプロパティにアクセスし、 **[!UICONTROL スケジューラータイプ]** フィールドを設定します。

   ![](../assets/segment-trigger-schedule.png)

   デフォルトでは、セグメントは可能な限り **[!UICONTROL 早く遍歴に入ります]**。つまり、旅行が公開されてから1時間後です。 特定の日時または定期的な日時にセグメントが旅行に参加するようにする場合は、リストから目的の値を選択します。

   >[!NOTE]
   >
   >「 **[!UICONTROL スケジュール]** 」セクションは、「セグメントを **[!UICONTROL 読み取り]** 」アクティビティがキャンバスにドロップされた場合にのみ使用できます。

   ![](../assets/segment-trigger-properties.png)

## 遍歴のテストと公開 {#testing-publishing}

セグメントを **[!UICONTROL 読み取り]** アクティビティを使用すると、一元プロファイル上で、またはセグメントに適格なプロファイルから選択した100個のランダムなプロファイルをテストできます。

これを行うには、テストモードをアクティブ化し、左側のペインから目的のオプションを選択します。

![](../assets/segment-trigger-test-modes.png)

その後、通常どおりテストモードを設定して実行できます。 遍歴をテストする方法の詳細な手順を [この節で説明します](../building-journeys/testing-the-journey.md)。

テストが実行されると、「 **[!UICONTROL Show logs]** 」ボタンを使用して、選択したテストオプションに従ってテスト結果を確認できます。

* **[!UICONTROL 一度に1つのプロファイル]**:テストログには、単一テストモードを使用した場合と同じ情報が表示されます。 詳しくは、[この節](../building-journeys/testing-the-journey.md#viewing_logs)を参照してください。

* **[!UICONTROL 一度に最大100プロファイル]**:テストログでは、Adobe Experience Platformからのセグメントエクスポートの進行状況と、その旅に出たすべての人の個々の進行状況を追跡できます。

   最大100個のプロファイルを一度に使用して遍歴をテストすると、視覚的なフローを使用した遍歴の中の個人の進行状況を追跡できないことに注意してください。

   ![](../assets/read-segment-log.png)

テストが成功したら、遍歴を公開できます( [Publishing the jeurney](../building-journeys/publishing-the-journey.md))。 セグメントに属する個人が、その旅行のプロパティ **[!UICONTROL スケジューラー]** セクションで指定された日時に旅行に参加します。

>[!NOTE]
>
>繰り返しのない（できるだけ早く開始する、または「1回」開始する）新しいバージョンのセグメントベースの遍歴を行う場合、以前にその旅に参加したすべての個人は、その新しいバージョンを公開時に再入力しません。 再入場を許可する場合は、重複を行う必要があります。
