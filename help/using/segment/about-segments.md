---
product: adobe campaign
title: Adobe Experience Platform セグメントについて
description: Adobe Experience Platform セグメントの設定方法について説明します
feature: Journeys
role: User
level: Intermediate
exl-id: 94e1e3e3-9a46-41ca-bec1-f41287925372
source-git-commit: e5c0db2e1f85ea72fd54f91e4a26cc287377fb0e
workflow-type: tm+mt
source-wordcount: '366'
ht-degree: 52%

---

# Adobe Experience Platform セグメントについて {#about-segments}

を使用している場合、 [Adobe Experience Platform Segmentation Service](https://experienceleague.adobe.com/docs/experience-platform/segmentation/home.html?lang=ja) セグメントを作成するには、 [!DNL Journey Orchestration]. 専用のイベントアクティビティにより、Adobe Experience Platformのセグメントのエントリと離脱に基づいて、個人をジャーニーにエントリさせたり、ジャーニーに進ませたりできます。 また、シンプルな式エディターや高度な式エディターを使用して、ジャーニーで複雑な条件を構築できます。

「シルバー顧客」セグメントがあるとします。このアクティビティを使用すると、新しいシルバーの顧客全員をジャーニーにエントリさせ、パーソナライズされた一連のメッセージを送ることができます。また、このセグメントに基づいて、条件を簡単に作成できます。

可能性は次のとおりです。 [!DNL Journey Orchestration] には、次のセグメントがあります。

* Adobe Experience Platformセグメントのリストにアクセスします。 詳しくは、 [セグメントの作成](../segment/creating-a-segment.md).
* でセグメントを直接作成 [!DNL Journey Orchestration] セグメント化サービスを使用して作成するのと同じ方法です。 詳しくは、 [セグメントの作成](../segment/creating-a-segment.md).
* シンプルな式エディターまたは高度な式エディターを使用して、ジャーニーの条件でセグメントを活用します。 詳しくは、 [条件でのセグメントの使用](../segment/using-a-segment.md).
* を追加します。 **[!UICONTROL セグメントの選定]** イベントを設定して、Adobe Experience Platformセグメントでプロファイルのエントリと離脱をリッスンすることができます。 詳しくは、 [イベントアクティビティ](../building-journeys/segment-qualification-events.md).

## Journey Orchestrationの評価方法 {#evaluation-method-in-journey-orchestration}

Journey Orchestrationでは、オーディエンスは、次の評価方法の 1 つを使用して、セグメント定義から生成されます。

* ストリーミングセグメンテーション - セグメントのオーディエンスリストは、新しいデータがシステムに流入するのに応じて、リアルタイムで最新の状態に保たれます。
* バッチセグメンテーション - セグメントのオーディエンスリストは、過去 1 時間に到着したデータに基づいて、1 時間ごとに更新されます。

バッチセグメント化とストリーミングセグメント化のどちらを使用するかは、セグメントルールの評価の複雑さとコストに基づいて、セグメント定義ごとにシステムによって決定されます。

セグメントリストの&#x200B;**[!UICONTROL 評価方法]**&#x200B;列で、各セグメントの評価方法を確認できます。

まずセグメントを定義した後、プロファイルは認定されるたびにオーディエンスに追加されます。

以前のデータからオーディエンスをバックフィルするには、最大 24 時間かかる場合があります。 オーディエンスがバックフィルされた後も、オーディエンスは常に最新の状態に保たれ、常にターゲティングの準備ができています。