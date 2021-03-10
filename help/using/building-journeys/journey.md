---
product: adobe campaign
solution: Journey Orchestration
title: ジャーニー構築について
description: ビジネスユーザーとしてイベント、オーケストレーション、アクションアクティビティを組み合わせ、ジャーニーを構築する方法を学びます。
feature: ジャーニー
role: 開業医
level: 中級
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '441'
ht-degree: 14%

---


# ジャーニーの作成 {#concept_gq5_sqt_52b}

この手順は、**ビジネスユーザー**&#x200B;が実行します。 ここでジャーニーを作成します。 様々なイベント、オーケストレーション、アクションアクティビティを組み合わせて、複数手順のクロスチャネルシナリオを構築します。

ジャーニーインターフェイスを使用すると、アクティビティをパレットからキャンバスに簡単にドラッグ&amp;ドロップできます。 また、アクティビティを重複クリックして、次のステップでキャンバスに追加することもできます。 各アクティビティは、プロセス内の特定の役割と場所を持ちます。 アクティビティが順番に並べられます。 アクティビティが完了すると、フローは続行され、次のアクティビティなどを処理します。

1つのジャーニーで許可される名前空間は1つだけです。 最初のイベントをドロップすると、異なる名前空間を持つイベントは灰色表示になります。 最初のイベントに名前空間がない場合は、名前空間を含むすべてのイベントが灰色表示になります。 [このページ](../event/selecting-the-namespace.md)を参照してください。また、ジャーニーに名前空間のないイベントが含まれる場合、Adobe Experience Platformのフィールドグループは灰色表示になります。 最後に、同じジャーニーで複数のイベントを使用する場合は、同じ名前空間を使用する必要があります。

新しいジャーニーを開始すると、最初の手順としてキャンバスにドロップできない要素は非表示になります。 これは、すべてのアクション、条件のアクティビティ、待ち、反応に関するものです。

## クイックスタート {#creating_journey}

ジャーニーを作成して公開する主な手順は次のとおりです。

1. 上部のメニューで、「**[!UICONTROL ホーム]**」タブをクリックします。

   ジャーニーのリストが表示されます。 インターフェイスの詳細は、[このページ](../building-journeys/using-the-journey-designer.md)を参照してください。

   ![](../assets/journey30.png)

1. 「**[!UICONTROL 作成]**」をクリックして、新しいジャーニーを作成します。

   ![](../assets/journey31.png)

1. 右側に表示される設定ペインで、ジャーニーのプロパティを編集します。[このページ](../building-journeys/changing-properties.md)を参照してください。

   ![](../assets/journey32.png)

1. イベントアクティビティをパレットからカンバスにドラッグ&amp;ドロップして開始します。 アクティビティを重複クリックしてキャンバスに追加することもできます。

   ![](../assets/journey33.png)

1. その他のアクティビティをドラッグ&amp;ドロップして設定します。 [イベントアクティビティ](../building-journeys/event-activities.md)、[オーケストレーションアクティビティ](../building-journeys/about-orchestration-activities.md)、[アクションアクティビティ](../building-journeys/about-action-activities.md)の各ページを参照してください。

   ![](../assets/journey34.png)

1. ジャーニーが自動的に保存されます。 ジャーニーをテストして公開します。 [ジャーニーのテスト](../building-journeys/testing-the-journey.md)と[ジャーニーの公開](../building-journeys/publishing-the-journey.md)を参照してください。

   ![](../assets/journey36.png)

## ジャーニーの終了{#ending_a_journey}

ジャーニーを終了する方法は2つあります。

* その人は道の最後のアクティビティに着く。 最後のアクティビティは、エンドアクティビティまたは別のアクティビティにすることができます。 エンドアクティビティでパスを終了する義務はありません。 [このページ](../building-journeys/end-activity.md)を参照してください。
* 訪問者は、条件アクティビティ(または条件を含む待機アクティビティ)に到達し、どの条件とも一致しません。

再入場が許可された場合は、ジャーニーに再入場できます。 [このページ](../building-journeys/changing-properties.md)を参照してください。
