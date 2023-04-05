---
product: adobe campaign
title: スロットル API の使用
description: スロットル API の詳細を説明します
products: journeys
feature: Journeys
role: User
level: Intermediate
source-git-commit: fa493cf1e856378e4d79a6932c30cebf5e11e028
workflow-type: tm+mt
source-wordcount: '788'
ht-degree: 3%

---

# スロットル API の使用

スロットル API を使用すると、スロットル設定を作成、設定および監視できます。

>[!IMPORTANT]
>
>現在、1 つの組織につき 1 つの設定のみを使用できます。 設定は、実稼動用サンドボックス（ヘッダーの x-sandbox-name を通じて指定）で定義する必要があります。
>
>設定は組織レベルで適用されます。
>
>API で設定された制限に達すると、それ以上のイベントは最大 6 時間キューに入れられます。 この値は変更できません。

## スロットル API の説明 {#description}

| メソッド | パス | 説明 |
|---|---|---|
| [!DNL POST] | list/throttlingConfigs | スロットル構成の一覧を取得する |
| [!DNL POST] | /throttlingConfigs | スロットル設定の作成 |
| [!DNL POST] | /throttlingConfigs/`{uid}`/deploy | スロットル設定のデプロイ |
| [!DNL POST] | /throttlingConfigs/`{uid}`/undeploy | スロットル設定のデプロイ解除 |
| [!DNL POST] | /throttlingConfigs/`{uid}`/canDeploy | スロットル設定をデプロイできるかどうかを確認します |
| [!DNL PUT] | /throttlingConfigs/`{uid}` | スロットル設定の更新 |
| [!DNL GET] | /throttlingConfigs/`{uid}` | スロットル設定の取得 |
| [!DNL DELETE] | /throttlingConfigs/`{uid}` | スロットル設定の削除 |

## スロットル設定 {#configuration}

スロットル設定の構造は次のとおりです。 **名前** および **説明** 属性はオプションです。

```
{
    "name": "<given name - free text>",
    "description": "<given description - free text>"
    "urlPattern": "<endpoint URL - wildcards are allowed>",
    "methods": [ "<HTTP method such as GET, POST, PUT>" ],
    "maxThroughput": <max call throughput>
}
```

例：

```
{
  "name": "throttling-config-external",
  "description": "example of throttling config for an external endpoint",
  "urlPattern": "https://api.example.org/data/2.5/*",
  "methods": ["POST", "PUT"],
  "maxThroughput": 4000
}
```

## エラー

設定を作成または更新する際、プロセスは指定された設定を検証し、一意の ID で識別される検証ステータスを返します。次のいずれかがおこなわれます。

```
"ok" or "error"
```

>[!IMPORTANT]
>
>属性 **maxThroughput**, **urlPattern** および **メソッド** は必須です。
>
>**maxThroughput** 値は 200 ～ 5000 の範囲で設定する必要があります。

スロットル設定を作成、削除またはデプロイする際に、次のエラーが発生する場合があります。

