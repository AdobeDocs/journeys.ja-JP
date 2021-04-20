---
product: adobe campaign
solution: Journey Orchestration
title: イベントについて
description: イベントの詳細
feature: Journeys
role: Business Practitioner
level: Intermediate
translation-type: tm+mt
source-git-commit: f73e357d8947997f7f5872efa6a5ef4f51bc63a9
workflow-type: tm+mt
source-wordcount: '357'
ht-degree: 49%

---


# 一般原則 {#concept_gfj_fqt_52b}

>[!CONTEXTUALHELP]
>id="jo_events"
>title="イベントについて"
>abstract="イベントは人と結び付いています。人の行動や人に関連した出来事に関する。 これは、[!DNL Journey Orchestration] が次のベストアクションを調整するためにジャーニーでリッスンするものです。"

イベントは人と結び付いています。イベントは、人の行動（例えば、製品の購入、ショップへの訪問、web サイトからの退出など）、または、人にリンクされて発生した何か（例えば、10,000 ロイヤルティポイントへの到達）に関連しています。これは、[!DNL Journey Orchestration] が次のベストアクションを調整するためにジャーニーでリッスンするものです。

この設定は&#x200B;**必須**&#x200B;です。[!DNL Journey Orchestration] はイベントをリッスンするように設計されており、常に&#x200B;**技術ユーザー**&#x200B;が実行します。

イベントの設定を使用すると、[!DNL Journey Orchestration] がイベントとして受け取る情報を定義できます。1 つのジャーニーの異なる手順で複数のイベントを使用できます。また、同じイベントを複数のジャーニーで使用できます。

ドラフトジャーニーまたはライブジャーニーで使用されるイベントを編集する場合、名前と説明の変更およびペイロードフィールドの追加のみが可能です。ジャーニーの中断を避けるために、ドラフトジャーニーやライブジャーニーの編集は厳しく制限されています。

次の2種類のイベントを定義できます。

* **ルール** ベースイベント：このタイプのイベントでは、eventIDは生成されません。単純な式エディタを使用して、ジャーニーをトリガーする関連イベントを特定するためにシステムで使用されるルールを定義するだけです。 このルールは、イベントペイロードで使用可能な任意のフィールドに基づくことができます。例えば、プロファイルの場所や、プロファイルの買い物かごに追加された項目数などです。

   >[!CAUTION]
   >
   >キャップルールは、ルールベースのイベントに対して定義されます。 特定の組織(ORG)でジャーニーが処理できる正規イベントの数を1秒あたり5,000個に制限します。 Journey OrchestrationのSLAに対応しています。 この[ページ](https://helpx.adobe.com/legal/product-descriptions/journey-orchestration.html)を参照してください。

* **System-** generatedevents:これらのイベントにはeventIDが必要です。このeventIDフィールドは、イベントの作成時に自動的に生成されます。 イベントをプッシュするシステムはIDを生成しないでください。ペイロードプレビューで使用可能なIDを渡す必要があります。

イベントの作成方法については、[ページ](../event/about-creating.md)を参照してください。

