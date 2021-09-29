---
product: adobe campaign
title: 交差
description: 関数の交差について説明します
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 19a4b7f8-5636-4b8f-b81f-28ff7da99671
source-git-commit: f2f5cc29f5079419662439f1cb1dee8fcb1b1ab9
workflow-type: tm+mt
source-wordcount: '79'
ht-degree: 10%

---

# 交差{#intersect}

2つの入力リストの共通値を返します。 2つのリストのいずれかがnullの場合、は空のリストを返します。

## カテゴリ

リスト

## 関数の構文

`intersect(<parameters>)`

## パラメーター

| パラメーター | タイプ |
|-----------|------------------|
| リスト1 | list |
| リスト2 | list |

## 署名と戻り値の型

`intersect(listString,listString)`:listString 
`intersect(listDecimal,listDecimal)`:listDecimal 
`intersect(listInteger,listInteger)`:listInteger 
`intersect(listDateTime,listDateTime)`:listDateTime 
`intersect(listDateTimeOnly,listDateTimeOnly)`:listDateTimeOnly 
`intersect(listDateOnly,listDateOnly)`:listDateOnly 
`intersect(listDuration,listDuration)`:listDuration 
`intersect(listBoolean,listBoolean)`:listBoolean

リストを返します。

## 例

```
intersect(
    ["sports", "news", "documentary"],
    ["sports", "movies", "documentary"]
)
```

[&quot;sports&quot;, &quot;news&quot;]を返します

```
intersect(
    #{ExperienceDataPlatform.profile.interests},
    ["sports", "news", "documentary"]
)
```

プロファイル属性とカテゴリのリストの間の共通項目を返します。

```
intersect(
        	#{ExperienceDataPlatform.profile.interests},
            @{myEvent.sport_interests}
)
```

プロファイル属性と指定されたイベントフィールドの間の共通項目を返します。