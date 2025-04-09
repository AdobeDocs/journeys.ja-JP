---
product: adobe campaign
title: イベントについて
description: イベントについて学ぶ
feature: Journeys
role: User
level: Intermediate
exl-id: 2115ab1d-1084-4429-8315-0357c8525c47
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '446'
ht-degree: 90%

---

# 一般原則 {#concept_gfj_fqt_52b}


>[!CAUTION]
>
>**Adobe Journey Optimizerをお探しですか** Journey Optimizerのドキュメントについては、[ こちら ](https://experienceleague.adobe.com/ja/docs/journey-optimizer/using/ajo-home){target="_blank"} をクリックしてください。
>
>
>_このドキュメントでは、Journey Optimizerに置き換えられた従来のJourney Orchestration マテリアルについて説明します。 Journey OrchestrationやJourney Optimizerへのアクセスに関するご質問は、アカウントチームにお問い合わせください。_



>[!CONTEXTUALHELP]
>id="jo_events"
>title="イベントについて"
>abstract="イベントは人物と結び付いています。人物の行動や、人物とのつながりで発生する事象に関連しています。[!DNL Journey Orchestration] はジャーニーでこのイベントをリッスンして、次の最適なアクションを編成します。"

イベントは人物と結び付いています。これは、人物の行動（例えば、人物が製品を購入した、ショップを訪問した、web サイトを離脱したなど）または人物と結び付いて起こったこと（例えば、人物が 10,000 ロイヤルティポイントに到達したなど）に関連しています。[!DNL Journey Orchestration] はジャーニーでこのイベントをリッスンして、次の最適なアクションを編成します。

この設定は&#x200B;**必須**&#x200B;です。[!DNL Journey Orchestration] はイベントをリッスンするように設計されており、常に&#x200B;**技術ユーザー**&#x200B;が実行します。

イベントの設定を使用すると、[!DNL Journey Orchestration] がイベントとして受け取る情報を定義できます。 1 つのジャーニーの異なる手順で複数のイベントを使用できます。また、同じイベントを複数のジャーニーで使用できます。

ドラフトジャーニーまたはライブジャーニーで使用されるイベントを編集する場合、名前と説明の変更およびペイロードフィールドの追加のみが可能です。ジャーニーの中断を避けるために、ドラフトジャーニーやライブジャーニーの編集は厳しく制限されています。

次の 2 種類のイベントを定義できます。

* **ルールベース**&#x200B;イベント：このタイプのイベントでは、eventID は生成されません。簡単な式エディターを使用して、システムがジャーニーをトリガーする関連イベントの特定に使用するルールを定義します。このルールは、イベントペイロードで使用可能な任意のフィールドに基づくことができます。例えば、プロファイルの場所や、プロファイルの買い物かごに追加された項目数などです。

  >[!CAUTION]
  >
  >キャッピングルールは、ルールベースのイベントに対して定義します。ジャーニーが処理できる対象イベントの数を、特定の組織（ORG）で 1 秒あたり 5,000 個に制限します。これは Journey Orchestration の SLA に対応しています。 この[ページ](https://helpx.adobe.com/jp/legal/product-descriptions/journey-orchestration.html)を参照してください。

* **システム生成**&#x200B;イベント：このイベントでは eventID が必要です。eventID フィールドは、イベントの作成時に自動的に生成されます。イベントをプッシュするシステムでは、ID を生成せずに、ペイロードプレビューにある ID を渡す必要があります。

Journey Orchestrationでは、イベントを Adobe Experience Platform にストリーミングまたはバッチ処理する必要があります。このデータは、必ずしもリアルタイムプロファイルに移動する必要はありません。イベントを別のジャーニーでセグメント化や参照に使用する場合は、プロファイルのデータセットを有効にすることをお勧めします。

イベントの作成方法については、この[ページ](../event/about-creating.md)を参照してください。
