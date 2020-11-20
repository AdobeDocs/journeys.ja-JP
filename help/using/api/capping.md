---
product: adobe campaign
solution: Journey Orchestration
title: 制限APIの説明
description: Capping APIについて詳しく説明します。
products: journeys
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '1108'
ht-degree: 2%

---


# Capping APIの使用

## はじめに

[!DNL Journey Orchestration]のAPIは5000イベント/秒をサポートしていますが、一部の外部システムまたはAPIは同等のスループットを持つことができませんでした。 そのため、外部システム [!DNL Journey Orchestration] に課すレートを監視および制限するCapping APIと呼ばれる専用機能が付属しています。

データソースの設定中に、ジャーニーで使用される追加情報を取得するためのシステムへの接続を定義するか、アクションの定義のために、メッセージまたはAPI呼び出しを送信するサードパーティ製システムの接続を設定します。 JeurneyによってAPI呼び出しが実行されるたびに、上限APIが照会され、その呼び出しはAPIエンジンを通じて行われます。 制限が定義されている場合、呼び出しは拒否され、外部システムで過負荷が発生することはありません。

アクションまたはデータソースの設定について詳しくは、「アクション [について](https://docs.adobe.com/content/help/en/journeys/using/action-journeys/action.html) 」または「データソース [について」を参照してください。](https://docs.adobe.com/content/help/en/journeys/using/data-source-journeys/about-data-sources.html)


## リソース

>[!NOTE]
>
>Capping APIについては、ここで利用可能なSwaggerファイル内で説明し [!DNL Journey Orchestration] ています [](https://adobedocs.github.io/JourneyAPI/docs/)。

このAPIを [!DNL Journey Orchestration] インスタンスで使用するには、AdobeI/Oコンソールを使用する必要があります。 開始するには、この「 [Adobe開発者コンソール使用の手引き](https://www.adobe.io/apis/experienceplatform/console/docs.html#!AdobeDocs/adobeio-console/master/getting-started.md) 」に従って、このページのセクションを使用します。

統合をテストして準備するには、Postmanコレクションを [こちらから入手できます](https://raw.githubusercontent.com/AdobeDocs/JourneyAPI/master/postman-collections/Journey-Orchestration_Capping-API_postman-collection.json)。

## 認証

### API アクセスの設定

[!DNL Journey Orchestration] APIアクセスは次の手順で設定します。 これらの各手順は、 [AdobeI/Oドキュメントで詳しく説明し](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md)ます。

>[!CAUTION]
>
>AdobeI/Oで証明書を管理するには、組織の <b>System Administrator</b> 権限または管理コンソールの [開発者アカウントを持っていることを確認します](https://helpx.adobe.com/enterprise/using/manage-developers.html) 。

1. **デジタル証明書をお持ちであることを確認するか**、必要に応じて証明書を作成します。 証明書と共に提供される公開鍵と秘密鍵は、次の手順で必要になります。
1. **AdobeI/Oの [!DNL Journey Orchestration] Service** への新しい統合を作成し、構成します。 製品プロファイルへのアクセスは、 [!DNL Journey Orchestration] とAdobe Experience Platformに必要です。 次に、資格情報が生成されます（APIキー、クライアントシークレット。.）。
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

   組織IDの値を取得するには、管理者またはAdobeのテクニカルコンタクトに問い合わせてください。 新しい統合を作成する際に、AdobeI/Oに取得することもできます( <a href="https://www.adobe.io/authentication.html">AdobeI/Oのドキュメントを参照</a>)。

* **&lt;ACCESS_TOKEN>**:JWTをPOST要求で交換する際に取得した個人アクセストークン。

* **&lt;API_KEY>**:個人のAPIキーを参照してください。 これは、 [!DNL Journey Orchestration] サービスへの新しい統合を作成した後、AdobeI/Oで提供されます。



## 制限APIの説明

Capping APIは、制限設定の作成、設定、監視に役立ちます。

| 方法 | パス | 説明 |
|---|---|---|
| [!DNL POST] | リスト/エンドポイントの設定 | エンドポイントのキャッピング設定のリストを取得します |
| [!DNL POST] | /endpointConfigs | 端点のキャッピング設定を作成する |
| [!DNL POST] | /endpointConfigs/`{uid}`/deploy | エンドポイントの制限設定のデプロイ |
| [!DNL POST] | /endpointConfigs/`{uid}`/undeploy | エンドポイントの上限設定のデプロイ解除 |
| [!DNL POST] | /endpointConfigs/`{uid}`/canDeploy | エンドポイントキャッピング設定をデプロイできるかどうかを確認します |
| [!DNL PUT] | /endpointConfigs/`{uid}` | エンドポイントの上限設定の更新 |
| [!DNL GET] | /endpointConfigs/`{uid}` | エンドポイントの上限設定を取得します |
| [!DNL DELETE] | /endpointConfigs/`{uid}` | エンポイントキャッピング設定の削除 |

設定が作成または更新されると、ペイロードの構文と整合性を保証するためのチェックが自動的に実行されます。
問題が発生した場合は、設定の修正に役立つ警告またはエラーが返されます。



## エンドポイントの設定

エンドポイント設定の基本的な構造を次に示します。

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

canDeploy **** メソッドが呼び出されると、プロセスは設定を検証し、一意のIDで識別される検証ステータスを返します。次のいずれかが返されます。

```
"ok" or "error"
```

潜在的なエラーは次のとおりです。

* **ERR_ENDPOINTCONFIG_100**:capping config:URLが見つからないか、無効です
* **ERR_ENDPOINTCONFIG_101**:capping config:誤ったURL
* **ERR_ENDPOINTCONFIG_102**:capping config:urlの形式が正しくありません：url内のwildcharはホストでは使用できません：ポート
* **ERR_ENDPOINTCONFIG_103**:capping config:HTTPメソッドがありません
* **ERR_ENDPOINTCONFIG_104**:capping config:呼び出しの評価が定義されていません
* **ERR_ENDPOINTCONFIG_107**:capping config:無効な最大呼び出し数(maxCallsCount)
* **ERR_ENDPOINTCONFIG_108**:capping config:無効な最大呼び出し数(periodInMs)
* **ERR_ENDPOINTCONFIG_111**:capping config:エンドポイント設定を作成できません：無効なペイロード
* **ERR_ENDPOINTCONFIG_112**:capping config:エンドポイント設定を作成できません：JSONペイロードが必要です
* **ERR_AUTHORING_ENDPOINTCONFIG_1**:無効なサービス名 `<!--<given value>-->`:は、&#39;dataSource&#39;または&#39;action&#39;である必要があります


潜在的な警告は次のとおりです。

**ERR_ENDPOINTCONFIG_106**:capping config:最大HTTP接続数が定義されていません：デフォルトでは制限なし



## 使用例

この節では、でキャッピング設定を管理する際に実行できる5つの主な使用例を示し [!DNL Journey Orchestration]ます。

テストと設定を行う際に役立つPostmanコレクションは [こちらから入手できます](https://raw.githubusercontent.com/AdobeDocs/JourneyAPI/master/postman-collections/Journey-Orchestration_Capping-API_postman-collection.json)。

このPostman Collectionは、 __[AdobeI/OコンソールのIntegrations](https://console.adobe.io/integrations)__/Try out/Download for Postmanを介して生成されたPostman変数コレクションを共有するように設定されています。これにより、選択した環境値を持つPostman統合ファイルが生成されます。

Postmanにダウンロードしてアップロードした後は、3つの変数を追加する必要があります。 `{JO_HOST}`、`{Base_Path}` および `{SANDBOX_NAME}`。
* `{JO_HOST}` : [!DNL Journey Orchestration] ゲートウェイURL
* `{BASE_PATH}` :エントリポイントを設定します。 値は「/authoring」です。
* `{SANDBOX_NAME}` :API操作を実行するサンドボックス名に対応するヘッダ **ー** x-sandbox-name（例えば&#39;prod&#39;）。 詳しくは、 [サンドボックスの概要](https://docs.adobe.com/content/help/en/experience-platform/sandbox/home.html) を参照してください。

次の節では、Rest API呼び出しの順序付けされたリストがユースケースを実行するのを見つけます。

ユースケースn°1: **新しいキャッピング設定の作成と展開**

1. リスト
1. create
1. candeploy
1. デプロイ

ユースケースn°2: **制限設定がまだデプロイされていない場合の更新とデプロイ**

1. リスト
1. get
1. update
1. candeploy
1. デプロイ

ユースケースn°3: **デプロイ済のキャッピング構成のデプロイ解除と削除**

1. リスト
1. デプロイ解除
1. delete

ユースケースn°4: **デプロイ済のキャッピング設定を削除します。**

1回のAPI呼び出しでのみ、forceDeleteパラメーターを使用して、設定のデプロイを解除したり、設定を削除したりできます。
1. リスト
1. 削除、forceDelete param

ユースケースn°5: **既に展開されているキャッピング設定の更新**

1. リスト
1. get
1. update
1. デプロイ解除
1. candeploy
1. デプロイ

