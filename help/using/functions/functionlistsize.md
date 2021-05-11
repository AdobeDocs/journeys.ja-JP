---
product: adobe campaign
solution: Journey Orchestration
title: listSize
description: 関数listSizeについて説明します
feature: ジャーニー
role: Data Engineer
level: Experienced
exl-id: c0d34a8d-33e9-4c7b-9b7d-a1b21ed96d35
translation-type: tm+mt
source-git-commit: 8ab3951f9c97a0a964f5c123978ed256d3aedc45
workflow-type: tm+mt
source-wordcount: '46'
ht-degree: 34%

---

# listSize {#listSize}

リスト内の要素数を数えます。

## カテゴリ

リスト

## 関数の構文

`listSize(<parameters>)`

## パラメーター

| パラメーター | タイプ |
|-----------|------------------|
| リスト | listString |
| リスト | listBoolean |
| リスト | listInteger |
| リスト | listDecimal |
| リスト | listDuration |
| リスト | listDateTime |
| リスト | listDateTimeOnly |

## 署名と戻り値の型

`listSize(<listInteger>)`

`listSize(<listDecimal>)`

`listSize(<listString>)`

`listSize(<listBoolean>)`

`listSize(<listDateTimeOnly>)`

`listSize(<listDateTime>)`

`listSize(<listDuration>)`

`listSize(<listPoint>)`

整数を返します。

## 例

`listSize([10,2,3])`

3を返します。
