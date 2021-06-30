---
product: adobe campaign
title: テストプロファイルの作成
description: テストプロファイルの作成について説明します
exl-id: f1be46a8-04b9-4f40-b18e-9099099d2e1c
source-git-commit: fb6bdb60ac70a94a62956a306bedee9cb607e2a2
workflow-type: tm+mt
source-wordcount: '726'
ht-degree: 2%

---

# テストプロファイルの作成 {#create-test-profiles}

テストプロファイルは、ジャーニーでテストモードを使用する場合に必要です。 テストモードの使用方法については、[この節](../building-journeys/testing-the-journey.md)を参照してください。

Adobe Experience Platformでテストプロファイルを作成する方法は異なります。 このドキュメントでは、次の2つの方法に焦点を当てます。[csvファイル](../building-journeys/creating-test-profiles.md#create-test-profiles-csv)をアップロードし、[API呼び出し](../building-journeys/creating-test-profiles.md#create-test-profiles-api)を使用する。 データセットにjsonファイルをアップロードすることもできます。[データ取り込みに関するドキュメント](https://experienceleague.adobe.com/docs/experience-platform/ingestion/tutorials/ingest-batch-data.html#add-data-to-dataset)を参照してください。

これらの読み込み方法を使用して、プロファイル属性を更新することもできます。 これにより、既存のプロファイルをテストプロファイルに変換できます。 同様のファイルまたはAPI呼び出しを使用し、「testProfile」フィールドの値を「true」にするだけです。

テストプロファイルの作成は、Adobe Experience Platformで通常のプロファイルを作成する場合と似ています。 詳しくは、[リアルタイム顧客プロファイルのドキュメント](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html)を参照してください。

## 前提条件{#test-profile-prerequisites}

プロファイルを作成するには、まずAdobe Experience Platformでスキーマとデータセットを作成する必要があります。

まず、**スキーマ**&#x200B;を作成する必要があります。 次の手順に従います。

1. Adobe Experience Platformで、左側のメニューの「**[!UICONTROL スキーマ]**」をクリックします。
   ![](../assets/test-profiles-0.png)
1. 右上の「**[!UICONTROL スキーマを作成]**」をクリックし、スキーマタイプ（例：**[!UICONTROL XDM Individual Profile]**）を選択します。
   ![](../assets/test-profiles-1.png)
1. スキーマの名前を選択します。
1. 「**[!UICONTROL Mixins]**」セクションで、「**[!UICONTROL 追加]**」をクリックします。
   ![](../assets/test-profiles-1-bis.png)
1. 適切なmixinを選択します。 必ず&#x200B;**[!UICONTROL プロファイルテストの詳細]** mixinを追加してください。 「**[!UICONTROL Mixin]**を追加」をクリックします。
   ![](../assets/test-profiles-1-ter.png)
Mixinのリストがスキーマの概要画面に表示されます。

   ![](../assets/test-profiles-2.png)
1. フィールドのリストで、プライマリIDとして定義するフィールドをクリックします。
   ![](../assets/test-profiles-3.png)
1. **[!UICONTROL フィールドのプロパティ]**&#x200B;の右パネルで、「**[!UICONTROL ID]**」および「**[!UICONTROL プライマリID]**」オプションをオンにし、名前空間を選択します。 プライマリIDを電子メールアドレスにする場合は、**[!UICONTROL Email]**&#x200B;名前空間を選択します。 「**[!UICONTROL 適用]**」をクリックします。
   ![](../assets/test-profiles-4.png)
1. スキーマを選択し、**[!UICONTROL スキーマのプロパティ]**&#x200B;で「**[!UICONTROL プロファイル]**」オプションを有効にします。
   ![](../assets/test-profiles-5.png)
1. 「**[!UICONTROL 保存]**」をクリックします。

>[!NOTE]
>
>スキーマの作成について詳しくは、[XDMのドキュメント](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/resources/schemas.html#prerequisites)を参照してください。

次に、プロファイルがインポートされるデータセット&#x200B;**を**&#x200B;作成する必要があります。 次の手順に従います。

1. Adobe Experience Platformで、左側のメニューの「**[!UICONTROL データセット]**」をクリックし、「**[!UICONTROL データセットを作成]**」をクリックします。
   ![](../assets/test-profiles-6.png)
1. 「**[!UICONTROL スキーマからデータセットを作成]**」を選択します。
   ![](../assets/test-profiles-7.png)
1. 前に作成したスキーマを選択し、「**[!UICONTROL 次へ]**」をクリックします。
   ![](../assets/test-profiles-8.png)
1. 名前を選択し、「**[!UICONTROL 完了]**」をクリックします。
   ![](../assets/test-profiles-9.png)
1. 「**[!UICONTROL プロファイル]**」オプションを有効にします。
   ![](../assets/test-profiles-10.png)

>[!NOTE]
>
> データセットの作成について詳しくは、[カタログサービスのドキュメント](https://experienceleague.adobe.com/docs/experience-platform/catalog/datasets/user-guide.html#getting-started)を参照してください。

## csvファイルを使用したテストプロファイルの作成{#create-test-profiles-csv}

Adobe Experience Platformでは、様々なプロファイルフィールドを含むcsvファイルをデータセットにアップロードすることで、プロファイルを作成できます。 これが最も簡単な方法です。

1. スプレッドシートソフトウェアを使用して、簡単なcsvファイルを作成します。
1. 必要なフィールドごとに1列を追加します。 プライマリIDフィールド（上記の例では「personID」）と「testProfile」フィールドを必ず追加し、「true」に設定します。
   ![](../assets/test-profiles-11.png)
1. プロファイルごとに1行を追加し、各フィールドの値を入力します。
   ![](../assets/test-profiles-12.png)
1. スプレッドシートをcsvファイルとして保存します。 コンマが区切り文字として使用されていることを確認します。
1. Adobe Experience Platformで、左側のメニューの「**[!UICONTROL ワークフロー]**」をクリックします。
   ![](../assets/test-profiles-14.png)
1. 「**[!UICONTROL XDMスキーマにCSVをマッピング]**」を選択し、「****を起動」をクリックします。
   ![](../assets/test-profiles-16.png)
1. プロファイルのインポート先のデータセットを選択します。 「**[!UICONTROL 次へ]**」をクリックします。
   ![](../assets/test-profiles-17.png)
1. 「**[!UICONTROL ファイルを選択]**」をクリックし、csvファイルを選択します。 ファイルがアップロードされたら、「**[!UICONTROL 次へ]**」をクリックします。
   ![](../assets/test-profiles-18.png)
1. ソースのcsvフィールドをスキーマフィールドにマッピングし、「**[!UICONTROL 完了]**」をクリックします。
   ![](../assets/test-profiles-19.png)
1. データのインポートが開始されます。 ステータスは&#x200B;**[!UICONTROL 処理]**&#x200B;から&#x200B;**[!UICONTROL 成功]**&#x200B;に移動します。 右上の「**[!UICONTROL データセットのプレビュー]**」をクリックします。
   ![](../assets/test-profiles-20.png)
1. テストプロファイルが正しく追加されていることを確認します。
   ![](../assets/test-profiles-21.png)

テストプロファイルが追加され、ジャーニーのテスト時に使用できるようになりました。 [この節](../building-journeys/testing-the-journey.md)を参照してください。
>[!NOTE]
>
> csvのインポートについて詳しくは、[データ取得のドキュメント](https://experienceleague.adobe.com/docs/experience-platform/ingestion/tutorials/map-a-csv-file.html#tutorials)を参照してください。

## API呼び出しを使用したテストプロファイルの作成{#create-test-profiles-api}

また、API呼び出しを使用してテストプロファイルを作成することもできます。 [このページ](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html)を参照してください。

「プロファイルテストの詳細」mixinを含むプロファイルスキーマを使用する必要があります。 testProfileフラグはこのmixinの一部です。

プロファイルを作成する場合は、次の値を渡す必要があります。testProfile = true

既存のプロファイルを更新して、そのtestProfileフラグを「true」に変更することもできます。

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