* **ERR_THROTTLING_CONFIG_100**:スロットリング設定： `<mandatory attribute>` 必須
* **ERR_THROTTLING_CONFIG_101**:スロットリング設定：maxThroughput は必須で、200 以上 5000 以下である必要があります
* **ERR_THROTTLING_CONFIG_104**:スロットリング設定：不正な URL パターンです
* **ERR_THROTTLING_CONFIG_105**:スロットリング設定：URL パターンのホスト部分で使用できないワイルドカード
* **ERR_THROTTLING_CONFIG_106**:スロットリング設定：無効なペイロード
* **THROTTLING_CONFIG_ERROR_FORBIDDEN_ERROR:1456**「展開済みのスロットル構成を削除できません。 削除する前にデプロイ解除する»
* **THROTTLING_CONFIG_ERROR_DELETE:1457**、「スロットル構成を削除できません：予期しないエラーが発生しました。
* **THROTTLING_CONFIG_DEPLOY_ERROR:1458**、「スロットル構成を展開できません：予期しないエラーが発生しました。
* **THROTTLING_CONFIG_UNDEPLOY_ERROR:1459**、「スロットル構成のデプロイを解除できません：予期しないエラーが発生しました。
* **THROTTLING_CONFIG_ERROR_GET:1460**、「スロットル構成を取得できません：予期しないエラーが発生しました。
* **THROTTLING_CONFIG_UPDATE_NOT_ACTIVE_ERROR:1461**、「スロットル構成を更新できません：ランタイムバージョンがアクティブではありません&quot;
* **THROTTLING_CONFIG_UPDATE_ERROR:1462**、「スロットル構成を更新できません：予期しないエラーが発生しました。
* **THROTTLING_CONFIG_NON_PROD_SANDBOX_ERROR:1463**、「スロットリング構成では操作が許可されていません：非 prod sandbox&quot;
* **THROTTLING_CONFIG_CREATE_ERROR:1464**、「スロットル構成を作成できません：予期しないエラーが発生しました。
* **THROTTLING_CONFIG_CREATE_LIMIT_ERROR:1465**、「スロットル構成を作成できません：1 組織あたり 1 つの設定のみ許可されます
* **THROTTLING_CONFIG_ALREADY_DEPLOYED_ERROR:14466**、「スロットル構成を展開できません：既にデプロイ済み
* **THROTTLING_CONFIG_NOT_FOUND_ERROR:14467**、「スロットル構成が見つかりません」
* **THROTTLING_CONFIG_NOT_DEPLOYED_ERROR:14468**、「スロットル構成のデプロイを解除できません：未デプロイ」

**エラーの例**

実稼動以外のサンドボックスで設定を作成しようとする場合：

```
{
    "status": 400,
    "error": "{\"code\":1463,\"family\":\"INPUT_OUTPUT_ERROR\",\"message\":\"Operation not allowed on throttling config: non prod sandbox\",\"service\":\"vyg-authoring-api\",\"version\":\"ed87515\",\"context\":\"com.adobe.voyager.service.authoring.restapis.v1_0.ThrottlingConfigService:384\",\"schema\":\"throttlingConfigs$ui-tests\"}",
    "requestId": "5sgnAYXs8mpswwjAFEIaAU2faQYbtyHc"
}
```

指定されたサンボックスが存在しない場合：

```
{
    "status": 500,
    "error": "{\"code\":4000,\"family\":\"INTERNAL_ERROR\",\"message\":\"INTERNAL ERROR\",\"service\":\"vyg-authoring-api\",\"version\":\"ed87515\",\"context\":\"com.adobe.voyager.common.exceptions.ApiErrorException:43\"}",
    "requestId": "04ZJ4e5ki4bYs3lfO17a7hovRGewjvdK"
}
```

別の設定を作成する場合：

```
{
    "status": 400,
    "error": "{\"code\":1465,\"family\":\"INPUT_OUTPUT_ERROR\",\"message\":\"Can't create throttling config: only one config allowed per org\",\"service\":\"vyg-authoring-api\",\"version\":\"ed87515\",\"context\":\"com.adobe.voyager.service.authoring.restapis.v1_0.ThrottlingConfigService:108\",\"schema\":\"throttlingConfigs$prod\"}",
    "requestId": "A7ezT8JhOQT4WIAf1Fv7K2wCDA8281qM"
}
```

## 使用例 {#uc}

