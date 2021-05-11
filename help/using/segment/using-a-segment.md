---
product: adobe campaign
solution: Journey Orchestration
title: セグメントの使用
description: セグメントの使用方法
feature: ジャーニー
role: Business Practitioner
level: Intermediate
exl-id: 9a0490c8-c940-44d2-af1a-d1863c51465d
translation-type: tm+mt
source-git-commit: 8ab3951f9c97a0a964f5c123978ed256d3aedc45
workflow-type: tm+mt
source-wordcount: '171'
ht-degree: 2%

---

# 条件でのセグメントの使用 {#using-a-segment}

ここでは、ジャーニー条件でセグメントを使用する方法について説明します。 ジャーニーで&#x200B;**[!UICONTROL セグメントの資格]**&#x200B;イベントを使用する方法については、[](../building-journeys/segment-qualification-events.md)を参照してください。

ジャーニー条件でセグメントを使用するには、次の手順に従います。

1. ジャーニーを開き、**[!UICONTROL 条件]**&#x200B;アクティビティをドロップし、**データソース条件**を選択します。
   ![](../assets/journey47.png)

1. 必要な追加パスごとに&#x200B;**[!UICONTROL 追加パス]**&#x200B;をクリックします。 各パスに対して、**[!UICONTROL 式]**&#x200B;フィールドをクリックします。

   ![](../assets/segment3.png)

1. 左側で、**[!UICONTROL セグメント]**&#x200B;ノードを展開します。 条件に使用するセグメントをドラッグ&amp;ドロップします。 デフォルトでは、セグメントの条件はtrueです。

   ![](../assets/segment4.png)

   >[!NOTE]
   >
   >**実現**&#x200B;および&#x200B;**既存の**&#x200B;セグメントパーティシペーションのステータスの個人のみが、セグメントのメンバーと見なされます。 セグメントの評価方法について詳しくは、[Segmentation Serviceドキュメント](https://experienceleague.adobe.com/docs/experience-platform/segmentation/tutorials/evaluate-a-segment.html?lang=en#interpret-segment-results)を参照してください。

ジャーニー条件とシンプル式エディターの使用方法について詳しくは、[条件アクティビティ](../building-journeys/condition-activity.md#about_condition)を参照してください。
