---
product: adobe campaign
solution: Journey Orchestration
title: インポートのエクスポートAPIの説明
description: インポートエクスポートAPIについて詳しく説明します。
products: journeys
translation-type: tm+mt
source-git-commit: 8da1d4a6c01279bf502c3ec39bdaba8fcc8e64f8
workflow-type: tm+mt
source-wordcount: '1131'
ht-degree: 3%

---


# Export-Import APIの使用

1回のAPI呼び出しで、ジャーニーバージョンとその関連オブジェクト(ジャーニー、イベント、データソース、フィールドグループ、カスタムアクション)を書き出します。 書き出し結果のペイロードは、ジャーニーを別の環境（インスタンスまたはサンドボックス）に簡単に読み込むために使用できます。
この機能を使用すると、複数のインスタンスまたは複数のテスト環境ワークフローにわたってジャーニーを管理できます。


## リソース

Journey OrchestrationのExport-Import APIは、[ここ](https://adobedocs.github.io/JourneyAPI/docs/)で入手できるSwaggerファイル内で説明されています。

このAPIをJourney Orchestrationインスタンスで使用するには、AdobeI/Oコンソールを使用する必要があります。 この[Adobe開発者コンソール使用の手引き](https://www.adobe.io/apis/experienceplatform/console/docs.html#!AdobeDocs/adobeio-console/master/getting-started.md)に従って開始し、このページのセクションを使用します。

統合をテストし、準備するために、Postmanコレクションを[ここ](https://raw.githubusercontent.com/AdobeDocs/JourneyAPI/master/postman-collections/Journey-Orchestration_Export-import-API_postman-collection.json)で利用できます。


## Export-Importのフロー

環境間でジャーニーを書き出しおよび読み込むには、次の手順に従うことをお勧めします。

1. 開始環境でジャーニーを作成し、パラメータを設定します。 [詳細情報はこちら](https://docs.adobe.com/content/help/ja-JP/journeys/using/building-journeys/about-journey-building/journey.html)
1. ジャーニーのバージョンにエラーがないかどうかを確認します。 [詳細情報はこちら](https://docs.adobe.com/content/help/en/journeys/using/building-journeys/testing-the-journey.html)
1. **/リスト/ジャーニー** APIを呼び出して、最新ジャーニーのUIDジャーニーとUIDを取得します。 必要に応じて、**/ジャーニー/`{uid}`/latest**&#x200B;を呼び出して、最新ジャーニー版のUIDを探すことができます。
1. 開始環境パラメーター（orgIDとsandboxName）を使用して&#x200B;**export** APIを呼び出します。
1. リターンペイロードを開き、次の項目を確認します。
   * 書き出したジャーニーに&#x200B;**固有の資格情報**&#x200B;が含まれている場合は、これらの資格情報を新しい環境に対応する資格情報に置き換える必要があります。
   * 書き出したジャーニーに&#x200B;**XDMスキーマ**&#x200B;を指す&#x200B;**イベント**&#x200B;が含まれている場合、IDの値が異なる場合は、xdmEntityノードの新しい環境のスキーマIDを使用して、スキーマID参照を手動で更新する必要があります。 この更新は、イベントごとに行う必要があります。 [詳細情報はこちら](https://docs.adobe.com/content/help/en/journeys/using/events-journeys/experience-event-schema.html)
   * ジャーニーに電子メール、SMS、またはプッシュ操作が含まれる場合、ターゲット環境内の名前が開始環境内の名前と異なる場合は、テンプレート名またはmobileApp名の更新が必要になる場合があります。
1. ターゲット環境パラメーター（orgIDとsandboxName）を使用して&#x200B;**Import** APIを呼び出します。 読み込みAPIは必要な回数だけ呼び出すことができます。 ジャーニーに含まれる各オブジェクトのUUIDと名前は、import APIを呼び出すたびに生成されます。
1. ジャーニーを読み込むと、Journey Orchestrationアプリで公開できます。 詳細情報[ここ](https://docs.adobe.com/content/help/en/journeys/using/building-journeys/publishing-the-journey.html)


## 認証

### API アクセスの設定

Journey OrchestrationAPIアクセスは、次の手順で設定します。 これらの各手順の詳細については、[Adobe I/Oドキュメント](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md)を参照してください。

>[!CAUTION]
>
>Adobe I/Oで証明書を管理するには、組織の<b>システム管理者</b>権限、または管理コンソールの[開発者アカウント](https://helpx.adobe.com/enterprise/using/manage-developers.html)権限があることを確認してください。

1. **デジタル証明書をお持ちであることを確認するか**、必要に応じて証明書を作成します。証明書と共に提供される公開鍵と秘密鍵は、次の手順で必要になります。
1. **Adobe I/Oで [!DNL Journey Orchestration]** Servicesへの新しい統合を作成し、設定します。Journey OrchestrationとAdobe Experience Platformには、商品プロファイルへのアクセスが必要です。 次に、資格情報が生成されます（APIキー、クライアントシークレット。.）。
1. **以前に生成した秘密鍵証明書** からJSON Web Token(JWT)を作成し、秘密鍵で署名します。JWTは、AdobeがIDを確認し、APIへのアクセスを許可するために必要なすべてのID情報とセキュリティ情報をエンコードします。 この手順の詳細は、[](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/JWT/JWT.md)セクションで説明します。
1. **POSTの要求またはDeveloper Consoleインターフェイスを使用して、JWTをアクセス** トークンと交換します。このアクセストークンは、APIリクエストの各ヘッダーで使用する必要があります。

セキュリティで保護されたサービス間Adobe I/OAPIセッションを確立するには、Adobeサービスへのすべての要求をAuthorizationヘッダーに以下の情報を含める必要があります。

```
curl -X GET https://journey.adobe.io/authoring/XXX \
 -H 'Authorization: Bearer <ACCESS_TOKEN>' \
 -H 'x-api-key: <API_KEY>' \
 -H 'x-gw-ims-org-id: <ORGANIZATION>'
```

* **&lt;organization>**:これは個人の組織IDです。各インスタンスに対して1つの組織IDがAdobeによって提供されます。

   * &lt;organization> :実稼働インスタンス
   組織IDの値を取得するには、管理者またはAdobeのテクニカルコンタクトに問い合わせてください。 新しい統合を作成する際に、ライセンスリストでAdobe I/Oに取り込むこともできます([Adobe I/Oドキュメント](https://www.adobe.io/authentication.html)を参照)。

* **&lt;access_token>**:JWTをPOST要求で交換する際に取得した個人アクセストークン。

* **&lt;api_key>**:個人のAPIキーを参照してください。[!DNL Journey Orchestration]サービスへの新しい統合を作成した後、Adobe I/Oで提供されます。



## Export-Import APIの説明

このAPIを使用すると、UIDで識別されるジャーニーバージョンと、そのUIDで識別されるすべての関連オブジェクト(ジャーニー、イベント、データソース、フィールドグループ、カスタムアクション)をエクスポートできます。
結果のペイロードは、別の環境（サンドボックスまたはインスタンス）のジャーニーバージョンをインポートするために使用できます。

| 方法 | パス | 説明 |
|---|---|---|
| `[POST]` | /jeurneyVersions/import | ジャーニーバージョンの書き出しの結果として生じるジャーニーバージョンのコンテンツの読み込み |
| `[GET]` | /jeurneyVersions/`{uid}`/export | ジャーニーバージョンの書き出し |
| `[GET]` | /ジャーニー/`{uid}`/最新 | ジャーニーの最新ジャーニーバージョンの取得 |
| `[POST]` | /リスト/ジャーニー | ジャーニーのメタデータとジャーニーバージョンのリスト |


### 特性とガードレールの書き出し

* 書き出しの前に、ジャーニーが有効である必要があります。

* 秘密鍵証明書はエクスポートされず、プレースホルダー（INSERT_SECRET_HEREなど）が応答ペイロードに挿入されます。
書き出しの呼び出し後、ターゲット環境にペイロードを読み込む前に、(ターゲット環境に対応する)新しい秘密鍵証明書を手動で挿入する必要があります。

* 次のオブジェクトは書き出されますが、ターゲット環境に読み込まれることはありません。 これらは、Journey Orchestrationが自動的に管理するシステムリソースです。 「INSERT_SECRET_HERE」を置き換える必要はありません。
   * **DataProviders**:&quot;Adobe Campaign Standardデータプロバイダ&quot; (acsDataProvider)と&quot;Experience Platform&quot; (acpsDataProvider)
   * **フィールドグループ** (dataEntities):&quot;ProfileFieldGroup&quot; (acpsDataPack)



### インポートの特性

* 読み込み中に、ジャーニーオブジェクトは新しいUIDと新しい名前を使用して作成され、ターゲット環境（インスタンスまたはサンドボックス）内で一意性を確保します。

* インポートペイロードにシークレットプレースホルダーが含まれる場合、エラーがスローされます。 ジャーニーを読み込むには、POST呼び出しの前に、秘密鍵証明書の情報を置き換える必要があります。

## 警告とエラー

潜在的なエラーは次のとおりです。

* **書き出し時刻**&#x200B;に、ジャーニーのバージョンが有効でない場合：エラー500

* **読み込み時間**&#x200B;に、変更後のペイロードが有効でないか、ペイロードで秘密鍵証明書が適切に定義されていない場合：エラー400

* 読み込み手順の後、イベントのXDMスキーマIDがターゲット環境で有効でない場合は、Journey Orchestrationアプリケーションにエラーが表示されます。 この場合、ジャーニーを公開することはできません。