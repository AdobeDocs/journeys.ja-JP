---
title: インポートのエクスポートAPIの説明
description: インポートエクスポートAPIについて詳しく説明します。
contentOwner: sauviat
products: journeys
audience: audiences
content-type: reference
topic-tags: journeys
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c92d7a4e5ef02f87f705871cd0fdb8c2523966d2
workflow-type: tm+mt
source-wordcount: '1103'
ht-degree: 2%

---


# エクスポートインポートAPIの操作

1回のAPI呼び出しでジャーニーバージョンとその関連オブジェクト(ジャーニー、イベント、データソース、フィールドグループ、カスタムアクション)を書き出します。 エクスポートの結果のペイロードは、別の環境（インスタンスまたはサンドボックス）への遍歴を簡単にインポートするために使用できます。
この機能を使用すると、複数のインスタンスにわたるジャーニーや複数のテスト環境ワークフローを管理できます。


## リソース

Journey OrchestrationインポートエクスポートAPIについては、 [ここで利用可能なSwaggerファイル内で説明し](https://adobedocs.github.io/JourneyAPI/docs/)ています。

このAPIをJourney Orchestrationインスタンスで使用するには、AdobeI/Oコンソールを使用する必要があります。 開始するには、この「 [Adobe開発者コンソール使用の手引き](https://www.adobe.io/apis/experienceplatform/console/docs.html#!AdobeDocs/adobeio-console/master/getting-started.md) 」に従って、このページのセクションを使用します。

統合をテストして準備するには、Postmanコレクションを [こちらから入手できます](https://raw.githubusercontent.com/AdobeDocs/JourneyAPI/master/postman-collections/Journey-Orchestration_Export-import-API_postman-collection.json)。


## Export-Importのフロー

環境間のジャーニーをエクスポートおよびインポートするには、次の手順に従うことをお勧めします。

1. 開始環境で遍歴を作成し、パラメータを設定します。 [詳細情報はこちら](https://docs.adobe.com/content/help/ja-JP/journeys/using/building-journeys/about-journey-building/journey.html)
1. ジャーニーバージョンにエラーがないかどうかを確認します。 [詳細情報はこちら](https://docs.adobe.com/content/help/en/journeys/using/building-journeys/testing-the-journey.html)
1. / **リスト/ジャーニー** APIを呼び出して、最新のジャーニーバージョンのUIDジャーニーとUIDを取得します。 必要に応じて、 **/journeys/`{uid}`/latest** /を呼び出して、最新のジャーニーバージョンのUIDを探すことができます。
1. 開始 **環境パラメーター（orgIDとsandboxName）を使用して** export APIを呼び出します。
1. リターンペイロードを開き、次の項目を確認します。
   * 書き出したジャーニーに **特定の資格情報が含まれる場合**、これらの資格情報を新しい環境に対応する資格情報に置き換える必要があります。
   * 書き出したジャーニーに **XDMスキーマを指す** イベントが含まれる場合は ****、ID値が異なる場合は、xdmEntityノードの新しい環境のスキーマIDを使用して、スキーマID参照を手動で更新する必要があります。 この更新は、イベントごとに行う必要があります。 [詳細情報はこちら](https://docs.adobe.com/content/help/en/journeys/using/events-journeys/experience-event-schema.html)
   * 電子メール、SMS、またはプッシュアクションがジャーニーに含まれる場合、ターゲット環境内の名前が開始環境内の名前と異なる場合は、テンプレート名またはmobileApp名の更新が必要になる場合があります。
1. ターゲット環境で **import** APIを呼び出します。 読み込みAPIは必要な回数だけ呼び出すことができます。 この遍歴に含まれるUUIDと各ノードの名前は、インポートAPIを呼び出すたびに生成されます。
1. ジャーニーを読み込むと、新しいサンドボックスまたは環境に公開できます。


## 認証

### API アクセスの設定

Journey OrchestrationAPIアクセスは、次の手順で設定します。 これらの各手順は、 [AdobeI/Oドキュメントで詳しく説明し](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md)ます。

>[!CAUTION]
>
>AdobeI/Oで証明書を管理するには、組織の <b>System Administrator</b> 権限または管理コンソールの [開発者アカウントを持っていることを確認します](https://helpx.adobe.com/enterprise/using/manage-developers.html) 。

1. **デジタル証明書をお持ちであることを確認するか**、必要に応じて証明書を作成します。 証明書と共に提供される公開鍵と秘密鍵は、次の手順で必要になります。
1. **AdobeI/Oの[!DNL Journey Orchestration]Service** への新しい統合を作成し、構成します。 Journey OrchestrationとAdobe Experience Platformには、商品プロファイルへのアクセスが必要です。 次に、資格情報が生成されます（APIキー、クライアントシークレット。.）。
1. **以前に生成した秘密鍵証明書からJSON Web Token(JWT)** を作成し、秘密鍵で署名します。 JWTは、AdobeがIDを確認し、APIへのアクセスを許可するために必要なすべてのID情報とセキュリティ情報をエンコードします。 この手順については、この [節で説明します](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/JWT/JWT.md)
1. **POSTリクエストまたはDeveloper Consoleインターフェイスを通じて** 、JWTをアクセストークンと交換します。 このアクセストークンは、APIリクエストの各ヘッダーで使用する必要があります。

セキュリティで保護されたサービス間AdobeI/O APIセッションを確立するには、Adobeサービスへのすべての要求を、次の情報をAuthorizationヘッダーに含める必要があります。

```
curl -X GET https://journey.adobe.io/authoring/XXX \
 -H 'Authorization: Bearer <ACCESS_TOKEN>' \
 -H 'x-api-key: <API_KEY>' \
 -H 'x-gw-ims-org-id: <ORGANIZATION>'
```

* **&lt;組織>**:これは個人の組織IDです。各インスタンスに対して1つの組織IDがAdobeによって提供されます。

   * &lt;組織>:実稼働インスタンス
   組織IDの値を取得するには、管理者またはAdobeのテクニカルコンタクトに問い合わせてください。 新しい統合を作成する際に、AdobeI/Oに取得することもできます( [AdobeI/Oのドキュメントを参照](https://www.adobe.io/authentication.html))。

* **&lt;ACCESS_TOKEN>**:JWTをPOST要求で交換する際に取得した個人アクセストークン。

* **&lt;API_KEY>**:個人のAPIキーを参照してください。 これは、 [!DNL Journey Orchestration] サービスへの新しい統合を作成した後、AdobeI/Oで提供されます。



## インポートAPIのエクスポートの説明

このAPIを使用すると、ジャーニーバージョンと、関連するすべてのオブジェクト(ジャーニー、イベント、データソース、フィールドグループ、カスタムアクション)をuidごとに書き出すことができます。
結果のペイロードは、別の環境（サンドボックスまたはインスタンス）でジャーニーバージョンをインポートするために使用できます。

| 方法 | パス | 説明 |
|---|---|---|
| `[POST]` | /jeurneyVersions/import | ジャーニーバージョンのエクスポートから生じるジャーニーバージョンのコンテンツの読み込み |
| `[GET]` | /jeurneyVersions/`{uid}`/export | ジャーニーバージョンの書き出し |
| `[GET]` | /journeys/`{uid}`/latest | 旅行の最新のジャーニーバージョンを入手する |
| `[POST]` | /リスト/ジャーニー | ジャーニーのメタデータと旅のバージョンをリストする |


### 特性とガードレールの書き出し

* 秘密鍵証明書は書き出されず、プレースホルダ（INSERT_SECRET_HEREなど）が挿入されます。
ペイロードのエクスポート後、ターゲット環境にペイロードをインポートする前に、(ターゲット環境に対応する)新しい秘密鍵証明書を手動で挿入する必要があります。

* データソースに **builtIn:trueパラメーターが含まれる場合**、「INSERT_SECRET_HERE」を置き換える必要はありません。 これは、ジャーニー環境によって自動的に管理されるシステムデータソースです。

* 次のオブジェクトは書き出されますが、ターゲット環境には読み込まれません。
   * **DataProviders**: acsDataProviderとacpsDataProvider
   * **フィールドグループ**:acpsFieldGroup
   * **カスタムアクション**:acsAction

* エクスポートの前に、この遍歴は有効でなければなりません。

### インポートの特性

* 読み込み中に、ターゲット環境（インスタンスまたはSandbox）で一意性を確保するために、新しいUUIDと新しい名前を使用してジャーニーオブジェクトが作成されます。

* インポートペイロードにシークレットプレースホルダーが含まれる場合、エラーがスローされます。 POST呼び出しを行う前に、秘密鍵証明書の情報を置き換えて、遍歴を読み込む必要があります。

## 警告とエラー

潜在的なエラーは次のとおりです。

* エク **スポート時**、ジャーニーバージョンが有効でない場合：エラー500

* 読み **込み時**、変更後にペイロードが有効でない場合、またはペイロードで秘密鍵証明書が適切に定義されていない場合：エラー400

* 読み込み手順の後、イベントのXDMスキーマIDを変更せずにターゲット環境でジャーニーを公開しようとすると、エラーが表示されます。

