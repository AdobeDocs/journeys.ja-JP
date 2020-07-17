---
title: 疲労スコアの活用
description: ジャーニーで疲労スコアを活用する方法を学びます。
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
source-git-commit: eb4474313d3c0470448f9959ed757902ef0ecd2a
workflow-type: tm+mt
source-wordcount: '255'
ht-degree: 6%

---


# ジャーニーAIの活用 {#concept_dsh_1ry_wfb}

この使用例では、疲労スコアを活用して、旅行中に顧客に過度の勧誘をしないようにする方法を示します。

>[!NOTE]
>
>予測疲労スコア機能は、Adobe Campaign Standardデータサービス機能を使用するお客様のみ利用できます。

## イベントの設定 {#section_ptb_ws1_ffb}

に示す手順に従い [](../event/about-events.md)ます。

## データソースの設定 {#section_o3n_4yy_wfb}

次の手順を実行して、組み込みデータソースの疲労スコアフィールドを選択します。

1. 上部のメニューで、「 **[!UICONTROL データソース]** 」タブをクリックし、組み込みAdobe Experience Platformのデータソースを選択します。

   ![](../assets/journey23.png)

1. 使用事例に必要なフィールドが選択されていることを確認します。
1. 「 **[!UICONTROL 新しいフィールド]**&#x200B;をクリックし、プロファイル **[!UICONTROL グループモデルを選択して、]** を追加します。 **[!UICONTROL fatigueLevel]** fatigueScore ****__ Fields 19

   ![](../assets/journeyuc3_1.png)

1. 「**[!UICONTROL 保存]**」をクリックします。

## ジャーニーの構築 {#section_uzm_pyy_wfb}

遍歴を作成、検証、公開するには、の手順に従い [](../building-journeys/journey.md)ます。

使用事例では、 **[!UICONTROL fatigueLevel]** フィールドを活用しています。 fatigueScore **** フィールドを使用することもできます。

次の手順を実行して、旅程で疲労レベルを活用します。

1. イベント追加と条件を持っています。

   ![](../assets/journeyuc2_14.png)

1. 「 **[!UICONTROL Data Source Condition]** 」タイプを選択し、「 **[!UICONTROL 式]** 」フィールドをクリックします。

   ![](../assets/journeyuc3_2.png)

1. シンプルな式エディターで、 **[!UICONTROL fatigueLevel]** (_ExperiencePlatformDataSource/JeurneryAIScores/プロファイル/jeurneyAI/emailScore/fatigue_)フィールドを探し、右にドロップして、次の条件を作成します。 &quot;fatigueLevel is equal to &quot;Low&quot;. 「**[!UICONTROL OK]**」をクリックします。

   ![](../assets/journeyuc3_3.png)

   詳細式は次のとおりです。

   ```
   #{ExperiencePlatformDataSource.JourneyAIScores.Profile.journeyAI.emailScore.fatigue.fatigueLevel} == "low"
   ```

1. この条件で、中疲労レベルと高疲労レベルを示す2つのパスを作成します。

   ![](../assets/journeyuc3_4.png)

1. 疲労レベルごとに異なるアクションを追加できるようになりました。

   ![](../assets/journeyuc3_5.png)
