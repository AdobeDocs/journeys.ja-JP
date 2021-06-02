---
product: adobe campaign
title: 'イベントイベントのExperienceEventJourney Orchestrationについて '
description: 'イベントイベントのExperienceEventスキーマについてJourney Orchestration '
feature: ジャーニー
role: Business Practitioner
level: Intermediate
exl-id: ffec0d42-8632-4806-97df-da2a2372ca53
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '325'
ht-degree: 0%

---

# [!DNL Journey Orchestration]イベントのExperienceEventスキーマについて

[!DNL Journey Orchestration] イベントは、ストリーミング取得経由でAdobe Experience Platformに送信されるXDMエクスペリエンスイベントです。

そのため、[!DNL Journey Orchestration]のイベントを設定するための重要な前提条件は、Adobe Experience Platformのエクスペリエンスデータモデル(XDM)とXDMエクスペリエンスイベントスキーマの作成方法、およびXDM形式のデータをAdobe Experience Platformにストリーミングする方法に精通していることです。

## [!DNL Journey Orchestration]イベントのスキーマ要件

[!DNL Journey Orchestration]のイベントを設定する最初の手順は、イベントを表すXDMスキーマと、そのイベントのインスタンスをAdobe Experience Platformに記録するために作成されたデータセットを確実に作成することです。 イベントのデータセットは厳密に必要ではありませんが、イベントを特定のデータセットに送信すると、ユーザーのイベント履歴を今後の参照や分析に備えることができるので、常に有効です。 イベントに適したスキーマとデータセットをまだ持っていない場合は、これらの両方のタスクをAdobe Experience Platform Webインターフェイスで実行できます。

![](../assets/schema1.png)

[!DNL Journey Orchestration]イベントに使用されるXDMスキーマは、次の要件を満たす必要があります。

* スキーマは、XDM ExperienceEventクラスのものである必要があります。

   ![](../assets/schema2.png)

* システム生成イベントの場合、スキーマにオーケストレーションeventID mixinを含める必要があります。 [!DNL Journey Orchestration] は、このフィールドを使用して、ジャーニーで使用されるイベントを識別します。

   ![](../assets/schema3.png)

* イベントの件名を識別するIDフィールドを宣言します。 IDが指定されていない場合は、IDマップを使用できます。 これは推奨されません。

   ![](../assets/schema4.png)

* このデータを後でジャーニーで参照できるようにする場合は、プロファイルのスキーマとデータセットをマークします。

   ![](../assets/schema5.png)

   ![](../assets/schema6.png)

* ユーザーに関する情報、イベントの生成元となったデバイス、場所、イベントに関連するその他の意味のある状況など、イベントに含める他のコンテキストデータを取り込むためのデータフィールドを自由に含めます。

   ![](../assets/schema7.png)

   ![](../assets/schema8.png)
