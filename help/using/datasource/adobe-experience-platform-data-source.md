---
product: adobe campaign
title: 'Adobe Experience Platform データソース '
description: 'Adobe Experience Platformデータソースの設定方法を説明します '
feature: ジャーニー
role: Business Practitioner
level: Intermediate
exl-id: 847fa819-2b92-49e5-8a5e-4f3f0acd5e35
source-git-commit: fb6bdb60ac70a94a62956a306bedee9cb607e2a2
workflow-type: tm+mt
source-wordcount: '365'
ht-degree: 9%

---

# Adobe Experience Platform データソース {#concept_zrb_nqt_52b}

Adobe Experience Platformデータソースは、リアルタイム顧客プロファイルサービスへの接続を定義します。 このデータソースは組み込みで、事前設定されています。 削除できません。 このデータソースは、リアルタイム顧客プロファイルサービスからデータを取得して使用するように設計されています（例えば、ジャーニーに参加した人が女性かどうかを確認します）。 プロファイルデータとエクスペリエンスイベントデータを使用できます。 リアルタイム顧客プロファイルサービスの詳細については、この[ページ](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html)を参照してください。

>[!NOTE]
>
>1年未満で作成された1,000件の最新のエクスペリエンスイベントを取得できます。

リアルタイム顧客プロファイルサービスへの接続を許可するには、キーを使用して個人を識別し、キーをコンテキスト化する名前空間を使用する必要があります。 その結果、このデータソースは、キーと名前空間を含むイベントでジャーニーが開始する場合にのみ使用できます。 [このページ](../building-journeys/journey.md)を参照してください。

事前設定済みの「ProfileFieldGroup」フィールドグループを編集し、新しいフィールドグループを追加して、ドラフトジャーニーやライブジャーニーで使用されていないフィールドグループを削除できます。 [このページ](../datasource/field-groups.md)を参照してください。

次に、組み込みデータソースにフィールドグループを追加する主な手順を示します。

1. データソースのリストから、組み込みのAdobe Experience Platformデータソースを選択します。

   画面の右側にデータソース設定ペインが開きます。

   ![](../assets/journey23.png)

1. 「**[!UICONTROL 新しいフィールドグループを追加]**」をクリックして、取得する一連のフィールドを新しく定義します。 [このページ](../datasource/field-groups.md)を参照してください。

   ![](../assets/journey24.png)

1. 「**[!UICONTROL スキーマ]**」ドロップダウンからスキーマを選択します。 このフィールドには、Adobe Experience Platformで使用できるプロファイルスキーマとエクスペリエンスイベントスキーマが一覧表示されます。 [!DNL Journey Orchestration]では、スキーマの作成は実行されません。 Adobe Experience Platformで行われます
1. 使用するフィールドを選択します。
1. キャッシュ期間を定義します。
1. 「**[!UICONTROL 保存]**」をクリックします。

フィールドグループの名前にカーソルを置くと、右側に2つのアイコンが表示されます。 フィールドグループを削除および複製できます。 「**[!UICONTROL 削除]**」アイコンは、フィールドグループがライブジャーニーまたはドラフトジャーニーで使用されていない場合にのみ使用できます（「**[!UICONTROL 使用される場所]**」フィールドに表示される情報）。
