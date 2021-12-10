---
title: ステップイベントフィールドの一覧
description: ステップイベントフィールドの一覧
feature: Journeys
topic: Content Management
role: User
level: Intermediate
exl-id: 177b4a97-c757-40ca-a190-fbd88169e5e2
source-git-commit: 4291dfc91c2fb29d294416ceed022ee00842c870
workflow-type: tm+mt
source-wordcount: '306'
ht-degree: 100%

---

# ステップイベントフィールドの一覧 {#sharing-field-list}

ステップイベントフィールドはカテゴリ別に整理されています。

* デバッグ情報フィールド
* ジャーニーフィールド
* プロファイルフィールド
* サービスイベントフィールド

## debugInfo

| フィールド名 | タイプ | 説明 |
|---|---|------------|
| requestId | 文字列 | リクエストのフローを追跡するために Journey Orchestration で使用されるリクエスト ID です。 |

## journey

このフィールドグループは、ジャーニーのスキーマで（journeyStepEvent と関連して）使用します。次のフィールドが含まれています。

| フィールド名 | タイプ | 説明 |
|---|---|------------|
| ID | 文字列 | 指定されたジャーニーの識別子 |
| VersionID | 文字列 | ジャーニーバージョンの ID。この ID はジャーニーの ID を表します。 |
| name | 文字列 | ジャーニーの名前 |
| description | 文字列 | ジャーニーの説明 |
| version | 文字列 | バージョン（`major`.`minor` のように表されます） |

## profile

このフィールドグループは、journeyStepEvent に固有のものです。このイベントはジャーニーと関連しており、identityMap を持たず、存在する場合はプロファイル ID を示しています。

journeyStepEvent の場合、ID に関連するフィールドも追加する必要があります。

| フィールド名 | タイプ | 説明 |
|---|---|------------|
| ID | 文字列 | プロファイル識別子は、ジャーニーで送信／使用されたプロファイルを識別します。例：foo@adobe.com |
| namespace | 文字列 | このフィールドは、ジャーニーで使用されるプロファイルで参照される名前空間を記述します。例：Email、ECID |

## serviceEvents

この Mixin には、プロファイルエクスポートジョブに対応するすべてのフィールドが含まれています。

| フィールド名 | タイプ | 説明 |
|---|---|------------|
| ID | 文字列 | トリガーされたセグメントエクスポートジョブの識別子 |
| status | 文字列 | セグメントエクスポートジョブのステータス：待機中、開始済み、終了 |
| exportCountTotal | 整数 | セグメントエクスポートジョブの可能な最大値 |
| exportCountRealized | 整数 | ジョブを通じてエクスポートされたセグメントの実際の数 |
| exportCountFailed | 整数 | ジョブを通じたエクスポート中に失敗したセグメントの数 |
| exportSegmentID | 文字列 | エクスポートするセグメントの識別子 |
| eventType | 文字列 | エラーイベントか情報イベントかを示すイベントタイプ：Info、Error |
| eventCode | 文字列 | 対応する eventType の理由を示すエラーコード |

## stepEvents

このカテゴリには、元のステップイベントフィールドが含まれます。この[節](../building-journeys/sharing-legacy-fields.md)を参照してください。
