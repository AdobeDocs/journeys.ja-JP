---
product: adobe campaign
title: 条件でのセグメントの使用
description: セグメントの使用方法を学ぶ
feature: Journeys
role: User
level: Intermediate
exl-id: 9a0490c8-c940-44d2-af1a-d1863c51465d
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '207'
ht-degree: 59%

---

# 条件でのセグメントの使用 {#using-a-segment}


>[!CAUTION]
>
>**Adobe Journey Optimizerをお探しですか** Journey Optimizerのドキュメントについては、[ こちら ](https://experienceleague.adobe.com/ja/docs/journey-optimizer/using/ajo-home){target="_blank"} をクリックしてください。
>
>
>_このドキュメントでは、Journey Optimizerに置き換えられた従来のJourney Orchestration マテリアルについて説明します。 Journey OrchestrationやJourney Optimizerへのアクセスに関するご質問は、アカウントチームにお問い合わせください。_


この節では、ジャーニー条件でセグメントを使用する方法について説明します。ジャーニーで **[!UICONTROL セグメントの選定]** イベントを使用する方法については、この [ 節 ](../building-journeys/segment-qualification-events.md) を参照してください。

ジャーニー条件でセグメントを使用するには、次の手順に従います。

1. ジャーニーを開いて&#x200B;**[!UICONTROL 条件]**&#x200B;アクティビティをドロップし、「**データソース条件**」を選択します。
   ![](../assets/journey47.png)

1. 必要な追加パスごとに「**[!UICONTROL パスを追加]**」をクリックします。各パスに対して「**[!UICONTROL 式]**」フィールドをクリックします。

   ![](../assets/segment3.png)

1. 左側で、**[!UICONTROL セグメント]**&#x200B;ノードを展開します。条件に使用するセグメントをドラッグ＆ドロップします。デフォルトでは、セグメントの条件は true です。

   ![](../assets/segment4.png)

   >[!NOTE]
   >
   >セグメント参加ステータスが&#x200B;**実現**&#x200B;と&#x200B;**既存**&#x200B;の個人のみが、セグメントのメンバーと見なされます。セグメントの評価方法について詳しくは、[セグメント化サービスのドキュメント](https://experienceleague.adobe.com/docs/experience-platform/segmentation/tutorials/evaluate-a-segment.html?lang=ja#interpret-segment-results)を参照してください。

ジャーニー条件と簡単な式エディターの使用方法について詳しくは、[ 条件アクティビティ ](../building-journeys/condition-activity.md#about_condition) を参照してください。
