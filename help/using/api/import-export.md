---
product: adobe campaign
title: インポートエクスポートAPIの説明
description: インポート書き出しAPIについて詳しく説明します。
products: journeys
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '1131'
ht-degree: 3%

---


# Export-Import APIの使用

1回のAPI呼び出しで、ジャーニーバージョンとその関連オブジェクト（ジャーニー、イベント、データソース、フィールドグループ、カスタムアクション）をすべて書き出す。 書き出し結果のペイロードを使用して、ジャーニーを別の環境（インスタンスまたはサンドボックス）に簡単に読み込むことができます。
この機能を使用すると、複数のインスタンスまたは複数のテスト環境ワークフローにわたってジャーニーを管理できます。


## リソース

Journey OrchestrationのExport-Import APIは、[ここ](https://adobedocs.github.io/JourneyAPI/docs/)にあるSwaggerファイル内で説明されます。

このAPIをJourney Orchestrationインスタンスで使用するには、AdobeI/Oコンソールを使用する必要があります。 この[Adobe開発者コンソールの使用の手引き](https://www.adobe.io/apis/experienceplatform/console/docs.html#!AdobeDocs/adobeio-console/master/getting-started.md)に従って開始し、このページの各セクションを使用します。

統合をテストし、準備するために、[ここ](https://raw.githubusercontent.com/AdobeDocs/JourneyAPI/master/postman-collections/Journey-Orchestration_Export-import-API_postman-collection.json)でPostmanコレクションを利用できます。


## 書き出し — 読み込みのフロー

環境をまたいでジャーニーを書き出しおよび読み込むには、次の手順に従うことをお勧めします。

1. 開始環境でジャーニーを作成し、パラメーターを設定する。 [詳細情報はこちら](https://docs.adobe.com/content/help/ja-JP/journeys/using/building-journeys/about-journey-building/journey.html)
1. ジャーニーのバージョンにエラーがないかどうかを確認します。 [詳細情報はこちら](https://docs.adobe.com/content/help/en/journeys/using/building-journeys/testing-the-journey.html)
1. **/list/journeys** APIを呼び出して、最新のジャーニーバージョンのUIDジャーニーとUIDを取得します。 必要に応じて&#x200B;**/journeys/`{uid}`/latest**&#x200B;を呼び出し、最新バージョンのジャーニーのUIDを確認できます。
1. 開始環境パラメーター（orgIDとsandboxName）を使用して&#x200B;**export** APIを呼び出します。
1. リターンペイロードを開き、次の項目を確認します。
   * 書き出したジャーニーに&#x200B;**固有の資格情報**&#x200B;が含まれている場合は、これらの資格情報を新しい環境に対応する資格情報に置き換える必要があります。
   * 書き出したジャーニーに&#x200B;**events**&#x200B;が含まれ、その参照先が&#x200B;**XDMスキーマ**&#x200B;である場合、IDの値が異なる場合は、xdmEntityノードの新しい環境のスキーマIDを使用してスキーマID参照を手動で更新する必要があります。 この更新は、イベントごとにおこなう必要があります。 [詳細情報はこちら](https://docs.adobe.com/content/help/en/journeys/using/events-journeys/experience-event-schema.html)
   * ジャーニーに電子メール、SMS、プッシュアクションが含まれる場合、ターゲット環境の名前が開始環境の名前と異なる場合は、テンプレート名またはmobileApp名を更新する必要が生じる場合があります。
1. ターゲット環境パラメーター（orgIDとsandboxName）を使用して&#x200B;**Import** APIを呼び出します。 インポートAPIは、必要な回数だけ呼び出すことができます。 ジャーニーに含まれる各オブジェクトのUUIDと名前は、インポートAPIを呼び出すたびに生成されます。
1. 読み込んだジャーニーは、Journey Orchestrationアプリケーションで公開できます。 詳細[ここ](https://docs.adobe.com/content/help/en/journeys/using/building-journeys/publishing-the-journey.html)


## 認証

### API アクセスの設定

Journey OrchestrationAPIアクセスは、以下の手順で設定します。 これらの各手順については、[Adobe I/Oのドキュメント](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md)で詳しく説明しています。

>[!CAUTION]
>
>Adobe I/Oで証明書を管理するには、組織の<b>システム管理者</b>権限を持っているか、Admin Consoleの[開発者アカウント](https://helpx.adobe.com/enterprise/using/manage-developers.html)を持っている必要があります。

1. **電子証明書があることを確認する**&#x200B;か、必要に応じて作成します。証明書と共に提供される公開鍵と秘密鍵は、次の手順で必要になります。
1. **サービスへの新しい統合を [!DNL Journey Orchestration]** Adobe I/Oで作成し、設定します。製品プロファイルへのアクセスは、Journey OrchestrationとAdobe Experience Platformに必要です。 資格情報が生成されます（APIキー、クライアント秘密鍵など）。
1. **以前に生成された資格情報からJSON Webトークン(JWT)** を作成し、秘密鍵で署名します。JWTは、IDを検証し、APIへのアクセス権を付与するためにAdobeで必要な、すべてのIDおよびセキュリティ情報をエンコードします。 この手順については、この[節](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/JWT/JWT.md)で詳しく説明します。
1. **JWTをアクセストークンと交換するには、POSTリ** クエストを使用するか、開発者コンソールインターフェイスを使用します。このアクセストークンは、APIリクエストの各ヘッダーで使用する必要があります。

セキュアなサービス間Adobe I/OAPIセッションを確立するには、Adobeサービスへのすべてのリクエストに、以下の情報をAuthorizationヘッダーに含める必要があります。

```
curl -X GET https://journey.adobe.io/authoring/XXX \
 -H 'Authorization: Bearer <ACCESS_TOKEN>' \
 -H 'x-api-key: <API_KEY>' \
 -H 'x-gw-ims-org-id: <ORGANIZATION>'
```

* **&lt;organization>**:これは個人の組織IDで、各インスタンスに対してAdobeが提供するIDは1つです。

   * &lt;organization> :実稼動インスタンス
   組織IDの値を取得するには、管理者または担当のAdobe技術担当者を参照してください。 新しい統合を作成する際に、ライセンスリストでAdobe I/Oに取り込むこともできます([Adobe I/Oのドキュメント](https://www.adobe.io/authentication.html)を参照)。

* **&lt;access_token>**:JWTを交換する際に取得された、POST要求を介した個人用アクセストークン。

* **&lt;api_key>**:個人用APIキー。[!DNL Journey Orchestration]サービスへの新しい統合を作成した後、Adobe I/Oで提供されます。



## Export-Import APIの説明

このAPIを使用すると、UIDおよびすべての関連オブジェクト（ジャーニー、イベント、データソース、フィールドグループ、カスタムアクション）で識別されるジャーニーバージョンをUID別に書き出すことができます。
結果のペイロードは、ジャーニーバージョンを別の環境（サンドボックスまたはインスタンス）に読み込むために使用できます。

| メソッド | パス | 説明 |
|---|---|---|
| `[POST]` | /journeyVersions/import | ジャーニーバージョンの書き出しから生成されたジャーニーバージョンのコンテンツの読み込み |
| `[GET]` | /journeyVersions/`{uid}`/export | ジャーニーのバージョンの書き出し |
| `[GET]` | /journeys/`{uid}`/latest | ジャーニーの最新バージョンを入手する |
| `[POST]` | /list/journeys | ジャーニーのメタデータとジャーニーバージョンのリスト |


### 書き出しの特性とガードレール

* エクスポートの前に、ジャーニーが有効である必要があります。

* 資格情報は書き出されず、プレースホルダー(INSERT_SECRET_HERE)が応答ペイロードに挿入されます。
書き出し呼び出しの後、ターゲット環境でペイロードを読み込む前に、（ターゲット環境に対応する）新しい資格情報を手動で挿入する必要があります。

* 次のオブジェクトは書き出されますが、対象の環境には読み込まれません。 これらは、システムが自動的に管理するJourney Orchestrationリソースです。 &quot;INSERT_SECRET_HERE&quot;を置き換える必要はありません。
   * **データプロバイダー**:「Adobe Campaign Standard Data Provider」(acsDataProvider)および「Experience Platform」(acppsDataProvider)
   * **フィールドグループ** (dataEntities):「ProfileFieldGroup」(acppsDataPack)



### インポートの特性

* インポート時に、ジャーニーオブジェクトは、ターゲット環境（インスタンスまたはサンドボックス）で一意性を確保するために、新しいUIDと新しい名前で作成されます。

* インポートペイロードにシークレットプレースホルダーが含まれている場合、エラーがスローされます。 ジャーニーを読み込むには、認証呼び出しの前にPOST情報を置き換える必要があります。

## 警告とエラー

潜在的なエラーは次のとおりです。

* **書き出し時刻**&#x200B;に、ジャーニーのバージョンが有効でない場合：エラー500

* **読み込み時刻**&#x200B;に、変更後にペイロードが有効でない場合、またはペイロードで資格情報が適切に定義されていない場合：エラー400

* 読み込み手順の後、イベントのXDMスキーマIDがターゲット環境で有効でない場合は、Journey Orchestrationアプリケーションにエラーが表示されます。 このような場合、ジャーニーを公開することはできません。