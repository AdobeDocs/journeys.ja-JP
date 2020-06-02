---
title: セグメントの使用
description: セグメントの使用方法
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
source-git-commit: b238c1851ae640b3146b8457931e1c416387c76a
workflow-type: tm+mt
source-wordcount: '146'
ht-degree: 0%

---



# 条件でのセグメントの使用 {#using-a-segment}

>「セグメント」タブとJourney Orchestrationでのセグメントの作成/変更は、6月15日に利用可能になります。

ここでは、セグメントを遍歴条件で使用する方法について説明します。
セグメント認定 **イベントの遍歴での使用方法については、「** イベントのアクティビティ [」を参照してください](../building-journeys/event-activities.md#segment-qualification)。

セグメントを遍歴条件で使用するには、次の手順に従います。

1. ジャーニーを開き、 **条件** アクティビティをドロップして、 **データソース条件を選択します**。
   ![](../assets/journey47.png)
1. 必要 **な追加のパスごとにパス** をクリックします。 各パスに対して、 **式** フィールドをクリックします。
   ![](../assets/segment3.png)
1. 左側で、 **セグメント** (Segments)ノードを展開します。 条件に使用するセグメントをドラッグ&amp;ドロップします。 デフォルトでは、セグメントの条件はtrueです。
   ![](../assets/segment4.png)

ジャーニー条件とシンプルな式エディターの使用方法について詳しくは、 [条件アクティビティを参照してください](../building-journeys/condition-activity.md#about_condition)。
