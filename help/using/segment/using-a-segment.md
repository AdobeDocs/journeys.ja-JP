---
product: adobe campaign
title: セグメントの使用
description: セグメントの使用方法を説明します
feature: ジャーニー
role: Business Practitioner
level: Intermediate
exl-id: 9a0490c8-c940-44d2-af1a-d1863c51465d
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '171'
ht-degree: 2%

---

# 条件でのセグメントの使用 {#using-a-segment}

この節では、ジャーニー条件でのセグメントの使用方法を説明します。 ジャーニーでの&#x200B;**[!UICONTROL セグメントの選定]**&#x200B;イベントの使用方法については、この[節](../building-journeys/segment-qualification-events.md)を参照してください。

ジャーニー条件でセグメントを使用するには、次の手順に従います。

1. ジャーニーを開き、**[!UICONTROL 条件]**&#x200B;アクティビティをドロップして、**データソース条件**を選択します。
   ![](../assets/journey47.png)

1. 必要に応じて、「**[!UICONTROL パス]**&#x200B;を追加」をクリックします。 各パスで、「**[!UICONTROL 式]**」フィールドをクリックします。

   ![](../assets/segment3.png)

1. 左側で、「**[!UICONTROL セグメント]**」ノードを展開します。 条件に使用するセグメントをドラッグ&amp;ドロップします。 デフォルトでは、セグメントの条件はtrueです。

   ![](../assets/segment4.png)

   >[!NOTE]
   >
   >セグメントのメンバーとして考慮されるのは、**認識済み**&#x200B;および&#x200B;**既存の**&#x200B;セグメントパーティシペーションステータスを持つ個人のみです。 セグメントの評価方法について詳しくは、[セグメント化サービスのドキュメント](https://experienceleague.adobe.com/docs/experience-platform/segmentation/tutorials/evaluate-a-segment.html?lang=en#interpret-segment-results)を参照してください。

ジャーニー条件とシンプルな式エディターの使用方法について詳しくは、[条件アクティビティ](../building-journeys/condition-activity.md#about_condition)を参照してください。
