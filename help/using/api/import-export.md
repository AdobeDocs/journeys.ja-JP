---
product: adobe campaign
title: インポートのエクスポート APIの説明
description: インポート書き出しAPIについて詳しく見る。
products: journeys
source-git-commit: 8f409fe6e37a3b80527d9a5514b066e539dcd9f3
workflow-type: tm+mt
source-wordcount: '1160'
ht-degree: 20%

---


# Export-Import APIの操作

1回のAPI呼び出しで、ジャーニーバージョンとそのすべての関連オブジェクト（ジャーニー、イベント、データソース、フィールドグループ、カスタムアクション）を書き出すことができます。 書き出し結果のペイロードを使用すると、ジャーニーを別の環境（インスタンスまたはサンドボックス）に簡単に読み込むことができます。
この機能を使用すると、複数のインスタンスまたは複数のテスト環境ワークフローのジャーニーを管理できます。


## リソース

Journey Orchestration Export-Import APIは、利用可能なSwagger ファイル [ここ](https://adobedocs.github.io/JourneyAPI/docs/)に記載されています。

このAPIをJourney Orchestration インスタンスで使用するには、AdobeI/O コンソールを使用する必要があります。 この[Adobe Developer Consoleの概要](https://www.adobe.io/apis/experienceplatform/console/docs.html#!AdobeDocs/adobeio-console/master/getting-started.md)に従って開始し、このページのセクションを使用できます。

統合をテストおよび準備するために、Postman コレクションを[こちら](https://raw.githubusercontent.com/AdobeDocs/JourneyAPI/master/postman-collections/Journey-Orchestration_Export-import-API_postman-collection.json)から利用できます。


## Export-Import フロー

環境間でジャーニーを書き出して読み込むには、次の手順に従うことをお勧めします。

1. 開始環境でジャーニーを作成し、パラメーターを設定します。 [詳細情報はこちら](https://experienceleague.adobe.com/docs/journeys/using/building-journeys/about-journey-building/journey.html)
1. ジャーニーのバージョンにエラーがないかどうかを確認します。 [詳細情報はこちら](https://experienceleague.adobe.com/docs/journeys/using/building-journeys/testing-the-journey.html)
1. **/list/journeys** APIを呼び出して、最新のジャーニーバージョンのUID ジャーニーとUIDを取得します。 必要に応じて、**/journeys/`{uid}`/latest**&#x200B;を呼び出して、最新のジャーニーバージョンのUIDを見つけることができます。
1. 開始環境パラメーター（orgIDおよびsandboxName）を使用して、**export** APIを呼び出します。
1. リターンペイロードを開き、次の項目を確認します。
   * 書き出したジャーニーに&#x200B;**特定の資格情報**&#x200B;が含まれている場合は、これらの資格情報を新しい環境に対応する資格情報に置き換える必要があります。
   * 書き出したジャーニーに&#x200B;**イベント**&#x200B;が含まれ、**XDM スキーマ**&#x200B;を指している場合、ID値が異なる場合は、xdmEntity ノードの新しい環境のスキーマ IDでスキーマ ID参照を手動で更新する必要があります。 この更新は、イベントごとに実行する必要があります。 [詳細情報はこちら](https://experienceleague.adobe.com/docs/journeys/using/events-journeys/experience-event-schema.html)
   * ジャーニーに電子メール、smsまたはプッシュアクションが含まれている場合、ターゲット環境の名前が開始環境の名前と異なる場合は、テンプレート名またはmobileApp名を更新する必要がある場合があります。
1. ターゲット環境パラメーター（orgIDおよびsandboxName）を使用して、**Import** APIを呼び出します。 import APIは必要な回数だけ呼び出すことができます。 インポート APIを呼び出すたびに、ジャーニーに含まれる各オブジェクトのUUIDと名前が生成されます。
1. ジャーニーを読み込んだら、Journey Orchestration アプリケーションで公開できます。 詳細情報[こちら](https://experienceleague.adobe.com/docs/journeys/using/building-journeys/publishing-the-journey.html)


## 認証

### API アクセスのセットアップ

Journey Orchestration API アクセスは、次の手順で設定します。 これらの各手順について詳しくは、[Adobe I/O のドキュメント](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md)を参照してください。

>[!CAUTION]
>
>Adobe I/O で証明書を管理するには、組織の<b>システム管理者</b>権限または Admin Console の[開発者アカウント](https://helpx.adobe.com/jp/enterprise/using/manage-developers.html)があることを確認してください。

1. **電子証明書があることを確認するか**、必要に応じて作成します。 証明書に記載されている公開鍵と秘密鍵は、以降の手順で必要になります。
1. Adobe I/O で **[!DNL Journey Orchestration] サービスへの新しい統合を作成**&#x200B;し、設定します。 Journey OrchestrationとAdobe Experience Platformでは、製品プロファイルへのアクセスが必要です。 次に、資格情報を生成します（API キー、クライアントシークレットなど）。

>[!CAUTION]
>
>アクセストークンを生成するJWT メソッドは非推奨（廃止予定）になりました。 すべての新しい統合は、[OAuth サーバー間の認証方法](https://experienceleague.adobe.com/docs/experience-platform/landing/platform-apis/api-authentication.html#select-oauth-server-to-server)を使用して作成する必要があります。 また、アドビでは、既存の統合を OAuth 方法に移行することをお勧めします。
>
>次の重要なドキュメントを参照してください。>[JWTからOAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)へのアプリケーションの移行ガイド>[OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)を使用する新規および古いアプリケーションの実装ガイド>[OAuth サーバー間の資格情報メソッドを使用する利点](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/#why-oauth-server-to-server-credentials)


サービス間のセキュアな Adobe I/O API セッションを確立するには、アドビサービスへのすべてのリクエストで、以下の情報を Authorization ヘッダーに含める必要があります。

```
curl -X GET https://journey.adobe.io/authoring/XXX \
 -H 'Authorization: Bearer <ACCESS_TOKEN>' \
 -H 'x-api-key: <API_KEY>' \
 -H 'x-gw-ims-org-id: <ORGANIZATION>'
```

* **&lt;ORGANIZATION>**：これはあなたの個人組織IDです。Adobeによって、インスタンスごとに1つの組織IDが提供されます。

   * &lt;ORGANIZATION>：実稼動インスタンス

  組織 ID の値を取得するには、管理者またはアドビの技術担当者にお問い合わせください。 また、新しい統合を作成する際に、ライセンスリストで Adobe I/O に取得することもできます（[Adobe I/O のドキュメント](https://www.adobe.io/authentication.html)を参照してください）。

* **&lt;ACCESS_TOKEN>**：個人用アクセストークン

* **&lt;API_KEY>**：個人用 API キーです。 [!DNL Journey Orchestration] サービスへの新しい統合を作成した後、Adobe I/O で提供されます。



## Export-Import APIの説明

このAPIを使用すると、UIDによって識別されるジャーニーバージョンと、そのuidによるすべての関連オブジェクト（ジャーニー、イベント、データソース、フィールドグループ、カスタムアクション）を書き出すことができます。
結果のペイロードを使用して、ジャーニーバージョンを別の環境（サンドボックスまたはインスタンス）に読み込むことができます。

| メソッド | パス | 説明 |
|---|---|---|
| `[POST]` | /journeyVersions/import | ジャーニーバージョンの書き出しから得られるジャーニーバージョンコンテンツの読み込み |
| `[GET]` | /journeyVersions/`{uid}`/export | ジャーニーバージョンの書き出し |
| `[GET]` | /journeys/`{uid}`/latest | ジャーニーの最新ジャーニーバージョンの取得 |
| `[POST]` | /list/journeys | ジャーニーのメタデータとそのジャーニーバージョンのリスト |


### 書き出し特性とガードレール

* ジャーニーはエクスポート前に有効である必要があります。

* 資格情報は書き出されず、プレースホルダー（INSERT_SECRET_HEREなど）が応答ペイロードに挿入されます。
書き出し呼び出しの後、ターゲット環境にペイロードを読み込む前に、新しい資格情報（ターゲット環境に対応）を手動で挿入する必要があります。

* 次のオブジェクトは書き出されますが、ターゲット環境では読み込まれません。 これらのリソースは、Journey Orchestrationで自動的に管理されます。 「INSERT_SECRET_HERE」を置き換える必要はありません。
   * **DataProviders**: &quot;Adobe Campaign Standard Data Provider&quot; （acsDataProvider）および&quot;Experience Platform&quot; （acppsDataProvider）
   * **フィールドグループ** （dataEntities）: &quot;ProfileFieldGroup&quot; （acppsDataPack）



### 読み込み特性

* 読み込み中に、ジャーニーオブジェクトが新しいUIDと新しい名前で作成され、ターゲット環境（インスタンスまたはサンドボックス）での一意性が確保されます。

* インポートペイロードにシークレットのプレースホルダーが含まれている場合は、エラーがスローされます。 ジャーニーを読み込むには、POST呼び出しの前に資格情報を置き換える必要があります。

## 警告とエラー

潜在的なエラーは次のとおりです。

* ジャーニーのバージョンが無効な場合、**書き出し時間**&#x200B;に：エラー500

* **読み込み時間**&#x200B;に、変更後のペイロードが無効であるか、ペイロードで資格情報が明確に定義されていない場合：エラー400

* インポート手順の後、イベントのXDM スキーマ IDがターゲット環境で有効でない場合、Journey Orchestration アプリケーションにエラーが表示されます。 この場合、ジャーニーを公開することはできません。