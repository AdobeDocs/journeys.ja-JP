---
product: adobe campaign
title: journeySteps イベントの共通フィールド
description: journeySteps イベントの共通フィールド
feature: Journeys
role: User
level: Intermediate
exl-id: 5cf8e6b5-2162-4aa3-b071-96ede31948e6
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '581'
ht-degree: 100%

---

# journeySteps イベントの共通フィールド {#sharing-common-fields}

この Mixin は、journeyStepEvent と journeyStepProfileEvent が共有します。

[!DNL Journey Orchestration] が Adobe Experience Platform に送信する一般的な XDM フィールドです。共通フィールドは、ジャーニーで処理される各ステップに対して送信されます。カスタムアクションやカスタムエンリッチメントには、より具体的なフィールドが使用されます。

イベントのサイズを制限するため、これらのフィールドの一部は、特定の処理パターン（アクションの実行、データの取得など）でのみ使用できます。

## エントリ

ユーザーがジャーニーにエントリしたかどうかを示します。存在しない場合、値は false とみなします。

型：ブール型

値：true/false

## 再エントリ

ユーザーが同じインスタンスでジャーニーに再度エントリしたかどうかを示します。存在しない場合、値は false とみなします。

型：ブール型

値：true/false

## instanceEnded

インスタンスが終了したかどうか（成功または失敗）を示します。

型：ブール型

## eventID

ステップ処理など、処理中のイベント ID。イベントが外部イベントの場合、値は eventId です。イベントが内部イベントの場合、値は内部 eventId（scheduledNotificationReceived、executedAction など）です。

型：文字列

## nodeID

（キャンバスから得られる）クライアントノード ID。

型：文字列

## stepID

現在処理中のステップを表す一意の ID です。

型：文字列

## stepName

現在処理中のステップの名前。

型：文字列

## stepType

ステップのタイプ。

型：文字列

使用可能な値：

* 条件
* アクション
* スケジューラー
* タイマー

## stepStatus

処理が完了（およびステップイベントが実行された）ときの、ステップのステータス。

型：文字列

ステータスには次の種類があります。

* ended：ステップにトランジションがなく、正常に処理が終了しました。
* error：ステップ処理でエラーが発生しました。
* transitions：ステップは、別のステップへトランジションするイベントの待機中です。
* capped：アクションまたはエンリッチメント実行中にキャッピングエラーが発生し、ステップが失敗しました。
* timedout：ステップは、アクションまたはエンリッチメント中に発生したタイムアウトエラーで失敗しました。
* instanceTimedout：インスタンスがタイムアウトに到達したので、ステップの処理が停止しました。

## journeyID

ジャーニー ID。

型：文字列

## journeyVersionID

ジャーニーバージョンの ID。この ID は、journeyStepEvent においてジャーニーを参照する ID です。

型：文字列

## journeyVersionName

ジャーニーバージョンの名前。

型：文字列

## journeyVersion

ジャーニーのバージョン。

型：文字列

## instanceID

ジャーニーインスタンスの内部 ID。

型：文字列

## externalKey

イベントから抽出された外部キーを処理します。

型：文字列

## parentStepID

インスタンス内で現在処理されているステップの親ステップ ID。

型：文字列

## parentStepName

現在のステップの親ステップ名。

型：文字列

## parentTransitionID

処理済みのステップにインスタンスを導いたトランジションの ID。

型：文字列

## parentTransitionName

インスタンスを処理済みのステップに導いたトランジションの名前。

型：文字列

## inTest

このジャーニーがテストモードになっているかどうかを示します。

型：ブール型

## processingTime

インスタンスステップのエントリから処理の終了までの合計時間（ミリ秒）です。

型：long

## instanceType

インスタンスの種類（バッチまたは単一の場合）を示します。

型：文字列

値：バッチ／単一

## recurrenceIndex

ジャーニーがバッチおよび定期的な場合の繰り返しのインデックス（最初の実行はrecurrenceIndex = 1）。

型：long

## isBatchToUnitary

この単一インスタンスがバッチインスタンスからトリガーされたかどうかを示します。

型：ブール型

## batchExternalKey

バッチイベントの外部キー。

型：文字列

## batchInstanceID

これは、バッチインスタンス ID です。

型：文字列

## batchUnitaryBranchID

インスタンスがバッチインスタンスからトリガーされた場合は、単一の分岐 ID。

型：文字列
