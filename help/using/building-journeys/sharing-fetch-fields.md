---
product: adobe campaign
title: journeyStep イベントのデータ取得フィールド
description: journeyStep イベントのデータ取得フィールド
feature: ジャーニー
role: Business Practitioner
level: Intermediate
exl-id: 4df471ae-c6b7-452e-8e44-a108d0da276f
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '372'
ht-degree: 5%

---

# journeyStep イベントのデータ取得フィールド {#sharing-fetch-fields}

このmixinは、 journeyStepEventとjourneyStepProfileEventによって共有されます。

ステップの処理中に、フィールドグループでN個のデータを取得できます。

## fetchTotalTime

ステップ処理中のデータ取得に費やされた合計時間（ミリ秒）。

型：long

## fetchTypeInError

取得エラーがAdobe Experience Platform上にあるか、カスタムデータソース上にあるかを定義します。

型：文字列

値:
* aep
* custom

## fetchError

データ取得の処理時に発生するエラーのタイプ。

型：文字列

値:
* http
* 制限
* timedout
* error

## fetchErrorCode

取得エラーのコード。 エラーにHTTPコードなどのコードがある場合に存在します。 例えば、actionExecErrorがhttpの場合、コード404はHTTP 404エラーを表します。

型：文字列

## fetchOriginError

タイムアウトは、次の2つの場合に発生する可能性があります。

* 最初の試行時に、アクションが実行されます。 この場合、実行は完了しないので、基になるエラーは発生しません
* 再試行時：この場合、 actionExecOrigError/actionExecOrigErrorCodeは、再試行前に試行で発生したエラーを示します。

例えば、データが統合プロファイルサービスから取得され、最初の試行時にHTTP 500エラーが返されます。 フェッチは再試行されましたが、2回の試行の時間がタイムアウトを超えています。 次に、アクション実行にタイムアウトのタグが付けられます。 アクションパーツは次のようになります。

```
    ...
    "fetchTypeInError": "aep",
    "fieldgroupIdInError": "MyProfileFieldgroup",
    "fetchError": "timedout",
    "fetchOrigError": "http",
    "fetchOrigErrorCode": "500"
```

型：文字列

## fetchOriginErrorCode

システム[!DNL Journey Orchestration]から提供されるエラーコードはクエリ中です。 例えば、404、500などです。

型：文字列

## fetchCount

ソースのタイプに関係なく、データがフェッチされた回数。

型：long

## fetchPlatformTotalTime

Adobe Experience Platformからデータを取得するのに要した合計時間（ミリ秒）。 注釈：この時間は、エンジンがエンリッチメントイベントをエンリッチメントサービスに送信し、応答を受け取った時点から計算されます。

型：long

## fetchPlatformCount

Adobe Experience Platformからデータがフェッチされた回数。

型：long

## fetchCustomTotalTime

カスタムデータを取得する時間（ミリ秒）。 注釈：この時間は、エンジンがエンリッチメントイベントをエンリッチメントサービスに送信し、応答を受け取った時点から計算されます

型：long

## fetchCustomCount

外部システムからカスタムデータを取得する回数。

型：long
