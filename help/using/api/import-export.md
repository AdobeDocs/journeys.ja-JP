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

1回のAPI呼び出しでジャーニーバージョンとその関連オブジェクト(ジャーニー、イベント、データソース、フィールドグループ、カスタムアクション)を書き出します。 エクスポートの結果のペイロードは、別の環境（インスタンスまたはサンドボックス）への遍歴を簡単にインポートするために使用できます。
この機能を使用すると、複数のインスタンスにわたるジャーニーや複数のテスト環境ワークフローを管理できます。


## リソース

Journey OrchestrationのExport-Import APIは、[ここ](https://adobedocs.github.io/JourneyAPI/docs/)で入手できるSwaggerファイル内で説明されています。

このAPIをJourney Orchestrationインスタンスで使用するには、AdobeI/Oコンソールを使用する必要があります。 この[Adobe開発者コンソール使用の手引き](https://www.adobe.io/apis/experienceplatform/console/docs.html#!AdobeDocs/adobeio-console/master/getting-started.md)に従って開始し、このページのセクションを使用します。

統合をテストし、準備するために、Postmanコレクションを[ここ](https://raw.githubusercontent.com/AdobeDocs/JourneyAPI/master/postman-collections/Journey-Orchestration_Export-import-API_postman-collection.json)で利用できます。


## Export-Importのフロー

環境間のジャーニーをエクスポートおよびインポートするには、次の手順に従うことをお勧めします。

1. 開始環境で遍歴を作成し、パラメータを設定します。 [詳細情報はこちら](https://docs.adobe.com/content/help/ja-JP/journeys/using/building-journeys/about-journey-building/journey.html)
1. ジャーニーバージョンにエラーがないかどうかを確認します。 [詳細情報はこちら](https://docs.adobe.com/content/help/en/journeys/using/building-journeys/testing-the-journey.html)
1. **/リスト/ジャーニー** APIを呼び出して、最新のジャーニーバージョンのUIDジャーニーとUIDを取得します。 必要に応じて、**/journeys/`{uid}`/latest**&#x200B;を呼び出して、最新のジャーニーバージョンのUIDを探すことができます。
1. 開始環境パラメーター（orgIDとsandboxName）を使用して&#x200B;**export** APIを呼び出します。
1. リターンペイロードを開き、次の項目を確認します。
   * 書き出したジャーニーに&#x200B;**固有の資格情報**&#x200B;が含まれる場合は、これらの資格情報を新しい環境に対応する資格情報に置き換える必要があります。
   * 書き出したジャーニーに&#x200B;**XDMスキーマ**&#x200B;を指す&#x200B;**イベント**&#x200B;が含まれている場合、IDの値が異なる場合は、xdmEntityノードの新しい環境のスキーマIDでスキーマID参照を手動で更新する必要があります。 この更新は、イベントごとに行う必要があります。 [詳細情報はこちら](https://docs.adobe.com/content/help/en/journeys/using/events-journeys/experience-event-schema.html)
   * 電子メール、SMS、またはプッシュアクションがジャーニーに含まれる場合、ターゲット環境内の名前が開始環境内の名前と異なる場合は、テンプレート名またはmobileApp名の更新が必要になる場合があります。
1. ターゲット環境パラメーター（orgIDとsandboxName）を使用して&#x200B;**Import** APIを呼び出します。 読み込みAPIは必要な回数だけ呼び出すことができます。 UUIDと、この遍歴に含まれる各オブジェクトの名前は、読み込みAPIを呼び出すたびに生成されます。
1. Jarneyを読み込むと、Journey Orchestrationアプリケーションで公開できます。 詳細情報[ここ](https://docs.adobe.com/content/help/en/journeys/using/building-journeys/publishing-the-journey.html)


## 認証

### API アクセスの設定

Journey OrchestrationAPIアクセスは、次の手順で設定します。 各手順の詳細については、[Adobe I/Oのドキュメント](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md)を参照してください。

>[!CAUTION]
>
>Adobe I/Oで証明書を管理するには、組織の<b>システム管理者</b>権限、または管理コンソールの[開発者アカウント](https://helpx.adobe.com/enterprise/using/manage-developers.html)権限があることを確認してください。

1. **デジタル証明書をお持ちであることを確認するか**、必要に応じて証明書を作成します。証明書と共に提供される公開鍵と秘密鍵は、次の手順で必要になります。
1. **Adobe I/Oで [!DNL Journey Orchestration]** Serviceへの新しい統合を作成し、設定します。Journey OrchestrationとAdobe Experience Platformには、商品プロファイルへのアクセスが必要です。 次に、資格情報が生成されます（APIキー、クライアントシークレット。.）。
1. **以前に生成した秘密鍵証明書** からJSON Web Token(JWT)を作成し、秘密鍵で署名します。JWTは、AdobeがIDを確認し、APIへのアクセスを許可するために必要なすべてのID情報とセキュリティ情報をエンコードします。 この手順の詳細は、[](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/JWT/JWT.md)セクションで説明します。
1. **POSTの要求またはDeveloper Consoleインターフェイスを使用して、JWTをアクセス** トークンと交換します。このアクセストークンは、APIリクエストの各ヘッダーで使用する必要があります。

セキュリティで保護されたサービス間Adobe I/OAPIセッションを確立するには、Adobeサービスへのすべての要求を、次の情報をAuthorizationヘッダーに含める必要があります。

```
curl -X GET https://journey.adobe.io/authoring/XXX \
 -H 'Authorization: Bearer <ACCESS_TOKEN>' \
 -H 'x-api-key: <API_KEY>' \
 -H 'x-gw-ims-org-id: <ORGANIZATION>'
```

* **&lt;organization>**:これは個人の組織IDです。各インスタンスに対して1つの組織IDがAdobeによって提供されます。

   * &lt;organization> :実稼働インスタンス
   組織IDの値を取得するには、管理者またはAdobeのテクニカルコンタクトに問い合わせてください。 また、新しい統合を作成する際に、ライセンスリストでAdobe I/Oに取得することもできます([Adobe I/Oのドキュメント](https://www.adobe.io/authentication.html)を参照)。

* **&lt;access_token>**:JWTをPOST要求で交換する際に取得した個人アクセストークン。

* **&lt;api_key>**:個人のAPIキーを参照してください。[!DNL Journey Orchestration]サービスへの新しい統合を作成した後、Adobe I/Oで提供されます。



## Export-Import APIの説明

このAPIを使用すると、UIDとすべての関連オブジェクト(ジャーニー、イベント、データソース、フィールドグループ、カスタムアクション)で識別されるジャーニーバージョンを、uidでエクスポートできます。
結果のペイロードは、別の環境（サンドボックスまたはインスタンス）でジャーニーバージョンをインポートするために使用できます。

| 方法 | パス | 説明 |
|---|---|---|
| `[POST]` | /jeurneyVersions/import | ジャーニーバージョンのエクスポートから生じるジャーニーバージョンのコンテンツの読み込み |
| `[GET]` | /jeurneyVersions/`{uid}`/export | ジャーニーバージョンの書き出し |
| `[GET]` | /journeys/`{uid}`/latest | 旅行の最新のジャーニーバージョンを入手する |
| `[POST]` | /リスト/ジャーニー | ジャーニーのメタデータと旅のバージョンをリストする |


### 特性とガードレールの書き出し

* エクスポートの前に、この遍歴は有効でなければなりません。

* 秘密鍵証明書はエクスポートされず、プレースホルダー（INSERT_SECRET_HEREなど）が応答ペイロードに挿入されます。
書き出しの呼び出し後、ターゲット環境にペイロードを読み込む前に、(ターゲット環境に対応する)新しい秘密鍵証明書を手動で挿入する必要があります。

* 次のオブジェクトは書き出されますが、ターゲット環境に読み込まれることはありません。 これらは、Journey Orchestrationが自動的に管理するシステムリソースです。 「INSERT_SECRET_HERE」を置き換える必要はありません。
   * **DataProviders**:&quot;Adobe Campaign Standardデータプロバイダ&quot; (acsDataProvider)と&quot;Experience Platform&quot; (acpsDataProvider)
   * **フィールドグループ** (dataEntities):&quot;ProfileFieldGroup&quot; (acpsDataPack)



### インポートの特性

* 読み込み中に、ターゲット環境（インスタンスまたはサンドボックス）内で一意性を確保するために、新しいUIDと新しい名前を使用してジャーニーオブジェクトが作成されます。

* インポートペイロードにシークレットプレースホルダーが含まれる場合、エラーがスローされます。 POST呼び出しを行う前に、秘密鍵証明書の情報を置き換えて、遍歴を読み込む必要があります。

## 警告とエラー

潜在的なエラーは次のとおりです。

* **書き出し時刻**&#x200B;に、ジャーニーのバージョンが有効でない場合：エラー500

* **読み込み時間**&#x200B;に、変更後のペイロードが有効でないか、ペイロードで秘密鍵証明書が適切に定義されていない場合：エラー400

* 読み込み手順の後、イベントのXDMスキーマIDがターゲット環境で有効でない場合は、Journey Orchestrationアプリケーションにエラーが表示されます。 このような場合には、この旅を出版することは不可能です。