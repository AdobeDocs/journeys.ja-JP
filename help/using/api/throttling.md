---
product: adobe campaign
title: Throttling API の操作
description: Throttling API の詳細について説明します
products: journeys
feature: Journeys
role: User
level: Intermediate
exl-id: 76afe397-3e18-4e01-9b0b-c21705927ce2
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '791'
ht-degree: 91%

---

# Throttling API の操作


>[!CAUTION]
>
>**Adobe Journey Optimizerをお探しですか** Journey Optimizerのドキュメントについては、[&#x200B; こちら &#x200B;](https://experienceleague.adobe.com/ja/docs/journey-optimizer/using/ajo-home){target="_blank"} をクリックしてください。
>
>
>_このドキュメントでは、Journey Optimizerに置き換えられた従来のJourney Orchestration マテリアルについて説明します。 Journey OrchestrationやJourney Optimizerへのアクセスに関するご質問は、アカウントチームにお問い合わせください。_


Throttling API を使用すると、スロットル設定を作成、設定および監視して、1 秒あたりに送信されるイベントの数を制限できます。

>[!IMPORTANT]
>
>現在、1 つの組織につき 1 つの設定のみを使用できます。設定は、（ヘッダーの x-sandbox-name を通じて指定される）実稼動サンドボックスで定義する必要があります。
>
>設定は、組織レベルで適用されます。
>
>API で設定された制限に達すると、以降のイベントは最大 6 時間キューに入れられます。この値は変更できません。

## Throttling API の説明 {#description}

| メソッド | パス | 説明 |
|---|---|---|
| [!DNL POST] | list/throttlingConfigs | スロットル設定のリストを取得します |
| [!DNL POST] | /throttlingConfigs | スロットル設定を作成します |
| [!DNL POST] | /throttlingConfigs/`{uid}`/deploy | スロットル設定をデプロイします |
| [!DNL POST] | /throttlingConfigs/`{uid}`/undeploy | スロットル設定のデプロイを解除します |
| [!DNL POST] | /throttlingConfigs/`{uid}`/canDeploy | スロットル設定をデプロイできるかどうかを確認します |
| [!DNL PUT] | /throttlingConfigs/`{uid}` | スロットル設定を更新します |
| [!DNL GET] | /throttlingConfigs/`{uid}` | スロットル設定を取得します |
| [!DNL DELETE] | /throttlingConfigs/`{uid}` | スロットル設定を削除します |

## スロットル設定{#configuration}

スロットル設定の構造は次のとおりです。**name** 属性と **description** 属性はオプションです。

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

設定を作成または更新する際に、プロセスは指定された設定を検証し、設定の一意の ID で識別される検証ステータス（次のいずれか）を返します。

```
"ok" or "error"
```

>[!IMPORTANT]
>
>属性 **maxThroughput**、**urlPattern** および **methods** は必須です。
>
>**maxThroughput** 値は 200～5000 の範囲で設定する必要があります。

スロットル設定を作成、削除またはデプロイする際に、次のエラーが発生する場合があります。

* **ERR_THROTTLING_CONFIG_100**：スロットル設定 : `<mandatory attribute>` は必須です
* **ERR_THROTTLING_CONFIG_101**：スロットル設定 : maxThroughput は必須で、200 以上 5000 以下にする必要があります
* **ERR_THROTTLING_CONFIG_104**：スロットル設定 : 不正な URL パターンです
* **ERR_THROTTLING_CONFIG_105**：スロットル設定 : URL パターンのホスト部分ではワイルドカードは使用できません
* **ERR_THROTTLING_CONFIG_106**：スロットル設定 : 無効なペイロードです
* **THROTTLING_CONFIG_DELETE_FORBIDDEN_ERROR : 1456**、「デプロイ済みのスロットル設定は削除できません。デプロイを解除してから削除します」
* **THROTTLING_CONFIG_DELETE_ERROR : 1457**、「スロットル設定を削除できません : 予期しないエラーが発生しました」
* **THROTTLING_CONFIG_DEPLOY_ERROR : 1458**、「スロットル設定をデプロイできません : 予期しないエラーが発生しました」
* **THROTTLING_CONFIG_UNDEPLOY_ERROR : 1459**、「スロットル設定のデプロイを解除できません : 予期しないエラーが発生しました」
* **THROTTLING_CONFIG_GET_ERROR : 1460**、「スロットル設定を取得できません : 予期しないエラーが発生しました」
* **THROTTLING_CONFIG_UPDATE_NOT_ACTIVE_ERROR : 1461**、「スロットル設定を更新できません : ランタイムバージョンがアクティブではありません」
* **THROTTLING_CONFIG_UPDATE_ERROR : 1462**、「スロットル設定を更新できません : 予期しないエラーが発生しました」
* **THROTTLING_CONFIG_NON_PROD_SANDBOX_ERROR : 1463**、「スロットル設定に対する操作が許可されていません : 実稼動以外のサンドボックスです」
* **THROTTLING_CONFIG_CREATE_ERROR : 1464**、「スロットル設定を作成できません : 予期しないエラーが発生しました」
* **THROTTLING_CONFIG_CREATE_LIMIT_ERROR : 1465**、「スロットル設定を作成できません : 1 組織あたり 1 つの設定のみ許可されます」
* **THROTTLING_CONFIG_ALREADY_DEPLOYED_ERROR : 14466**、「スロットル設定をデプロイできません : 既にデプロイされています」
* **THROTTLING_CONFIG_NOT_FOUND_ERROR : 14467**、「スロットル設定が見つかりません」
* **THROTTLING_CONFIG_NOT_DEPLOYED_ERROR : 14468**、「スロットル設定のデプロイを解除できません : まだデプロイされていません」

**エラーの例**

実稼動以外のサンドボックスで設定を作成しようとした場合：

```
{
    "status": 400,
    "error": "{\"code\":1463,\"family\":\"INPUT_OUTPUT_ERROR\",\"message\":\"Operation not allowed on throttling config: non prod sandbox\",\"service\":\"vyg-authoring-api\",\"version\":\"ed87515\",\"context\":\"com.adobe.voyager.service.authoring.restapis.v1_0.ThrottlingConfigService:384\",\"schema\":\"throttlingConfigs$ui-tests\"}",
    "requestId": "5sgnAYXs8mpswwjAFEIaAU2faQYbtyHc"
}
```

指定したサンドボックスが存在しない場合：

```
{
    "status": 500,
    "error": "{\"code\":4000,\"family\":\"INTERNAL_ERROR\",\"message\":\"INTERNAL ERROR\",\"service\":\"vyg-authoring-api\",\"version\":\"ed87515\",\"context\":\"com.adobe.voyager.common.exceptions.ApiErrorException:43\"}",
    "requestId": "04ZJ4e5ki4bYs3lfO17a7hovRGewjvdK"
}
```

別の設定を作成しようとした場合：

```
{
    "status": 400,
    "error": "{\"code\":1465,\"family\":\"INPUT_OUTPUT_ERROR\",\"message\":\"Can't create throttling config: only one config allowed per org\",\"service\":\"vyg-authoring-api\",\"version\":\"ed87515\",\"context\":\"com.adobe.voyager.service.authoring.restapis.v1_0.ThrottlingConfigService:108\",\"schema\":\"throttlingConfigs$prod\"}",
    "requestId": "A7ezT8JhOQT4WIAf1Fv7K2wCDA8281qM"
}
```

## ユースケース {#uc}

テストと設定に役立つ Postman コレクションを[こちら](https://raw.githubusercontent.com/AdobeDocs/JourneyAPI/master/postman-collections/Journey-Orchestration_Throttling-API_postman-collection.json)から使用できます。

この Postman コレクションは、__[Adobe I/O コンソールの統合](https://console.adobe.io/integrations)／試す／Postman 用にダウンロード__&#x200B;を使用して生成された Postman 変数コレクションを共有するようにセットアップされています。これにより、選択した統合値を使用して Postman 環境ファイルが生成されます。

ダウンロードして Postman にアップロードしたら、`{JO_HOST}`、`{BASE_PATH}` および `{SANDBOX_NAME}` の 3 つの変数を追加する必要があります。
* `{JO_HOST}`：[!DNL Journey Orchestration] ゲートウェイ URL
* `{BASE_PATH}`：API のエントリポイント。値は「/authoring」です
* `{SANDBOX_NAME}`：API 操作が行われるサンドボックス名に対応するヘッダー **x-sandbox-name**（例えば、「prod」）。詳しくは、[サンドボックスの概要](https://experienceleague.adobe.com/docs/experience-platform/sandbox/home.html?lang=ja)を参照してください。

次の節では、ユースケースを実行するための Rest API 呼び出しの順序付きリストを示します。

ユースケース n°1：**新しいスロットル設定の作成とデプロイ**

1. list
1. create
1. candeploy
1. deploy

ユースケース n°2：**まだデプロイされていないスロットル設定の更新とデプロイ**

1. list
1. get
1. update
1. candeploy
1. deploy

ユースケース n°3：**デプロイ済みのスロットル設定のデプロイ解除と削除**

1. list
1. undeploy
1. delete

ユースケース n°4：**デプロイ済みのスロットル設定の削除**

forceDelete パラメーターを使用すると、1 回の API 呼び出しで設定をデプロイ解除および削除できます。

1. list
1. delete（forceDelete パラメーターを使用）

ユースケース n°5：**既にデプロイされているスロットル設定の更新**

>[!NOTE]
>
>更新前に設定のデプロイを解除する必要はありません

1. list
1. get
1. update

## ランタイムレベルでの設定のライフサイクル {#config}

設定のデプロイを解除すると、設定がランタイムレベルで非アクティブとマークされ、保留中のイベントは引き続き 24 時間処理されます。その後、ランタイムサービスで削除されます。

設定のデプロイを解除した後は、設定を更新して再デプロイできます。これにより、新しいランタイム設定が作成され、今後のアクションの実行で考慮されます。

既にデプロイされている設定を更新すると、新しい値が直ちに考慮されます。基になるシステムリソースは、自動的に適応されます。これは、設定をデプロイ解除してから再デプロイする場合に比べて最適です。

## 応答の例 {#responses}

**作成 - POST**

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

**更新 - PUT**

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

**読み取り（更新後）- GET**

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

**読み取り（デプロイ後）- GET**

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
