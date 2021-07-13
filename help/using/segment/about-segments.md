---
product: adobe campaign
title: Adobe Experience Platform セグメントについて
description: Adobe Experience Platform セグメントの設定方法について説明します
feature: ジャーニー
role: User
level: Intermediate
exl-id: 94e1e3e3-9a46-41ca-bec1-f41287925372
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '210'
ht-degree: 26%

---

# Adobe Experience Platform セグメントについて {#about-segments}

[Adobe Experience Platform Segmentation Service](https://experienceleague.adobe.com/docs/experience-platform/segmentation/home.html?lang=ja)を使用してセグメントを作成する場合は、[!DNL Journey Orchestration]でそれらを活用できます。 専用のイベントアクティビティを使用することで、Adobe Experience Platformのセグメントのエントリと離脱に基づいて、個人がジャーニーにエントリしたり、ジャーニーに進んだりできるようになります。 また、シンプルまたは高度な式エディターを使用して、ジャーニーで複雑な条件を作成することもできます。

「シルバー顧客」セグメントがあるとします。このアクティビティを使用すると、新しいシルバーの顧客全員をジャーニーにエントリさせ、パーソナライズされた一連のメッセージを送ることができます。また、このセグメントに基づいて、条件を簡単に作成できます。

次に、セグメントを提供する[!DNL Journey Orchestration]の可能性を示します。

* Adobe Experience Platformセグメントのリストにアクセスします。 [セグメントの作成](../segment/creating-a-segment.md)を参照してください。
* セグメント化サービスを使用してセグメントを作成するのと同じ方法で、[!DNL Journey Orchestration]でセグメントを直接作成します。 [セグメントの作成](../segment/creating-a-segment.md)を参照してください。
* シンプルまたは高度な式エディターを使用して、ジャーニーの条件でセグメントを活用します。 [条件でのセグメントの使用](../segment/using-a-segment.md)を参照してください。
* Adobe Experience Platformセグメント内のプロファイルのエントリと離脱をリッスンするために、**[!UICONTROL セグメント認定]**&#x200B;イベントをジャーニーに追加します。 [イベントアクティビティ](../building-journeys/segment-qualification-events.md)を参照してください。
