---
product: adobe campaign
title: キャッピング API の説明
description: キャッピング API の詳細を説明します。
products: journeys
feature: Journeys
role: User
level: Intermediate
exl-id: 6f28e62d-7747-43f5-a360-1d6af14944b6
source-git-commit: a32a208fcaef9a408c850c0ad74ab44e3eb44709
workflow-type: tm+mt
source-wordcount: '1173'
ht-degree: 9%

---

# キャッピング API の使用

## はじめに

[!DNL Journey Orchestration]の API は 5000 イベント/秒をサポートしていますが、一部の外部システムや API は同等のスループットを持つことができませんでした。 だからこそ [!DNL Journey Orchestration] には、外部システムに課せる率を監視および制限する、Capping API と呼ばれる専用の機能が付属しています。

データソースの設定時に、ジャーニーで使用される追加情報を取得するためのシステムへの接続を定義します。または、アクション定義の際に、メッセージや API 呼び出しを送信するサードパーティシステムへの接続を設定します。 ジャーニーが API 呼び出しを実行するたびに、キャッピング API に対するクエリが実行され、その呼び出しは API エンジンを通じておこなわれます。 制限が定義されている場合、呼び出しは拒否され、外部システムはオーバーロードされません。

外部データソースの場合、1 秒あたりの最大呼び出し回数は 15 に設定されています。 1 秒あたりの呼び出し回数が 15 を超えると、残りの呼び出しは破棄されます。 プライベート外部データソースに対しては、この上限を増やすことができます。 アドビに連絡して、エンドポイントを許可リストに含めてください。パブリック外部データソースに対しては、この操作は行えません。外部システムを統合する際のベストプラクティスとガードレールについて詳しくは、こちらを参照してください。 [ページ](../about/external-systems.md).

