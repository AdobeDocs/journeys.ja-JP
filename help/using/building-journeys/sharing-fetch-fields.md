---
product: adobe campaign
title: journeyStep イベントのデータ取得フィールド
description: journeyStep イベントのデータ取得フィールド
feature: ジャーニー
role: User
level: Intermediate
exl-id: 4df471ae-c6b7-452e-8e44-a108d0da276f
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '372'
ht-degree: 95%

---

# journeyStep イベントのデータ取得フィールド {#sharing-fetch-fields}

この Mixin は、journeyStepEvent と journeyStepProfileEvent が共有します。

ステップの処理中に、フィールドグループで N 個のデータを取得できます。

## fetchTotalTime

ステップ処理中のデータ取得に費やした合計時間（ミリ秒単位）です。

型：long

## fetchTypeInError

取得エラーがAdobe Experience Platform上にあるか、カスタムデータソース上にあるかを定義します。

型：文字列

値：
* aep
* custom

## fetchError

データ取得の処理時に発生するエラーの種類です。

型：文字列

値：
* http
* キャッピング
* timedout
* error

## fetchErrorCode

取得エラーコード。エラーにコードがあるかどうかを示します（HTTP など）。例えば、actionExecError が http の場合、コード 404 は HTTP 404 エラーを表します。

型：文字列

## fetchOriginError

タイムアウトは、次の 2 つの場合に発生する可能性があります。

* 初回試行時に、アクションが実行されます。この場合、実行は完了せず、基になるエラーはありません。
* 再試行時。この場合、actionExecOrigError/actionExecOrigErrorCode は、再試行前に試行したときのエラーを示します。

例えば、統合プロファイルサービスからデータを取得中、最初の試行時に HTTP 500 エラーが返されます。フェッチを再試行しますが、2 回の試行のデュレーションがタイムアウトを超えます。次に、アクションの実行にタイムアウトのタグが付けられます。アクション部分は次のようになります。

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

システム [!DNL Journey Orchestration] から提供されたエラーコードを問い合わせています。例えば、404、500などのエラーコード。

型：文字列

## fetchCount

データの取得回数（ソースのタイプを問わない）。

型：long

## fetchPlatformTotalTime

Adobe Experience Platform からデータを取得するのに要した合計時間（ミリ秒）。備考：この時間は、エンジンがエンリッチメントイベントをエンリッチメントサービスに送信し、応答を受信した時点から計算されます。

型：long

## fetchPlatformCount

Adobe Experience Platform からデータが取得された回数。

型：long

## fetchCustomTotalTime

カスタムデータの取得にかかる時間（ミリ秒）。備考：この時間は、エンジンがエンリッチメントイベントをエンリッチメントサービスに送信し、応答を受信した時点から計算されます

型：long

## fetchCustomCount

外部システムからカスタムデータを取得した回数。

型：long
