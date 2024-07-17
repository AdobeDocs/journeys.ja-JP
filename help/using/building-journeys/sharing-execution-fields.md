---
product: adobe campaign
title: journeyStep イベントのアクション実行フィールド
description: journeyStep イベントのアクション実行フィールド
feature: Journeys
role: User
level: Intermediate
exl-id: 9af66037-63d7-41a8-86d1-b03c655dfb82
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '322'
ht-degree: 100%

---

# journeyStep イベントのアクション実行フィールド {#sharing-execution-fields}

この Mixin は、journeyStepEvent と journeyStepProfileEvent が共有します。

処理が必要なアクションがステップにある場合、これらのフィールドはイベントペイロードに追加されます。

## actionID

実行中のアクションの ID。

型：文字列

## actionName

アクションの名前。名前が設定されていない場合、stepName が使用されます。

型：文字列

## actionType

アクションのタイプ。

型：文字列

## actionParameterized

アクションがパラメータ化されているかどうかを示します。

型：ブール型

## actionExecutionTime

現在のアクションを実行するのに費やした時間（ミリ秒）。

型：long

## actionExecutionError

アクションが呼び出されたときに発生するエラーの種類。

型：文字列

値：
* http
* capping
* timeout
* error

## actionExecutionErrorCode

アクション実行エラーのコード。エラーにコードがあるかどうかを示します（HTTP など）。

型：文字列

## actionExecutionOriginError

タイムアウトは、次の 2 つの場合に発生する可能性があります。

* アクションの実行を最初に試行したとき。この場合、実行は完了せず、基になるエラーはありません。
* 再試行時。この場合、actionExecOrigError/actionExecOrigErrorCode は、再試行前に試行したときのエラーを示します。

たとえば、メールが送信され、最初の試行時に HTTP 500 エラーが返されます。フェッチを再試行しますが、2 回の試行のデュレーションがタイムアウトを超えます。次に、アクションの実行にタイムアウトのタグが付けられます。アクション部分は次のようになります。

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

actionExecOrigError のエラーコード。

型：文字列

## actionBusinessType

アクションのタイプを示します。

値：

* 組み込み
* ACS メール
* ACS SMS
* ACS プッシュ
* 顧客
* Epsilon
* ...

型：文字列

## deliveryJobID

バッチジャーニーの配信ジョブ ID を示します。

型：文字列

## batchDeliveryID

バッチジャーニーの配信 ID を示します。

型：文字列

## fromSegmentTrigger

バッチジャーニーがオーディエンスセグメントからトリガーされるかどうかを示します。

型：ブール型

## actionSchedulerCount

ステップの処理中にスケジューラーサービスに送信されたスケジューラー通知リクエストの数。

型：long