アクションまたはデータソースの設定について詳しくは、 [アクションについて](https://experienceleague.adobe.com/docs/journeys/using/action-journeys/action.html) または [データソースについて](https://experienceleague.adobe.com/docs/journeys/using/data-source-journeys/about-data-sources.html)

## リソース

>[!NOTE]
>
>この [!DNL Journey Orchestration] キャッピング API は、使用可能な Swagger ファイル内で説明されます [ここ](https://adobedocs.github.io/JourneyAPI/docs/).

この API を [!DNL Journey Orchestration] 例えば、AdobeI/O コンソールを使用する必要があります。 次の手順から始めることができます [はじめに —Adobe開発者コンソール](https://www.adobe.io/apis/experienceplatform/console/docs.html#!AdobeDocs/adobeio-console/master/getting-started.md) その後、このページの「 」セクションを使用します。

統合をテストおよび準備するために、Postman コレクションを使用できます [ここ](https://raw.githubusercontent.com/AdobeDocs/JourneyAPI/master/postman-collections/Journey-Orchestration_Capping-API_postman-collection.json).

## 認証

### API アクセスの設定

[!DNL Journey Orchestration] API アクセスは、次の手順で設定します。 これらの各手順について詳しくは、 [Adobe I/O文書](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md).

>[!CAUTION]
>
>証明書をAdobe I/Oで管理するには、 <b>システム管理者</b> 組織または [開発者アカウント](https://helpx.adobe.com/jp/enterprise/using/manage-developers.html) Admin Console でログインします。

1. **電子証明書を持っていることを確認します**&#x200B;または必要に応じて作成します。 証明書と共に提供される公開鍵と秘密鍵は、次の手順で必要になります。
1. **への新しい統合の作成 [!DNL Journey Orchestration] サービス** をAdobe I/Oし、設定します。 次の場合には、製品プロファイルへのアクセスが必要です。 [!DNL Journey Orchestration] Adobe Experience Platform 資格情報が生成されます（API キー、クライアント秘密鍵。.）。
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

   組織 ID 値を取得するには、管理者または担当のAdobe技術担当者にお問い合わせください。 また、新しい統合を作成する際に、Adobe I/Oに取得することもできます ( <a href="https://www.adobe.io/authentication.html">Adobe I/O文書</a>) をクリックします。

* **&lt;access_token>**:個人用アクセストークン。POSTリクエストで JWT を交換する際に取得されました。

* **&lt;api_key>**:個人用 API キー。 への新しい統合を作成した後、Adobe I/Oで提供されます。 [!DNL Journey Orchestration] サービス。



## キャッピング API の説明

キャッピング API は、キャッピング設定を作成、設定および監視するのに役立ちます。

| メソッド | パス | 説明 |
|---|---|---|
| [!DNL POST] | list/endpointConfigs | エンドポイントキャッピング設定のリストを取得します |
| [!DNL POST] | /endpointConfigs | エンドポイントキャップ設定の作成 |
| [!DNL POST] | /endpointConfigs/`{uid}`/deploy | エンドポイントキャップ設定のデプロイ |
| [!DNL POST] | /endpointConfigs/`{uid}`/undeploy | エンドポイントキャッピング設定のデプロイ解除 |
| [!DNL POST] | /endpointConfigs/`{uid}`/canDeploy | エンドポイントキャッピング設定をデプロイできるかどうかを確認します |
| [!DNL PUT] | /endpointConfigs/`{uid}` | エンドポイントキャップ設定の更新 |
| [!DNL GET] | /endpointConfigs/`{uid}` | エンドポイントキャップの設定の取得 |
| [!DNL DELETE] | /endpointConfigs/`{uid}` | エンポイントキャップ設定の削除 |

設定を作成または更新すると、ペイロードの構文と整合性を保証するチェックが自動的に実行されます。
問題が発生した場合は、設定を修正するのに役立つ警告またはエラーが返されます。



## エンドポイントの設定

エンドポイント設定の基本構造を次に示します。

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

When a **canDeploy** メソッドが呼び出されると、プロセスは設定を検証し、次のいずれかの方法で一意の ID で識別される検証ステータスを返します。

```
"ok" or "error"
```

潜在的なエラーは次のとおりです。

* **ERR_ENDPOINTCONFIG_100**:キャッピングの設定：url が見つからないか、無効です
* **ERR_ENDPOINTCONFIG_101**:キャッピングの設定：不正な URL です
* **ERR_ENDPOINTCONFIG_102**:キャッピングの設定：url の形式が正しくありません：host:port では、url 内の wildchar は使用できません
* **ERR_ENDPOINTCONFIG_103**:キャッピングの設定：HTTP メソッドがありません
* **ERR_ENDPOINTCONFIG_104**:キャッピングの設定：呼び出しの評価が定義されていません
* **ERR_ENDPOINTCONFIG_107**:キャッピングの設定：無効な最大呼び出し数 (maxCallsCount)
* **ERR_ENDPOINTCONFIG_108**:キャッピングの設定：無効な最大呼び出し数 (periodInMs)
* **ERR_ENDPOINTCONFIG_111**:キャッピングの設定：エンドポイント設定を作成できません：無効なペイロード
* **ERR_ENDPOINTCONFIG_112**:キャッピングの設定：エンドポイント設定を作成できません：JSON ペイロードを期待しています
* **ERR_AUTHORING_ENDPOINTCONFIG_1**:無効なサービス名 `<!--<given value>-->`:は、「dataSource」または「action」である必要があります


潜在的な警告は次のとおりです。

**ERR_ENDPOINTCONFIG_106**:キャッピングの設定：最大 HTTP 接続数が定義されていません：デフォルトでは制限なし



## 使用例

この節では、キャッピング設定の管理に使用できる 5 つの主なユースケースを次に示します。 [!DNL Journey Orchestration].

テストおよび設定を支援するために、Postman コレクションを利用できます [ここ](https://raw.githubusercontent.com/AdobeDocs/JourneyAPI/master/postman-collections/Journey-Orchestration_Capping-API_postman-collection.json).

この Postman コレクションは、 __[Adobe I/Oコンソールの統合](https://console.adobe.io/integrations) > 試す > Postman 用にダウンロード__：選択した統合値を持つ Postman 環境ファイルを生成します。

ダウンロードして Postman にアップロードしたら、次の 3 つの変数を追加する必要があります。 `{JO_HOST}`,`{Base_Path}` および `{SANDBOX_NAME}`.
* `{JO_HOST}` : [!DNL Journey Orchestration] ゲートウェイ URL
* `{BASE_PATH}` :API のエントリポイント。 値は「/authoring」です
* `{SANDBOX_NAME}` :ヘッダー **x-sandbox-name** （例えば、「prod」）API 操作が実行されるサンドボックス名に対応します。 詳しくは、「[サンドボックスの概要](https://experienceleague.adobe.com/docs/experience-platform/sandbox/home.html?lang=ja)」を参照してください。

以下の節では、ユースケースを実行するための Rest API 呼び出し順序付きリストを見つけます。

使用例 n°1: **新しいキャッピング設定の作成とデプロイメント**

1. list
1. 作成
1. candeploy
1. デプロイ

使用例 n°2: **まだデプロイされていないキャッピング設定の更新とデプロイ**

1. リスト
1. get
1. 更新
1. candeploy
1. デプロイ

ユースケース n°3: **デプロイ済みのキャッピング設定のデプロイ解除と削除**

1. リスト
1. デプロイ解除
1. 次を削除します。

ユースケース n°4: **デプロイ済みのキャッピング設定を削除します。**

1 回の API 呼び出しで、 forceDelete パラメーターを使用して、設定のデプロイを解除および削除できます。
1. リスト
1. 削除、forceDelete パラメーターを使用

ユースケース n°5: **既にデプロイ済みのキャッピング設定の更新**

1. リスト
1. get
1. 更新
1. デプロイ解除
1. candeploy
1. デプロイ
