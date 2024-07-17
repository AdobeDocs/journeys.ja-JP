---
product: adobe campaign
title: ジャーニー API の基本を学ぶ
description: ジャーニー API の詳細について説明します
products: journeys
feature: Journeys
role: User
level: Intermediate
exl-id: a5dd3d23-c820-4ab7-bc6c-b1dcfe15022c
source-git-commit: 87d5cf223d9adec27eabcb55f2e09aa6d40b23a6
workflow-type: tm+mt
source-wordcount: '791'
ht-degree: 90%

---

# ジャーニー API の基本を学ぶ

## Capping API とThrottling API について

データソースやアクションを設定する際は、システムへの接続を確立して、ジャーニーで使用する追加情報を取得したり、メッセージや API 呼び出しを送信したりします。

ジャーニー API では 1 秒あたり最大 5000 イベントをサポートしていますが、一部の外部システムや API は同等のスループットを持たない場合があります。これらのシステムに対する過負荷を防止するために、**Capping** API と&#x200B;**Throttling** API を使用して、1 秒あたりに送信されるイベントの数を制限できます。

API 呼び出しがジャーニーで実行されるたびに、呼び出しが API エンジンを通過します。API で設定された上限に達すると、Capping API を使用している場合は呼び出しが拒否され、Throttling API を使用している場合は最大 6 時間キューに入れられて、受信した順序でできるだけ早く処理されます。

たとえば、外部システムに対して 1 秒あたり 100 呼び出しまで、というキャッピングルールまたはスロットルルールを定義したとします。システムは、10 件の異なるジャーニーでカスタムアクションによって呼び出されます。1 つのジャーニーで 1 秒間に 200 件の呼び出しを受け取った場合、使用可能な 100 個のスロットを使用し、残りの 100 個のスロットを破棄するかキューに入れます。最大レートを超えたので、他の 9 つのジャーニーにはスロットは残りません。この精度は、外部システムを過負荷やクラッシュから保護するのに役立ちます。

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

>[!CAUTION]
>
>アクセストークンを生成する JWT メソッドは非推奨（廃止予定）になりました。 すべての新しい統合は、[OAuth サーバー間認証方法 ](https://experienceleague.adobe.com/docs/experience-platform/landing/platform-apis/api-authentication.html#select-oauth-server-to-server) を使用して作成する必要があります。 また、Adobeでは、既存の統合環境を OAuth 方式に移行することをお勧めします。
>
>以下の重要なドキュメントを参照してください。
>[JWT から OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/) へのアプリケーションの移行ガイド
>[OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/) を使用した新旧のアプリケーションの実装ガイド
>[OAuth サーバー間資格情報方式を使用する場合の利点 ](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/#why-oauth-server-to-server-credentials)

サービス間のセキュアな Adobe I/O API セッションを確立するには、アドビサービスへのすべてのリクエストで、以下の情報を Authorization ヘッダーに含める必要があります。

```
curl -X GET https://journey.adobe.io/authoring/XXX \
 -H 'Authorization: Bearer <ACCESS_TOKEN>' \
 -H 'x-api-key: <API_KEY>' \
 -H 'x-gw-ims-org-id: <ORGANIZATION>'
```

* **&lt;ORGANIZATION>**：これは個人の組織 ID で、インスタンスごとに 1 つの組織 ID がアドビから提供されます。組織 ID の値を取得するには、管理者またはアドビの技術担当者にお問い合わせください。また、新しい統合を作成する際に、ライセンスリストで Adobe I/O に取得することもできます（[Adobe I/O のドキュメント](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md)を参照してください）。

* **&lt;ACCESS_TOKEN>**：個人用アクセストークンです

* **&lt;API_KEY>**：個人用 API キーです。[!DNL Journey Orchestration] サービスへの新しい統合を作成した後、Adobe I/O で提供されます。
