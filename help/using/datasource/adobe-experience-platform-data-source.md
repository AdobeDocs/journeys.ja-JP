---
title: 'Adobe Experience Platform データソース '
description: 'Adobe Experience Platformデータソースの設定方法を学習します。 '
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: tm+mt
source-git-commit: e353d593ab2710f50a88a3715378c86c2e37b4f6
workflow-type: tm+mt
source-wordcount: '366'
ht-degree: 11%

---


# Adobe Experience Platform データソース {#concept_zrb_nqt_52b}

Adobe Experience Platformデータソースは、リアルタイム顧客プロファイルサービスへの接続を定義します。 このデータソースは組み込みで事前設定されています。 削除できません。 このデータソースは、Real-time Customer Customer Serviceからデータを取得して使用するように設計されています（例えば、旅に出た人が女性かどうかを確認します）。 プロファイルデータとエクスペリエンスイベントデータを使用できます。 Real-time Customer Customer Serviceの詳細については、この [ページを参照してください](https://docs.adobe.com/content/help/ja-JP/experience-platform/profile/home.html)。

>[!NOTE]
>
>1年未満で作成された最新の1,000件のエクスペリエンスイベントを取得できます。

Real-time Customer Customer Serviceへの接続を可能にするには、キーを使用して人を特定し、キーを変換する名前空間を使用する必要があります。 その結果、キーと名前空間を含むイベントを持つジャーニー開始の場合にのみ、このデータソースを使用できます。 [このページ](../building-journeys/journey.md)を参照してください。

「ProfileFieldGroup」という名前の事前設定済みのフィールドグループを編集し、新しいグループを追加して、ドラフトまたはライブジャーニーで使用されていないフィールドグループを削除できます。 [このページ](../datasource/field-groups.md)を参照してください。

組み込みデータソースにフィールドグループを追加する主な手順は次のとおりです。

1. データソースのリストから、ビルドインAdobe Experience Platformデータソースを選択します。

   画面の右側にデータソース設定ペインが開きます。

   ![](../assets/journey23.png)

1. 「新しいフィ **[!UICONTROL ールドグループ]** 」をクリックして、取得する一連の新しいフィールドを定義します。 [このページ](../datasource/field-groups.md)を参照してください。

   ![](../assets/journey24.png)

1. 「 **[!UICONTROL スキーマ]** 」ドロップダウンからスキーマを選択します。 このフィールドリストのプロファイルとエクスペリエンスのイベントスキーマは、Adobe Experience Platformで入手できます。 ではスキーマの作成は実行されません [!DNL Journey Orchestration]。 Adobe Experience Platformで行われる
1. 使用するフィールドを選択します。
1. キャッシュ期間を定義します。
1. 「 **[!UICONTROL 保存]**」をクリックします。

フィールドグループの名前にカーソルを置くと、右側に2つのアイコンが表示されます。 フィールドグループを削除し、重複できます。 「 **[!UICONTROL 削除]** 」アイコンは、フィールドグループがライブまたはドラフトの遍歴で使用されていない場合(「使用先 **** 」フィールドに表示される情報)にのみ使用できます。
