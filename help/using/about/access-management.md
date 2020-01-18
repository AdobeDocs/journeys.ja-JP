---
title: アクセス管理
description: アクセス管理の詳細
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: tm+mt
source-git-commit: fed6fd8d8ee497ec47727f7297dc72f319fabe27

---


# アクセス管理{#concept_rfj_wpt_52b}

## アクセス管理について {#about-access-management}

製品プロファイルは、組織内で同じ権限を共有する一連のユーザーに割り当てられます。

管理コンソールで、次の標準搭載された製品プロファイルのいずれかをユーザーに割り当てることができます。

* **[!UICONTROL Limited Access User]**:ジャーニーとレポートに読み取り専用でアクセスできるユーザー。 この製品プロファイルには、次の権限が含まれます。
   * ジャーニーを読む
   * レポートの読み取り

* **[!UICONTROL Administrators]**:管理メニューにアクセスできるユーザーで、ジャーニー、イベントおよびレポートを管理できます。 この製品プロファイルには、次の権限が含まれます。
   * ジャーニーの管理と実行
   * イベント、データソースおよびアクションの管理
   * レポートの管理
   >[!NOTE]
   >
   >**[!UICONTROL Administrators]**は、Adobe Campaign Standardでトランザクションメッセージング（またはメッセージングテンプレート）の作成、編集、および公開を可能にする唯一の製品プロファイルです。 この製品プロファイルは、Adobe Campaign Standardを使用してジャーニーでメッセージを送信する場合に必要です。

* **[!UICONTROL Standard User]**:ジャーニー管理などの基本的なアクセス権を持つユーザー。 この製品プロファイルには、次の権限が含まれます。
   * ジャーニーの管理と実行
   * レポートの管理

権利とJargeny Orchestrationの [様々な機能の互換性は](../assets/do-not-localize/acs_rights_journeys.pdf) 、次のとおりです。

## 製品プロファイルの割り当て {#assigning-product-profile}

製品プロファイルは管理コンソールで管理されます。 For more on this, refer to the [Admin Console documentation](https://helpx.adobe.com/enterprise/managing/user-guide.html).

Jureny Orchestrationにアクセスするユーザーの製品プロファイルを割り当てるには：

1. 管理コンソールで、を選択しま **[!UICONTROL Journey orchestration]**す。

   ![](../assets/user_management.png)

1. 新しいユーザーをリンクする製品プロファイルを選択します。

   ![](../assets/user_management_2.png)

1. クリック **[!UICONTROL Add user]**.

   また、新しいユーザーをユーザーグループに追加して、共有された権限のセットを微調整することもできます。 詳しくは、この[ページ](https://helpx.adobe.com/enterprise/using/user-groups.html)を参照してください。

   ![](../assets/user_management_3.png)

1. 新しいユーザーの電子メールアドレスを入力し、をクリックしま **[!UICONTROL Save]**す。

   ![](../assets/user_management_4.png)

次に、Jargeny Orchestrationインスタンスにリダイレクトする電子メールをユーザーに受信する必要があります。