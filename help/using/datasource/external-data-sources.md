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
source-git-commit: a0db4d65218861b71d35f83ccf2d15e25a1597e8

---



# 外部データソース {#concept_t2s_kqt_52b}

外部データソースを使用すると、例えばホテルの予約システムを使用して人が部屋を登録したかどうかを確認する場合など、サードパーティ製システムへの接続を定義できます。 組み込みのExperience Platformデータソースとは異なり、必要な数の外部データソースを作成できます。

POSTまたはGETを使用したREST APIとJSONを返すREST APIがサポートされています。 APIキー、基本認証モード、カスタム認証モードがサポートされています。

次に、リアルタイムの天気データに従って旅行の行動をカスタマイズするために使用する天気APIサービスの例を示します。

API呼び出しの例を2つ示します。

* _https://api.adobeweather.org/weather?city=London,uk&amp;appid=1234_
* _https://api.adobeweather.org/weather?lat=35&amp;lon=139&amp;appid=1234_

この呼び出しは、メインURL(_https://api.adobeweather.org/weather_)、2つのパラメーターセット（市区町村を表す「city」、緯度と経度を表す「lat/long」）、APIキー(appid)で構成されます。

新しい外部データソースを作成および設定する主な手順は、次のとおりです。

1. データソースのリストから、をクリックして新し **[!UICONTROL Add]** い外部データソースを作成します。

   ![](../assets/journey25.png)

   画面の右側にデータソース設定ウィンドウが開きます。

   ![](../assets/journey26.png)

1. データソースの名前を入力します。

   >[!NOTE]
   >
   >スペースや特殊文字は使用しないでください。 30文字以内にする必要があります。

1. データソースに説明を追加します。 この手順はオプションです。
1. 外部サービスのURLを追加します。 この例では、次のようになります。 _https://api.adobeweather.org/weather_。

   >[!CAUTION]
   >
   >セキュリティ上の理由から、HTTPSの使用を強くお勧めします。 また、一般に公開されていないアドビのアドレスやIPアドレスの使用は許可されていません。

   ![](../assets/journey27.png)

1. 外部サービスの設定に応じて認証を設定します。 **[!UICONTROL No authentication]**、ま **[!UICONTROL Basic]**&#x200B;た **[!UICONTROL Custom]** は **[!UICONTROL API key]**、 カスタム認証モードの詳細については、を参照してくださ [](../datasource/external-data-sources.md#section_wjp_nl5_nhb)い。 この例では、以下を選択します。


   * **[!UICONTROL Type]**:&quot;APIキー&quot;
   * **[!UICONTROL Value]**:&quot;1234&quot;（これはAPIキーの値です）
   * **[!UICONTROL Name]**:&quot;appid&quot;（これはAPIキーパラメーター名です）
   * **[!UICONTROL Location]**:「クエリパラメーター」（APIキーはURL内にあります）
   ![](../assets/journey28.png)

1. をクリックして、各APIパラメーターセットに対して新しいフィールドグループを追加しま **[!UICONTROL Add a New Field Group]**&#x200B;す。 フィールドグループ名にはスペースや特殊文字を使用しないでください。 この例では、2つのフィールドグループを作成し、各パラメータセット（cityとlong/lat）に1つずつ作成する必要があります。

「long/lat」パラメータセットの場合、次の情報を含むフィールドグループを作成します。

* **[!UICONTROL Used in]**:フィールドグループを使用するジャーニーの数を表示します。 このアイコンをクリックす **[!UICONTROL View journeys]** ると、このフィールドグループを使用するジャーニーのリストが表示されます。
* **[!UICONTROL Method]**:postまたはGETメソッドを選択します。 この例では、GETメソッドを選択します。
* **[!UICONTROL Cache duration]**:この場合、天気を10分間キャッシュします。
* **[!UICONTROL Response Payload]**:フィールド内をク **[!UICONTROL Payload]** リックし、呼び出しによって返されたペイロードの例を貼り付けます。 この例では、気象APIウェブサイトで見つかったペイロードを使用しました。 フィールドタイプが正しいことを確認します。 APIが呼び出されるたびに、ペイロードの例に含まれるすべてのフィールドが取得されます。 現在渡されているペイロードを変 **[!UICONTROL Paste a new payload]** 更する場合は、をクリックします。
* **[!UICONTROL Dynamic Values]**:この例では、異なるパラメータをコマで区切って「long,lat」と入力します。 パラメータ値は実行コンテキストに依存するので、ジャーニーで定義されます。 [](../expression/expressionadvanced.md)を参照してください。
* **[!UICONTROL Sent Payload]**:このフィールドは、この例では表示されません。 POSTメソッドを選択した場合にのみ使用できます。 サードパーティシステムに送信するペイロードを貼り付けます。

パラメータが必要なGET呼び出しの場合は、フィールドにパラメータを入力すると、 **[!UICONTROL Parameters]** 呼び出しの最後に自動的に追加されます。 POST呼び出しの場合は、次の操作が必要です。

* 呼び出し時に渡すパラメーターをフィールドに一覧 **[!UICONTROL Parameter]** 表示します（以下の例を参照）。&quot;identifier&quot;)。
* 送信したペイロードの本文でも、同じ構文で指定します。 これを行うには、次を追加する必要があります。&quot;param&quot;:&quot;name of your parameter&quot;(以下の例では、&quot;identifier&quot;)。 次の構文に従います。

   ```
   {"id":{"param":"identifier"}}
   ```

