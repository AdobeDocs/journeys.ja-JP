---
title: はじめに
description: Jargeny Orchestrationの使い始めに
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: tm+mt
source-git-commit: fed6fd8d8ee497ec47727f7297dc72f319fabe27

---


# はじめに{#concept_y4b_4qt_52b}

Jureny Orchestrationには、2種類のユーザーがあり、それぞれ特定のタスクを実行します。技術ユ **ーザー** 、ビジネス **ユーザー**。 ユーザーアクセスは、製品プロファイルと権限を通じて管理されます。 ユーザアクセス [](../about/access-management.md) の設定方法については、を参照してください。

Jureny Orchestrationを設定して使用する主な手順は次のとおりです。

1. **イベントの設定**

   必要な情報とその処理方法を定義する必要があります。 この設定は必須です。 この手順は、技術ユーザーが実 **行します**。

   詳しくは、[](../event/about-events.md)を参照してください。

   ![](../assets/journey7.png)

1. **データソースの設定**

   例えば、状況に応じて、ジャーニーで使用される追加情報を取得するには、システムへの接続を定義する必要があります。 組み込みのExperience Platformデータソースも、プロビジョニング時に設定されます。 この手順は、イベントのデータのみを活用する場合は不要です。 この手順は、技術ユーザーが実 **行します**。

   詳しくは、[](../datasource/about-data-sources.md)を参照してください。

   ![](../assets/journey22.png)

1. **アクションの設定**

   サードパーティ製のシステムを使用してメッセージを送信する場合は、Jureny Orchestrationとの接続を構成する必要があります。 [](../action/about-custom-action-configuration.md)を参照してください。

   Adobe Campaign Standardを使用してメッセージを送信する場合は、組み込みのアクションを設定する必要があります。 [](../action/working-with-adobe-campaign.md)を参照してください。

   これらの手順は、技術ユーザーが実 **行します**。

   ![](../assets/custom2.png)

1. **旅のデザイン**

   様々なイベント、オーケストレーション、アクションのアクティビティを組み合わせて、複数ステップのクロスチャネルシナリオを構築します。 このステップは、ビジネスユーザ **ーが実行する**。

   詳しくは、[](../building-journeys/journey.md)を参照してください。

   ![](../assets/journeyuc2_24.png)

1. **遍歴のテストと公開**

   この旅を検証し、アクティブにする必要があります。 このステップは、ビジネスユーザ **ーが実行する**。

   For more on this, see [](../building-journeys/testing-the-journey.md) and [](../building-journeys/publishing-the-journey.md).

   ![](../assets/journeyuc2_32bis.png)

1. **旅の監視**

   専用のレポートツールを使用して、旅の効果を測定します。 このステップは、ビジネスユーザ **ーが実行する**。

   詳しくは、[](../reporting/about-journey-reports.md)を参照してください。

   ![](../assets/dynamic_report_journey_12.png)

