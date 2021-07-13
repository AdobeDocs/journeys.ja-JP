---
product: adobe campaign
title: データソースの設定
description: ジャーニーのシンプルなユースケースでデータソースを設定する方法を説明します
feature: ジャーニー
role: User
level: Intermediate
exl-id: 87f63d7d-b7d9-4243-a5ce-8948939f3d93
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '141'
ht-degree: 100%

---

# データソースの設定{#concept_ax3_bcy_w2b}

このユースケースでは、メッセージにパーソナライゼーションデータを使用します。また、受信者が女性であるかどうかを確認する必要があります。この情報は、リアルタイム顧客プロファイルデータベースに保存されています。**技術ユーザー**&#x200B;は、これらのフィールドが組み込みの Adobe Experience Platform データソースで定義されていることを確認する必要があります。

データソースの設定について詳しくは、[このページ](../datasource/about-data-sources.md)を参照してください。

1. 上部のメニューで、「**[!UICONTROL データソース]**」タブをクリックし、組み込みの Adobe Experience Platform データソースを選択します。

   ![](../assets/journey23.png)

1. フィールドグループで、次のフィールドが選択されていることを確認します。

   * _person > name > firstName_
   * _person > name > lastName_
   * _person > gender_
   * _personalEmail > address_

1. 「**[!UICONTROL 保存]**」をクリックします。

データソースが設定され、ジャーニーで使用できる状態になります。
