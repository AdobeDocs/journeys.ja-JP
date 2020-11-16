---
title: データソースの設定
description: ジャーニーのシンプルなユースケースでデータソースを設定する方法を説明します
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: tm+mt
source-git-commit: bcb8a71a27e2b9e37af7d0260cec04ed0fda24ee
workflow-type: tm+mt
source-wordcount: '140'
ht-degree: 92%

---


# データソースの設定{#concept_ax3_bcy_w2b}

このユースケースでは、メッセージにパーソナライゼーションデータを使用します。また、受信者が女性であるかどうかを確認する必要があります。この情報は、リアルタイム顧客プロファイルデータベースに保存されています。**技術ユーザー**&#x200B;は、これらのフィールドが組み込みの Adobe Experience Platform データソースで定義されていることを確認する必要があります。

For additional information on data source configuration, refer to [this page](../datasource/about-data-sources.md).

1. 上部のメニューで、「**[!UICONTROL データソース]**」タブをクリックし、組み込みの Adobe Experience Platform データソースを選択します。

   ![](../assets/journey23.png)

1. フィールドグループで、次のフィールドが選択されていることを確認します。

   * _ユーザー／姓名／名_
   * _ユーザー／姓名／姓_
   * _ユーザー／性別_
   * _個人用メール／ アドレス_

1. 「**[!UICONTROL 保存]**」をクリックします。

データソースが設定され、ジャーニーで使用できる状態になります。
