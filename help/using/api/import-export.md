---
product: adobe campaign
title: インポート エクスポート API の説明
description: Import export API の詳細情報。
products: journeys
source-git-commit: 8f409fe6e37a3b80527d9a5514b066e539dcd9f3
workflow-type: tm+mt
source-wordcount: '1027'
ht-degree: 18%

---


# Export-Import API の操作

1 回の API 呼び出しで、ジャーニーバージョンとその関連オブジェクト（ジャーニー、イベント、データソース、フィールドグループ、カスタムアクション）をすべて書き出します。 結果のペイロードを書き出すと、ジャーニーを別の環境（インスタンスまたはサンドボックス）に簡単に読み込むために使用できます。
この機能を使用すると、複数のインスタンスまたは複数のテスト環境ワークフローにわたってジャーニーを管理できます。


## リソース

Journey Orchestrationの Export-Import API は、使用可能な Swagger ファイル [ こちら ](https://adobedocs.github.io/JourneyAPI/docs/) に記述されています。

Journey Orchestrationインスタンスでこの API を使用するには、AdobeI/O コンソールを使用する必要があります。 この [Adobe Developer Consoleの概要 ](https://www.adobe.io/apis/experienceplatform/console/docs.html#!AdobeDocs/adobeio-console/master/getting-started.md) に従って開始し、このページのセクションを使用できます。

統合をテストして準備するために、Postman コレクションを使用できます [ ここでは ](https://raw.githubusercontent.com/AdobeDocs/JourneyAPI/master/postman-collections/Journey-Orchestration_Export-import-API_postman-collection.json)。


## 書き出し – 読み込みフロー

次の手順に従って、環境全体でジャーニーをエクスポートしインポートすることをお勧めします。

1. 開始環境でジャーニーを作成し、パラメーターを設定します。 [ 詳細はこちら ](https://experienceleague.adobe.com/docs/journeys/using/building-journeys/about-journey-building/journey.html?lang=ja)
1. ジャーニーバージョンにエラーがないかどうかを確認します。 [ 詳細はこちら ](https://experienceleague.adobe.com/docs/journeys/using/building-journeys/testing-the-journey.html?lang=ja)
1. **/list/journeys** API を呼び出して、UID ジャーニーと最新のジャーニーバージョンの UID を取得します。 必要に応じて、**/journeys/`{uid}`/latest** を呼び出して、最新のジャーニーバージョンの UID を確認できます。
1. **export** API を起動環境パラメーター（orgID および sandboxName）で呼び出します。
1. リターンペイロードを開き、次の項目を確認します。
   * 書き出されたジャーニーに **特定の資格情報** が含まれている場合は、これらの資格情報を新しい環境に対応する資格情報に置き換える必要があります。
   * 書き出されたジャーニーに **XDM スキーマ** を指す **イベント** が含まれている場合、ID の値が異なる場合は、xdmEntity ノードの新しい環境のスキーマ ID でスキーマ ID 参照を手動で更新する必要があります。 この更新は、イベントごとに行う必要があります。 [ 詳細はこちら ](https://experienceleague.adobe.com/docs/journeys/using/events-journeys/experience-event-schema.html?lang=ja)
   * ジャーニーにメール、SMS またはプッシュアクションが含まれている場合、ターゲット環境の名前が開始環境の名前と異なる場合は、テンプレート名または mobileApp 名の更新が必要になる場合があります。
1. ターゲットの環境パラメーター（orgID および sandboxName）を使用して **Import** API を呼び出します。 読み込み API は、必要な回数だけ呼び出すことができます。 ジャーニーに含まれる各オブジェクトの UUID と名前は、import API を呼び出すたびに生成されます。
1. ジャーニーが読み込まれたら、Journey Orchestrationアプリケーションで公開できます。 詳細情報 [ こちら ](https://experienceleague.adobe.com/docs/journeys/using/building-journeys/publishing-the-journey.html?lang=ja)


## 認証

### API アクセスのセットアップ

Journey OrchestrationAPI アクセスは、以下の手順でセットアップします。 これらの各手順について詳しくは、[Adobe I/O のドキュメント](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md)を参照してください。

>[!CAUTION]
>
>Adobe I/O で証明書を管理するには、組織の<b>システム管理者</b>権限または Admin Console の[開発者アカウント](https://helpx.adobe.com/jp/enterprise/using/manage-developers.html)があることを確認してください。

1. **電子証明書があることを確認するか**、必要に応じて作成します。証明書に記載されている公開鍵と秘密鍵は、以降の手順で必要になります。
1. Adobe I/O で **[!DNL Journey Orchestration] サービスへの新しい統合を作成**&#x200B;し、設定します。Journey OrchestrationおよびAdobe Experience Platformには、製品プロファイルへのアクセスが必要です。 次に、資格情報を生成します（API キー、クライアントシークレットなど）。

>[!CAUTION]
>
>アクセストークンを生成する JWT メソッドは非推奨（廃止予定）になりました。 すべての新しい統合は、[OAuth サーバー間認証方法 ](https://experienceleague.adobe.com/docs/experience-platform/landing/platform-apis/api-authentication.html?lang=ja#select-oauth-server-to-server) を使用して作成する必要があります。 また、Adobeでは、既存の統合環境を OAuth 方式に移行することをお勧めします。
>
>以下の重要なドキュメントを参照してください。
>[JWT から OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/) へのアプリケーションの移行ガイド
>[OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/) を使用した新旧のアプリケーションの実装ガイド
>[OAuth サーバー間資格情報方式を使用する場合の利点 ](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/#why-oauth-server-to-server-credentials)


サービス間のセキュアな Adobe I/O API セッションを確立するには、アドビサービスへのすべてのリクエストで、以下の情報を Authorization ヘッダーに含める必要があります。

```
curl -X GET https://journey.adobe.io/authoring/XXX \
 -H 'Authorization: Bearer <ACCESS_TOKEN>' \
 -H 'x-api-key: <API_KEY>' \
 -H 'x-gw-ims-org-id: <ORGANIZATION>'
```

* **&lt;ORGANIZATION>**：これは個人の組織 ID で、インスタンスごとに 1 つの組織 ID がAdobeから提供されます。

   * &lt;ORGANIZATION>：実稼動インスタンス

  組織 ID の値を取得するには、管理者またはアドビの技術担当者にお問い合わせください。また、新しい統合を作成する際に、ライセンスリストで Adobe I/O に取得することもできます（[Adobe I/O のドキュメント](https://www.adobe.io/authentication.html)を参照してください）。

* **&lt;ACCESS_TOKEN>**：個人用アクセストークンです

* **&lt;API_KEY>**：個人用 API キーです。[!DNL Journey Orchestration] サービスへの新しい統合を作成した後、Adobe I/O で提供されます。



## Export-Import API の説明

この API を使用すると、UID で識別されるジャーニーバージョンと、UID によってすべての関連オブジェクト（ジャーニー、イベント、データソース、フィールドグループ、カスタムアクション）を書き出すことができます。
結果のペイロードを使用して、別の環境（サンドボックスまたはインスタンス）にジャーニーバージョンを読み込むことができます。

| メソッド | パス | 説明 |
|---|---|---|
| `[POST]` | /journeyVersions/import | ジャーニーバージョンの書き出しから生成されたジャーニーバージョンのコンテンツを読み込みます |
| `[GET]` | /journeyVersion/`{uid}`/export | ジャーニーバージョンのエクスポート |
| `[GET]` | /journeys/`{uid}`/latest | ジャーニーの最新のジャーニーバージョンを取得 |
| `[POST]` | /list/journeys | ジャーニーのメタデータとジャーニーバージョンのリスト |


### 特性とガードレールの書き出し

* 書き出す前に、ジャーニーが有効である必要があります。

* 資格情報は書き出されず、プレースホルダー（INSERT_SECRET_HERE）が応答ペイロードに挿入されます。
エクスポート呼び出しの後、ターゲット環境にペイロードを読み込む前に、（ターゲット環境に対応する）新しい資格情報を手動で挿入する必要があります。

* 以下のオブジェクトはエクスポートされますが、ターゲット環境ではインポートされません。 これらは、Journey Orchestrationによって自動的に管理されるシステムリソースです。 「INSERT_SECRET_HERE」を置き換える必要はありません。
   * **DataProviders**:「Adobe Campaign Standard Data Provider」（acsDataProvider）と「Experience Platform」（acppsDataProvider）
   * **フィールドグループ** （dataEntities）:「ProfileFieldGroup」（acppsDataPack）



### インポート特性

* 読み込み時に、ターゲット環境（インスタンスまたはサンドボックス）内での一意性を確保するために、新しい UID と新しい名前でジャーニーオブジェクトが作成されます。

* 読み込みペイロードに秘密鍵のプレースホルダーが含まれている場合、エラーがスローされます。 ジャーニーをインポートするには、POSTを呼び出す前に、資格情報を置き換える必要があります。

## 警告とエラー

潜在的なエラーは次のとおりです。

* **エクスポート時**、ジャーニーバージョンが有効でない場合：エラー 500

* **読み込み時** に、変更後にペイロードが有効でない場合、またはペイロードで資格情報が適切に定義されていない場合：エラー 400

* インポート手順の後、イベントの XDM スキーマ ID がターゲット環境で有効でない場合、Journey Orchestrationアプリケーションにエラーが表示されます。 この場合、ジャーニーを公開することはできません。