![](../assets/journey29.png)

クリック **[!UICONTROL Save]**.

データソースが設定され、ジャーニー（例えば、お客様の環境で使用したり、電子メールをパーソナライズしたりする）で使用できる状態になりました。 温度が30°Cを超える場合は、特定の通信を送信することを決定できます。

## カスタム認証モード{#section_wjp_nl5_nhb}

この認証モードは、複雑な認証に使用されます。複雑な認証は、OAuth2などのAPIラッププロトコルを呼び出して、アクションの実際のHTTP要求に挿入されるアクセストークンを取得するためによく使用されます。

カスタム認証を設定する場合、下のボタンをクリックして、カスタム認証ペイロードが正しく設定されているかどうかを確認できます。

![](../assets/journey29-bis.png)

テストが成功すると、ボタンが緑色に変わります。

![](../assets/journey29-ter.png)

この認証を使用すると、アクションの実行は次の2つの手順で行われます。

1. エンドポイントを呼び出して、アクセストークンを生成します。
1. アクセストークンを適切な方法で挿入して、REST APIを呼び出します。

この認証には2つの部分があります。

アクセストークンを生成するために呼び出されるエンドポイントの定義：

* endpoint:エンドポイントの生成に使用するURL
* エンドポイント（GETまたはPOST）のHTTPリクエストのメソッド
* ヘッダー：必要に応じて、この呼び出しでヘッダーとして挿入されるキーと値のペア
* body:メソッドがPOSTの場合に呼び出しの本文を示します。 bodyParams（キーと値のペア）で定義された、制限付きのボディ構造をサポートします。 bodyTypeは、呼び出しでの本文の形式とエンコーディングを記述します。
   * &#39;form&#39;:つまり、コンテンツタイプはapplication/x-www-form-urlencoded(charset UTF-8)で、キーと値のペアは次のようにシリアル化されます。key1=value1&amp;key2=value2&amp;...
   * &#39;json&#39;:つまり、コンテンツタイプはapplication/json(charset UTF-8)で、キーと値のペアは次のようにjsonオブジェクトとしてシリアル化されます。 _{ &quot;key1&quot;:&quot;value1&quot;, &quot;key2&quot;:&quot;value2&quot;, ...}_

アクションのHTTPリクエストでアクセストークンを挿入する方法の定義：

* authorizationType:生成されたアクセストークンを、アクションのHTTP呼び出しで挿入する方法を定義します。 次の値を指定できます。

   * bearer:は、次のようなアクセストークンを認証ヘッダーに挿入する必要があることを示します。認 _証：Bearer &lt;アクセストークン>_
   * header:は、アクセストークンをヘッダーとして挿入する必要があることを示します。このヘッダー名は、tokenTargetプロパティで定義されています。 例えば、tokenTargetがmyHeaderの場合、アクセストークンは次のようにヘッダーとして挿入されます。 _myHeader:&lt;アクセストークン>_
   * queryParam:は、アクセストークンをqueryParam（tokenTargetプロパティで定義されるクエリパラメーター名）として挿入する必要があることを示します。 例えば、tokenTargetがmyQueryParamの場合、アクション呼び出しのURLは次のようになります。 _&lt;url>?myQueryParam=&lt;アクセストークン>_

* tokenInResponse:は、認証呼び出しからアクセストークンを抽出する方法を示します。 このプロパティは次のようになります。
   * &#39;response&#39;:は、HTTP応答がアクセストークンであることを示します。
   * json内のセレクター（応答がjsonである場合、XMLなどの他の形式はサポートされません）。 このセレクターの形式は、 _json://&lt;アクセストークンプロパティのパス>です_。 例えば、呼び出しの応答が次の場合： _{ &quot;access_token&quot;:&quot;theToken&quot;, &quot;timestamp&quot;:12323445656}_、tokenInResponseは次のようになります。 _json://access_token_

この認証の形式は次のとおりです。

```
{
    "type": "customAuthorization",
    "authorizationType": "<value in 'bearer', 'header' or 'queryParam'>",
    (optional, mandatory if authorizationType is 'header' or 'queryParam') "tokenTarget": "<name of the header or queryParam if the authorizationType is 'header' or 'queryParam'>",
    "endpoint": "<URL of the authentication endpoint>",
    "method": "<HTTP method to call the authentication endpoint, in 'GET' or 'POST'>",
    (optional) "headers": {
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
