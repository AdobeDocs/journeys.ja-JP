---
product: adobe campaign
title: intersect
description: intersect 関数について説明します
feature: Journeys
role: Developer
level: Experienced
exl-id: 19a4b7f8-5636-4b8f-b81f-28ff7da99671
source-git-commit: d3de66b9b28efa2636f5c0fd5a0d7ccb6132dbdd
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# intersect{#intersect}

2 つの入力リストで共通する値を返します。2 つのリストのいずれかが null の場合、空のリストを返します。

## カテゴリ

リスト

## 関数の構文

`intersect(<parameters>)`

## パラメーター

| パラメーター | タイプ |
|-----------|------------------|
| リスト 1 | リスト |
| リスト 2 | リスト |

## シグネチャと戻り値のタイプ

`intersect(listString,listString)`：listString
`intersect(listDecimal,listDecimal)`：listDecimal
`intersect(listInteger,listInteger)`：listInteger
`intersect(listDateTime,listDateTime)`：listDateTime
`intersect(listDateTimeOnly,listDateTimeOnly)`：listDateTimeOnly
`intersect(listDateOnly,listDateOnly)`：listDateOnly
`intersect(listDuration,listDuration)`：listDuration
`intersect(listBoolean,listBoolean)`：listBoolean

リストを返します。

## 例

```json
intersect(
    ["sports", "news", "documentary"],
    ["sports", "movies", "documentary"]
)
```

[&quot;sports&quot;, &quot;news&quot;] を返します。

```json
intersect(
    #{ExperienceDataPlatform.profile.interests},
    ["sports", "news", "documentary"]
)
```

プロファイル属性と指定されたカテゴリリストの間の共通項目を返します。

```json
intersect(
    #{ExperienceDataPlatform.profile.interests},
        @{myEvent.sport_interests}
)
```

プロファイル属性と指定されたイベントフィールドの間の共通項目を返します。
