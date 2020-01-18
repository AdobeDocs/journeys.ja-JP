---
title: 旅のビルディングについて
description: 旅の作り方
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
source-git-commit: 1bc8d845716044671a11c200e4bab92302841994

---



# 旅行の作成 {#concept_gq5_sqt_52b}

この手順は、ビジネス・ユーザーが **実行します**。 ここで旅を創り出します 様々なイベント、オーケストレーション、アクションのアクティビティを組み合わせて、複数ステップのクロスチャネルシナリオを構築します。

ジャーニーインターフェイスを使用すると、アクティビティをパレットからキャンバスに簡単にドラッグ&amp;ドロップできます。 また、次の手順でアクティビティをダブルクリックしてキャンバスに追加することもできます。 各アクティビティには、特定の役割とプロセス内の場所があります。 アクティビティの順序が決まります。 アクティビティが完了すると、フローは続行し、次のアクティビティを処理します。

1回の遍歴で許可される名前空間は1つだけです。 最初のイベントをドロップすると、異なる名前空間を持つイベントは灰色表示になります。 最初のイベントに名前空間がない場合、名前空間を持つすべてのイベントは灰色表示になります。 [](../event/selecting-the-namespace.md)を参照してください。また、名前空間のないイベントがジャーニーに含まれる場合、エクスペリエンスプラットフォームフィールドグループは灰色表示になります。 最後に、同じ遍歴で複数のイベントを使用する場合は、同じ名前空間を使用する必要があります。

## クイックスタート {#creating_journey}

ジャーニーを作成して公開する主な手順は次のとおりです。

1. 上部のメニューで、タブをクリック **[!UICONTROL Home]**します。

   ジャーニーのリストが表示されます。 インターフ [](../building-journeys/using-the-journey-designer.md) ェイスの詳細については、を参照してください。

   ![](../assets/journey30.png)

1. 新しい **[!UICONTROL Create]**旅を作成します。

   ![](../assets/journey31.png)

1. 右側に表示される設定ペインで、ジャーニーのプロパティを編集します。 [](../building-journeys/changing-properties.md)を参照してください。

   ![](../assets/journey32.png)

1. まず、イベントアクティビティをパレットからキャンバスにドラッグ&amp;ドロップします。 アクティビティをダブルクリックして、キャンバスに追加することもできます。


   ![](../assets/journey33.png)

1. 他のアクティビティをドラッグ&amp;ドロップして設定します。 See [](../building-journeys/event-activities.md), [](../building-journeys/about-orchestration-activities.md) and [](../building-journeys/about-action-activities.md).

   ![](../assets/journey34.png)

1. 旅は自動的に保存されます。 遍歴をテストし、公開します。 [](../building-journeys/testing-the-journey.md)および[](../building-journeys/publishing-the-journey.md)を参照してください。

   ![](../assets/journey36.png)

## 旅行の終了{#ending_a_journey}

旅を終えるには2つの方法があります。

* その人は、パスの最後のアクティビティに到達します。 この最後のアクティビティは、終了アクティビティまたは別のアクティビティにすることができます。 パスを終了アクティビティで終了する義務はありません。 [](../building-journeys/end-activity.md)を参照してください。
* その人は、条件アクティビティ（または条件を持つ待機アクティビティ）に到達し、どの条件にも一致しません。

再入場が許されれば、再入場が可能。 [](../building-journeys/changing-properties.md)を参照してください。

