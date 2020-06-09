---
title: jurneryStepイベントデータ取得フィールド
description: jurneryStepイベントデータ取得フィールド
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
source-git-commit: 1e7765352ec91be50b51633927ab038d3492b71a
workflow-type: tm+mt
source-wordcount: '366'
ht-degree: 1%

---


# jurneryStepイベントデータ取得フィールド {#sharing-fetch-fields}

このミックスインは、jearnyStepEventとjearnyStepProfileEventで共有されます。

ステップの処理中に、フィールドグループに対してN個のデータ取得を行うことができます。

## fetchTotalTime

ステップ処理中のデータ取得に費やした合計時間（ミリ単位）です。

タイプ： long

## fetchTypeInError

フェッチインエラーがプラットフォーム上にあるか、カスタムデータソース上にあるかを定義します。

タイプ： string

値:
* aep
* custom

## fetchError

データ取得の処理時に発生するエラーの種類です。

タイプ： string

値:
* http
* キャッピング
* 時限
* error

## fetchErrorCode

取得エラーのコード。 HTTPなどのコードがエラーにある場合に表示されます。 例えば、actionExecErrorがhttpの場合、コード404はHTTP 404エラーを表します。

タイプ： string

## fetchOriginError

タイムアウトは、次の2つの場合に発生する可能性があります。

* 最初に実行しようとすると、アクションが実行されます。 この場合、実行は完了せず、基になるエラーはありません
* 再試行時： この場合、actionExecOrigError/actionExecOrigErrorCodeは、再試行前に試行されたエラーを示します。

例えば、統合プロファイルサービスからデータを取得中で、最初の試行時にHTTP 500エラーが返されます。 フェッチは再試行されますが、2回の試行の時間がタイムアウトを超えます。 次に、アクションの実行にタイムアウトのタグが付けられます。 アクションパーツは次のようになります。

```
    ...
    "fetchTypeInError": "aep",
    "fieldgroupIdInError": "MyProfileFieldgroup",
    "fetchError": "timedout",
    "fetchOrigError": "http",
    "fetchOrigErrorCode": "500"
```

タイプ： string

## fetchOriginErrorCode

システムから提供されるエラーコード [!DNL Journey Orchestration] を照会しています。 例えば、404、500などの

タイプ： string

## fetchCount

ソースのタイプに関係なく、データがフェッチされる回数。

タイプ： long

## fetchPlatformTotalTime

データプラットフォームからデータを取得するのに要した合計時間（ミリ秒）です。 備考： この時間は、エンジンがエンリッチメントイベントをエンリッチメントサービスに送信し、応答を受信した時間から計算されます。

タイプ： long

## fetchPlatformCount

データがプラットフォームからフェッチされた回数。

タイプ： long

## fetchCustomTotalTime

カスタムデータの取得にかかる時間（ミリ秒）。 備考： この時間は、エンジンがエンリッチメントイベントをエンリッチメントサービスに送信し、応答を受信した時点から計算されます

タイプ： long

## fetchCustomCount

カスタムデータが外部システムからフェッチされた回数。

タイプ： long
