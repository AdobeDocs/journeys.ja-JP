---
product: adobe campaign
title: Adobe Experience Platform セグメントについて
description: Adobe Experience Platform セグメントの設定方法について説明します
feature: Journeys
role: User
level: Intermediate
exl-id: 94e1e3e3-9a46-41ca-bec1-f41287925372
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '407'
ht-degree: 41%

---

# Adobe Experience Platform セグメントについて {#about-segments}


>[!CAUTION]
>
>**Adobe Journey Optimizerをお探しですか** Journey Optimizerのドキュメントについては、[&#x200B; こちら &#x200B;](https://experienceleague.adobe.com/ja/docs/journey-optimizer/using/ajo-home){target="_blank"} をクリックしてください。
>
>
>_このドキュメントでは、Journey Optimizerに置き換えられた従来のJourney Orchestration マテリアルについて説明します。 Journey OrchestrationやJourney Optimizerへのアクセスに関するご質問は、アカウントチームにお問い合わせください。_


[Adobe Experience Platform Segmentation Service](https://experienceleague.adobe.com/docs/experience-platform/segmentation/home.html?lang=ja) を使用してセグメントを作成する場合は、それらを [!DNL Journey Orchestration] で利用できます。 専用のイベントアクティビティにより、Adobe Experience Platform セグメントのエントリと離脱に基づいて、個人のジャーニーを開始したり進めたりすることができます。 また、シンプルな式エディターまたは高度な式エディターを使用して、ジャーニーで複雑な条件を作成することもできます。

「シルバー顧客」セグメントがあるとします。このアクティビティを使用すると、新しいシルバーの顧客全員をジャーニーにエントリさせ、パーソナライズされた一連のメッセージを送信できます。 また、このセグメントに基づいて条件を簡単に作成できます。

次に、セグメントで提供され [!DNL Journey Orchestration] 可能性を示します。

* Adobe Experience Platform セグメントのリストにアクセスします。 [&#x200B; セグメントの作成 &#x200B;](../segment/creating-a-segment.md) を参照してください。
* セグメント化サービス [!DNL Journey Orchestration] 使用して作成するのと同じ方法で、で直接セグメントを作成します。 [&#x200B; セグメントの作成 &#x200B;](../segment/creating-a-segment.md) を参照してください。
* シンプルな式エディターまたは高度な式エディターを使用して、ジャーニーの条件でセグメントを活用します。 [&#x200B; 条件でのセグメントの使用 &#x200B;](../segment/using-a-segment.md) を参照してください。
* Adobe Experience Platform セグメントでプロファイルのエントリと離脱をリッスンするために、**[!UICONTROL セグメントの選定]** イベントをジャーニーに追加します。 [&#x200B; イベントアクティビティ &#x200B;](../building-journeys/segment-qualification-events.md) を参照してください。

## Journey Orchestrationにおける評価手法 {#evaluation-method-in-journey-orchestration}

Journey Orchestrationでは、オーディエンスは、次のいずれかの評価方法を使用して、セグメント定義から生成されます。

* ストリーミングセグメンテーション - セグメントのオーディエンスリストは、新しいデータがシステムに流入するのに応じて、リアルタイムで最新の状態に保たれます。
* バッチセグメンテーション - セグメントのオーディエンスリストは、過去 1 時間に到着したデータに基づいて、1 時間ごとに更新されます。

バッチセグメント化とストリーミングセグメント化のどちらを使用するかは、セグメントルールの評価の複雑さとコストに基づいて、セグメント定義ごとにシステムによって決定されます。

セグメントリストの&#x200B;**[!UICONTROL 評価方法]**&#x200B;列で、各セグメントの評価方法を確認できます。

まずセグメントを定義した後、プロファイルは認定されるたびにオーディエンスに追加されます。

以前のデータからオーディエンスをバックフィルするには、最大 24 時間かかる場合があります。 オーディエンスがバックフィルされた後も、オーディエンスは常に最新の状態に保たれ、常にターゲティングの準備ができています。