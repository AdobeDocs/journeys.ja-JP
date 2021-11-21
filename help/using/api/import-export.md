---
product: adobe campaign
title: インポート書き出し API の説明
description: インポート書き出し API の詳細を説明します。
products: journeys
source-git-commit: fb6bdb60ac70a94a62956a306bedee9cb607e2a2
workflow-type: tm+mt
source-wordcount: '1123'
ht-degree: 2%

---


# Export-Import API の使用

1 回の API 呼び出しで、ジャーニーのバージョンとその関連するすべてのオブジェクト（ジャーニー、イベント、データソース、フィールドグループ、カスタムアクション）を書き出します。 書き出し結果のペイロードは、ジャーニーを別の環境（インスタンスまたはサンドボックス）に簡単に読み込むために使用できます。
この機能を使用すると、複数のインスタンスにまたがるジャーニーや、複数のテスト環境ワークフローに関するジャーニーを管理できます。


## リソース

Journey Orchestrationの Export-Import API は、使用可能な Swagger ファイル内で説明されます [ここ](https://adobedocs.github.io/JourneyAPI/docs/).

この API をJourney Orchestrationインスタンスで使用するには、AdobeI/O コンソールを使用する必要があります。 次の手順から始めることができます [はじめに —Adobe開発者コンソール](https://www.adobe.io/apis/experienceplatform/console/docs.html#!AdobeDocs/adobeio-console/master/getting-started.md) その後、このページの「 」セクションを使用します。

統合をテストおよび準備するために、Postman コレクションを使用できます [ここ](https://raw.githubusercontent.com/AdobeDocs/JourneyAPI/master/postman-collections/Journey-Orchestration_Export-import-API_postman-collection.json).


## 書き出し — 読み込みフロー

環境をまたいでジャーニーを書き出し、読み込むには、次の手順に従うことをお勧めします。

1. 開始環境でジャーニーを作成し、パラメーターを設定します。 [詳細情報はこちら](https://experienceleague.adobe.com/docs/journeys/using/building-journeys/about-journey-building/journey.html)
1. ジャーニーのバージョンにエラーがないかどうかを確認します。 [詳細情報はこちら](https://experienceleague.adobe.com/docs/journeys/using/building-journeys/testing-the-journey.html)
1. 呼び出し **/list/journeys** 最新のジャーニーバージョンの UID ジャーニーと UID を取得する API。 必要に応じて、 **/journeys/`{uid}`/latest** 最新のジャーニーバージョンの UID を見つける。
1. を **書き出し** 開始環境パラメーターを含む API（orgID と sandboxName）
1. リターンペイロードを開き、次の項目を確認します。
   * 書き出したジャーニーに **特定の資格情報**&#x200B;の場合は、これらの資格情報を新しい環境に対応する資格情報に置き換える必要があります。
   * 書き出したジャーニーに **イベント** それは **XDM スキーマ** ID の値が異なる場合は、xdmEntity ノードの新しい環境のスキーマ ID を使用して、スキーマ ID 参照を手動で更新する必要があります。 この更新は、イベントごとにおこなう必要があります。 [詳細情報はこちら](https://experienceleague.adobe.com/docs/journeys/using/events-journeys/experience-event-schema.html)
   * ジャーニーに電子メール、SMS、プッシュアクションが含まれる場合、ターゲット環境の名前が開始環境の名前と異なる場合は、テンプレート名または mobileApp 名を更新する必要が生じる場合があります。
1. を **インポート** ターゲット環境パラメーター（orgID と sandboxName）を含む API。 インポート API は、必要な回数だけ呼び出すことができます。 ジャーニーに含まれる各オブジェクトの UUID と名前は、インポート API を呼び出すたびに生成されます。
1. ジャーニーを読み込んだら、アプリケーションでJourney Orchestrationを公開できます。 詳細情報 [ここ](https://experienceleague.adobe.com/docs/journeys/using/building-journeys/publishing-the-journey.html)


## 認証

### API アクセスの設定

Journey OrchestrationAPI へのアクセスは、次の手順で設定します。 これらの各手順について詳しくは、 [Adobe I/O文書](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md).

>[!CAUTION]
>
>証明書をAdobe I/Oで管理するには、 <b>システム管理者</b> 組織または [開発者アカウント](https://helpx.adobe.com/jp/enterprise/using/manage-developers.html) Admin Console でログインします。

1. **電子証明書を持っていることを確認します**&#x200B;または必要に応じて作成します。 証明書と共に提供される公開鍵と秘密鍵は、次の手順で必要になります。
1. **への新しい統合の作成 [!DNL Journey Orchestration] サービス** をAdobe I/Oし、設定します。 製品プロファイルへのアクセスは、Journey OrchestrationとAdobe Experience Platformに必要です。 資格情報が生成されます（API キー、クライアント秘密鍵。.）。
1. **JSON Web トークン (JWT) の作成** 以前に生成された資格情報から、秘密鍵で署名します。 JWT は、ID を検証し、API へのアクセス権を付与するためにAdobeが必要とするすべての ID およびセキュリティ情報をエンコードします。 この手順について詳しくは、この節を参照してください。 [セクション](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/JWT/JWT.md)
1. **アクセストークンとの JWT の交換** POSTリクエストを通じて、または開発者コンソールインターフェイスを通じて。 このアクセストークンは、API リクエストの各ヘッダーで使用する必要があります。

セキュアなサービス間Adobe I/OAPI セッションを確立するには、Adobe サービスへのすべてのリクエストに、以下の情報を Authorization ヘッダーに含める必要があります。

```
curl -X GET https://journey.adobe.io/authoring/XXX \
 -H 'Authorization: Bearer <ACCESS_TOKEN>' \
 -H 'x-api-key: <API_KEY>' \
 -H 'x-gw-ims-org-id: <ORGANIZATION>'
```

* **&lt;organization>**:これは個人の組織 ID で、各インスタンスに対してAdobeが提供する ID は 1 つです。

   * &lt;organization> :実稼動インスタンス
   組織 ID 値を取得するには、管理者または担当のAdobe技術担当者にお問い合わせください。 また、新しい統合を作成する際に、Adobe I/Oに取得することもできます ( [Adobe I/O文書](https://www.adobe.io/authentication.html)) をクリックします。

* **&lt;access_token>**:個人用アクセストークン。POSTリクエストで JWT を交換する際に取得されました。

* **&lt;api_key>**:個人用 API キー。 への新しい統合を作成した後、Adobe I/Oで提供されます。 [!DNL Journey Orchestration] サービス。



## Export-Import API の説明

この API を使用すると、UID で識別されるジャーニーバージョンと、その UID で識別されるすべての関連オブジェクト（ジャーニー、イベント、データソース、フィールドグループ、カスタムアクション）を書き出すことができます。
結果のペイロードは、ジャーニーバージョンを別の環境（サンドボックスまたはインスタンス）に読み込むために使用できます。

| メソッド | パス | 説明 |
|---|---|---|
| `[POST]` | /journeyVersions/import | ジャーニーバージョンの書き出しから生成されたジャーニーバージョンのコンテンツを読み込む |
| `[GET]` | /journeyVersions/`{uid}`/export | ジャーニーのバージョンの書き出し |
| `[GET]` | /journeys/`{uid}`/latest | ジャーニーの最新のジャーニーバージョンを取得する |
| `[POST]` | /list/journeys | ジャーニーのメタデータとジャーニーバージョンのリスト |


### 書き出しの特性とガードレール

* エクスポートの前に、ジャーニーが有効である必要があります。

* 資格情報は書き出されず、プレースホルダー (INSERT_SECRET_HERE) が応答ペイロードに挿入されます。
書き出し呼び出しの後、ターゲット環境でペイロードを読み込む前に、（ターゲット環境に対応する）新しい資格情報を手動で挿入する必要があります。

* 次のオブジェクトは書き出されますが、ターゲット環境にはインポートされません。 これらは、Journey Orchestrationが自動的に管理するシステムリソースです。 &quot;INSERT_SECRET_HERE&quot;を置き換える必要はありません。
   * **DataProviders**:「Adobe Campaign Standard Data Provider」(acsDataProvider) および「Experience Platform」(acppsDataProvider)
   * **フィールドグループ** (dataEntities):&quot;ProfileFieldGroup&quot; (acppsDataPack)



### インポートの特性

* インポート時に、ジャーニーオブジェクトは新しい UID と新しい名前で作成され、ターゲット環境（インスタンスまたはサンドボックス）で一意性を確保します。

* インポートペイロードにシークレットのプレースホルダーが含まれている場合は、エラーがスローされます。 ジャーニーを読み込むには、POST呼び出しの前に、資格情報を置き換える必要があります。

## 警告とエラー

潜在的なエラーは次のとおりです。

* 時刻 **書き出し時間**&#x200B;ジャーニーのバージョンが無効な場合は、次の手順を実行します。エラー 500

* 時刻 **インポート時間**&#x200B;変更後にペイロードが有効でない場合、またはペイロードで資格情報が適切に定義されていない場合は、を指定します。エラー 400

* 読み込み手順の後、イベントの XDM スキーマ ID がターゲット環境で有効でない場合は、Journey Orchestrationアプリケーションにエラーが表示されます。 このような場合、ジャーニーを公開することはできません。