---
title: はじめに
description: Journey Orchestration の基本を学ぶ
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: ht
source-git-commit: eb4474313d3c0470448f9959ed757902ef0ecd2a
workflow-type: ht
source-wordcount: '291'
ht-degree: 100%

---


# はじめに{#concept_y4b_4qt_52b}

[!DNL Journey Orchestration] には、**技術ユーザー**&#x200B;と&#x200B;**ビジネスユーザー**&#x200B;の 2 種類のユーザーがいて、それぞれが特定のタスクを実行します。ユーザーアクセスは、製品プロファイルと権限によって管理されます。ユーザーアクセスを設定する方法については、[](../about/access-management.md)を参照してください。

次に、[!DNL Journey Orchestration] を設定して使用する主な手順を示します。

1. **イベントの設定**

   必要な情報とその処理方法を定義する必要があります。この設定は必須です。この手順は、**技術ユーザー**&#x200B;が実行します。

   詳しくは、[](../event/about-events.md)を参照してください。

   ![](../assets/journey7.png)

1. **データソースの設定**

   例えば、状況に応じて、ジャーニーで使用される追加情報（例：条件）を取得するには、システムへの接続を定義する必要があります。組み込みの Adobe Experience Platform データソースも、プロビジョニング時に設定されます。この手順は、ジャーニーでイベントのデータのみを活用する場合には必要ありません。この手順は、**技術ユーザー**&#x200B;が実行します。

   詳しくは、[](../datasource/about-data-sources.md)を参照してください。

   ![](../assets/journey22.png)

1. **アクションの設定**

   サードパーティシステムを利用してメッセージを送信する場合は、[!DNL Journey Orchestration] との接続を設定する必要があります。[](../action/about-custom-action-configuration.md) を参照してください。

   Adobe Campaign Standard を使用してメッセージを送信する場合は、組み込みのアクションを設定する必要があります。[](../action/working-with-adobe-campaign.md) を参照してください。

   これらの手順は、**技術ユーザー**&#x200B;が実行します。

   ![](../assets/custom2.png)

1. **ジャーニーのデザイン**

   様々なイベント、オーケストレーション、アクションアクティビティを組み合わせて、複数手順のクロスチャネルシナリオを構築します。この手順は、**ビジネスユーザー**&#x200B;が実行します。

   詳しくは、[](../building-journeys/journey.md)を参照してください。

   ![](../assets/journeyuc2_24.png)

1. **ジャーニーのテストと公開**

   ジャーニーを検証し、アクティブにする必要があります。この手順は、**ビジネスユーザー**&#x200B;が実行します。

   詳しくは、[](../building-journeys/testing-the-journey.md)および[](../building-journeys/publishing-the-journey.md)を参照してください。

   ![](../assets/journeyuc2_32bis.png)

1. **ジャーニーの監視**

   専用のレポートツールを使用して、ジャーニーの効果を測定します。この手順は、**ビジネスユーザー**&#x200B;が実行します。

   詳しくは、[](../reporting/about-journey-reports.md)を参照してください。

   ![](../assets/dynamic_report_journey_12.png)

