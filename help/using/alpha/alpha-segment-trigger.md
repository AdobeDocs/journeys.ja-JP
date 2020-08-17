---
title: セグメントトリガーアクティビティ
description: セグメントトリガーの詳細
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
source-git-commit: 76c2f4c1f459bb7bb21101708340137ae5f89ae0
workflow-type: tm+mt
source-wordcount: '576'
ht-degree: 1%

---


# セグメントトリガーアクティビティ {#segment-trigger-activity}

## セグメントトリガーアクティビティについて {#about-segment-trigger-actvitiy}

>[!NOTE]
>
>発行時またはテストモードのアクティベーション時に、標準搭載のアクションアクティビティAdobe Campaign Standardがキャンバスに存在する場合は、その移動は1秒あたり13回の参加で制限されます。 <br>発行時またはテストモードのアクティベーション時に、キャンバスにあらかじめ用意されているAdobe Campaign Standardのアクションアクティビティがない場合は、1秒あたり1000イベントに制限されます。

セグメントトリガーアクティビティを使用すると、Adobe Experience Platformセグメントに属するすべての個人を旅行に参加させることができます。 旅行への参加は1回でも、定期的に行うことができます。

例えば、Adobe Experience Platformにゴールド顧客セグメントがあるとします。 セグメントトリガーアクティビティを使用すると、ゴールド顧客セグメントに属するすべての個人を遍歴に加え、それらを個別のジャーニーに流し込み、すべての遍歴機能を活用できます。条件、タイマー、イベント、アクション。

## Configuring the activity {#configuring-segment-trigger-activity}

>[!NOTE]
>
>セグメントエクスポートの待ち時間が長いので、1時間より短い時間枠でセグメントベースの遍歴をトリガーすることはできません。

1. オーケストレーション **[!UICONTROL カテゴリを展開し、キャンバスに]** セグメントトリガー **** アクティビティをドロップします。

   このアクティビティは、旅の最初のステップとして位置づけられなければなりません。

1. アクティビティ追加の **[!UICONTROL ラベル]** 。 この手順はオプションです。

1. アクティビティ **[!UICONTROL スケジューラータイプを設定します]**。

   デフォルトで、セグメントは可能な限り早く **[!UICONTROL 旅行に入ります]**。つまり、旅行が公開されてから1時間後です。 セグメントを特定の日時または定期的に旅行に参加させる場合は、リストから目的のオプションを選択します。

   定期的な旅行の場合は、開始と旅の終わりも定義できます。

   ![](../assets/segment-trigger-schedule.png)

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

1. Click **[!UICONTROL Ok]** to confirm. その後、利用可能なアクティビティを活用して旅を立てることができます。

1. ジャーニーの準備が整ったら、そのジャーニーをテストできる可能性があります( [「ジャーニーのテスト](../building-journeys/testing-the-journey.md)」を参照)。

   セグメントトリガー **** アクティビティから始まる遍歴でテストモードがアクティブになると、選択したセグメントに適格なプロファイルの中から100個のテストプロファイルがランダムに選択されます。 テストログを使用すると、その遍歴における個人のパスと、発生する可能性のあるエラーを確認できます(ログの [表示を参照](../building-journeys/testing-the-journey.md#viewing_logs))。

   >[!NOTE]
   >
   >ただし、単一のジャーニーに存在する視覚的な流れ機能を使用して、旅をたどった100人の人を見ることはできません。

1. その後、ジャーニーを公開できます(「ジャーニーの [公開](../building-journeys/publishing-the-journey.md)」を参照)。 セグメントに属する個人が、セグメントトリガーアクティビティスケジューラーで指定された日時に遍歴に入ります。

   >[!IMPORTANT]
   >
   >Adobe Experience Platformセグメントは、1日に1回(**バッチ** セグメント)またはリアルタイム(ストリー&#x200B;**ムセグメント** )で計算されます。
   >
   >選択したセグメントがストリーミングされる場合、このセグメントに属する個人がリアルタイムで遍歴に参加する可能性があります。 セグメントがバッチの場合、新たにこのセグメントに適格となった訪問者は、セグメントの計算がAdobe Experience Platformで実行されたときに、その旅行に入る可能性があります。
