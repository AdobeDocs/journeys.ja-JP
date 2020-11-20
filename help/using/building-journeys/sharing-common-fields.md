---
product: adobe campaign
solution: Journey Orchestration
title: journeystepsイベント共通フィールド
description: journeystepsイベント共通フィールド
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '581'
ht-degree: 0%

---


# journeysteps events common fields {#sharing-common-fields}

このミックスインは、jearnyStepEventとjearnyStepProfileEventで共有されます。

以下は、Adobe Experience Platformに [!DNL Journey Orchestration] 送信される一般的なXDMフィールドです。 一般的なフィールドは、遍歴で処理される各ステップに対して送信されます。 カスタムアクションやカスタムエンリッチメントには、より具体的なフィールドが使用されます。

これらのフィールドの一部は、特定の処理パターン（アクションの実行、データの取得など）でのみ使用できます。 イベントのサイズを制限するために、

## 入り口

ユーザーが旅行に参加したかどうかを示します。 存在しない場合、値はfalseとみなします。

タイプ：boolean

値：true/false

## 再入場

ユーザーが同じインスタンスで再度遍歴に入ったかどうかを示します。 存在しない場合、値はfalseとみなします。

タイプ：boolean

値：true/false

## instanceEnded

インスタンスが終了したかどうかを示します（成功したかどうか）。

タイプ：boolean

## eventID

処理中のイベントID（ステップ処理用）。 イベントが外部イベントの場合、値はeventIdです。 イベントが内部イベントの場合、値は内部eventId（scheduledNotificationReceived、executedActionなど）です。

タイプ：string

## nodeID

（キャンバスからの）クライアントノードID。

タイプ：string

## stepID

現在処理中のステップを表す一意のIDです。

タイプ：string

## stepName

現在処理中のステップの名前。

タイプ：string

## stepType

ステップのタイプ。

タイプ：string

可能な値：

* 条件
* アクション
* スケジューラー
* タイマー

## stepStatus

処理が完了した場合(およびステップイベントが起動した場合)のステータスを表すステップのステータス。

タイプ：string

ステータスは次のとおりです。

* 終了：ステップにトランジションがなく、その処理は正常に終了しました。
* エラー：ステップ処理でエラーが発生しました。
* トランジション:ステップは、別のステップへのトランジションのイベントを待っています。
* capped:操作またはエンリッチメント中に発生したキャッピングエラーで、ステップが失敗しました。
* timedout:タイムアウトエラーが発生した場合にステップが失敗し、アクションまたはエンリッチメント中に発生しました。
* instanceTimedout:インスタンスがタイムアウトに達したので、ステップの処理が停止しました。

## jurneryID

旅のID。

タイプ：string

## jeurneyVersionID

ジャーニーバージョンのID。 このidは、jearnyStepEventの場合の、遍歴へのID参照を表します。

タイプ：string

## jeurneyVersionName

ジャーニーバージョンの名前。

タイプ：string

## jurneryVersion

ジャーニーバージョンのバージョン。

タイプ：string

## instanceID

ジャーニーインスタンスの内部ID。

タイプ：string

## externalKey

イベントから抽出された外部キーを処理します。

タイプ：string

## parentStepID

インスタンス内の現在処理されているステップの親のステップID。

タイプ：string

## parentStepName

現在のステップの親のステップ名。

タイプ：string

## parentTransitionID

処理済みのステップにインスタンスを導いたトランジションのID。

タイプ：string

## parentTransitionName

インスタンスを処理済みのステップに導いたトランジションの名前。

タイプ：string

## inTest

この遍歴がテストモードかどうかを示します。

タイプ：boolean

## processingTime

インスタンスステップが処理の開始から終了までの合計時間（ミリ秒）です。

タイプ：long

## instanceType

インスタンスタイプ（バッチまたは単一の場合）を示します。

タイプ：string

値：バッチ/単一

## recurrenceIndex

遍歴がバッチおよび定期的な場合の繰り返しのインデックス（最初の実行はrecurrenceIndex = 1）。

タイプ：long

## isBatchToUnitary

この単一インスタンスがバッチインスタンスからトリガーされたかどうかを示します。

タイプ：boolean

## batchExternalKey

バッチイベントの外部キー。

タイプ：string

## batchInstanceID

これは、バッチインスタンスIDです。

タイプ：string

## batchUnitaryBranchID

インスタンスがバッチインスタンスからトリガーされた場合は、単一のブランチID。

タイプ：string
