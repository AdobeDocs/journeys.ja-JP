---
product: adobe campaign
solution: Journey Orchestration
title: journeyStep イベントのアクション実行フィールド
description: journeyStep イベントのアクション実行フィールド
feature: ジャーニー
role: 開業医
level: 中級
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '324'
ht-degree: 7%

---


# journeyStep イベントのアクション実行フィールド {#sharing-execution-fields}

このミックスインは、jearnyStepEventとjearnyStepProfileEventで共有されます。

ステップに処理するアクションがある場合、これらのフィールドはイベントペイロードに追加されます。

## actionID

実行中のアクションのID。

タイプ：string

## actionName

アクションの名前。 名前が設定されていない場合、stepNameが使用されます。

タイプ：string

## actionType

アクションのタイプ。

タイプ：string

## actionParameterized

アクションがパラメータ化されているかどうかを示します。

タイプ：boolean

## actionExecutionTime

現在のアクションを実行するのに費やした時間（ミリ秒）。

タイプ：long

## actionExecutionError

アクションが呼び出されたときに発生するエラーの種類です。

タイプ：string

値:
* http
* キャッピング
* タイムアウト
* error

## actionExecutionErrorCode

アクション実行エラーのコード。 HTTPなどのコードがエラーにある場合に表示されます。

タイプ：string

## actionExecutionOriginError

タイムアウトは、次の2つの場合に発生する可能性があります。

* 最初の試行時に、アクションが実行されます。 この場合、実行は完了せず、基になるエラーはありません
* 再試行時：この場合、actionExecOrigError/actionExecOrigErrorCodeは、再試行前に試行されたエラーを示します。

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

タイプ：string

## actionExecutionOriginCode

actionExecOrigErrorのエラーコードです。

タイプ：string

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

タイプ：string

## deliveryJobID

バッチジャーニーの配信ジョブIDを示します。

タイプ：string

## batchDeliveryID

バッチジャーニーの配信IDを示します。

タイプ：string

## fromSegmentTrigger

ここでは、バッチジャーニーがオーディエンスセグメントからトリガーされるかどうかを説明します。

タイプ：boolean

## actionSchedulerCount

ステップ処理中にスケジューラーサービスに送信されたスケジューラー通知要求の数。

タイプ：long
