---
product: adobe campaign
title: ジャーニー API の概要
description: ジャーニー API の詳細を説明します
products: journeys
feature: Journeys
role: User
level: Intermediate
source-git-commit: 137637a753ba44cc4f8e397b77c3fc076ec3de3f
workflow-type: tm+mt
source-wordcount: '829'
ht-degree: 11%

---

# ジャーニー API の概要

## 制限およびスロットリング API について

データソースやアクションを設定する際は、システムへの接続を確立して、ジャーニーで使用する追加情報を取得するか、メッセージや API 呼び出しを送信します。

ジャーニーAPI は、1 秒あたり最大 5000 個のイベントをサポートしていますが、一部の外部システムや API は、同等のスループットを持っていない場合があります。 これらのシステムの過負荷を防ぐには、 **キャッピング** および **スロットル** 1 秒あたりに送信されるイベント数を制限する API。

API 呼び出しがジャーニーによって実行されるたびに、API エンジンを通過します。 API で設定された制限に達すると、Capping API を使用している場合は呼び出しが拒否され、Throttling API を使用している場合は、受け取った順序で、できるだけ早くキューに登録して処理されます。

例えば、外部システムに対して 1 秒あたり 100 呼び出しの制限または制限ルールを定義したとします。 システムは、10 の異なるジャーニーのカスタムアクションによって呼び出されます。 1 つのジャーニーが 1 秒に 200 通の呼び出しを受け取った場合、使用可能な 100 個のスロットを使用し、残り 100 個のスロットを破棄またはキューに入れます。 最大レートを超えたので、他の 9 つのジャーニーにはスロットは残りません。この精度は、外部システムを過負荷やクラッシュから保護するのに役立ちます。

>[!IMPORTANT]
>
>**キャッピングルール** は、特定のエンドポイント（URL が呼び出される）に対して、サンドボックスレベルで設定されますが、そのサンドボックスのすべてのジャーニーに対してグローバルです。
>
>**スロットルルール** は、特定のエンドポイントに対してのみ実稼動サンドボックスに対して設定されますが、すべてのサンドボックスにわたるすべてのジャーニーに対してグローバルです。 組織ごとに 1 つのスロットル設定のみを指定できます。

これらの API の使用方法について詳しくは、次の節を参照してください。

* [キャッピング API](capping.md)
* [スロットル API](throttling.md)

両方の API は、利用可能な Swagger ファイルでも説明されています [ここ](https://adobedocs.github.io/JourneyAPI/docs/).

## データソースとカスタムアクションの処理能力 {#capacity}

の場合 **外部データソース**&#x200B;の場合、1 秒あたりの最大呼び出し数は 15 に制限されます。 この制限を超えると、使用中の API に応じて、追加の呼び出しは破棄されるか、キューに追加されます。 Adobeに接続してエンドポイントをに含めることで、プライベート外部データソースに対するこの制限を増やすことができます許可リストが、これはパブリック外部データソースのオプションではありません。 * [データソースの設定方法を説明します](../datasource/about-data-sources.md).

>[!NOTE]
>
>データソースで、データソースで使用されているものとは異なるエンドポイントを持つカスタム認証を使用する場合は、アドビに連絡して、そのエンドポイントも許可リストに含める必要があります。

の場合 **カスタムアクション**&#x200B;外部 API の処理能力を評価する必要があります。 例えば、Journey Optimizerが 1 秒あたり 1000 回の呼び出しを送信し、システムが 1 秒あたり 100 回の呼び出しのみをサポートする場合、システムが飽和しないように制限またはスローリング設定を定義する必要があります。 [アクションの設定方法を説明します](../action/action.md)

## API アクセスの設定 {#api}

これらの API を [!DNL Journey Orchestration] 例えば、AdobeI/O コンソールを使用する必要があります。 [!DNL Journey Orchestration] API アクセスは、次の手順で設定します。 これらの各手順について詳しくは、 [Adobe I/O文書](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md).

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

* **&lt;organization>**:これは個人の組織 ID で、各インスタンスに対してAdobeが提供する ID は 1 つです。 組織 ID 値を取得するには、管理者または担当のAdobe技術担当者にお問い合わせください。 また、新しい統合を作成する際に、Adobe I/Oに取得することもできます ( <a href="https://www.adobe.io/authentication.html">Adobe I/O文書</a>) をクリックします。

* **&lt;access_token>**:個人用アクセストークン。POSTリクエストで JWT を交換する際に取得されました。

* **&lt;api_key>**:個人用 API キー。 への新しい統合を作成した後、Adobe I/Oで提供されます。 [!DNL Journey Orchestration] サービス。
