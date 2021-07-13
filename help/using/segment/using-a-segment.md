---
product: adobe campaign
title: セグメントの使用
description: セグメントの使用方法を説明します
feature: ジャーニー
role: User
level: Intermediate
exl-id: 9a0490c8-c940-44d2-af1a-d1863c51465d
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '171'
ht-degree: 63%

---

# 条件でのセグメントの使用 {#using-a-segment}

この節では、ジャーニー条件でセグメントを使用する方法について説明します。ジャーニーでの&#x200B;**[!UICONTROL セグメントの選定]**&#x200B;イベントの使用方法については、この[節](../building-journeys/segment-qualification-events.md)を参照してください。

ジャーニー条件でセグメントを使用するには、次の手順に従います。

1. ジャーニーを開いて&#x200B;**[!UICONTROL 条件]**&#x200B;アクティビティをドロップし、「**データソース条件**」を選択します。
   ![](../assets/journey47.png)

1. 必要な追加パスごとに「**[!UICONTROL パスを追加]**」をクリックします。各パスに対して「**[!UICONTROL 式]**」フィールドをクリックします。

   ![](../assets/segment3.png)

1. 左側で、**[!UICONTROL セグメント]**&#x200B;ノードを展開します。条件に使用するセグメントをドラッグ＆ドロップします。デフォルトでは、セグメントの条件は true です。

   ![](../assets/segment4.png)

   >[!NOTE]
   >
   >セグメントのメンバーとして考慮されるのは、**認識済み**&#x200B;および&#x200B;**既存の**&#x200B;セグメントパーティシペーションステータスを持つ個人のみです。 セグメントの評価方法について詳しくは、[Segmentation Service ドキュメント](https://experienceleague.adobe.com/docs/experience-platform/segmentation/tutorials/evaluate-a-segment.html?lang=ja#interpret-segment-results)を参照してください。

ジャーニー条件とシンプルな式エディターの使用方法について詳しくは、[条件アクティビティ](../building-journeys/condition-activity.md#about_condition)を参照してください。
