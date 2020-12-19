---
product: adobe campaign
solution: Journey Orchestration
title: 'Adobe Experience Platform データソース '
description: 'Adobe Experience Platformデータソースの設定方法を学習します。 '
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '366'
ht-degree: 11%

---


# Adobe Experience Platform データソース {#concept_zrb_nqt_52b}

Adobe Experience Platformデータソースは、リアルタイム顧客プロファイルサービスへの接続を定義します。 このデータソースは組み込みで事前設定されています。 削除できません。 このデータソースは、Real-time Customer Customer Serviceからデータを取得して使用するように設計されています（例えば、旅に出た人が女性かどうかを確認します）。 プロファイルデータとエクスペリエンスイベントデータを使用できます。 Real-time Customer Customer Serviceの詳細については、[ページ](https://docs.adobe.com/content/help/ja-JP/experience-platform/profile/home.html)を参照してください。

>[!NOTE]
>
>1年未満で作成された最新の1,000件のエクスペリエンスイベントを取得できます。

Real-time Customer Customer Serviceへの接続を可能にするには、キーを使用して人を特定し、キーを変換する名前空間を使用する必要があります。 その結果、キーと名前空間を含むイベントを持つジャーニー開始の場合にのみ、このデータソースを使用できます。 [このページ](../building-journeys/journey.md)を参照してください。

「ProfileFieldGroup」という名前の事前設定済みのフィールドグループを編集し、新しいグループを追加して、ドラフトまたはライブジャーニーで使用されていないフィールドグループを削除できます。 [このページ](../datasource/field-groups.md)を参照してください。

組み込みデータソースにフィールドグループを追加する主な手順は次のとおりです。

1. データソースのリストから、ビルドインAdobe Experience Platformデータソースを選択します。

   画面の右側にデータソース設定ペインが開きます。

   ![](../assets/journey23.png)

1. **[!UICONTROL 新しいフィールドグループ追加]**&#x200B;をクリックして、取得する一連のフィールドを定義します。 [このページ](../datasource/field-groups.md)を参照してください。

   ![](../assets/journey24.png)

1. **[!UICONTROL スキーマ]**&#x200B;ドロップダウンからスキーマを選択します。 このフィールドリストのプロファイルとエクスペリエンスのイベントスキーマは、Adobe Experience Platformで入手できます。 [!DNL Journey Orchestration]ではスキーマの作成は実行されません。 Adobe Experience Platformで行われる
1. 使用するフィールドを選択します。
1. キャッシュ期間を定義します。
1. 「**[!UICONTROL 保存]**」をクリックします。

フィールドグループの名前にカーソルを置くと、右側に2つのアイコンが表示されます。 フィールドグループを削除し、重複できます。 「**[!UICONTROL 削除]**」アイコンは、フィールドグループがライブまたはドラフトの遍歴で使用されていない場合（**[!UICONTROL 「]**&#x200B;で使用」フィールドに表示される情報）にのみ使用できます。
