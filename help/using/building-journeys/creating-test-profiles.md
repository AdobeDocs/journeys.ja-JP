---
product: adobe campaign
solution: Journey Orchestration
title: テストプロファイルの作成
description: 'テストプロファイルの作成について '
translation-type: tm+mt
source-git-commit: 8c7c7d85d4e7835721b70faa7b3b6166796e79c4
workflow-type: tm+mt
source-wordcount: '968'
ht-degree: 2%

---


# テストプロファイルを作成{#create-test-profiles}

![](../assets/do-not-localize/badge.png)

テストプロファイルは、ジャーニーでテストモードを使用する場合に必要です。 [既存のプロファイル](../building-journeys/creating-test-profiles.md#turning-profile-into-test)をテストプロファイルにするか、[テストプロファイル](../building-journeys/creating-test-profiles.md#create-test-profiles-csv)を作成します。 テストモードの使い方については、[この](../building-journeys/testing-the-journey.md)を参照してください。

Adobe Experience Platformでテストプロファイルを作成するには、様々な方法があります。 このドキュメントでは、次の2つの方法に焦点を当てます。[csvファイル](../building-journeys/creating-test-profiles.md#create-test-profiles-csv)をアップロードし、[APIを使用して](../building-journeys/creating-test-profiles.md#create-test-profiles-api)を呼び出します。 データセットにjsonファイルをアップロードすることもできます。詳しくは、[データ収集ドキュメント](https://experienceleague.adobe.com/docs/experience-platform/ingestion/tutorials/ingest-batch-data.html#add-data-to-dataset)を参照してください。

テストプロファイルの作成は、Adobe Experience Platformで正規プロファイルを作成するのと似ています。 詳しくは、[リアルタイム顧客プロファイルドキュメント](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html)を参照してください。

## 前提条件{#test-profile-prerequisites}

プロファイルを作成するには、まずAdobe Experience Platformでスキーマとデータセットを作成する必要があります。

まず、**スキーマ**&#x200B;を作成する必要があります。 次の手順に従います。

1. Adobe Experience Platformで、左のメニューの&#x200B;**スキーマ**をクリックします。
   ![](../assets/test-profiles-0.png)
1. 右上の「**スキーマを作成**」をクリックし、スキーマの種類を選択します(例：**XDM個別プロファイル**)。
   ![](../assets/test-profiles-1.png)
1. スキーマの名前を選択します。
1. 「**ミックスイン**」セクションで、「**追加**」をクリックします。
   ![](../assets/test-profiles-1-bis.png)
1. 適切なミックスインを選択します。 **プロファイルテストの詳細**&#x200B;ミックスインを追加してください。 **ミックスイン追加**をクリックします。
   ![](../assets/test-profiles-1-ter.png)
ミックスインのリストは、スキーマの概要画面に表示されます。

   ![](../assets/test-profiles-2.png)
1. フィールドのリストで、主IDとして定義するフィールドをクリックします。
   ![](../assets/test-profiles-3.png)
1. **フィールドのプロパティ**&#x200B;右パネルで、**ID**&#x200B;および&#x200B;**プライマリID**&#x200B;オプションを確認し、名前空間を選択します。 プライマリIDを電子メールアドレスにする場合は、**電子メール**&#x200B;名前空間を選択します。 「**適用**」をクリックします。
   ![](../assets/test-profiles-4.png)
1. スキーマを選択し、**スキーマのプロパティ**&#x200B;で&#x200B;**プロファイル**オプションを有効にします。
   ![](../assets/test-profiles-5.png)
1. 「**保存**」をクリックします。

>[!NOTE]
>
>スキーマの作成について詳しくは、[XDMドキュメント](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/resources/schemas.html#prerequisites)を参照してください。

次に、プロファイルを読み込むデータセット&#x200B;**を**&#x200B;作成する必要があります。 次の手順に従います。

1. Adobe Experience Platformで、左のメニューで「**データセット**」をクリックし、「**データセットを作成**」をクリックします。
   ![](../assets/test-profiles-6.png)
1. 「**スキーマからデータセットを作成**」を選択します。
   ![](../assets/test-profiles-7.png)
1. 以前に作成したスキーマを選択し、「**次へ**」をクリックします。
   ![](../assets/test-profiles-8.png)
1. 名前を選択し、**完了**をクリックします。
   ![](../assets/test-profiles-9.png)
1. **プロファイル**オプションを有効にします。
   ![](../assets/test-profiles-10.png)

>[!NOTE]
>
> データセットの作成について詳しくは、[カタログサービスのドキュメント](https://experienceleague.adobe.com/docs/experience-platform/catalog/datasets/user-guide.html#getting-started)を参照してください。

## プロファイルをテストプロファイルに変換{#turning-profile-into-test}

既存のプロファイルをテストプロファイルに変換できます。 Adobe Experience Platformでは、プロファイルの作成時と同じ方法でプロファイル属性を更新できます。

これを行うには、ジャーニーで&#x200B;**プロファイル**&#x200B;の更新アクションアクティビティを使用し、testProfileブール値フィールドをfalseからtrueに変更します。

ジャーニーは、**読み取りセグメント**&#x200B;と&#x200B;**更新プロファイル**&#x200B;アクティビティで構成されます。 まず、テストプロファイルにしたいプロファイルをターゲットにしたセグメントを作成する必要があります。

>[!NOTE]
>
> **testProfile**&#x200B;フィールドを更新するので、選択したプロファイルにこのフィールドを含める必要があります。 関連するスキーマには、**プロファイルテストの詳細**&#x200B;ミックスインが必要です。 [この節](../building-journeys/creating-test-profiles.md#test-profiles-prerequisites)を参照してください。

1. 顧客ジャーニー管理で、左のメニューから「**セグメント**」をクリックし、右上の「**セグメント**を作成」をクリックします。
   ![](../assets/test-profiles-22.png)
1. セグメント名を定義し、セグメントを作成します。目的のプロファイルをターゲットするフィールドと値を選択します。
   ![](../assets/test-profiles-23.png)
1. 「**保存**」をクリックし、プロファイルがセグメントのターゲットを正しく設定していることを確認します。
   ![](../assets/test-profiles-24.png)

   >[!NOTE]
   >
   > セグメントの計算には時間がかかる場合があります。 セグメントの詳細については、[このセクション](../segment/about-segments.md)を参照してください。

1. 次に、**セグメント**&#x200B;を読み取るオーケストレーションアクティビティを使用して、新しいジャーニーと開始を作成します。
1. 以前に作成したセグメントと、プロファイルが使用する名前空間を選択します。
   ![](../assets/test-profiles-25.png)
1. &lt;追加a0/>プロファイル&#x200B;**の更新アクティビティ。**
1. スキーマ、**testProfiles**フィールド、データセットを選択し、値を「true」に設定します。
   ![](../assets/test-profiles-26.png)
1. 追加&#x200B;****&#x200B;アクティビティを終了し、**発行**をクリックします。
   ![](../assets/test-profiles-27.png)
1. Adobe Experience Platformで、プロファイルが正しく更新されていることを確認します。
   ![](../assets/test-profiles-28.png)

   >[!NOTE]
   >
   > **プロファイル**&#x200B;の更新アクティビティの詳細については、[この](../building-journeys/update-profiles.md)を参照してください。

## CSVファイルを使用したテストプロファイルの作成{#create-test-profiles-csv}

Adobe Experience Platformでは、様々なプロファイルフィールドを含むCSVファイルをプロファイルセットにアップロードして、を作成できます。 これが最も簡単な方法です。

1. スプレッドシートソフトウェアを使用して、単純なCSVファイルを作成します。
1. 必要な各フィ追加ールドに対して1列。 主IDフィールド（上記の例では「personID」）と「testProfile」フィールドを「true」に設定して追加します。
   ![](../assets/test-profiles-11.png)
1. プロファイルご追加とに1行を入力し、各フィールドの値を入力します。
   ![](../assets/test-profiles-12.png)
1. スプレッドシートをCSVファイルとして保存します。 カンマが区切り文字として使用されていることを確認します。
1. Adobe Experience Platformで、左のメニューの&#x200B;**ワークフロー**をクリックします。
   ![](../assets/test-profiles-14.png)
1. 「**CSVをXDMスキーマにマップ**」を選択し、「****を起動」をクリックします。
   ![](../assets/test-profiles-16.png)
1. プロファイルの読み込み先のデータセットを選択します。 「**次へ**」をクリックします。
   ![](../assets/test-profiles-17.png)
1. 「**ファイルを選択**」をクリックし、csvファイルを選択します。 ファイルをアップロードしたら、「**次へ**」をクリックします。
   ![](../assets/test-profiles-18.png)
1. ソースcsvフィールドをスキーマフィールドにマップし、「**完了**」をクリックします。
   ![](../assets/test-profiles-19.png)
1. データのインポートが開始されます。 ステータスが&#x200B;**処理**&#x200B;から&#x200B;**成功**&#x200B;に変わります。 右上の&#x200B;**プレビューデータセット**をクリックします。
   ![](../assets/test-profiles-20.png)
1. テストプロファイルが正しく追加されていることを確認します。
   ![](../assets/test-profiles-21.png)

テストプロファイルが追加され、ジャーニーをテストする際に使用できるようになりました。 [こちらの節](../building-journeys/testing-the-journey.md)を参照してください。
>[!NOTE]
>
> CSVのインポートについて詳しくは、[データ収集ドキュメント](https://experienceleague.adobe.com/docs/experience-platform/ingestion/tutorials/map-a-csv-file.html#tutorials)を参照してください。

## API呼び出しを使用したテストプロファイルの作成{#create-test-profiles-api}

また、API呼び出しを使用してテストプロファイルを作成することもできます。 この[ページ](https://docs.adobe.com/content/help/ja-JP/experience-platform/profile/home.html)を参照してください。

「プロファイルテストの詳細」ミックスインが含まれるプロファイルスキーマを使用する必要があります。 testProfileフラグは、このmixinの一部です。

プロファイルを作成する場合は、次の値を渡す必要があります。testProfile = true。

既存のプロファイルを更新して、testProfileフラグを「true」に変更することもできます。

テストプロファイルを作成するためのAPI呼び出しの例を以下に示します。

```
curl -X POST \
'https://dcs.adobedc.net/collection/xxxxxxxxxxxxxx' \
-H 'Cache-Control: no-cache' \
-H 'Content-Type: application/json' \
-H 'Postman-Token: xxxxx' \
-H 'cache-control: no-cache' \
-H 'x-api-key: xxxxx' \
-H 'x-gw-ims-org-id: xxxxx' \
-d '{
"header": {
"msgType": "xdmEntityCreate",
"msgId": "xxxxx",
"msgVersion": "xxxxx",
"xactionid":"xxxxx",
"datasetId": "xxxxx",
"imsOrgId": "xxxxx",
"source": {
"name": "Postman"
},
"schemaRef": {
"id": "https://example.adobe.com/mobile/schemas/xxxxx",
"contentType": "application/vnd.adobe.xed-full+json;version=1"
}
},
"body": {
"xdmMeta": {
"schemaRef": {
"contentType": "application/vnd.adobe.xed-full+json;version=1"
}
},
"xdmEntity": {
"_id": "xxxxx",
"_mobile":{
"ECID": "xxxxx"
},
"testProfile":true
}
}
}'
```

