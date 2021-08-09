---
product: adobe campaign
title: キャッピングAPIの説明
description: キャッピングAPIについて詳しく説明します。
products: journeys
feature: ジャーニー
role: User
level: Intermediate
exl-id: 6f28e62d-7747-43f5-a360-1d6af14944b6
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '1171'
ht-degree: 9%

---

# キャッピングAPIの使用

## はじめに

[!DNL Journey Orchestration]のAPIでは5000イベント/秒がサポートされていますが、一部の外部システムまたはAPIで同等のスループットを持つことができませんでした。そのため、[!DNL Journey Orchestration]には、外部システムに課せるレートを監視および制限するCapping APIと呼ばれる専用機能が付属しています。

データソースの設定時に、ジャーニーで使用される追加情報を取得するために、またはアクション定義のために、システムへの接続を定義します。メッセージやAPI呼び出しを送信するサードパーティシステムの接続を設定します。 ジャーニーによってAPI呼び出しが実行されるたびに、キャッピングAPIに対するクエリが実行され、呼び出しはAPIエンジンを通じておこなわれます。 制限が定義されている場合、呼び出しは拒否され、外部システムは過負荷になりません。

外部データソースの場合、1 秒あたりの最大呼び出し回数は 15 に設定されています。 1 秒あたりの呼び出し回数が 15 を超えると、残りの呼び出しは破棄されます。 プライベート外部データソースに対しては、この上限を増やすことができます。 エンドポイントを許可リストに加えるには、アドビにお問い合わせください。パブリック外部データソースに対しては、この操作は行えません。外部システムを統合する際のベストプラクティスとガードレールについて詳しくは、[ページ](../about/external-systems.md)を参照してください。

