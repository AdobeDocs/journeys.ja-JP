---
title: journeyStep イベントのアクション実行フィールド
description: journeyStep イベントのアクション実行フィールド
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
source-git-commit: 10402a774bda66629f30869102d5e6ceca267535
workflow-type: tm+mt
source-wordcount: '320'
ht-degree: 5%

---


# journeyStep イベントのアクション実行フィールド {#sharing-execution-fields}

このミックスインは、jearnyStepEventとjearnyStepProfileEventで共有されます。

ステップに処理するアクションがある場合、これらのフィールドはイベントペイロードに追加されます。

## actionID

実行中のアクションのID。

タイプ： string

## actionName

アクションの名前。 名前が設定されていない場合、stepNameが使用されます。

タイプ： string

## actionType

アクションのタイプ。

タイプ： string

## actionParameterized

アクションがパラメータ化されているかどうかを示します。

タイプ： boolean

## actionExecutionTime

現在のアクションを実行するのに費やされた時間（ミリ秒）。

タイプ： long

## actionExecutionError

アクションが呼び出されたときに発生するエラーの種類です。

タイプ： string

値:
* http
* キャッピング
* timeout
* error

## actionExecutionErrorCode

アクション実行エラーのコード。 HTTPなどのコードがエラーにある場合に表示されます。

タイプ： string

## actionExecutionOriginError

タイムアウトは、次の2つの場合に発生する可能性があります。

* 最初の試行時に、アクションが実行されます。 この場合、実行は完了せず、基になるエラーはありません
* 再試行時： この場合、actionExecOrigError/actionExecOrigErrorCodeは、再試行前に試行されたエラーを示します。

例えば、電子メールが送信され、最初の試行時にHTTP 500エラーが返されます。 フェッチは再試行されますが、2回の試行の時間がタイムアウトを超えます。 次に、アクションの実行にタイムアウトのタグが付けられます。 アクションパーツは次のようになります。

```
    ...
    "actionId": "myActionId",
    "actionName": "My mail sending",
    "actionType": "acsRestAction",
    "actionParameterized": true,
    "actionExecError": "timedout",
    "actionExecOrigError": "http",
    "actionExecOrigErrorCode": "500"
```

タイプ： string

## actionExecutionOriginCode

actionExecOrigErrorのエラーコードです。

タイプ： string

## actionBusinessType

アクションのタイプを示します。

値:

* 組み込み
* ACS電子メール
* ACS SMS
* ACSプッシュ
* 顧客
* エプシロン
* ...

タイプ： string

## deliveryJobID

バッチジャーニーの配信ジョブIDを説明します。

タイプ： string

## batchDeliveryID

バッチジャーニーの配信IDを示します。

タイプ： string

## fromSegmentTrigger

これは、オーディエンスセグメントからバッチジャーニーがトリガーされるかどうかを説明します。

タイプ： boolean

## actionSchedulerCount

ステップ処理中にスケジューラーサービスに送信されたスケジューラー通知要求の数。

タイプ： long
