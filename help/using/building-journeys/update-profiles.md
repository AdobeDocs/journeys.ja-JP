---
product: adobe campaign
title: プロファイルを更新
description: プロファイルを更新
feature: Journeys
role: User
level: Intermediate
exl-id: eaf2c795-0920-4b9c-9f06-801e43c1844b
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '392'
ht-degree: 88%

---

# プロファイルを更新 {#update-profile}


>[!CAUTION]
>
>**Adobe Journey Optimizerをお探しですか** Journey Optimizerのドキュメントについては、[ こちら ](https://experienceleague.adobe.com/ja/docs/journey-optimizer/using/ajo-home){target="_blank"} をクリックしてください。
>
>
>_このドキュメントでは、Journey Optimizerに置き換えられた従来のJourney Orchestration マテリアルについて説明します。 Journey OrchestrationやJourney Optimizerへのアクセスに関するご質問は、アカウントチームにお問い合わせください。_


「**[!UICONTROL プロファイルを更新]**」アクションアクティビティを使用すると、イベントやデータソースから得られた情報または特定の値を使用して、既存の Adobe Experience Platform のプロファイルを更新できます。

## 重要な注意事項

* 「**プロファイルを更新**」アクションは、名前空間を持つイベントで開始されるジャーニーでのみ使用できます。
* このアクションでは、既存のフィールドのみが更新され、新しいプロファイルフィールドは作成されません。
* 「**プロファイルを更新**」アクションを使用して、購入などのエクスペリエンスイベントを生成することはできません。
* 他のアクションのように、エラーやタイムアウトの場合の代替パスを定義でき、2 つのアクションを並行して配置することはできません。
* Platform に送信される更新リクエストは高速ですが、1 秒以内や即時というわけではありません。通常は数秒かかりますが、もっと時間がかかる場合もあり、保証はありません。そのため、例えば、アクションで使用している「フィールド 1」が、そのアクションの直前に配置された「プロファイルを更新」アクションで更新される場合でも、更新された「フィールド 1」が必ず使用されるとは限りません。
* テストモードでは、プロファイルの更新はシミュレートされません。更新はテストプロファイルに対して実行されます。
* この&#x200B;**プロファイルを更新**&#x200B;アクティビティは、定義済みリストとして定義された XDM フィールドをサポートしていません。

## プロファイル更新の使用

1. ジャーニーのデザインをイベントから始めます。この[節](../building-journeys/journey.md)を参照してください。

1. パレットの「**アクション**」セクションで、「**プロファイルを更新**」アクティビティをキャンバスにドロップします。

   ![](../assets/profileupdate0.png)

1. リストからスキーマを選択します。

1. 「**フィールド**」をクリックして、更新するフィールドを選択します。選択できるフィールドは 1 つだけです。

   ![](../assets/profileupdate2.png)

1. リストからデータセットを選択します。

   >[!NOTE]
   >
   >**プロファイルの更新**&#x200B;アクションは、プロファイルデータをリアルタイムで更新しますが、データセットは更新しません。データセットの選択は、プロファイルがデータセットに関連するレコードであるため、必要です。

1. 「**値**」フィールドをクリックして、使用する値を定義します。

   * 簡単な式エディターを使用して、データソースまたは受信イベントからフィールドを選択できます。

     ![](../assets/profileupdate4.png)

   * 特定の値を定義する場合や高度な機能を利用する場合は、「**詳細設定モード**」をクリックします。

     ![](../assets/profileupdate3.png)

これで、「**プロファイルを更新**」を設定できました。

![](../assets/profileupdate1.png)
