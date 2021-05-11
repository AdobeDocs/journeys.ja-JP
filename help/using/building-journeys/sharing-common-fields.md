---
product: adobe campaign
solution: Journey Orchestration
title: journeystepsイベント共通フィールド
description: journeystepsイベント共通フィールド
feature: ジャーニー
role: Business Practitioner
level: Intermediate
exl-id: 5cf8e6b5-2162-4aa3-b071-96ede31948e6
translation-type: tm+mt
source-git-commit: 8ab3951f9c97a0a964f5c123978ed256d3aedc45
workflow-type: tm+mt
source-wordcount: '582'
ht-degree: 1%

---

# journeystepsイベント共通フィールド{#sharing-common-fields}

このミックスインは、jearnyStepEventとjearnyStepProfileEventで共有されます。

[!DNL Journey Orchestration]がAdobe Experience Platformに送る一般的なXDMフィールドです。 共通フィールドは、ジャーニーで処理される各ステップに対して送信されます。 カスタムアクションやカスタムエンリッチメントには、より具体的なフィールドが使用されます。

これらのフィールドの一部は、特定の処理パターン（アクションの実行、データの取得など）でのみ使用できます。 イベントのサイズを制限するために、

## 入り口

ユーザーがジャーニーを入力したかどうかを示します。 存在しない場合、値はfalseとみなします。

タイプ：boolean

値：true/false

## 再入場

ユーザーが同じインスタンスでジャーニーを再入力したかどうかを示します。 存在しない場合、値はfalseとみなします。

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

ジャーニーのID。

タイプ：string

## jeurneyVersionID

ジャーニーバージョンのID。 このidは、jearnyStepEventの場合に、ジャーニーへのID参照を表します。

タイプ：string

## jeurneyVersionName

ジャーニーバージョンの名前。

タイプ：string

## jurneryVersion

ジャーニーのバージョン。

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

このジャーニーがテストモードになっているかどうかを示します。

タイプ：boolean

## processingTime

インスタンスステップが処理の開始から終了までの合計時間（ミリ秒）です。

タイプ：long

## instanceType

インスタンスタイプ（バッチまたは単一の場合）を示します。

タイプ：string

値：バッチ/単一

## recurrenceIndex

ジャーニーがバッチおよび定期的な場合の繰り返しのインデックス（最初の実行はrecurrenceIndex = 1）。

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
