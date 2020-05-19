---
title: 'Journey OrchestrationイベントのExperienceEventスキーマについて '
description: 'Journey OrchestrationイベントのExperienceEventスキーマについて説明します。 '
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
source-git-commit: 9b8d4bebe024e90733cb1ae6d31b36fb6ce4b606
workflow-type: tm+mt
source-wordcount: '327'
ht-degree: 0%

---



# Journey OrchestrationイベントのExperienceEventスキーマについて

Jureny Orchestrationイベントは、XDM Experienceイベントで、Streaming Ingestionを介してAdobe Experience Platformに送信されます。

そのため、Jeurney Orchestrationのイベントを設定するための重要な前提条件は、PlatformのExperience Data Model（またはXDM）およびXDM Experienceイベントスキーマの作成方法、およびXDM形式のデータをPlatformにストリーミングする方法に精通していることです。

## 遍歴オーケストレーションイベントのスキーマ要件

Jureny Orchestrationのイベントを設定する最初の手順は、イベントを表すXDMスキーマと、イベントのインスタンスを記録するためにプラットフォーム上で作成されたデータセットを確実に作成することです。 イベントのデータセットは必ずしも必要ではありませんが、特定のデータセットに送信すると、イベントのイベント履歴を今後の参照と分析のために維持できるので、常に有効です。 お使いのイベントに適したスキーマとデータセットがまだない場合は、これらのタスクの両方をプラットフォームのWebインターフェイスで実行できます。

![](../assets/schema1.png)

Jureny Orchestrationイベントに使用されるXDMスキーマは、以下の要件を満たす必要があります。

* スキーマは、XDM ExperienceEventクラスである必要があります。

![](../assets/schema2.png)

* スキーマにオーケストレーションイベントIDミックスインを含める必要があります。 Jureny Orchestrationは、このフィールドを使用して、ジャーニーで使用されるイベントを識別します。

![](../assets/schema3.png)

* イベントの件名を識別するIDフィールドを宣言します。 IDが指定されていない場合は、IDマップを使用できます。 これは推奨されません。

![](../assets/schema4.png)

* このデータを後でJeurneyで参照できるようにする場合は、プロファイルのスキーマとデータセットをマークします。

![](../assets/schema5.png)

![](../assets/schema6.png)

* イベントに関する情報、イベントの生成元のデバイス、場所、イベントに関連するその他の有意義な状況など、ユーザーに含めたいその他のコンテキストデータを取り込むためのデータフィールドを自由に含めてください。

![](../assets/schema7.png)

![](../assets/schema8.png)