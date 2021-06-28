---
product: adobe campaign
title: 疲労スコアの活用
description: ジャーニーで疲労スコアを活用する方法を説明します
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: ht
source-wordcount: '268'
ht-degree: 100%

---


# ジャーニー AI の活用 {#concept_dsh_1ry_wfb}

このユースケースでは、疲労スコアを活用して、ジャーニーで顧客に過度の勧誘をしないようにする方法を示します。

>[!NOTE]
>
>予測疲労スコア機能は、[Adobe Experience Platform データコネクタ](https://docs.adobe.com/content/help/ja-JP/campaign-standard/using/developing/mapping-campaign-and-aep-data/aep-about-data-connector.html)を使用するお客様のみ利用できます。

## イベントの設定 {#section_ptb_ws1_ffb}

手順については、[このページ](../event/about-events.md)を参照してください。

## データソースの設定 {#section_o3n_4yy_wfb}

次の手順を実行して、組み込みデータソースの疲労スコアフィールドを選択します。

1. 上部のメニューで、「**[!UICONTROL データソース]**」タブをクリックし、組み込みの Adobe Experience Platform データソースを選択します。

   ![](../assets/journey23.png)

1. ユースケースに必要なフィールドが選択されていることを確認します。
1. 「**[!UICONTROL 新しいフィールドグループを追加]**」をクリックし、**[!UICONTROL プロファイル]**&#x200B;モデルを選択して、「**[!UICONTROL fatigueLevel]**」フィールドおよび「**[!UICONTROL fatigueScore]**」フィールドを追加します（_journeyAI／emailScore／疲労_&#x200B;の下）。

   ![](../assets/journeyuc3_1.png)

1. 「**[!UICONTROL 保存]**」をクリックします。

## ジャーニーの構築 {#section_uzm_pyy_wfb}

ジャーニーを作成、検証、公開するには、[このページ](../building-journeys/journey.md)の手順に従います。

このユースケースでは、「**[!UICONTROL fatigueLevel]**」フィールドを活用しています。「**[!UICONTROL fatigueScore]**」フィールドを使用することもできます。

次の手順を実行して、ジャーニーで疲労レベルを活用します。

1. ジャーニーにイベントと条件を追加します。

   ![](../assets/journeyuc2_14.png)

1. 「**[!UICONTROL データソースの条件]**」タイプを選択し、「**[!UICONTROL 式]**」フィールドをクリックします。

   ![](../assets/journeyuc3_2.png)

1. シンプルな式エディターに、**[!UICONTROL fatigueLevel]**（_ExperiencePlatformDataSource／JourneyAIScores／プロファイル／journeyAI／emailScore／疲労_）フィールドを探し、右にドロップして、「fatigueLevel が「Low」に等しい」という条件を作成します。「**[!UICONTROL OK]**」をクリックします。

   ![](../assets/journeyuc3_3.png)

   詳細式は次のとおりです。

   ```
   #{ExperiencePlatformDataSource.JourneyAIScores.Profile.journeyAI.emailScore.fatigue.fatigueLevel} == "low"
   ```

1. この条件で、中疲労レベルと高疲労レベルを示す他の 2 つのパスを作成します。

   ![](../assets/journeyuc3_4.png)

1. 疲労レベルごとに異なるアクションを追加できるようになりました。

   ![](../assets/journeyuc3_5.png)
