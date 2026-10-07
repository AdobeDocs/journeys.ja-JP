---
product: adobe campaign
title: serializeList
description: serializeList 関数について説明します
feature: Journeys
role: Developer
level: Experienced
exl-id: 84912d38-32ee-4cfe-8cb4-bad12f9c52af
product_v2:
  - id: cf67d108-ecf9-4fde-af49-3a3c39083bc8
    internal-label: Journey Orchestration
feature_v2:
  - id: 7de3230f-9523-5ba5-8d5c-2313288b27ef
    internal-label: Journeys
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: 255cd6677e7c9ebff63ea9a1028a042c19e63ecc
workflow-type: tm+mt
source-wordcount: '88'
ht-degree: 100%
---
# serializeList {#serializeList}

最初のパラメーターで指定されたリスト（任意のタイプ）を文字列に変換します。 2 番目のパラメーターは、使用する区切り記号を表します。 3 番目のパラメーターは、式の各要素に引用符を含めるかどうかを示すブール値です。

## カテゴリ

リスト

## 関数の構文

`serializeList(<parameters>)`

## パラメーター

| パラメーター | タイプ |
|-----------|------------------|
| 文字列 | 文字列 |
| ブール | ブール |
| 日時のみ | 日時のみ |
| リスト | listString |
| リスト | listBoolean |
| リスト | listPoint |
| リスト | listDecimal |
| リスト | listDuration |
| リスト | listDateTime |
| リスト | listDateTimeOnly |
| リスト | listDateOnly |

## シグネチャと戻り値のタイプ

`serializeList(<listInteger>,<string>,<boolean>)`

`serializeList(<listDecimal>,<string>,<boolean>)`

`serializeList(<listString>,<string>,<boolean>)`

`serializeList(<listBoolean>,<string>,<boolean>)`

`serializeList(<listDateTimeOnly>,<string>,<boolean>)`

`serializeList(<listDateTime>,<string>,<boolean>)`

`serializeList(<listDateOnly>,<string>,<boolean>)`

`serializeList(<listDuration>,<string>,<boolean>)`

`serializeList(<listPoint>,<string>,<boolean>)`

文字列を返します。

## 例

`serializeList(["Hello","World"], " ", false)`

「Hello World」を返します。

`serializeList(["Hello", "World"], ",", true)`

「&amp;quot;Hello&amp;quot;,&amp;quot;World&amp;quot;」を返します。
