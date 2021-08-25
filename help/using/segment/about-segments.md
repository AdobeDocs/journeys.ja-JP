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
ht-degree: 39%

---

# Adobe Experience Platform セグメントについて {#about-segments}

[Adobe Experience Platform Segmentation Service](https://experienceleague.adobe.com/docs/experience-platform/segmentation/home.html?lang=ja)を使用してセグメントを作成する場合は、[!DNL Journey Orchestration]でそれらを活用できます。 専用のイベントアクティビティを使用することで、Adobe Experience Platformのセグメントのエントリと離脱に基づいて、個人がジャーニーにエントリしたり、ジャーニーに進んだりできるようになります。 また、シンプルまたは高度な式エディターを使用して、ジャーニーで複雑な条件を作成することもできます。

「シルバー顧客」セグメントがあるとします。このアクティビティを使用すると、新しいシルバーの顧客全員をジャーニーにエントリさせ、パーソナライズされた一連のメッセージを送ることができます。また、このセグメントに基づいて、条件を簡単に作成できます。

次に、セグメントを提供する[!DNL Journey Orchestration]の可能性を示します。

* Adobe Experience Platformセグメントのリストにアクセスします。 [セグメントの作成](../segment/creating-a-segment.md)を参照してください。
* セグメント化サービスを使用してセグメントを作成するのと同じ方法で、[!DNL Journey Orchestration]でセグメントを直接作成します。 [セグメントの作成](../segment/creating-a-segment.md)を参照してください。
* シンプルまたは高度な式エディターを使用して、ジャーニーの条件でセグメントを活用します。 [条件でのセグメントの使用](../segment/using-a-segment.md)を参照してください。
* Adobe Experience Platformセグメント内のプロファイルのエントリと離脱をリッスンするために、**[!UICONTROL セグメント認定]**&#x200B;イベントをジャーニーに追加します。 [イベントアクティビティ](../building-journeys/segment-qualification-events.md)を参照してください。

## Journey Orchestrationの評価方法 {#evaluation-method-in-journey-orchestration}

Journey Orchestrationでは、オーディエンスは、次の評価方法の1つを使用して、セグメント定義から生成されます。

* ストリーミングセグメント化 — 新しいデータがシステムにフローされる間、セグメントのオーディエンスリストはリアルタイムで最新の状態に保たれます。
* バッチセグメント化 — セグメントのオーディエンスリストは、過去1時間に到達したデータに基づいて1時間ごとに更新されます。

バッチセグメント化とストリーミングセグメント化のどちらを使用するかは、セグメントルールの評価の複雑さとコストに基づいて、セグメント定義ごとにシステムによって決定されます。

セグメントリストの&#x200B;**[!UICONTROL 評価方法]**&#x200B;列で、各セグメントの評価方法を確認できます。

まずセグメントを定義した後、プロファイルは認定されるたびにオーディエンスに追加されます。

以前のデータからオーディエンスをバックフィルするには、最大 24 時間かかる場合があります。 オーディエンスがバックフィルされた後も、オーディエンスは常に最新の状態に保たれ、常にターゲティングの準備ができています。