---
title: Platformセグメントについて
description: Platformセグメントの設定方法
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
source-git-commit: 14c8828a8c8e223b58b3512f02f2ee06136b98c5
workflow-type: tm+mt
source-wordcount: '197'
ht-degree: 0%

---


# Platformセグメントについて {#about-segments}

セグメントの作成に [Platformセグメントサービス](https://docs.adobe.com/content/help/en/experience-platform/segmentation/home.html) （英語のみ）を使用している場合は、で利用でき [!DNL Journey Orchestration]ます。 専用のイベントアクティビティにより、Platformセグメントの入口と出口に基づいて、個人が旅に出たり進んだりできます。 また、シンプルまたは高度な式エディターを使用して、ジャーニー内に複雑な条件を作成することもできます。

「シルバー顧客」セグメントがあるとします。 このアクティビティを使うと、新しい銀の顧客全員を旅に出させ、パーソナライズされた一連のメッセージを送ることができます。 また、このセグメントに基づいて、簡単に条件を作成できます。

セグメントには、次のような [!DNL Journey Orchestration] オファーがあります。

* Platformセグメントのリストにアクセスします。 See [Creating a segment](../segment/creating-a-segment.md).
* Segmentation Serviceを使用した場合と同様 [!DNL Journey Orchestration] に、セグメントを直接作成します。 See [Creating a segment](../segment/creating-a-segment.md).
* シンプルまたはアドバンス式エディタを使用して、遍歴の条件でセグメントを活用します。 詳しくは、条件でのセグメントの [使用を参照してください](../segment/using-a-segment.md)。
* Platformセグメント内の追加プロファイルの入口と出口をリッスンするための、遍歴に対するセグメントクオリフィケーション **** イベント。 「 [イベントアクティビティ](../building-journeys/event-activities.md#segment-qualification)」を参照してください。

