---
product: adobe campaign
solution: Journey Orchestration
title: データソースの設定
description: ジャーニーのシンプルなユースケースでデータソースを設定する方法を説明します
translation-type: ht
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: ht
source-wordcount: '140'
ht-degree: 100%

---


# データソースの設定{#concept_ax3_bcy_w2b}

このユースケースでは、メッセージにパーソナライゼーションデータを使用します。また、受信者が女性であるかどうかを確認する必要があります。この情報は、リアルタイム顧客プロファイルデータベースに保存されています。**技術ユーザー**&#x200B;は、これらのフィールドが組み込みの Adobe Experience Platform データソースで定義されていることを確認する必要があります。

データソースの設定について詳しくは、[このページ](../datasource/about-data-sources.md)を参照してください。

1. 上部のメニューで、「**[!UICONTROL データソース]**」タブをクリックし、組み込みの Adobe Experience Platform データソースを選択します。

   ![](../assets/journey23.png)

1. フィールドグループで、次のフィールドが選択されていることを確認します。

   * _ユーザー／姓名／名_
   * _ユーザー／姓名／姓_
   * _ユーザー／性別_
   * _個人用メール／ アドレス_

1. 「**[!UICONTROL 保存]**」をクリックします。

データソースが設定され、ジャーニーで使用できる状態になります。
