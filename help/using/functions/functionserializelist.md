---
product: adobe campaign
title: serializeList
description: serializeList関数の詳細
feature: ジャーニー
role: Data Engineer
level: Experienced
exl-id: 84912d38-32ee-4cfe-8cb4-bad12f9c52af
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '87'
ht-degree: 22%

---

# serializeList {#serializeList}

最初のパラメーターで指定されたリスト（任意の型）を文字列に変換します。 2番目のパラメーターは、使用する区切り文字を表します。 3番目のパラメーターは、式の各要素に引用符を含める必要があるかどうかを示すブール値です。

## カテゴリ

リスト

## 関数の構文

`serializeList(<parameters>)`

## パラメーター

| パラメーター | タイプ |
|-----------|------------------|
| 文字列 | 文字列 |
| Boolean | Boolean |
| DateTimeOnly | DateTimeOnly |
| リスト | listString |
| リスト | listBoolean |
| リスト | listPoint |
| リスト | listDecimal |
| リスト | listDuration |
| リスト | listDateTime |
| リスト | listDateTimeOnly |

## 署名と戻り値の型

`serializeList(<listInteger>,<string>,<boolean>)`

`serializeList(<listDecimal>,<string>,<boolean>)`

`serializeList(<listString>,<string>,<boolean>)`

`serializeList(<listBoolean>,<string>,<boolean>)`

`serializeList(<listDateTimeOnly>,<string>,<boolean>)`

`serializeList(<listDateTime>,<string>,<boolean>)`

`serializeList(<listDuration>,<string>,<boolean>)`

`serializeList(<listPoint>,<string>,<boolean>)`

文字列を返します。

## 例

`serializeList(["Hello","World"], " ", false)`

「Hello World」を返します。

`serializeList(["Hello", "World"], ",", true)`

&quot;&quot;Hello&quot;,&quot;World&quot;&quot;を返します。
