---
product: adobe campaign
title: キャッピング API の説明
description: キャッピング API の詳細を説明します。
products: journeys
feature: Journeys
role: User
level: Intermediate
exl-id: 6f28e62d-7747-43f5-a360-1d6af14944b6
source-git-commit: 1f91bae24dfcb291dd354e4bff9eab85afdaf5a1
workflow-type: tm+mt
source-wordcount: '527'
ht-degree: 5%

---


# キャッピング API の使用 {#work}

キャッピング API は、キャッピング設定を作成、設定および監視するのに役立ちます。

## キャッピング API の説明

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

テストおよび設定に役立つように、Postmanコレクションを利用できます [ここ](https://raw.githubusercontent.com/AdobeDocs/JourneyAPI/master/postman-collections/Journey-Orchestration_Capping-API_postman-collection.json).

このPostmanコレクションは、 __[Adobe I/Oコンソールの統合](https://console.adobe.io/integrations) > 試す > Postman用にダウンロード__：選択した統合値でPostman環境ファイルを生成します。

ダウンロードしてPostmanにアップロードしたら、次の 3 つの変数を追加する必要があります。 `{JO_HOST}`,`{BASE_PATH}` および `{SANDBOX_NAME}`.
* `{JO_HOST}` : [!DNL Journey Orchestration] ゲートウェイ URL
* `{BASE_PATH}` :API のエントリポイント。 値は「/authoring」です
* `{SANDBOX_NAME}` :ヘッダー **x-sandbox-name** （例えば、「prod」）API 操作が実行されるサンドボックス名に対応します。 詳しくは、「[サンドボックスの概要](https://experienceleague.adobe.com/docs/experience-platform/sandbox/home.html?lang=ja)」を参照してください。

以下の節では、ユースケースを実行するための Rest API 呼び出し順序付きリストを見つけます。

使用例 n°1: **新しいキャッピング設定の作成とデプロイメント**

1. リスト
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
1. 削除

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
