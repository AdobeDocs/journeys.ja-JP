---
product: adobe campaign
title: journeyStep イベントの ID フィールド
description: journeyStep イベントの ID フィールド
feature: Journeys
role: User
level: Intermediate
exl-id: 9c0ff38f-51dd-40bd-8c19-d142b9c23308
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '104'
ht-degree: 57%

---

# journeyStep イベントの ID フィールド {#sharing-identity-fields}


>[!CAUTION]
>
>**Adobe Journey Optimizerをお探しですか** Journey Optimizerのドキュメントについては、[ こちら ](https://experienceleague.adobe.com/ja/docs/journey-optimizer/using/ajo-home){target="_blank"} をクリックしてください。
>
>
>_このドキュメントでは、Journey Optimizerに置き換えられた従来のJourney Orchestration マテリアルについて説明します。 Journey OrchestrationやJourney Optimizerへのアクセスに関するご質問は、アカウントチームにお問い合わせください。_


この Mixin は、journeyStepEventに固有です。このイベントはジャーニーと関係があり、identityMap を持たず、（存在する場合）プロファイル ID を示しています。

journeyStepEvent の場合、ID に関連するフィールドも追加する必要があります。

## profileID

プロファイル識別子情報

型：文字列

## profileNamespace

プロファイル識別子の名前空間

型：文字列
