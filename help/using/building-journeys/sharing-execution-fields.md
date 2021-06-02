---
product: adobe campaign
title: journeyStep イベントのアクション実行フィールド
description: journeyStep イベントのアクション実行フィールド
feature: ジャーニー
role: Business Practitioner
level: Intermediate
exl-id: 9af66037-63d7-41a8-86d1-b03c655dfb82
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '321'
ht-degree: 7%

---

# journeyStep イベントのアクション実行フィールド {#sharing-execution-fields}

このmixinは、 journeyStepEventとjourneyStepProfileEventによって共有されます。

ステップに処理するアクションがある場合、それらのフィールドがイベントペイロードに追加されます。

## actionID

実行中のアクションのID。

型：文字列

## actionName

アクションの名前。 名前が設定されていない場合は、 stepNameが使用されます。

型：文字列

## actionType

アクションのタイプ。

型：文字列

## actionParameterized

アクションがパラメーター化されているかどうかを示します。

型：boolean

## actionExecutionTime

現在のアクションの実行に要した時間（ミリ秒）。

型：long

## actionExecutionError

アクションの呼び出し時に発生するエラーのタイプ。

型：文字列

値:
* http
* 制限
* タイムアウト
* error

## actionExecutionErrorCode

アクション実行エラーのコード。 エラーにHTTPコードなどのコードがある場合に存在します。

型：文字列

## actionExecutionOriginError

タイムアウトは、次の2つの場合に発生する可能性があります。

* 最初の試行時に、アクションが実行されます。 この場合、実行は完了しないので、基になるエラーは発生しません
* 再試行時：この場合、 actionExecOrigError/actionExecOrigErrorCodeは、再試行前に試行で発生したエラーを示します。

例えば、Eメールが送信され、最初の試行時にHTTP 500エラーが返されます。 フェッチは再試行されましたが、2回の試行の時間がタイムアウトを超えています。 次に、アクション実行にタイムアウトのタグが付けられます。 アクションパーツは次のようになります。

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

型：文字列

## actionExecutionOriginCode

actionExecOrigErrorのエラーコード。

型：文字列

## actionBusinessType

アクションのタイプを示します。

値:

* 組み込み
* ACS電子メール
* ACS SMS
* ACSプッシュ
* 顧客
* イプシロン
* ...

型：文字列

## deliveryJobID

バッチジョブの配信ジョブIDをジャーニーします。

型：文字列

## batchDeliveryID

バッチ配信のジャーニーID。

型：文字列

## fromSegmentTrigger

これは、バッチジャーニーがオーディエンスセグメントからトリガーされるかどうかを示します。

型：boolean

## actionSchedulerCount

ステップの処理中にスケジューラーサービスに送信されたスケジューラー通知要求の数。

型：long
