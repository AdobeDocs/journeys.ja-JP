---
product: adobe campaign
title: Capping API の説明
description: Capping APIについて詳しく説明します。
products: journeys
feature: Journeys
role: User
level: Intermediate
exl-id: 6f28e62d-7747-43f5-a360-1d6af14944b6
product_v2:
  - id: cf67d108-ecf9-4fde-af49-3a3c39083bc8
    internal-label: Journey Orchestration
feature_v2:
  - id: 7de3230f-9523-5ba5-8d5c-2313288b27ef
    internal-label: Journeys
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
source-git-commit: 255cd6677e7c9ebff63ea9a1028a042c19e63ecc
workflow-type: tm+mt
source-wordcount: '639'
ht-degree: 97%
---

# Capping API の使用 {#work}


>[!CAUTION]
>
>**Adobe Journey Optimizer をお探しですか**？ Journey Optimizer のドキュメントについて詳しくは、[こちら](https://experienceleague.adobe.com/ja/docs/journey-optimizer/using/ajo-home){target="_blank"}をクリックしてください。
>
>
>_このドキュメントは、Journey Optimizer に置き換えられた従来の Journey Orchestration 資料を参照しています。 Journey Orchestration または Journey Optimizer へのアクセスについてご質問がある場合は、アカウントチームにお問い合わせください。_


Capping APIは、キャッピング設定を作成、設定、監視するのに役立ちます。

## Capping API の説明

| メソッド | パス | 説明 |
|---|---|---|
| [!DNL POST] | list/endpointConfigs | エンドポイントキャップ設定のリストの取得 |
| [!DNL POST] | /endpointConfigs | エンドポイントキャップ設定の作成 |
| [!DNL POST] | /endpointConfigs/`{uid}`/deploy | エンドポイントキャップ設定のデプロイ |
| [!DNL POST] | /endpointConfigs/`{uid}`/undeploy | エンドポイントキャップ設定のデプロイ解除 |
| [!DNL POST] | /endpointConfigs/`{uid}`/canDeploy | エンドポイントキャップ設定をデプロイできるかどうかの確認 |
| [!DNL PUT] | /endpointConfigs/`{uid}` | エンドポイントキャップ設定の更新 |
| [!DNL GET] | /endpointConfigs/`{uid}` | エンドポイントキャップ設定の取得 |
| [!DNL DELETE] | /endpointConfigs/`{uid}` | エンポイントキャップ設定の削除 |

設定を作成または更新すると、ペイロードの構文と整合性を保証するチェックが自動的に実行されます。
問題が発生した場合は、設定を修正するのに役立つ警告またはエラーが返されます。

## エンドポイントの設定

エンドポイント設定の基本構造は次のとおりです。

```
{
    "url": "<endpoint URL>",  //wildcards are allowed in the endpoint URL
    "methods": [ "<HTTP method such as GET, POST, >, ...],
    "services": {
        "<service name>": { . //must be "action" or "dataSource" 
            "maxHttpConnections": <max connections count to the endpoint (optional)>
            "rating": {          
                "maxCallsCount": <max calls to be performed in the period defined by period/timeUnit>,
                "periodInMs": <integer value greater than 0>
            }
        },
        ...
    }
}
```

>[!IMPORTANT]
>
>**maxHttpConnections** パラメーターは、オプションです。 これを使用すると、Journey Optimizer が外部システムに対して開く接続の数を制限できます。
>
>設定できる最大値は 400 です。 何も指定しない場合、システムは動的なスケーリングに応じて、最大で数千の接続を開く可能性があります。

### 例：

```
`{
  "url": "https://api.example.org/data/2.5/*",
  "methods": [
    "GET"
  ],
  "services": {
    "dataSource": {
      "maxHttpConnections": 50,
      "rating": {
        "maxCallsCount": 500,
        "periodInMs": 1000
      }
    }
  },
  "orgId": "<IMS Org Id>"
}
```

## 警告とエラー

**canDeploy**&#x200B;メソッドを呼び出す際、プロセスは設定を検証し、次のいずれかの一意の ID によって識別される検証ステータスを返します。

```
"ok" or "error"
```

潜在的なエラーは次のとおりです。

* **ERR_ENDPOINTCONFIG_100**：キャップ設定：URL が見つからないか、無効です
* **ERR_ENDPOINTCONFIG_101**：キャップ設定：不正な URL です
* **ERR_ENDPOINTCONFIG_102**：キャップ設定：不正な URL です：ホスト内の URL にワイルド文字を使用することはできません:port
* **ERR_ENDPOINTCONFIG_103**：キャップ設定：HTTP メソッドがありません
* **ERR_ENDPOINTCONFIG_104**：キャップ設定：呼び出しの評価が定義されていません
* **ERR_ENDPOINTCONFIG_107**：キャップ設定：無効な最大呼び出し数（maxCallsCount）です
* **ERR_ENDPOINTCONFIG_108**：キャップ設定：無効な最大呼び出し数（periodInMs）です
* **ERR_ENDPOINTCONFIG_111**：キャップ設定：エンドポイント設定を作成できません：無効なペイロードです
* **ERR_ENDPOINTCONFIG_112**：キャップ設定：エンドポイント設定を作成できません：JSON ペイロードが予想されます
* **ERR_AUTHORING_ENDPOINTCONFIG_1**：無効なサービス名 `<!--<given value>-->`：「dataSource」または「action」である必要があります

潜在的な警告は次のとおりです。

**ERR_ENDPOINTCONFIG_106**：キャップ設定：最大 HTTP 接続数が定義されていません：デフォルトではキャップなし

## ユースケース

この節では、[!DNL Journey Orchestration] でキャップ設定を管理するために実行できる 5 つの主なユースケースを示します。

テストと設定に役立つように、[こちら](https://raw.githubusercontent.com/AdobeDocs/JourneyAPI/master/postman-collections/Journey-Orchestration_Capping-API_postman-collection.json)で Postman コレクションを使用できます。

この Postman コレクションは、__[Adobe I/O コンソールの統合](https://console.adobe.io/integrations)／試す／Postman 用にダウンロード__&#x200B;を使用して生成された Postman 変数コレクションを共有するようにセットアップされています。これにより、選択した統合値を使用して Postman 環境ファイルが生成されます。

ダウンロードして Postman にアップロードしたら、`{JO_HOST}`、`{BASE_PATH}` および `{SANDBOX_NAME}` の 3 つの変数を追加する必要があります。
* `{JO_HOST}`：[!DNL Journey Orchestration] ゲートウェイ URL
* `{BASE_PATH}`：API のエントリポイント。 値は「/authoring」です
* `{SANDBOX_NAME}`：API 操作が行われるサンドボックス名に対応するヘッダー **x-sandbox-name**（例えば、「prod」）。 詳しくは、[サンドボックスの概要](https://experienceleague.adobe.com/docs/experience-platform/sandbox/home.html?lang=ja)を参照してください。

以下の節では、ユースケースを実行するための Rest API 呼び出し順序付きリストを見つけます。

ユースケース n°1：**新しいキャップ設定の作成とデプロイ**

1. list
1. create
1. candeploy
1. デプロイ

ユースケース n°2：**まだデプロイされていないキャップ設定の更新とデプロイ**

1. list
1. get
1. update
1. candeploy
1. デプロイ

ユースケース n°3：**デプロイ済みのキャップ設定のデプロイ解除と削除**

1. list
1. undeploy
1. delete

ユースケース n°4：**デプロイ済みのキャップ設定の削除**

1 回の API 呼び出しで、 forceDelete パラメーターを使用して、設定をデプロイ解除および削除できます。
1. list
1. 削除、forceDelete パラメーターを使用

ユースケース n°5：**既にデプロイされているキャップ設定の更新**

1. list
1. get
1. update
1. undeploy
1. candeploy
1. デプロイ
