---
product: adobe campaign
solution: Journey Orchestration
title: 'Journey Orchestrationイベント用のExperienceEventスキーマについて '
description: 'Journey Orchestrationイベント用のExperienceEventスキーマについて説明します。 '
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '321'
ht-degree: 0%

---



# イベントのExperienceEventスキーマについて [!DNL Journey Orchestration]

[!DNL Journey Orchestration] イベントは、XDM Experienceイベントで、Streaming Ingestion経由でAdobe Experience Platformに送信されます。

イベントの設定に必要な重要な前提条件は、Adobe Experience PlatformのExperience Data Model（またはXDM）およびXDM Experienceイベントスキーマの作成方法、XDM形式のデータをAdobe Experience Platformにストリーミングする方法に精通していること [!DNL Journey Orchestration] です。

## [!DNL Journey Orchestration] イベントのスキーマ要件

のイベントを設定する最初の手順 [!DNL Journey Orchestration] は、イベントを表すXDMスキーマと、Adobe Experience Platform上のイベントのインスタンスを記録するために作成されたデータセットを確実に作成することです。 イベントのデータセットは必ずしも必要ではありませんが、特定のデータセットに送信すると、イベントのイベント履歴を今後の参照と分析のために維持できるので、常に有効です。 お使いのイベントに適したスキーマとデータセットがまだない場合は、これらのタスクはAdobe Experience PlatformのWebインターフェイスで実行できます。

![](../assets/schema1.png)

イベントに使用するXDMスキーマは、次の要件を満たす必要があり [!DNL Journey Orchestration] ます。

* スキーマは、XDM ExperienceEventクラスである必要があります。

   ![](../assets/schema2.png)

* スキーマにオーケストレーションイベントIDミックスインを含める必要があります。 [!DNL Journey Orchestration] このフィールドを使用して、ジャーニーで使用されるイベントを識別します。

   ![](../assets/schema3.png)

* イベントの件名を識別するためのIDフィールドを宣言します。 IDが指定されていない場合は、IDマップを使用できます。 これは推奨されません。

   ![](../assets/schema4.png)

* このデータを後でJeurneyで参照できるようにする場合は、プロファイルのスキーマとデータセットをマークします。

   ![](../assets/schema5.png)

   ![](../assets/schema6.png)

* イベントに関する情報、イベントの生成元のデバイス、場所、イベントに関連するその他の有意義な状況など、ユーザーに含めたいその他のコンテキストデータを取り込むためのデータフィールドを自由に含めてください。

   ![](../assets/schema7.png)

   ![](../assets/schema8.png)