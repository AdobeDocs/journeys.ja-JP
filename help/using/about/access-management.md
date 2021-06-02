---
product: adobe campaign
title: アクセス管理
description: アクセス管理の詳細
feature: ジャーニー
role: Business Practitioner
level: Intermediate
exl-id: a551efa5-c0d8-4138-96ca-fb407fad8c59
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '937'
ht-degree: 98%

---

# アクセス管理{#concept_rfj_wpt_52b}

## アクセス管理について {#about-access-management}

[!DNL Journey Orchestration] では、ユーザーに各種の権限を割り当てて、ユーザーがアクセスできるインターフェイスの部分を定義できます。

ユーザーは、Admin Console にアクセスできる管理者によって管理されます。Admin Console について詳しくは、この[ドキュメント](https://helpx.adobe.com/jp/enterprise/managing/user-guide.html)を参照してください。

[!DNL Journey Orchestration] にアクセスするには、次の条件を満たす必要があります。

* [!DNL Journey Orchestration] 権限に関連付けられた [!DNL Journey Orchestration] **[!UICONTROL 製品プロファイル]**&#x200B;の一部。
* [!DNL Adobe Experience Platform] **[!UICONTROL 製品プロファイル]**&#x200B;の一部。必須の権限はありません。[!DNL Journey Orchestration] インターフェイスからプラットフォームセグメントを作成および編集できるようにするには、**[!UICONTROL プロファイル管理]**&#x200B;権限が必要です。詳しくは、この[ページ](https://docs.adobe.com/content/help/ja-JP/experience-platform/access-control/home.html#adobe-admin-console)を参照してください。

Admin Console では、あらかじめ用意されている以下のデフォルト製品プロファイルのいずれかを、ユーザーに割り当てることができます。

* **[!UICONTROL 制限付きアクセスユーザー]**：ジャーニーおよびレポートに対する読み取り専用アクセス権を持つユーザー。この製品プロファイルには、次の権限が含まれます。
   * ジャーニーの読み取り
   * レポートの読み取り

* **[!UICONTROL 管理者]**：ジャーニー、イベント、レポートを管理できる、管理メニューへのアクセス権を持つユーザー。この製品プロファイルには、次の権限が含まれます。
   * ジャーニーの管理
   * ジャーニーの公開
   * イベント、データソース、アクションの管理
   * レポートの管理

   >[!NOTE]
   >
   >Adobe Campaign Standard でトランザクションメッセージ（またはメッセージングテンプレート）の作成、編集、および公開を可能にする製品プロファイルは、**[!UICONTROL 管理者]**&#x200B;のみです。Adobe Campaign Standard を使用してジャーニーでメッセージを送信する場合は、この製品プロファイルが必要です。Admin Consoleで名前を変更しないでください。

* **[!UICONTROL 標準ユーザー]**：ジャーニー管理などの基本的なアクセス権を持つユーザー。この製品プロファイルには、次の権限が含まれます。
   * ジャーニーの管理
   * ジャーニーの公開
   * レポートの管理
   * イベント、データソース、アクションの読み取り

デフォルトのプロファイルでは十分にユーザー管理できない場合は、独自のプロファイルを作成することもできます。
ユーザーは常に製品プロファイルにリンクされ、用意されている以下のような特定の権限を割り当てる必要があります。

* **[!UICONTROL ジャーニーの読み取り]**
* **[!UICONTROL レポートの読み取り]**
* **[!UICONTROL イベント、データソース、アクションの管理]**
* **[!UICONTROL イベント、データソース、アクションの読み取り]**
* **[!UICONTROL ジャーニーの管理]**
* **[!UICONTROL ジャーニーの公開]**
* **[!UICONTROL レポートの管理]**

次に、権限と [!DNL Journey Orchestration] の様々な機能との対応状況を示します。

![](../assets/do-not-localize/journey_permission.png)

## 製品プロファイルの作成 {#create-product-profile}

[!DNL Journey Orchestration] では、独自の製品プロファイルを作成し、ユーザーに一連の権限とサンドボックスを割り当てることができます。製品プロファイルを使用すると、インターフェイス内の特定の機能やオブジェクトへのアクセスを許可または拒否できます。

サンドボックスの作成および管理方法について詳しくは、[Adobe Experience Platform ドキュメント](https://docs.adobe.com/content/help/ja-JP/experience-platform/sandbox/ui/user-guide.translate.html)を参照してください。

製品プロファイルを作成し、権限とサンドボックスのセットを割り当てるには、次の手順に従います。

1. Admin Console で「**[!UICONTROL Journey Orchestration]**」を選択します。「**[!UICONTROL 製品プロファイル]**」タブで、「**[!UICONTROL 新規プロファイル]**」をクリックします。

   ![](../assets/do-not-localize/user_management_5.png)

1. 新しい製品プロファイルの&#x200B;**[!UICONTROL プロファイル名]**&#x200B;と&#x200B;**[!UICONTROL 説明]**&#x200B;を追加します。プロファイルの&#x200B;**[!UICONTROL 表示名]**&#x200B;をプロファイル名と異なる名前に設定するには、「**[!UICONTROL プロファイル名と同じ]**」をオフにし、**[!UICONTROL 表示名]**&#x200B;を入力します。

1. 「**[!UICONTROL ユーザー通知]**」カテゴリで、ユーザーがこの製品プロファイルに追加されたとき、または削除されたときに電子メールで通知するかどうかを選択します。

1. 終了したら、「**[!UICONTROL 完了]**」をクリックします。これで、新しい製品プロファイルが作成されました。

   ![](../assets/do-not-localize/user_management_1.png)

1. 新しい製品プロファイルを選択して、権限の管理を開始します。「**[!UICONTROL ユーザー]**」タブで、製品プロファイルにユーザーを追加します。詳しくは、この[ページ](../about/access-management.md#assigning-product-profile)を参照してください。

1. 上記と同じ手順を実行して、製品プロファイルに&#x200B;**[!UICONTROL 管理者]**&#x200B;を追加します。

1. 「**[!UICONTROL 権限]**」タブから、「**[!UICONTROL サンドボックス]**」または「**[!UICONTROL オーサリング]**」の 2 つのカテゴリのいずれかを選択して&#x200B;**[!UICONTROL 権限を編集]**&#x200B;ページを開き、製品プロファイルに対する権限を追加または削除します。

   ![](../assets/do-not-localize/user_management_7.png)

1. 「**[!UICONTROL サンドボックス]**」権限カテゴリで、製品プロファイルに割り当てるサンドボックスを選択します。「**[!UICONTROL 利用可能な権限項目]**」で、プラス（+）アイコンをクリックして、サンドボックスをプロファイルに割り当てます。サンドボックスについて詳しくは、[この節](../about/access-management.md#sandboxes)を参照してください。

   ![](../assets/do-not-localize/user_management_8.png)

1. 必要に応じて、「**[!UICONTROL 含まれる権限項目]**」で、横の X アイコンをクリックして製品プロファイルに対する権限を削除します。

   ![](../assets/do-not-localize/user_management_9.png)

1. 「**[!UICONTROL オーサリング]**」権限カテゴリから、上記と同じ手順を実行して、製品プロファイルに権限を追加します。
   <br>権限、および権限と [!DNL Journey Orchestration] の様々な機能の互換性について詳しくは、[この節](../about/access-management.md#about-access-management)を参照してください。

   ![](../assets/do-not-localize/user_management_10.png)

1. 終了したら、「**[!UICONTROL 保存]**」をクリックします。

これで、製品プロファイルの作成と設定が完了しました。このプロファイルにリンクされたユーザーは、[!DNL Journey Orchestration] に接続できます。

## 製品プロファイルの割り当て {#assigning-product-profile}

製品プロファイルは、組織内で同じ権限を共有する一連のユーザーに割り当てられます。
デフォルトで権限が割り当てられているすべての製品プロファイルのリストについては、この節を参照してください。

ユーザーが [!DNL Journey Orchestration] にアクセスできるように製品プロファイルを割り当てるには、以下の手順に従います。

1. Admin Console で「**[!UICONTROL Journey Orchestration]**」を選択します。

   ![](../assets/do-not-localize/user_management.png)

1. 新しいユーザーをリンクする製品プロファイルを選択します。

   ![](../assets/do-not-localize/user_management_2.png)

1. 「**[!UICONTROL ユーザーを追加]**」をクリックします。

   また、新しいユーザーをユーザーグループに追加して、共有された一連の権限を微調整することもできます。詳しくは、この[ページ](https://helpx.adobe.com/jp/enterprise/using/user-groups.html)を参照してください。

   ![](../assets/do-not-localize/user_management_3.png)

1. 新しいユーザーのメールアドレスを入力し、「**[!UICONTROL 保存]**」をクリックします。

   ![](../assets/do-not-localize/user_management_4.png)

その後、 [!DNL Journey Orchestration]インスタンスにリダイレクトする電子メールがユーザーに送信されます。

## サンドボックスの使用 {#sandboxes}

[!DNL Journey Orchestration] では、インスタンスをサンドボックスと呼ばれる個別の仮想環境に分割できます。
サンドボックスは、Admin Console の製品プロファイルから割り当てられます。サンドボックスの割り当て方法について詳しくは、[この節](../about/access-management.md#create-product-profile)を参照してください。

[!DNL Journey Orchestration] には、任意の組織用に作成された Adobe Experience Platform サンドボックスが反映されます。Adobe Experience Platform サンドボックスは、Adobe Experience Platform インスタンスから作成またはリセットできます。詳細な手順については、[サンドボックスユーザーガイド](https://docs.adobe.com/content/help/en/experience-platform/sandbox/ui/user-guide.html)を参照してください。

画面の左上に、サンドボックス切り替えコントロールがあります。サンドボックスを切り替えるには、切り替えボタンで現在アクティブなサンドボックスをクリックし、ドロップダウンリストから別のサンドボックスを選択します。
