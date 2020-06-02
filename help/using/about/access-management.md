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
source-git-commit: 2a53413c79f0213434f9ca6a7847bd7f20fbf41e
workflow-type: tm+mt
source-wordcount: '900'
ht-degree: 3%

---


# アクセス管理{#concept_rfj_wpt_52b}

## アクセス管理について {#about-access-management}

Jureny Orchestrationでは、ユーザーに一連の権限とサンドボックスを割り当てて、ユーザーがアクセスできるインターフェイスの部分を定義できます。

管理者は、管理コンソールにアクセスできる管理者が管理できます。 管理コンソールについて詳しくは、この [ドキュメントを参照してください](https://helpx.adobe.com/jp/enterprise/managing/user-guide.html)。

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
   >**[!UICONTROL Adobe Campaignプロファイル]** は、Administratorsのみで、トランザクションメッセージング（またはメッセージングテンプレート）の作成、編集、および公開を可能にします。 この製品プロファイルは、Adobe Campaign標準を使用してジャーニーでメッセージを送信する場合に必要です。

* **[!UICONTROL Standard User]**: jurney managementなどの基本的なアクセス権を持つユーザー。 この製品プロファイルには、次の権限が含まれます。
   * ジャーニーを管理
   * ジャーニーの公開
   * レポートの管理

標準搭載のプロファイルでユーザーを管理するのに十分でない場合は、独自のプロファイルを作成することもできます。
ユーザーは、常に製品プロファイルにリンクされ、次のような特定のビルドイン権限を割り当てる必要があります。

* **[!UICONTROL ジャーニーを読む]**
* **[!UICONTROL レポートの読み取り]**
* **[!UICONTROL イベント、データソースおよびアクションの管理]**
* **[!UICONTROL 読み取りイベント、データソース、およびアクション]**
* **[!UICONTROL ジャーニーを管理]**
* **[!UICONTROL ジャーニーの公開]**
* **[!UICONTROL レポートの管理]**

権限とJourney Orchestrationの様々な機能の互換性を次に示します。

![](../assets/journey_permission.png)

## 製品プロファイルの作成 {#create-product-profile}

Journey Orchestrationを使用すると、独自の製品プロファイルを作成し、ユーザーに一連の権限とサンドボックスを割り当てることができます。 製品プロファイルを使用すると、インターフェイス内の特定の機能やオブジェクトへのアクセスを許可または拒否できます。

サンドボックスの作成および管理方法について詳しくは、 [Adobe Experience Platformドキュメントを参照してください](https://docs.adobe.com/content/help/en/experience-platform/sandbox/ui/user-guide.html)。

製品プロファイルを作成し、権限とサンドボックスのセットを割り当てるには：

1. 管理コンソールで、「 **[!UICONTROL Jureny orchestration]**」を選択します。 「 **[!UICONTROL 製品のプロファイル]** 」タブで、「 **[!UICONTROL 新規プロファイル]**」をクリックします。

1. 新し追加い製品プロファイルの **[!UICONTROL プロファイル名]** と **[!UICONTROL 説明]** 。 プロファイルの **[!UICONTROL 表示名を変える場合は]** 、「プロファイル名と **[!UICONTROL 同じ」をオフにし、]** 表示名を入力します ****。

1. 「 **[!UICONTROL ユーザー通知]** 」カテゴリで、ユーザーがこの製品プロファイルに追加されたとき、または製品から削除されたときに電子メールで通知するかどうかを選択します。

1. 終了したら、「 **[!UICONTROL 完了]**」をクリックします。 これで、新しい製品プロファイルが作成されます。

1. 開始管理権限に対する新しい製品プロファイルを選択します。 「 **[!UICONTROL ユーザー]** 」タブで、製品プロファイルにユーザーを追加します。 詳しくは、この[ページ](../about/access-management.md#assigning-product-profile)を参照してください。

1. 上記と同じ手順を実行して、製品プロファイルに **[!UICONTROL 管理者]** を追加します。

1. 「 **[!UICONTROL 権限]** 」タブから、「 **[!UICONTROL Sandbox]** 」または「 **[!UICONTROL オーサリング」の2つのカテゴリのいずれかを選択して「権限を編集]****** 」ページを開き、製品プロファイルに対する権限を追加または削除します。

1. Sandbox **[!UICONTROL 権限カテゴリで]** 、製品プロファイルに割り当てるサンドボックスを選択します。 「 **[!UICONTROL 利用可能な権限項目]**」で、プラス(+)アイコンをクリックして、サンドボックスをプロファイルに割り当てます。

   >[!NOTE]
   >
   >Journey Orchestrationは、実稼働用および非実稼働用プラットフォームサンドボックスに接続できるようになりました。 有効な可用性： 2020年6月15日。
   <br>サンドボックスの詳細については、この [節を参照してください](../about/access-management.md#sandboxes)。

1. 必要に応じて、「 **[!UICONTROL 含まれる権限項目]**」で、製品プロファイルに対する権限を削除する横の「X」アイコンをクリックします。

1. オーサリング **[!UICONTROL 権限カテゴリから]** 、上記と同じ手順を実行して、製品プロファイルに権限を追加します。
   <br>権限と、権限とJourney Orchestrationの様々な機能間の互換性について詳しくは、この [節を参照してください](../about/access-management.md#about-access-management)。

1. 終了したら、「 **[!UICONTROL 保存]**」をクリックします。

これで、製品プロファイルが作成および設定されました。 このプロファイルにリンクされたユーザーは、Jureny Orchestrationに接続できるようになりました。

## 製品プロファイルの割り当て {#assigning-product-profile}

製品プロファイルは、組織内で同じ権限を共有するユーザーのセットに割り当てられます。
権限が割り当てられた、あらかじめ用意されているすべての製品プロファイルのリストは、このセクションで確認できます。

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

## サンドボックスの使用 {#sandboxes}

>[!NOTE]
>
>Journey Orchestrationは、実稼働用および非実稼働用プラットフォームサンドボックスに接続できるようになりました。 有効な可用性： 2020年6月15日。

Journey Orchestrationを使用すると、インスタンスをサンドボックスと呼ばれる個別の仮想環境にパーティション化できます。
サンドボックスは、管理コンソールの製品プロファイルを通じて割り当てられます。 サンドボックスの割り当て方法の詳細については、この [節を参照してください](../about/access-management.md#create-product-profile)。

Journey Orchestrationは、特定の組織用に作成されたプラットフォームサンドボックスを反映します。
プラットフォームサンドボックスは、Adobe Experience Platformインスタンスから作成またはリセットできます。 詳細手順については、『 [Sandboxユーザガイド](https://docs.adobe.com/content/help/en/experience-platform/sandbox/ui/user-guide.html) 』を参照してください。

画面の左上には、サンドボックス切り替えコントロールがあります。 サンドボックス間を切り替えるには、切り替えボタンで現在アクティブなサンドボックスをクリックし、ドロップダウンリストから別のサンドボックスを選択します。