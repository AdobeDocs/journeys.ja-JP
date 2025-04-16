---
product: adobe campaign
title: データソースの設定
description: ジャーニーのシンプルなユースケースでデータソースを設定する方法を説明します
feature: Journeys
role: User
level: Intermediate
exl-id: 87f63d7d-b7d9-4243-a5ce-8948939f3d93
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: ht
source-wordcount: '188'
ht-degree: 100%

---

# データソースの設定{#concept_ax3_bcy_w2b}


>[!CAUTION]
>
>**Adobe Journey Optimizer をお探しですか**？Journey Optimizer のドキュメントについて詳しくは、[こちら](https://experienceleague.adobe.com/ja/docs/journey-optimizer/using/ajo-home){target="_blank"}をクリックしてください。
>
>
>_このドキュメントは、Journey Optimizer に置き換えられた従来の Journey Orchestration 資料を参照しています。Journey Orchestration または Journey Optimizer へのアクセスについてご質問がある場合は、アカウントチームにお問い合わせください。_


このユースケースでは、メッセージにパーソナライゼーションデータを使用します。また、受信者が女性であるかどうかを確認する必要があります。この情報は、リアルタイム顧客プロファイルデータベースに保存されています。**技術ユーザー**&#x200B;は、これらのフィールドが組み込みの Adobe Experience Platform データソースで定義されていることを確認する必要があります。

データソースの設定について詳しくは、[このページ](../datasource/about-data-sources.md)を参照してください。

1. メニューウィンドウで、「**[!UICONTROL 管理者]**」を選択します。「**[!UICONTROL データソース]**」セクションで、「**[!UICONTROL 管理]**」をクリックします。
1. 組み込みの Adobe Experience Platform データソースを選択します。

   ![](../assets/journey23.png)

1. フィールドグループで、次のフィールドが選択されていることを確認します。

   * _person > name > firstName_
   * _person > name > lastName_
   * _person > gender_
   * _personalEmail > address_

1. 「**[!UICONTROL 保存]**」をクリックします。

データソースが設定され、ジャーニーで使用できる状態になります。
