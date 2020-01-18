---
title: '外部データソース '
description: '外部データソースの設定方法を説明します。 '
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 017d502e21605b3e0b8c61e5fea0b4f6a65d4470

---



# 外部データソース {#concept_t2s_kqt_52b}

外部データソースを使用すると、例えばホテルの予約システムを使用して人が部屋を登録したかどうかを確認する場合など、サードパーティ製システムへの接続を定義できます。 組み込みのExperience Platformデータソースとは異なり、外部データソースは必要な数だけ作成できます。

POSTまたはGETを使用し、JSONを返すREST APIがサポートされます。 APIキー、基本認証モード、カスタム認証モードがサポートされています。

次に、リアルタイムの天気データに従って旅行の動作をカスタマイズするために使用するweather APIサービスの例を示します。

API呼び出しの例を2つ示します。

* _https://api.adobeweather.org/weather?city=London,uk&amp;appid=1234_
* _https://api.adobeweather.org/weather?lat=35&amp;lon=139&amp;appid=1234_

この呼び出しは、メインURL(_https://api.adobeweather.org/weather_)、2つのパラメーターセット（市区町村、緯度と経度の「緯度/経度」）、およびAPIキー(appid)で構成されます。

新しい外部データソースを作成して設定する主な手順は次のとおりです。

1. データソースのリストで、をクリックして新し **[!UICONTROL Add]**い外部データソースを作成します。

   ![](../assets/journey25.png)

   画面の右側にデータソース設定ペインが開きます。

   ![](../assets/journey26.png)

1. データソースの名前を入力します。

   >[!NOTE]
   >
   >スペースや特殊文字は使用しないでください。 30文字以内にする必要があります。

1. データソースに説明を追加します。 この手順はオプションです。
1. 外部サービスのURLを追加します。 この例では、次のようになります。https://api.adobeweather.org/weather __.

   >[!CAUTION]
   >
   >セキュリティ上の理由から、HTTPSの使用を強くお勧めします。 また、一般に公開されていないアドビのアドレスやIPアドレスの使用は許可されていません。

   ![](../assets/journey27.png)

1. 外部サービス設定に応じて認証を設定します。 **[!UICONTROL No authentication]**、**[!UICONTROL Basic]**、ま **[!UICONTROL Custom]**たは**[!UICONTROL API key]**。 カスタム認証モードの詳細については、を参照してくださ [](../datasource/external-data-sources.md#section_wjp_nl5_nhb)い。 この例では、次の項目を選択します。


   * **[!UICONTROL Type]**:&quot;APIキー&quot;
   * **[!UICONTROL Value]**:&quot;1234&quot;（これはAPIキーの値です）
   * **[!UICONTROL Name]**:&quot;appid&quot;（これはAPIキーパラメーター名です）
   * **[!UICONTROL Location]**:「クエリパラメーター」（APIキーはURL内にあります）
   ![](../assets/journey28.png)

1. をクリックして、各APIパラメーターセットに対して新しいフィールドグループを追加しま **[!UICONTROL Add a New Field Group]**す。 フィールドグループ名にはスペースや特殊文字を使用しないでください。 この例では、各パラメーターセット（cityとlong/lat）に1つずつ、2つのフィールドグループを作成する必要があります。

「long/lat」パラメーターセットの場合、次の情報を持つフィールドグループを作成します。

* **[!UICONTROL Used in]**:フィールドグループを使用するジャーニーの数を表示します。 このアイコンをクリックす**[!UICONTROL View journeys]** ると、このフィールドグループを使用するジャーニーのリストが表示されます。
* **[!UICONTROL Method]**:postメソッドまたはGETメソッドを選択します。 この例では、GETメソッドを選択します。
* **[!UICONTROL Cache duration]**:この場合、天気を10分間キャッシュする必要があります。
* **[!UICONTROL Response Payload]**:フィールド内をク**[!UICONTROL Payload]** リックし、呼び出しによって返されたペイロードの例を貼り付けます。 この例では、天気予報APIウェブサイトで見つかったペイロードを使用しました。 フィールドタイプが正しいことを確認します。 APIが呼び出されるたびに、システムはペイロード例に含まれるすべてのフィールドを取得します。 現在渡されているペイロードを変 **[!UICONTROL Paste a new payload]**更する場合は、をクリックできます。
* **[!UICONTROL Dynamic Values]**:例では、異なるパラメータをコマで区切って「long,lat」と入力します。 パラメータ値は実行コンテキストに依存するので、ジャーニーで定義されます。[](../expression/expressionadvanced.md)を参照してください。
* **[!UICONTROL Sent Payload]**:このフィールドは、この例では表示されません。 POSTメソッドを選択した場合にのみ使用できます。 サードパーティシステムに送信するペイロードを貼り付けます。

パラメータが必要なGET呼び出しの場合は、フィールドにパラメータを入力すると、呼び出し **[!UICONTROL Parameters]**の最後に自動的に追加されます。 POST呼び出しの場合は、次の操作が必要です。

* 呼び出し時に渡すパラメーターをフィールドにリ **[!UICONTROL Parameter]**ストします（以下の例を参照）。&quot;identifier&quot;)。
* 送信されたペイロードの本文でも同じ構文を使用して指定します。 そのためには、以下を追加する必要があります。&quot;param&quot;:&quot;name of your parameter&quot;(以下の例では、&quot;identifier&quot;)。 次の構文に従います。

   ```
   {“id”:{“param”:“identifier”}}
   ```

![](../assets/journey29.png)

クリック **[!UICONTROL Save]**.

データソースが設定され、ジャーニー（例えば、お客様の環境で使用したり、電子メールをパーソナライズしたりする）で使用できる状態になりました。 温度が30°Cを超える場合は、特定の通信を送信することができます。

## カスタム認証モード{#section_wjp_nl5_nhb}

この認証モードは、複雑な認証に使用されます。複雑な認証は、OAuth2などのAPIラッピングプロトコルを呼び出して、アクションの実際のHTTP要求に挿入されるアクセストークンを取得するためによく使用されます。

カスタム認証を設定する際、下のボタンをクリックして、カスタム認証ペイロードが正しく設定されているかどうかを確認できます。

![](../assets/journey29-bis.png)

テストが成功すると、ボタンが緑色に変わります。

![](../assets/journey29-ter.png)

この認証を使用すると、アクションの実行は次の2つの手順で行われます。

1. エンドポイントを呼び出して、アクセストークンを生成します。
1. アクセストークンを適切な方法で挿入して、REST APIを呼び出します。

この認証には2つの部分があります。

アクセストークンを生成するために呼び出されるエンドポイントの定義：

* endpoint:エンドポイントの生成に使用するURL
* エンドポイントでのHTTPリクエストのメソッド（GETまたはPOST）
* ヘッダー：必要に応じて、この呼び出しでヘッダーとして挿入されるキー/値のペア
* body:メソッドがPOSTの場合の呼び出しの本文を示します。 bodyParams（キーと値のペア）で定義される、制限付きのボディ構造をサポートします。 bodyTypeは、呼び出しでの本文の形式とエンコーディングを示します。
   * &#39;form&#39;:つまり、コンテンツタイプはapplication/x-www-form-urlencoded(charset UTF-8)になり、キーと値のペアは次のようにシリアライズされます。key1=value1&amp;key2=value2&amp;...
   * &#39;json&#39;:つまり、コンテンツタイプはapplication/json(charset UTF-8)で、キーと値のペアは次のようにjsonオブジェクトとしてシリアライズされます。 _{ &quot;key1&quot;:&quot;value1&quot;, &quot;key2&quot;:&quot;value2”, ...}_

アクションのHTTPリクエストにアクセストークンを挿入する方法の定義です。

* authorizationType:生成されたアクセストークンをアクションのHTTP呼び出しに挿入する方法を定義します。 使用可能な値は次のとおりです。

   * bearer:は、次のようなアクセストークンを認証ヘッダーに挿入する必要があることを示します。認 _証：Bearer &lt;access token>_
   * header:は、アクセストークンをヘッダーとして挿入する必要があることを示します。このヘッダー名は、tokenTargetプロパティで定義されます。 例えば、tokenTargetがmyHeaderの場合、アクセストークンは次のようにヘッダーとして挿入されます。 _myHeader:&lt;アクセストークン>_
   * queryParam:は、アクセストークンをqueryParam（tokenTargetプロパティで定義されるクエリパラメーター名）として挿入する必要があることを示します。 例えば、tokenTargetがmyQueryParamの場合、アクション呼び出しのURLは次のようになります。 _&lt;url>?myQueryParam=&lt;アクセストークン>_

* tokenInResponse:は、認証呼び出しからアクセストークンを抽出する方法を示します。 このプロパティは次のように指定できます。
   * &#39;response&#39;:は、HTTP応答がアクセストークンであることを示します
   * json内のセレクター（応答がjsonである場合、XMLなどの他の形式はサポートされません）。 このセレクターの形式は、json:// _&lt;access tokenプロパティへのパス>です_。 例えば、呼び出しの応答が次の場合： _{ &quot;access_token&quot;:&quot;theToken&quot;, &quot;timestamp&quot;:12323445656}_、tokenInResponseは次のようになります。 _json://access_token_

この認証の形式は次のとおりです。

```
{
    "type": "customAuthorization",
    "authorizationType": "<value in 'bearer', 'header' or 'queryParam'>",
    (optional, mandatory if authorizationType is 'header' or 'queryParam') "tokenTarget": "<name of the header or queryParam if the authorizationType is 'header' or 'queryParam'>",
    "endpoint": "<URL of the authentication endpoint>",
    "method": "<HTTP method to call the authentication endpoint, in 'GET' or 'POST'>",
    (optional) "headers: {
        "<header name>": "<header value>",
        ...
    },
    (optional, mandatory if method is 'POST') "body": {
        "bodyType": "<'form'or 'json'>,
        "bodyParams": {
            "param1": value1,
            ...

        }
    },
    "tokenInResponse": "<'response' or json selector in format 'json://<field path to access token>'"
}
```
