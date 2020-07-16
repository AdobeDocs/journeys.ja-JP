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
source-git-commit: 94ef4e30d16b7d23dc029863fcd2d9f34173c433
workflow-type: tm+mt
source-wordcount: '917'
ht-degree: 3%

---


# アクセス管理{#concept_rfj_wpt_52b}

## アクセス管理について {#about-access-management}

[!DNL Journey Orchestration] ユーザーに一連の権限を割り当てて、ユーザーがアクセスできるインターフェイスの部分を定義できます。

管理者は、管理コンソールにアクセスできる管理者が管理できます。 管理コンソールについて詳しくは、この [ドキュメントを参照してください](https://helpx.adobe.com/jp/enterprise/managing/user-guide.html)。

アクセスするには、次の条件を満たす必要があ [!DNL Journey Orchestration]ります。

* の一部を参照してく [!DNL Journey Orchestration]****[!DNL Journey Orchestration] ださい。
* の一部が含まれている [!DNL Adobe Experience Platform] ことを確認します ****。 必須の権限がありません。 インターフ **[!UICONTROL ェイスからプラットフォームセグメントを作成および編集できるようにするには、プロファイル管理]**[!DNL Journey Orchestration] 権限が必要です。 詳しくは、この[ページ](https://docs.adobe.com/content/help/en/experience-platform/access-control/home.html#adobe-admin-console)を参照してください。

管理コンソールでは、次の既製の製品プロファイルのいずれかをユーザーに割り当てることができます。

* **[!UICONTROL 制限付きアクセスユーザ]**: ジャーニーおよびレポートに対する読み取り専用アクセス権を持つユーザー。 この製品プロファイルには、次の権限が含まれます。
   * ジャーニーを読む
   * レポートの読み取り

* **[!UICONTROL 管理者]**: ジャーニー、イベントおよびレポートを管理できる、管理メニューへのアクセス権を持つユーザー。 この製品プロファイルには、次の権限が含まれます。
   * ジャーニーを管理
   * ジャーニーの公開
   * イベント、データソースおよびアクションの管理
   * レポートの管理

   >[!NOTE]
   >
   >**[!UICONTROL Adobe Campaign Standardでのトランザクションメッセージング（またはメッセージングテンプレート）の作成、編集、および公開を可能にするのは、Administrators]** （管理者）のみの製品プロファイルです。 Adobe Campaign Standardを使用してジャーニーでメッセージを送信する場合は、この製品プロファイルが必要です。

* **[!UICONTROL Standard User]**: jurney managementなどの基本的なアクセス権を持つユーザー。 この製品プロファイルには、次の権限が含まれます。
   * ジャーニーを管理
   * ジャーニーの公開
   * レポートの管理

標準搭載のプロファイルでユーザーを管理するのに十分でない場合は、独自のプロファイルを作成することもできます。
ユーザーは常に製品プロファイルにリンクされ、次のような特定のビルドイン権限を割り当てる必要があります。

* **[!UICONTROL ジャーニーを読む]**
* **[!UICONTROL レポートの読み取り]**
* **[!UICONTROL イベント、データソースおよびアクションの管理]**
* **[!UICONTROL 読み取りイベント、データソース、およびアクション]**
* **[!UICONTROL ジャーニーを管理]**
* **[!UICONTROL ジャーニーの公開]**
* **[!UICONTROL レポートの管理]**

次に、権限との異なる機能の互換性 [!DNL Journey Orchestration]を示します。

![](../assets/journey_permission.png)

## 製品プロファイルの作成 {#create-product-profile}

[!DNL Journey Orchestration] 独自の製品プロファイルを作成し、ユーザーに一連の権限とサンドボックスを割り当てることができます。 製品プロファイルを使用すると、インターフェイス内の特定の機能やオブジェクトへのアクセスを許可または拒否できます。

サンドボックスの作成および管理方法について詳しくは、 [Adobe Experience Platformドキュメントを参照してください](https://docs.adobe.com/content/help/en/experience-platform/sandbox/ui/user-guide.html)。

製品プロファイルを作成し、権限とサンドボックスのセットを割り当てるには：

1. Admin Consoleで「 **[!UICONTROL Journey Orchestration]**」を選択します。 「 **[!UICONTROL 製品のプロファイル]** 」タブで、「 **[!UICONTROL 新規プロファイル]**」をクリックします。

   ![](../assets/user_management_5.png)

1. 新し追加い製品プロファイルの **[!UICONTROL プロファイル名]** と **[!UICONTROL 説明]** 。 プロファイルの **[!UICONTROL 表示名を変える場合は]** 、「プロファイル名と **[!UICONTROL 同じ」をオフにし、]** 表示名を入力します ****。

1. 「 **[!UICONTROL ユーザー通知]** 」カテゴリで、ユーザーがこの製品プロファイルに追加されたとき、または製品から削除されたときに電子メールで通知するかどうかを選択します。

1. 終了したら、「 **[!UICONTROL 完了]**」をクリックします。 これで、新しい製品プロファイルが作成されます。

   ![](../assets/user_management_1.png)

1. 開始管理権限に対する新しい製品プロファイルを選択します。 「 **[!UICONTROL ユーザー]** 」タブで、製品プロファイルにユーザーを追加します。 詳しくは、この[ページ](../about/access-management.md#assigning-product-profile)を参照してください。

1. 上記と同じ手順を実行して、製品プロファイルに **[!UICONTROL 管理者]** を追加します。

1. 「 **[!UICONTROL 権限]** 」タブから、「 **[!UICONTROL Sandbox]** 」または「 **[!UICONTROL オーサリング」の2つのカテゴリのいずれかを選択して「権限を編集]****** 」ページを開き、製品プロファイルに対する権限を追加または削除します。

   ![](../assets/user_management_7.png)

1. サンドボックス **[!UICONTROL 権限カテゴリで]** 、製品プロファイルに割り当てるサンドボックスを選択します。 「 **[!UICONTROL 利用可能な権限項目]**」で、プラス(+)アイコンをクリックして、サンドボックスをプロファイルに割り当てます。 For more information on sandboxes, refer to this [section](../about/access-management.md#sandboxes).

   ![](../assets/user_management_8.png)

1. 必要に応じて、「 **[!UICONTROL 含まれる権限項目]**」で、製品プロファイルに対する権限を削除する横の「X」アイコンをクリックします。

   ![](../assets/user_management_9.png)

1. オーサリング **[!UICONTROL 権限カテゴリから]** 、上記と同じ手順を実行して、製品プロファイルに権限を追加します。
   <br>権限と、権限と各種機能間の互換性について詳し [!DNL Journey Orchestration]くは、この [節を参照してください](../about/access-management.md#about-access-management)。

   ![](../assets/user_management_10.png)

1. 終了したら、「 **[!UICONTROL 保存]**」をクリックします。

これで、製品プロファイルが作成および設定されました。 このプロファイルにリンクされたユーザーは、に接続でき [!DNL Journey Orchestration]ます。

## 製品プロファイルの割り当て {#assigning-product-profile}

製品プロファイルは、組織内で同じ権限を共有するユーザーのセットに割り当てられます。
権限が割り当てられている、あらかじめ用意されているすべての製品プロファイルのリストについては、このセクションを参照してください。

ユーザーがアクセスできるように製品プロファイルを割り当てるには [!DNL Journey Orchestration]:

1. Admin Consoleで「 **[!UICONTROL Journey Orchestration]**」を選択します。

   ![](../assets/user_management.png)

1. 新しいユーザーをリンクする製品プロファイルを選択します。

   ![](../assets/user_management_2.png)

1. 「 **** user追加」をクリックします。

   また、新しいユーザーをユーザーグループに追加して、共有された権限のセットを微調整することもできます。 詳しくは、この[ページ](https://helpx.adobe.com/enterprise/using/user-groups.html)を参照してください。

   ![](../assets/user_management_3.png)

1. 新しいユーザーの電子メールアドレスを入力し、「 **[!UICONTROL 保存]**」をクリックします。

   ![](../assets/user_management_4.png)

その後、インスタンスにリダイレクトする電子メールがユーザーに送信され [!DNL Journey Orchestration] ます。

## サンドボックスの使用 {#sandboxes}

[!DNL Journey Orchestration] インスタンスをサンドボックスと呼ばれる個別の仮想環境に分割できます。
サンドボックスは、管理コンソールの製品プロファイルを通じて割り当てられます。 サンドボックスの割り当て方法の詳細については、この [節を参照してください](../about/access-management.md#create-product-profile)。

[!DNL Journey Orchestration] は、特定の組織用に作成されたPlatformサンドボックスを反映します。
Platformサンドボックスは、Adobe Experience Platformインスタンスから作成またはリセットできます。 詳細手順については、『 [Sandboxユーザガイド](https://docs.adobe.com/content/help/en/experience-platform/sandbox/ui/user-guide.html) 』を参照してください。

画面の左上には、サンドボックス切り替えコントロールがあります。 サンドボックス間を切り替えるには、切り替えボタンで現在アクティブなサンドボックスをクリックし、ドロップダウンリストから別のサンドボックスを選択します。