アクションまたはデータソースの設定について詳しくは、[アクションについて](https://experienceleague.adobe.com/docs/journeys/using/action-journeys/action.html)または[データソースについて](https://experienceleague.adobe.com/docs/journeys/using/data-source-journeys/about-data-sources.html)を参照してください。

## リソース

>[!NOTE]
>
>[!DNL Journey Orchestration]キャッピングAPIは、[ここ](https://adobedocs.github.io/JourneyAPI/docs/)にあるSwaggerファイル内で記述します。

このAPIを[!DNL Journey Orchestration]インスタンスで使用するには、AdobeI/Oコンソールを使用する必要があります。 この[Adobe開発者コンソールの使用の手引き](https://www.adobe.io/apis/experienceplatform/console/docs.html#!AdobeDocs/adobeio-console/master/getting-started.md)に従って開始し、このページの各セクションを使用します。

統合をテストし、準備するために、[ここ](https://raw.githubusercontent.com/AdobeDocs/JourneyAPI/master/postman-collections/Journey-Orchestration_Capping-API_postman-collection.json)でPostmanコレクションを利用できます。

## 認証

### API アクセスの設定

[!DNL Journey Orchestration] APIアクセスは、以下の手順で設定します。これらの各手順については、[Adobe I/Oのドキュメント](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md)で詳しく説明しています。

>[!CAUTION]
>
>Adobe I/Oで証明書を管理するには、組織の<b>システム管理者</b>権限を持っているか、Admin Consoleの[開発者アカウント](https://helpx.adobe.com/jp/enterprise/using/manage-developers.html)を持っている必要があります。

1. **電子証明書があることを確認する**&#x200B;か、必要に応じて作成します。証明書と共に提供される公開鍵と秘密鍵は、次の手順で必要になります。
1. **サービスへの新しい統合を [!DNL Journey Orchestration]** Adobe I/Oで作成し、設定します。製品プロファイルへのアクセスは、[!DNL Journey Orchestration]とAdobe Experience Platformに必要です。 資格情報が生成されます（APIキー、クライアント秘密鍵など）。
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

   組織IDの値を取得するには、管理者または担当のAdobe技術担当者を参照してください。 新しい統合を作成する際に、ライセンスリストでAdobe I/Oに取り込むこともできます(<a href="https://www.adobe.io/authentication.html">Adobe I/Oのドキュメント</a>を参照)。

* **&lt;access_token>**:JWTを交換する際に取得された、POST要求を介した個人用アクセストークン。

* **&lt;api_key>**:個人用APIキー。[!DNL Journey Orchestration]サービスへの新しい統合を作成した後、Adobe I/Oで提供されます。



## キャッピングAPIの説明

キャッピングAPIは、キャッピング設定を作成、設定および監視するのに役立ちます。

| メソッド | Path | 説明 |
|---|---|---|
| [!DNL POST] | list/endpointConfigs | エンドポイントキャッピング設定のリストの取得 |
| [!DNL POST] | /endpointConfigs | エンドポイントキャッピング設定の作成 |
| [!DNL POST] | /endpointConfigs/`{uid}`/deploy | エンドポイントキャッピング設定のデプロイ |
| [!DNL POST] | /endpointConfigs/`{uid}`/undeploy | エンドポイントキャッピング設定のデプロイ解除 |
| [!DNL POST] | /endpointConfigs/`{uid}`/canDeploy | エンドポイントキャッピング設定をデプロイできるかどうかの確認 |
| [!DNL PUT] | /endpointConfigs/`{uid}` | エンドポイントキャッピング設定の更新 |
| [!DNL GET] | /endpointConfigs/`{uid}` | エンドポイントキャッピングの設定の取得 |
| [!DNL DELETE] | /endpointConfigs/`{uid}` | エンポイントキャッピング設定の削除 |

設定を作成または更新すると、ペイロードの構文と整合性を保証するチェックが自動的に実行されます。
問題が発生した場合は、設定を修正するのに役立つ警告またはエラーが返されます。



## エンドポイントの設定

次に、エンドポイント設定の基本構造を示します。

```
{
    "url": "<endpoint URL>",  //wildcards are allowed in the endpoint URL
    "methods": [ "<HTTP method such as GET, POST, >, ...],
    "services": {
        "<service name>": { . //must be "action" or "dataSource" 
            "maxHttpConnections": <max connections count to the endpoint>
            "rating": {          
                "maxCallsCount": <max calls to be performed in the period defined by period/timeUnit>,
                "periodInMs": <integer value greater than 0>
            }
        },
        ...
    }
}
```

### 例：

```
`{
  "url": "https://api.example.org/data/2.5/*",
  "methods": [
    "GET"
  ],
  "services": {
    "dataSource": {
      "maxHttpConnections": 30000,
      "rating": {
        "maxCallsCount": 5000,
        "periodInMs": 1000
      }
    }
  },
  "orgId": "<IMS Org Id>"
}
```


## 警告とエラー

**canDeploy**&#x200B;メソッドが呼び出されると、プロセスは設定を検証し、一意のIDで識別される検証ステータスを返します。

```
"ok" or "error"
```

潜在的なエラーは次のとおりです。

* **ERR_ENDPOINTCONFIG_100**:キャッピング設定：URLが見つからないか、無効です
* **ERR_ENDPOINTCONFIG_101**:キャッピング設定：不正なURL
* **ERR_ENDPOINTCONFIG_102**:キャッピング設定：urlの形式が正しくありません。host:portでは、url内のwildcharを使用できません。
* **ERR_ENDPOINTCONFIG_103**:キャッピング設定：HTTPメソッドが見つかりません
* **ERR_ENDPOINTCONFIG_104**:キャッピング設定：呼び出しの評価が定義されていません
* **ERR_ENDPOINTCONFIG_107**:キャッピング設定：無効な最大呼び出し数(maxCallsCount)
* **ERR_ENDPOINTCONFIG_108**:キャッピング設定：無効な最大呼び出し数(periodInMs)
* **ERR_ENDPOINTCONFIG_111**:キャッピング設定：エンドポイント設定を作成できません：無効なペイロード
* **ERR_ENDPOINTCONFIG_112**:キャッピング設定：エンドポイント設定を作成できません：JSONペイロードを予期しています
* **ERR_AUTHORING_ENDPOINTCONFIG_1**:無効なサービス名 `<!--<given value>-->`です：は、&#39;dataSource&#39;または&#39;action&#39;である必要があります。


警告の可能性は次のとおりです。

**ERR_ENDPOINTCONFIG_106**:キャッピング設定：最大HTTP接続数が定義されていません：デフォルトでは無制限



## 使用例

この節では、[!DNL Journey Orchestration]で上限設定を管理するために実行できる5つの主な使用例を示します。

テストと設定を支援するために、Postmanコレクションは[ここ](https://raw.githubusercontent.com/AdobeDocs/JourneyAPI/master/postman-collections/Journey-Orchestration_Capping-API_postman-collection.json)から入手できます。

このPostmanコレクションは、__[Adobe I/Oコンソールの統合](https://console.adobe.io/integrations) >試行> Postman__&#x200B;のダウンロードで生成されたPostman変数コレクションを共有するように設定されています。このコレクションは、選択した統合値を持つPostman環境ファイルを生成します。

ダウンロードしてPostmanにアップロードしたら、次の3つの変数を追加する必要があります。`{JO_HOST}`、`{Base_Path}`および`{SANDBOX_NAME}`。
* `{JO_HOST}` : [!DNL Journey Orchestration] ゲートウェイURL
* `{BASE_PATH}` :APIのエントリポイント。値は「/authoring」です。
* `{SANDBOX_NAME}` :API操作が **おこなわれるサンドボックス名に対応するヘッダーx-sandbox-name** （例えば、「prod」）。詳しくは、「[サンドボックスの概要](https://experienceleague.adobe.com/docs/experience-platform/sandbox/home.html?lang=ja)」を参照してください。

次の節では、このユースケースを実行するためのRest API呼び出し順序付きリストを見つけます。

ユースケースn°1:**新しいキャッピング設定の作成とデプロイ**

1. list
1. 作成
1. candeploy
1. デプロイ

ユースケースn°2:**まだデプロイされていないキャッピング設定を更新し、デプロイします**

1. list
1. get
1. 更新
1. candeploy
1. デプロイ

ユースケースn°3:**デプロイ済みのキャッピング設定のデプロイ解除と削除**

1. list
1. デプロイ解除
1. 次を削除します。

ユースケースn°4:**デプロイ済みのキャッピング設定を削除します。**

1回のAPI呼び出しで、 forceDeleteパラメーターを使用して設定のデプロイを解除および削除できます。
1. list
1. 削除、forceDeleteパラメーターを使用

ユースケースn°5:**デプロイ済みのキャッピング設定の更新**

1. list
1. get
1. 更新
1. デプロイ解除
1. candeploy
1. デプロイ
