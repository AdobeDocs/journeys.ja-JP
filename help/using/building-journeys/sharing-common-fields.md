---
product: adobe campaign
title: journeystepsイベントの共通フィールド
description: journeystepsイベントの共通フィールド
feature: ジャーニー
role: Business Practitioner
level: Intermediate
exl-id: 5cf8e6b5-2162-4aa3-b071-96ede31948e6
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '582'
ht-degree: 1%

---

# journeystepsイベントの共通フィールド{#sharing-common-fields}

このmixinは、 journeyStepEventとjourneyStepProfileEventによって共有されます。

これらは、[!DNL Journey Orchestration]がAdobe Experience Platformに送信する一般的なXDMフィールドです。 共通のフィールドは、ジャーニーで処理される各ステップに対して送信されます。 より具体的なフィールドは、カスタムアクションやエンリッチメントに使用されます。

これらのフィールドの一部は、特定の処理パターン（アクションの実行、データ取得など）でのみ使用できます。 を設定します。

## エントリ

ユーザーがジャーニーに入ったかどうかを示します。 存在しない場合、値はfalseと見なされます。

型：boolean

値：true/false

## 再入場

ユーザーが同じインスタンスでジャーニーに再度入ったかどうかを示します。 存在しない場合、値はfalseと見なされます。

型：boolean

値：true/false

## instanceEnded

インスタンスが終了した（成功したかどうか）を示します。

型：boolean

## eventID

処理中のイベントID（ステップ処理用）。 イベントが外部のイベントの場合、値はそのeventIdになります。 イベントが内部イベントの場合、値は内部イベントID（scheduledNotificationReceived、executedActionなど）です。

型：文字列

## nodeID

（キャンバスからの）クライアントノードID。

型：文字列

## stepID

現在処理中のステップを表す一意のIDです。

型：文字列

## stepName

現在処理中のステップの名前。

型：文字列

## stepType

ステップのタイプ。

型：文字列

可能な値：

* 条件
* アクション
* スケジューラー
* タイマー

## stepStatus

ステップのステータス。処理が完了したときのステップのステータスを表します（およびステップイベントが発生しました）。

型：文字列

ステータスは次のとおりです。

* 終了：ステップにトランジションがなく、処理が正常に終了しました。
* エラー：ステップ処理でエラーが発生しました。
* トランジション：ステップは、イベントが別のステップに移るのを待っています。
* capped:アクションまたはエンリッチメント中に発生した、キャッピングエラーで手順が失敗しました。
* timedout:ステップがタイムアウトエラーで失敗し、アクションまたはエンリッチメント中に発生しました。
* instanceTimedout:インスタンスがタイムアウトに達したので、ステップは処理を停止しました。

## journeyID

ジャーニーのID。

型：文字列

## journeyVersionID

ジャーニーのバージョンのID。 このIDは、 journeyStepEventの場合、ジャーニーへのID参照を表します。

型：文字列

## journeyVersionName

ジャーニーのバージョンの名前。

型：文字列

## journeyVersion

ジャーニーのバージョン。

型：文字列

## instanceID

ジャーニーインスタンスの内部ID。

型：文字列

## externalKey

イベントから抽出され、処理する外部キー。

型：文字列

## parentStepID

インスタンス内の現在処理されたステップの親のステップID。

型：文字列

## parentStepName

現在のステップの親のステップ名。

型：文字列

## parentTransitionID

処理済みの手順にインスタンスを導いたトランジションのID。

型：文字列

## parentTransitionName

処理済みのステップにインスタンスを導いたトランジションの名前。

型：文字列

## inTest

このジャーニーがテストモードかどうかを示します。

型：boolean

## processingTime

インスタンスステップが開始してから処理の終了までの合計時間（ミリ秒）。

型：long

## instanceType

インスタンスタイプ（バッチの場合）または単一の場合)を示します。

型：文字列

値：バッチ/単一

## recurrenceIndex

ジャーニーがバッチで繰り返しの場合の繰り返しのインデックス（最初の実行はrecurrenceIndex = 1）。

型：long

## isBatchToUnitary

この単一インスタンスがバッチインスタンスからトリガーされたかどうかを示します。

型：boolean

## batchExternalKey

バッチイベントの外部キー。

型：文字列

## batchInstanceID

これはバッチインスタンスIDです。

型：文字列

## batchUnitaryBranchID

インスタンスがバッチインスタンスからトリガーされた場合は、単一のブランチID。

型：文字列