テストおよび設定に役立つように、Postmanコレクションを利用できます [ここ](https://raw.githubusercontent.com/AdobeDocs/JourneyAPI/master/postman-collections/Journey-Throttling-API_postman-collection.json).

このPostmanコレクションは、 __[Adobe I/Oコンソールの統合](https://console.adobe.io/integrations) > 試す > Postman用にダウンロード__：選択した統合値でPostman環境ファイルを生成します。

ダウンロードしてPostmanにアップロードしたら、次の 3 つの変数を追加する必要があります。 `{JO_HOST}`,`{BASE_PATH}` および `{SANDBOX_NAME}`.
* `{JO_HOST}` : [!DNL Journey Orchestration] ゲートウェイ URL
* `{BASE_PATH}` :API のエントリポイント。 値は「/authoring」です
* `{SANDBOX_NAME}` :ヘッダー **x-sandbox-name** （例えば、「prod」）API 操作が実行されるサンドボックス名に対応します。 詳しくは、「[サンドボックスの概要](https://experienceleague.adobe.com/docs/experience-platform/sandbox/home.html?lang=ja)」を参照してください。

以下の節では、ユースケースを実行するための Rest API 呼び出し順序付きリストを見つけます。

使用例 n°1: **新しいスロットル設定の作成とデプロイ**

1. リスト
1. 作成
1. candeploy
1. デプロイ

使用例 n°2: **まだデプロイされていないスロットル設定を更新およびデプロイします**

1. リスト
1. get
1. 更新
1. candeploy
1. デプロイ

ユースケース n°3: **デプロイ済みのスロットル設定のデプロイ解除と削除**

1. リスト
1. デプロイ解除
1. 削除

ユースケース n°4: **デプロイ済みのスロットル設定を削除する**

1 回の API 呼び出しで、 forceDelete パラメーターを使用して、設定のデプロイを解除および削除できます。

1. リスト
1. 削除、forceDelete パラメーターを使用

ユースケース n°5: **既にデプロイされているスロットル構成を更新します**

>[!NOTE]
>
>更新前に設定のデプロイを解除する必要はありません

1. リスト
1. get
1. 更新

## 実行時レベルでの設定のライフサイクル {#config}

設定がデプロイ解除されると、実行時レベルで非アクティブとマークされ、保留中のイベントは 24 時間引き続き処理されます。 その後、ランタイムサービスで削除されます。

設定がデプロイ解除された後は、設定を更新して再デプロイできます。 これにより、新しいランタイム設定が作成され、今後のアクションの実行で考慮されます。

既にデプロイされている設定を更新すると、新しい値が直ちに考慮されます。 基になるシステムリソースは、自動的に適応されます。 これは、設定をデプロイ解除してから再デプロイする場合に比べて最適です。

## 応答の例 {#responses}

**作成 —POST**

```
{
    "canDeploy": {
        "validationStatus": "ok"
    },
    "createdElement": {
        "name": "throttling-config-external",
        "description": "example of throttling config for an external endpoint",
        "urlPattern": "https://api.example.org/data/2.5/*",
        "methods": [
            "PUT",
            "POST"
        ],
        "maxThroughput": 4000,
        "orgId": "AC202A3A5F615BD30A495FDE@AdobeOrg",
        "sandboxId": "8872a010-f91e-11ea-895c-11ef8f98ba52",
        "sandboxName": "prod",
        "uid": "043a1aea-2dfd-4965-b93a-cb9a1eced0e6",
        "metadata": {
            "createdBy": "dacce1c3-d08b-4862-b434-2a4449c7e642@techacct.adobe.com",
            "createdById": "309F2A46640B0B300A495C83@techacct.adobe.com",
            "lastModifiedBy": "dacce1c3-d08b-4862-b434-2a4449c7e642@techacct.adobe.com",
            "lastModifiedById": "309F2A46640B0B300A495C83@techacct.adobe.com",
            "createdAt": "2023-03-22T10:48:16.099647Z",
            "lastModifiedAt": "2023-03-22T10:48:16.099647Z"
        },
        "state": "created",
        "authoringFormatVersion": "1.0"
    },
    "uid": "043a1aea-2dfd-4965-b93a-cb9a1eced0e6",
    "uri": "/voyager/apis/throttlingConfigs/043a1aea-2dfd-4965-b93a-cb9a1eced0e6",
    "resStatus": "created"
}
```

**更新 —PUT**

```
{
    "updatedElement": {
        "_id": "043a1aea-2dfd-4965-b93a-cb9a1eced0e6_8872a010-f91e-11ea-895c-11ef8f98ba52",
        "name": "throttling-config-external -- optional",
        "description": "example of throttling config for an external endpoint -- optional",
        "urlPattern": "https://api.example.org/data/2.5/*",
        "methods": [
            "POST"
        ],
        "maxThroughput": 5000,
        "orgId": "AC202A3A5F615BD30A495FDE@AdobeOrg",
        "sandboxId": "8872a010-f91e-11ea-895c-11ef8f98ba52",
        "sandboxName": "prod",
        "uid": "043a1aea-2dfd-4965-b93a-cb9a1eced0e6",
        "metadata": {
            "createdBy": "dacce1c3-d08b-4862-b434-2a4449c7e642@techacct.adobe.com",
            "createdById": "309F2A46640B0B300A495C83@techacct.adobe.com",
            "lastModifiedBy": "dacce1c3-d08b-4862-b434-2a4449c7e642@techacct.adobe.com",
            "lastModifiedById": "309F2A46640B0B300A495C83@techacct.adobe.com",
            "createdAt": "2023-03-22T10:48:16.099647Z",
            "lastModifiedAt": "2023-03-22T11:39:14.212983Z"
        },
        "state": "updated",
        "authoringFormatVersion": "1.0",
        "hasBeenDeployed": false
    },
    "uid": "043a1aea-2dfd-4965-b93a-cb9a1eced0e6",
    "uri": "/voyager/apis/throttlingConfigs/043a1aea-2dfd-4965-b93a-cb9a1eced0e6",
    "resStatus": "updated",
    "canDeploy": {
        "validationStatus": "ok"
    }
}
```

**読み取り（更新後） -GET**

```
{
    "result": {
        "_id": "043a1aea-2dfd-4965-b93a-cb9a1eced0e6_8872a010-f91e-11ea-895c-11ef8f98ba52",
        "name": "throttling-config-external -- optional",
        "description": "example of throttling config for an external endpoint -- optional",
        "urlPattern": "https://api.example.org/data/2.5/*",
        "methods": [
            "POST"
        ],
        "maxThroughput": 5000,
        "orgId": "AC202A3A5F615BD30A495FDE@AdobeOrg",
        "sandboxId": "8872a010-f91e-11ea-895c-11ef8f98ba52",
        "sandboxName": "prod",
        "uid": "043a1aea-2dfd-4965-b93a-cb9a1eced0e6",
        "metadata": {
            "createdBy": "dacce1c3-d08b-4862-b434-2a4449c7e642@techacct.adobe.com",
            "createdById": "309F2A46640B0B300A495C83@techacct.adobe.com",
            "lastModifiedBy": "dacce1c3-d08b-4862-b434-2a4449c7e642@techacct.adobe.com",
            "lastModifiedById": "309F2A46640B0B300A495C83@techacct.adobe.com",
            "createdAt": "2023-03-22T10:48:16.099647Z",
            "lastModifiedAt": "2023-03-22T11:39:14.212983Z"
        },
        "state": "updated",
        "authoringFormatVersion": "1.0",
        "hasBeenDeployed": false
    }
}
```

**読み取り（デプロイ後） -GET**

```
{
    "result": {
        "_id": "043a1aea-2dfd-4965-b93a-cb9a1eced0e6_8872a010-f91e-11ea-895c-11ef8f98ba52",
        "orgId": "AC202A3A5F615BD30A495FDE@AdobeOrg",
        "sandboxId": "8872a010-f91e-11ea-895c-11ef8f98ba52",
        "sandboxName": "prod",
        "uid": "043a1aea-2dfd-4965-b93a-cb9a1eced0e6",
        "urlPattern": "https://api.example.org/data/2.5/*",
        "methods": [
            "POST"
        ],
        "maxThroughput": 5000,
        "authoringFormatVersion": "1.0",
        "name": "throttling-config-external -- optional",
        "description": "example of throttling config for an external endpoint -- optional",
        "version": "1.0",
        "state": "deployed",
        "metadata": {
            "createdBy": "dacce1c3-d08b-4862-b434-2a4449c7e642@techacct.adobe.com",
            "createdById": "309F2A46640B0B300A495C83@techacct.adobe.com",
            "createdAt": "2023-03-22T10:48:16.099647Z",
            "lastModifiedBy": "dacce1c3-d08b-4862-b434-2a4449c7e642@techacct.adobe.com",
            "lastModifiedById": "309F2A46640B0B300A495C83@techacct.adobe.com",
            "lastModifiedAt": "2023-03-22T11:39:14.212983Z",
            "lastDeployedBy": "dacce1c3-d08b-4862-b434-2a4449c7e642@techacct.adobe.com",
            "lastDeployedById": "309F2A46640B0B300A495C83@techacct.adobe.com",
            "lastDeployedAt": "2023-03-22T11:46:07.532648Z"
        },
        "hasBeenDeployed": true
    }
}
```
