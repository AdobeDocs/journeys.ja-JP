---
product: adobe campaign
title: ジャーニーの作成について
description: ビジネスユーザーとしてイベント、オーケストレーション、アクションアクティビティを組み合わせ、ジャーニーを構築する方法を学びます。
feature: Journeys
role: User
level: Intermediate
exl-id: 540b5142-9323-4cc1-9b5a-3fa20a5945bf
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '610'
ht-degree: 60%

---

# ジャーニーの作成 {#concept_gq5_sqt_52b}


>[!CAUTION]
>
>**Adobe Journey Optimizerをお探しですか** Journey Optimizerのドキュメントについては、[ こちら ](https://experienceleague.adobe.com/ja/docs/journey-optimizer/using/ajo-home){target="_blank"} をクリックしてください。
>
>
>_このドキュメントでは、Journey Optimizerに置き換えられた従来のJourney Orchestration マテリアルについて説明します。 Journey OrchestrationやJourney Optimizerへのアクセスに関するご質問は、アカウントチームにお問い合わせください。_


このステップは、**ビジネスユーザー**&#x200B;が実行します。ここでジャーニーを作成します。様々なイベント、オーケストレーション、アクションなどのアクティビティを組み合わせて、複数のステップから成るクロスチャネルのシナリオを構築します。

ジャーニーのインターフェイスを使用すると、パレットからキャンバスにアクティビティを簡単にドラッグ＆ドロップできます。アクティビティをダブルクリックして、以下の手順でキャンバスに追加することもできます。各アクティビティには、プロセス内に固有の役割と配置があります。アクティビティには順序があります。1 つのアクティビティが完了すると、フローを続行して、次のアクティビティを処理します。これを順番に続けます。

1 つのジャーニーで使用できる名前空間は 1 つだけです。最初のイベントをドロップすると、異なる名前空間を持つイベントはグレー表示されます。 最初のイベントに名前空間がない場合、名前空間を持つすべてのイベントがグレー表示されます。 [このページ](../event/selecting-the-namespace.md)を参照してください。また、ジャーニーに名前空間のないイベントがある場合、Adobe Experience Platform フィールドグループはグレー表示されます。 また、同じジャーニーで複数のイベントを使用する場合は、同じ名前空間を使用する必要があります。

新しいジャーニーを開始した際、最初の手順としてキャンバスにドロップできない要素は非表示になっています。これは、すべてのアクション、条件のアクティビティ、待機、反応が対象です。

## クイックスタート {#creating_journey}

ジャーニーを作成して公開する主な手順は次のとおりです。

1. トップメニューで、「**[!UICONTROL ホーム]**」タブをクリックします。

   ジャーニーのリストが表示されます。 インターフェイスの詳細については、[ このページ ](../building-journeys/using-the-journey-designer.md) を参照してください。

   ![](../assets/journey30.png)

1. 「**[!UICONTROL 作成]**」をクリックして、新規のジャーニーを作成します。

   ![](../assets/journey31.png)

1. 右側に表示される設定ペインで、ジャーニーのプロパティを編集します。詳しくは、[このページ](../building-journeys/changing-properties.md)を参照してください。

   ![](../assets/journey32.png)

1. 最初に、イベントアクティビティを、パレットからキャンバスにドラッグ&amp;ドロップします。 アクティビティをダブルクリックして、キャンバスに追加することもできます。

   ![](../assets/journey33.png)

1. 他のアクティビティをドラッグ&amp;ドロップして設定します。 [ イベントアクティビティ ](../building-journeys/event-activities.md)、[ オーケストレーションアクティビティについて ](../building-journeys/about-orchestration-activities.md)、および [ アクションアクティビティについて ](../building-journeys/about-action-activities.md) のページを参照してください。

   ![](../assets/journey34.png)

1. ジャーニーは自動的に保存されます。 ジャーニーをテストし公開します。 [ ジャーニーのテスト ](../building-journeys/testing-the-journey.md) および [ ジャーニーの公開 ](../building-journeys/publishing-the-journey.md) を参照してください。

   ![](../assets/journey36.png)

## ジャーニーの終了 {#ending_a_journey}

個人のジャーニーは、次の 2 つの理由で終了します。

* その人物がアクティビティの最後のパスに到達した。この最後のアクティビティは、終了アクティビティまたは別のアクティビティにすることができます。必ずしも終了アクティビティでパスを終わらせなくても構いません。[このページ](../building-journeys/end-activity.md)を参照してください。
* その人物が条件アクティビティ（または条件を含む待機アクティビティ）に到達したが、どの条件にも一致しない。

再エントリが許可されているジャーニーの場合、その人物は再度エントリすることができます。詳しくは、[このページ](../building-journeys/changing-properties.md)を参照してください。

ジャーニーは、次の理由でクローズすることがあります。

* 「**[!UICONTROL 新規エントリに対してクローズ]**」ボタンを使用して手動でジャーニーをクローズする。
* ジャーニーの終了日に達しました。

（上記の理由のいずれかにより）ジャーニーをクローズした場合、ステータスは「**[!UICONTROL クローズ]**」になります。ジャーニーは、個人が新規にエントリするのを停止します。既にジャーニーにエントリしている人は、通常どおりにジャーニーを完了することができます。デフォルトのグローバルタイムアウトである 30 日が経過すると、ジャーニーは&#x200B;**完了**&#x200B;ステータスに切り替わります。この[節](../building-journeys/changing-properties.md#entrance)を参照してください。

必要に応じて、ジャーニー内のすべての個人の進行を停止することもできます。ジャーニーを停止すると、ジャーニー内のすべての個人がタイムアウトになります。

ジャーニーを手動でクローズまたは停止する方法については、この [ 節 ](../building-journeys/terminating-a-journey.md) を参照してください。
