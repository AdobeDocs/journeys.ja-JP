---
product: adobe campaign
solution: Journey Orchestration
title: ジャーニー構築について
description: ビジネスユーザーとしてイベント、オーケストレーション、アクションアクティビティを組み合わせ、ジャーニーを構築する方法を学びます。
translation-type: tm+mt
source-git-commit: 6ebedad2cb8e78b4dd953bc7a2993cebbeefabcc
workflow-type: tm+mt
source-wordcount: '406'
ht-degree: 15%

---


# ジャーニーの作成 {#concept_gq5_sqt_52b}

この手順は、**ビジネスユーザー**&#x200B;が実行します。 ここで旅を創り出します 様々なイベント、オーケストレーション、アクションアクティビティを組み合わせて、複数手順のクロスチャネルシナリオを構築します。

ジャーニーインターフェイスを使用すると、アクティビティをパレットからキャンバスに簡単にドラッグ&amp;ドロップできます。 また、アクティビティを重複クリックして、次のステップでキャンバスに追加することもできます。 各アクティビティは、プロセス内の特定の役割と場所を持ちます。 アクティビティが順番に並べられます。 アクティビティが完了すると、フローは続行され、次のアクティビティなどを処理します。

1回の旅行で許可される名前空間は1つだけです。 最初のイベントをドロップすると、異なる名前空間を持つイベントは灰色表示になります。 最初のイベントに名前空間がない場合は、名前空間を含むすべてのイベントが灰色表示になります。 [このページ](../event/selecting-the-namespace.md)を参照してください。また、名前空間のないイベントを持つ旅行には、Adobe Experience Platformのフィールドグループも灰色表示になっています。 最後に、同じ遍歴で複数のイベントを使う場合は、同じ名前空間を使う必要があります。

## クイックスタート {#creating_journey}

ジャーニーを作成して投稿する主な手順は次のとおりです。

1. 上部のメニューで、「**[!UICONTROL ホーム]**」タブをクリックします。

   旅のリストが現れる。 インターフェイスの詳細は、[このページ](../building-journeys/using-the-journey-designer.md)を参照してください。

   ![](../assets/journey30.png)

1. 「**[!UICONTROL 作成]**」をクリックして新しいジャーニーを作成します。

   ![](../assets/journey31.png)

1. 右側に表示される設定ペインで、ジャーニーのプロパティを編集します。[このページ](../building-journeys/changing-properties.md)を参照してください。

   ![](../assets/journey32.png)

1. イベントアクティビティをパレットからカンバスにドラッグ&amp;ドロップして開始します。 アクティビティを重複クリックしてキャンバスに追加することもできます。

   ![](../assets/journey33.png)

1. その他のアクティビティをドラッグ&amp;ドロップして設定します。 [イベントアクティビティ](../building-journeys/event-activities.md)、[オーケストレーションアクティビティ](../building-journeys/about-orchestration-activities.md)、[アクションアクティビティ](../building-journeys/about-action-activities.md)の各ページを参照してください。

   ![](../assets/journey34.png)

1. 自動的に旅行が保存されます。 遍歴をテストし、公開します。 [遍歴のテスト](../building-journeys/testing-the-journey.md)と[旅のパブリッシング](../building-journeys/publishing-the-journey.md)を参照してください。

   ![](../assets/journey36.png)

## ジャーニー{#ending_a_journey}の終了

旅を終えるには、2つの方法があります。

* その人は道の最後のアクティビティに着く。 最後のアクティビティは、エンドアクティビティまたは別のアクティビティにすることができます。 パスをエンドアクティビティで終了する義務はありません。 [このページ](../building-journeys/end-activity.md)を参照してください。
* 訪問者は、条件アクティビティ(または条件を含む待機アクティビティ)に到達し、どの条件とも一致しません。

再入場が許可された場合は、再入場が可能です。 [このページ](../building-journeys/changing-properties.md)を参照してください。
