---
title: ジャーニー構築について
description: 旅の作り方を学ぶ
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
source-git-commit: d5c013ed6031e8138a8e2c099fc28af82966d3ec
workflow-type: tm+mt
source-wordcount: '366'
ht-degree: 3%

---



# ジャーニーの作成 {#concept_gq5_sqt_52b}

この手順は、 **ビジネス・ユーザが実行します**。 ここで旅を創り出します 様々なイベント、オーケストレーション、アクションアクティビティを組み合わせて、複数手順のクロスチャネルシナリオを構築します。

ジャーニーインターフェイスを使用すると、アクティビティをパレットからキャンバスに簡単にドラッグ&amp;ドロップできます。 また、アクティビティを重複クリックして、次のステップでキャンバスに追加することもできます。 各アクティビティは、プロセス内の特定の役割と場所を持ちます。 アクティビティが順番に並べられます。 アクティビティが完了すると、フローは続行され、次のアクティビティなどを処理します。

1回の旅行で許可される名前空間は1つだけです。 最初のイベントをドロップすると、異なる名前空間を持つイベントは灰色表示になります。 最初のイベントに名前空間がない場合は、名前空間を含むすべてのイベントが灰色表示になります。 [](../event/selecting-the-namespace.md)を参照してください。また、名前空間のないイベントが旅行に含まれる場合、エクスペリエンスプラットフォームフィールドグループも灰色表示になります。 最後に、同じ遍歴で複数のイベントを使う場合は、同じ名前空間を使う必要があります。

## クイックスタート {#creating_journey}

ジャーニーを作成して投稿する主な手順は次のとおりです。

1. 上部のメニューで、「 **[!UICONTROL ホーム]** 」タブをクリックします。

   旅のリストが現れる。 インターフェイス [](../building-journeys/using-the-journey-designer.md) の詳細については、を参照してください。

   ![](../assets/journey30.png)

1. Click **[!UICONTROL Create]** to create a new journey.

   ![](../assets/journey31.png)

1. 右側に表示される設定ペインで、ジャーニーのプロパティを編集します。 [](../building-journeys/changing-properties.md)を参照してください。

   ![](../assets/journey32.png)

1. イベントアクティビティをパレットからカンバスにドラッグ&amp;ドロップして開始します。 アクティビティを重複クリックしてキャンバスに追加することもできます。

   ![](../assets/journey33.png)

1. その他のアクティビティをドラッグ&amp;ドロップして設定します。 See [](../building-journeys/event-activities.md), [](../building-journeys/about-orchestration-activities.md) and [](../building-journeys/about-action-activities.md).

   ![](../assets/journey34.png)

1. 自動的に旅行が保存されます。 遍歴をテストし、公開します。 [](../building-journeys/testing-the-journey.md)および[](../building-journeys/publishing-the-journey.md)を参照してください。

   ![](../assets/journey36.png)

## 旅の終わり {#ending_a_journey}

旅を終えるには、2つの方法があります。

* その人は道の最後のアクティビティに着く。 最後のアクティビティは、エンドアクティビティまたは別のアクティビティにすることができます。 エンドアクティビティでパスを終了する義務はありません。 [](../building-journeys/end-activity.md)を参照してください。
* 訪問者は、条件アクティビティ(または条件を含む待機アクティビティ)に到達し、どの条件とも一致しません。

再入場が許可された場合は、再入場が可能です。 [](../building-journeys/changing-properties.md)を参照してください。
