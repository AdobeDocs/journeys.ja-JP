---
product: adobe campaign
title: ジャーニー API の基本を学ぶ
description: ジャーニー API の詳細について説明します
products: journeys
feature: Journeys
role: User
level: Intermediate
source-git-commit: fa493cf1e856378e4d79a6932c30cebf5e11e028
workflow-type: ht
source-wordcount: '832'
ht-degree: 100%

---

# ジャーニー API の基本を学ぶ

## Capping API とThrottling API について

データソースやアクションを設定する際は、システムへの接続を確立して、ジャーニーで使用する追加情報を取得したり、メッセージや API 呼び出しを送信したりします。

ジャーニー API では 1 秒あたり最大 5000 イベントをサポートしていますが、一部の外部システムや API は同等のスループットを持たない場合があります。これらのシステムに対する過負荷を防止するために、**Capping** API と&#x200B;**Throttling** API を使用して、1 秒あたりに送信されるイベントの数を制限できます。

API 呼び出しがジャーニーで実行されるたびに、呼び出しが API エンジンを通過します。API で設定された上限に達すると、Capping API を使用している場合は呼び出しが拒否され、Throttling API を使用している場合は最大 6 時間キューに入れられて、受信した順序でできるだけ早く処理されます。

例えば、1 秒あたり 100 呼び出しまでというキャッピングルールまたはスロットルルールを外部システムに対して定義したとします。システムは、10 件の異なるジャーニーでカスタムアクションによって呼び出されます。1 つのジャーニーで 1 秒間に 200 件の呼び出しを受け取った場合、使用可能な 100 個のスロットを使用し、残りの 100 個のスロットを破棄するかキューに入れます。最大レートを超えたので、他の 9 つのジャーニーにはスロットは残りません。この精度は、外部システムを過負荷やクラッシュから保護するのに役立ちます。

>[!IMPORTANT]
>
>**キャッピングルール**&#x200B;は、特定のエンドポイント（呼び出された URL）に対してサンドボックスレベルで設定されますが、そのサンドボックスのすべてのジャーニーに対してグローバルに適用されます。
>
>**スロットルルール**&#x200B;は、特定のエンドポイントに対して実稼動サンドボックスでのみ設定されますが、すべてのサンドボックスのすべてのジャーニーに対してグローバルに適用されます。組織ごとに 1 つのスロットル設定のみを指定できます。

これらの API の操作方法について詳しくは、次の節を参照してください。

* [Capping API](capping.md)
* [Throttling API](throttling.md)

どちらの API についても、[こちら](https://adobedocs.github.io/JourneyAPI/docs/)から入手可能な Swagger ファイルにも記述されています。

## データソースとカスタムアクションの処理能力 {#capacity}

**外部データソース**&#x200B;の場合、1 秒あたりの最大呼び出し回数は 15 に制限されています。この上限を超えると、使用中の API に応じて、追加の呼び出しは破棄されるかキューに入れられます。アドビに連絡して許可リストにエンドポイントを含めることにより、プライベート外部データソースについてこの上限を増やすことができますが、これはパブリック外部データソースの場合に選択できるオプションではありません。* [データソースの設定方法についてはこちらを参照してください](../datasource/about-data-sources.md)。

>[!NOTE]
>
>データソースで、データソースで使用されているものとは異なるエンドポイントを持つカスタム認証を使用する場合は、アドビに連絡して、そのエンドポイントも許可リストに含める必要があります。

**カスタムアクション**&#x200B;の場合は、外部 API の処理能力を評価しておく必要があります。例えば、Journey Optimizer が 1 秒あたり 1000 件の呼び出しを送信しているのに対して、システムが 1 秒あたり 100 件の呼び出ししかサポートできない場合、システムが飽和状態にならないようにキャッピング設定またはスロットル設定を定義する必要があります。[アクションの設定方法についてはこちらを参照してください](../action/action.md)

## API アクセスのセットアップ {#api}

[!DNL Journey Orchestration] インスタンスでこれらの API を使用するには、Adobe I/O コンソールを使用する必要があります。[!DNL Journey Orchestration] API アクセスは、以下の手順でセットアップします。これらの各手順について詳しくは、[Adobe I/O のドキュメント](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md)を参照してください。

>[!CAUTION]
>
>Adobe I/O で証明書を管理するには、組織の<b>システム管理者</b>権限または Admin Console の[開発者アカウント](https://helpx.adobe.com/jp/enterprise/using/manage-developers.html)があることを確認してください。

1. **電子証明書があることを確認するか**、必要に応じて作成します。証明書に記載されている公開鍵と秘密鍵は、以降の手順で必要になります。
1. Adobe I/O で **[!DNL Journey Orchestration] サービスへの新しい統合を作成**&#x200B;し、設定します。[!DNL Journey Orchestration] および Adobe Experience Platform には、製品プロファイルへのアクセスが必要です。次に、資格情報を生成します（API キー、クライアントシークレットなど）。
1. 生成済みの資格情報から **JSON Web トークン（JWT）を作成**&#x200B;し、それに秘密鍵で署名します。JWT では、アドビがユーザーの ID が正しいことを確認し API へのアクセス権をユーザーに付与するのに必要なすべての ID およびセキュリティ情報をエンコードします。この手順について詳しくは、[こちらの節](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/JWT/JWT.md)を参照してください
1. POST リクエストまたは Developer Console インターフェイスを通じて、**JWT をアクセストークンと交換します**。このアクセストークンを API リクエストの各ヘッダーで使用する必要があります。

サービス間のセキュアな Adobe I/O API セッションを確立するには、アドビサービスへのすべてのリクエストで、以下の情報を Authorization ヘッダーに含める必要があります。

```
curl -X GET https://journey.adobe.io/authoring/XXX \
 -H 'Authorization: Bearer <ACCESS_TOKEN>' \
 -H 'x-api-key: <API_KEY>' \
 -H 'x-gw-ims-org-id: <ORGANIZATION>'
```

* **&lt;ORGANIZATION>**：これは個人の組織 ID で、インスタンスごとに 1 つの組織 ID がアドビから提供されます。組織 ID の値を取得するには、管理者またはアドビの技術担当者にお問い合わせください。また、新しい統合を作成する際に、ライセンスリストで Adobe I/O に取得することもできます（<a href="https://www.adobe.io/authentication.html">Adobe I/O のドキュメント</a>を参照してください）。

* **&lt;ACCESS_TOKEN>**：POST リクエストを通じて JWT を交換する際に取得した個人用アクセストークンです。

* **&lt;API_KEY>**：個人用 API キーです。[!DNL Journey Orchestration] サービスへの新しい統合を作成した後、Adobe I/O で提供されます。