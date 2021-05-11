---
product: adobe campaign
solution: Journey Orchestration
title: はじめに
description: Journey Orchestration を設定し、初めてのジャーニーを構築するための主な手順を確認します。
feature: ジャーニー
role: Business Practitioner
level: Beginner
exl-id: fe7bb5fe-7b5e-46da-8ef8-ae9401522c03
translation-type: tm+mt
source-git-commit: 8ab3951f9c97a0a964f5c123978ed256d3aedc45
workflow-type: tm+mt
source-wordcount: '323'
ht-degree: 92%

---

# はじめに{#concept_y4b_4qt_52b}

[!DNL Journey Orchestration] には、**技術ユーザー**&#x200B;と&#x200B;**ビジネスユーザー**&#x200B;の 2 種類のユーザーがいて、それぞれが特定のタスクを実行します。ユーザーアクセスは、製品プロファイルと権限によって管理されます。ユーザーアクセスの設定方法については、[このページ](../about/access-management.md)を参照してください。

次に、[!DNL Journey Orchestration] を設定して使用する主な手順を示します。

1. **イベントの設定**

   必要な情報とその処理方法を定義する必要があります。この設定は必須です。この手順は、**技術ユーザー**&#x200B;が実行します。

   詳しくは、[こちらのページ](../event/about-events.md)を参照してください。

   ![](../assets/journey7.png)

1. **データソースの設定**

   例えば、状況に応じて、ジャーニーで使用される追加情報（例：条件）を取得するには、システムへの接続を定義する必要があります。組み込みの Adobe Experience Platform データソースも、プロビジョニング時に設定されます。この手順は、ジャーニーでイベントのデータのみを活用する場合には必要ありません。この手順は、**技術ユーザー**&#x200B;が実行します。

   詳しくは、[こちらのページ](../datasource/about-data-sources.md)を参照してください。

   ![](../assets/journey22.png)

1. **アクションの設定**

   サードパーティシステムを利用してメッセージを送信する場合は、[!DNL Journey Orchestration] との接続を設定する必要があります。[このページ](../action/about-custom-action-configuration.md)を参照してください。

   Adobe Campaign Standard を使用してメッセージを送信する場合は、組み込みのアクションを設定する必要があります。[このページ](../action/working-with-adobe-campaign.md)を参照してください。

   これらの手順は、**技術ユーザー**&#x200B;が実行します。

   ![](../assets/custom2.png)

1. **ジャーニーのデザイン**

   様々なイベント、オーケストレーション、アクションアクティビティを組み合わせて、複数手順のクロスチャネルシナリオを構築します。この手順は、**ビジネスユーザー**&#x200B;が実行します。

   詳しくは、[このページ](../building-journeys/journey.md)を参照してください。

   ![](../assets/journeyuc2_24.png)

1. **ジャーニーのテストと公開**

   ジャーニーを検証し、アクティブにする必要があります。この手順は、**ビジネスユーザー**&#x200B;が実行します。

   詳しくは、[ジャーニーのテスト](../building-journeys/testing-the-journey.md)および[ジャーニーの公開](../building-journeys/publishing-the-journey.md)を参照してください。

   ![](../assets/journeyuc2_32bis.png)

1. **ジャーニーの監視**

   専用のレポートツールを使用して、ジャーニーの効果を測定します。この手順は、**ビジネスユーザー**&#x200B;が実行します。

   詳しくは、[このページ](../reporting/about-journey-reports.md)を参照してください。

   ![](../assets/dynamic_report_journey_12.png)
