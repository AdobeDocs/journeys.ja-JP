---
title: '外部データソース '
description: '外部データソースの設定方法を学びます。 '
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
source-git-commit: a1c4eed8360efcbfcaa5e54c8831e1a4b2ecc02e
workflow-type: tm+mt
source-wordcount: '1251'
ht-degree: 0%

---



# 外部データソース {#concept_t2s_kqt_52b}

外部データソースを使用すると、サードパーティ製システムへの接続を定義できます。例えば、ホテルの予約システムを使用して、その人が部屋を登録したかどうかを確認する場合などです。 組み込みのExperience Platformデータソースとは異なり、外部データソースは必要な数だけ作成できます。

POSTまたはGETとRETURNING JSONを使用するREST APIがサポートされます。 APIキー、基本認証モード、カスタム認証モードがサポートされています。

次に、リアルタイムの天気データに従って旅の行動をカスタマイズするために使用するweather APIサービスの例を見てみましょう。

API呼び出しの例を2つ示します。

* _https://api.adobeweather.org/weather?city=London,uk&amp;appid=1234_
* _https://api.adobeweather.org/weather?lat=35&amp;lon=139&amp;appid=1234_

この呼び出しは、メインURL(_https://api.adobeweather.org/weather_)、2つのパラメーターセット（市区町村を表す「市区町村」、緯度と経度を表す「lat/long」）、APIキー(appid)で構成されます。

新しい外部データソースを作成および設定する主な手順は次のとおりです。

1. データソースのリストで、をクリックし **** 追加て、新しい外部データソースを作成します。

   ![](../assets/journey25.png)

   画面の右側にデータソース設定ペインが開きます。

   ![](../assets/journey26.png)

1. データソースの名前を入力します。

   >[!NOTE]
   >
   >スペースや特殊文字は使用しないでください。 30文字以内にしてください。

1. データ追加ソースの説明。 この手順はオプションです。
1. 外部サ追加ービスのURLです。 この例では、次のようになります。 _https://api.adobeweather.org/weather_.

   >[!CAUTION]
   >
   >セキュリティ上の理由から、HTTPSの使用を強くお勧めします。 また、一般公開されていないアドビのアドレスの使用およびIPアドレスの使用は許可されていません。

   ![](../assets/journey27.png)

1. 外部サービスの設定に応じて認証を設定します。 **[!UICONTROL 認証なし]**、 **[!UICONTROL 基本]**、 **[!UICONTROL カスタム]** 、 **[!UICONTROL APIキー]**。 カスタム認証モードの詳細については、を参照してください [](../datasource/external-data-sources.md#section_wjp_nl5_nhb)。 この例では、次を選択します。


   * **[!UICONTROL タイプ]**: &quot;APIキー&quot;
   * **[!UICONTROL 値]**: &quot;1234&quot;（これはAPIキーの値です）
   * **[!UICONTROL 名前]**: &quot;appid&quot;（これはAPIキーパラメーター名です）
   * **[!UICONTROL 場所]**: &quot;クエリパラメーター&quot;（APIキーはURL内にあります）
   ![](../assets/journey28.png)

1. 「追加新しいフィールドグループ追加」をクリックして、APIパラメーターセットごとに新しいフィールドグループを作成し ****&#x200B;ます。 フィールドグループ名にはスペースや特殊文字を使用しないでください。 この例では、パラメーターセット（cityとlong/lat）ごとに1つずつ、2つのフィールドグループを作成する必要があります。

「long/lat」パラメーターセットに対して、次の情報を持つフィールドグループを作成します。

* **[!UICONTROL 使用場所]**: フィールドグループを使用するジャーニーの数を表示します。 「 **[!UICONTROL 表示ジャーニー]** 」アイコンをクリックすると、このフィールドグループを使用してジャーニーのリストを表示できます。
* **[!UICONTROL メソッド]**: POSTまたはGETメソッドを選択します。 この場合、GETメソッドを選択します。
* **[!UICONTROL キャッシュ期間]**: この場合、天気を10分間キャッシュする必要があります。
* **[!UICONTROL 応答ペイロード]**: 「 **[!UICONTROL Payload]** 」フィールド内をクリックし、呼び出しによって返されたペイロードの例を貼り付けます。 この例では、weather APIのWebサイトで見つかったペイロードを使用しました。 フィールドの種類が正しいことを確認します。 APIが呼び出されるたびに、システムはペイロード例に含まれるすべてのフィールドを取得します。 現在渡されているペイロードを変更する場合は、「新しいペイロードを **[!UICONTROL 貼り付け]** 」をクリックできます。
* **[!UICONTROL 動的値]**: この例では、コマ(long,lat)で区切られた異なるパラメータを入力します。 パラメータ値は実行コンテキストに依存するので、ジャーニーで定義されます。 [](../expression/expressionadvanced.md)を参照してください。
* **[!UICONTROL Sent Payload]**: このフィールドは、この例では表示されません。 POSTメソッドを選択した場合にのみ使用できます。 サードパーティシステムに送信するペイロードを貼り付けます。

パラメータが必要なGET呼び出しの場合は、 **[!UICONTROL Parameters]** (s)フィールドにパラメータを入力すると、呼び出しの最後に自動的に追加されます。 POST呼び出しの場合は、次の操作が必要です。

* 呼び出し時に渡すパラメーターを「 **[!UICONTROL Parameter]** （パラメーター）」フィールドにリストします（以下の例を参照）。 &quot;識別子&quot;)。
* また、送信されたペイロードの本文で同じ構文を使用して指定します。 そのためには、次を追加する必要があります。 &quot;param&quot;: &quot;name of your parameter&quot;(下の例では次のようになります。 &quot;識別子&quot;)。 次の構文に従います。

   ```
   {"id":{"param":"identifier"}}
   ```

![](../assets/journey29.png)

「**[!UICONTROL 保存]**」をクリックします。

これで、データソースが設定され、ジャーニーで使用できる状態になりました。例えば、状況に応じて、電子メールをパーソナライズできます。 温度が30°Cを超える場合は、特定の通信を送信することができます。

## カスタム認証モード{#section_wjp_nl5_nhb}

>[!CONTEXTUALHELP]
>id="jo_authentication_payload"
>title="カスタム認証について"
>abstract="カスタム認証モードは、OAuth2などのAPIラッピングプロトコルを呼び出す複雑な認証に使用されます。 アクションの実行は、2つの手順で構成されるプロセスです。 まず、エンドポイントへの呼び出しを実行して、アクセストークンを生成する。 次に、アクションのHTTPリクエストにアクセストークンが挿入されます。"

この認証モードは、複雑な認証に使用されます。複雑な認証は、OAuth2などのAPIラッピングプロトコルを呼び出して、アクションに対する実際のHTTP要求に挿入されるアクセストークンを取得するためによく使用されます。

カスタム認証を設定する場合、下のボタンをクリックして、カスタム認証ペイロードが正しく設定されているかどうかを確認できます。

![](../assets/journey29-bis.png)

テストが成功すると、ボタンが緑色に変わります。

![](../assets/journey29-ter.png)

この認証を使用すると、アクションの実行は次の2つの手順で行われます。

1. エンドポイントを呼び出してアクセストークンを生成します。
1. アクセストークンを適切に挿入してREST APIを呼び出します。

この認証には2つの部分があります。

アクセストークンの生成時に呼び出されるエンドポイントの定義：

* endpoint: エンドポイントの生成に使用するURL
* エンドポイント（GETまたはPOST）でのHTTPリクエストのメソッド
* ヘッダー： 必要に応じて、この呼び出しでヘッダーとして挿入されるキー/値のペア
* body: メソッドがPOSTの場合の呼び出しの本文を説明します。 bodyParams（キー/値のペア）で定義される、制限付きのボディ構造をサポートしています。 bodyTypeは、次の呼び出しでの本文の形式とエンコーディングを記述します。
   * &#39;form&#39;: つまり、コンテンツタイプはapplication/x-www-form-urlencoded(charset UTF-8)になり、キー/値のペアは次のようにシリアル化されます。 key1=value1&amp;key2=value2&amp;...
   * &#39;json&#39;: つまり、コンテンツタイプはapplication/json(charset UTF-8)になり、キーと値のペアは次のようにjsonオブジェクトとしてシリアル化されます。 _{ &quot;key1&quot;: &quot;value1&quot;, &quot;key2&quot;: &quot;value2&quot;, ...}_

アクションのHTTPリクエストにアクセストークンを挿入する方法の定義です。

* authorizationType: 生成されたアクセストークンを、アクションのHTTP呼び出しに挿入する方法を定義します。 使用できる値は次のとおりです。

   * bearer: は、次のように、アクセストークンを認証ヘッダーに挿入する必要があることを示します。 _認証： Bearer &lt;アクセストークン>_
   * header: は、アクセストークンをヘッダーとして挿入する必要があることを示します。このヘッダー名は、tokenTargetプロパティで定義されます。 例えば、tokenTargetがmyHeaderの場合、アクセストークンは次のようにヘッダーとして挿入されます。 _myHeader: &lt;アクセストークン>_
   * queryParam: は、アクセストークンをqueryParam(プロパティtokenTargetで定義されるクエリパラメーター名)として挿入する必要があることを示します。 例えば、tokenTargetがmyQueryParamの場合、アクション呼び出しのURLは次のようになります。 _&lt;url>?myQueryParam=&lt;アクセストークン>_

* tokenInResponse: 認証呼び出しからアクセストークンを抽出する方法を示します。 このプロパティは次のいずれかになります。
   * &#39;response&#39;: は、HTTP応答がアクセストークンであることを示します
   * json内のセレクター（応答がjsonである場合、XMLなどの他の形式はサポートされません）。 このセレクターの形式は、json:// _&lt;アクセストークンプロパティのパス>_&#x200B;です。 例えば、呼び出しの応答が次の場合： _{ &quot;access_token&quot;: &quot;theToken&quot;, &quot;timestamp&quot;: 1232344565656 }_、tokenInResponseは次のようになります。 _json: //access_token_

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
