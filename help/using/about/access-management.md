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
workflow-type: tm+mt
source-wordcount: '297'
ht-degree: 6%

---


# アクセス管理{#concept_rfj_wpt_52b}

## アクセス管理について {#about-access-management}

製品プロファイルは、組織内で同じ権限を共有するユーザーのセットに割り当てられます。

管理コンソールでは、次の既製の製品プロファイルのいずれかをユーザーに割り当てることができます。

* **[!UICONTROL 制限付きアクセスユーザ]**: ジャーニーおよびレポートに対する読み取り専用アクセス権を持つユーザー。 この製品プロファイルには、次の権限が含まれます。
   * ジャーニーを読む
   * レポートの読み取り

* **[!UICONTROL 管理者]**: ジャーニー、イベントおよびレポートを管理できる、管理メニューへのアクセス権を持つユーザー。 この製品プロファイルには、次の権限が含まれます。
   * ジャーニーの管理と実行
   * イベント、データソースおよびアクションの管理
   * レポートの管理
   >[!NOTE]
   >
   >**[!UICONTROL Adobe Campaignプロファイル]** は、Administratorsのみで、トランザクションメッセージング（またはメッセージングテンプレート）の作成、編集、および公開を可能にします。 この製品プロファイルは、Adobe Campaign標準を使用してジャーニーでメッセージを送信する場合に必要です。

* **[!UICONTROL Standard User]**: jurney managementなどの基本的なアクセス権を持つユーザー。 この製品プロファイルには、次の権限が含まれます。
   * ジャーニーの管理と実行
   * レポートの管理

権限とJourney Orchestrationの様々な機能の互換性 [は](../assets/do-not-localize/acs_rights_journeys.pdf) 、次のとおりです。

## 製品プロファイルの割り当て {#assigning-product-profile}

製品プロファイルは管理コンソールで管理します。 For more on this, refer to the [Admin Console documentation](https://helpx.adobe.com/jp/enterprise/managing/user-guide.html).

製品プロファイルをJourney Orchestrationにアクセスするように割り当てるには：

1. 管理コンソールで、「 **[!UICONTROL Jureny orchestration]**」を選択します。

   ![](../assets/user_management.png)

1. 新しいユーザーをリンクする製品プロファイルを選択します。

   ![](../assets/user_management_2.png)

1. 「 **** user追加」をクリックします。

   また、新しいユーザーをユーザーグループに追加して、共有された権限のセットを微調整することもできます。 詳しくは、この[ページ](https://helpx.adobe.com/enterprise/using/user-groups.html)を参照してください。

   ![](../assets/user_management_3.png)

1. 新しいユーザーの電子メールアドレスを入力し、「 **[!UICONTROL 保存]**」をクリックします。

   ![](../assets/user_management_4.png)

その後、ユーザーは、Journey Orchestrationインスタンスにリダイレクトする電子メールを受け取る必要があります。