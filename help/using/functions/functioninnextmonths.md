---
title: inNextMonths
description: 関数inNextMonthsについて説明します。
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: d6360d616199d597255610959432c7b93fd4e25c

---


# inNextMonths {#inNextMonths}

渡された日付またはdateTimeが現在から現在+差分か月の間にある場合、trueを返します。

## カテゴリ

日付

## 関数の構文

`inNextMonths(<dateTime>,<delta>)`

## パラメーター

| パラメーター | タイプ |
|-----------|------------------|
| 日時 | dateTime |
| デルタ | 整数 |

## 署名と戻り値の型

`inNextMonths(<dateTime>,<integer>)`

ブール値を返します。

## 例

`inNextMonths(toDateTime('2020-01-12T01:11:00Z'), 4))`

trueを返します。
