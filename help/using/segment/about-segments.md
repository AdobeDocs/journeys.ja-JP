---
product: adobe campaign
title: Adobe Experience Platform セグメントについて
description: Adobe Experience Platform セグメントの設定方法について説明します
feature: Journeys
role: User
level: Intermediate
exl-id: 94e1e3e3-9a46-41ca-bec1-f41287925372
product_v2:
  - id: cf67d108-ecf9-4fde-af49-3a3c39083bc8
    internal-label: Journey Orchestration
feature_v2:
  - id: 7de3230f-9523-5ba5-8d5c-2313288b27ef
    internal-label: Journeys
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
source-git-commit: 255cd6677e7c9ebff63ea9a1028a042c19e63ecc
workflow-type: tm+mt
source-wordcount: '425'
ht-degree: 58%
---
# Adobe Experience Platform セグメントについて {#about-segments}


>[!CAUTION]
>
>**Adobe Journey Optimizer をお探しですか**？ Journey Optimizer のドキュメントについて詳しくは、[こちら](https://experienceleague.adobe.com/ja/docs/journey-optimizer/using/ajo-home){target="_blank"}をクリックしてください。
>
>
>_このドキュメントは、Journey Optimizer に置き換えられた従来の Journey Orchestration 資料を参照しています。 Journey Orchestration または Journey Optimizer へのアクセスについてご質問がある場合は、アカウントチームにお問い合わせください。_


[Adobe Experience Platform セグメント化サービス ](https://experienceleague.adobe.com/docs/experience-platform/segmentation/home.html?lang=ja)を使用してセグメントを作成している場合は、[!DNL Journey Orchestration]でそれらを活用できます。 専用のイベントアクティビティにより、Adobe Experience Platform セグメントの出入りに基づいて、個人をジャーニーに参加または前進させることができます。 これにより、シンプルまたは高度な式エディターを使用して、ジャーニー内の複雑な条件を構築することもできます。

「シルバー顧客」セグメントがあるとします。 このアクティビティを使用すると、新しいシルバーの顧客全員をジャーニーにエントリさせ、パーソナライズされた一連のメッセージを送ることができます。 また、このセグメントに基づいて条件を簡単に作成することもできます。

[!DNL Journey Orchestration]が提供するセグメントの可能性は次のとおりです。

* Adobe Experience Platform セグメントのリストにアクセスします。 [ セグメントの作成](../segment/creating-a-segment.md)を参照してください。
* セグメントをセグメント サービスを使用して作成するのと同じ方法で、[!DNL Journey Orchestration]で直接セグメントを作成します。 [ セグメントの作成](../segment/creating-a-segment.md)を参照してください。
* シンプルまたは高度な式エディターを使用して、ジャーニーの条件内のセグメントを活用します。 [条件でのセグメントの使用](../segment/using-a-segment.md)を参照してください。
* Adobe Experience Platform セグメントのプロファイルの出入りをリッスンするために、**[!UICONTROL セグメント選定]** イベントをジャーニーに追加します。 [ イベントアクティビティ ](../building-journeys/segment-qualification-events.md)を参照してください。

## Journey Orchestrationの評価方法 {#evaluation-method-in-journey-orchestration}

Journey Orchestrationでは、次のいずれかの評価方法を使用して、セグメント定義からオーディエンスが生成されます。

* ストリーミングセグメンテーション - セグメントのオーディエンスリストは、新しいデータがシステムに流入するのに応じて、リアルタイムで最新の状態に保たれます。
* バッチセグメンテーション - セグメントのオーディエンスリストは、過去 1 時間に到着したデータに基づいて、1 時間ごとに更新されます。

バッチセグメント化とストリーミングセグメント化のどちらを使用するかは、セグメントルールの評価の複雑さとコストに基づいて、セグメント定義ごとにシステムによって決定されます。

セグメントリストの&#x200B;**[!UICONTROL 評価方法]**&#x200B;列で、各セグメントの評価方法を確認できます。

まずセグメントを定義した後、プロファイルは認定されるたびにオーディエンスに追加されます。

以前のデータからオーディエンスをバックフィルするには、最大 24 時間かかる場合があります。 オーディエンスがバックフィルされた後も、オーディエンスは常に最新の状態に保たれ、常にターゲティングの準備ができています。