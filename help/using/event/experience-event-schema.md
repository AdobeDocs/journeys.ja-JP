---
product: adobe campaign
title: 'イベントイベントのExperienceEventJourney Orchestrationについて '
description: 'イベントイベントのExperienceEventスキーマについてJourney Orchestration '
feature: ジャーニー
role: User
level: Intermediate
exl-id: ffec0d42-8632-4806-97df-da2a2372ca53
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '325'
ht-degree: 56%

---

# [!DNL Journey Orchestration] イベントの ExperienceEvent スキーマについて

[!DNL Journey Orchestration] イベントは、ストリーミング取得経由でAdobe Experience Platformに送信されるXDMエクスペリエンスイベントです。

そのため、[!DNL Journey Orchestration]のイベントを設定するための重要な前提条件は、Adobe Experience Platformのエクスペリエンスデータモデル(XDM)とXDMエクスペリエンスイベントスキーマの作成方法、およびXDM形式のデータをAdobe Experience Platformにストリーミングする方法に精通していることです。

## [!DNL Journey Orchestration] イベントのスキーマ要件

[!DNL Journey Orchestration]のイベントを設定する最初の手順は、イベントを表すXDMスキーマと、そのイベントのインスタンスをAdobe Experience Platformに記録するために作成されたデータセットを確実に作成することです。 イベント用データセットは必ずしも必要ではありませんが、特定のデータセットにイベントを送信すると、ユーザーのイベント履歴を保持して後から参照および分析できるので便利です。イベントに適したスキーマとデータセットをまだ持っていない場合は、これらの両方のタスクをAdobe Experience Platform Webインターフェイスで実行できます。

![](../assets/schema1.png)

[!DNL Journey Orchestration] イベントに使用される XDM スキーマは、以下の要件を満たす必要があります。

* スキーマは、XDM ExperienceEvent クラスである必要があります。

   ![](../assets/schema2.png)

* システム生成イベントの場合、スキーマにオーケストレーション eventID Mixin を含める必要があります。[!DNL Journey Orchestration] はこのフィールドを使用して、ジャーニーで使用されるイベントを識別します。

   ![](../assets/schema3.png)

* イベントの件名を識別するための ID フィールドを宣言します。ID が指定されていない場合は、ID マップを使用できます。この方法は推奨されません。

   ![](../assets/schema4.png)

* このデータを後からジャーニーで参照できるようにする場合は、プロファイルのスキーマとデータセットをマークします。

   ![](../assets/schema5.png)

   ![](../assets/schema6.png)

* ユーザーに関する情報、イベントの生成元のデバイス、場所、イベントに関連するその他の有意義な状況など、イベントに含めたいその他のコンテキストデータを取り込むためのデータフィールドを自由に含めることができます。

   ![](../assets/schema7.png)

   ![](../assets/schema8.png)
