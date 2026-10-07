---
product: adobe campaign
title: データソースの設定
description: ジャーニーのシンプルなユースケースでデータソースを設定する方法を説明します
feature: Journeys
role: User
level: Intermediate
exl-id: 87f63d7d-b7d9-4243-a5ce-8948939f3d93
product_v2:
  - id: cf67d108-ecf9-4fde-af49-3a3c39083bc8
    internal-label: Journey Orchestration
feature_v2:
  - id: 7de3230f-9523-5ba5-8d5c-2313288b27ef
    internal-label: Journeys
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
source-git-commit: 255cd6677e7c9ebff63ea9a1028a042c19e63ecc
workflow-type: tm+mt
source-wordcount: '199'
ht-degree: 100%
---
# データソースの設定{#concept_ax3_bcy_w2b}


>[!CAUTION]
>
>**Adobe Journey Optimizer をお探しですか**？ Journey Optimizer のドキュメントについて詳しくは、[こちら](https://experienceleague.adobe.com/ja/docs/journey-optimizer/using/ajo-home){target="_blank"}をクリックしてください。
>
>
>_このドキュメントは、Journey Optimizer に置き換えられた従来の Journey Orchestration 資料を参照しています。 Journey Orchestration または Journey Optimizer へのアクセスについてご質問がある場合は、アカウントチームにお問い合わせください。_


このユースケースでは、メッセージにパーソナライゼーションデータを使用します。 また、受信者が女性であるかどうかを確認する必要があります。 この情報は、リアルタイム顧客プロファイルデータベースに保存されています。 **技術ユーザー**&#x200B;は、これらのフィールドがビルトインの Adobe Experience Platform データソースで定義されていることを確認する必要があります。

データソースの設定について詳しくは、[このページ](../datasource/about-data-sources.md)を参照してください。

1. メニューウィンドウで、「**[!UICONTROL 管理者]**」を選択します。 「**[!UICONTROL データソース]**」セクションで、「**[!UICONTROL 管理]**」をクリックします。
1. 組み込みの Adobe Experience Platform データソースを選択します。

   ![](../assets/journey23.png)

1. フィールドグループで、次のフィールドが選択されていることを確認します。

   * _person > name > firstName_
   * _person > name > lastName_
   * _person > gender_
   * _personalEmail > address_

1. 「**[!UICONTROL 保存]**」をクリックします。

データソースが設定され、ジャーニーで使用できる状態になります。
