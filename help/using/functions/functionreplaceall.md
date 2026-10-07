---
product: adobe campaign
title: replaceAll
description: replaceAll 関数について説明します
feature: Journeys
role: Developer
level: Experienced
exl-id: d60059e5-6bf8-4a57-88a4-5323d5f0fa0b
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
source-wordcount: '105'
ht-degree: 100%
---
# replaceAll {#replaceAll}

ターゲット文字列に一致するすべての出現箇所をベース文字列内の置換文字列で置き換えます。

置換は、文字列の先頭から末尾に向かって行われます。例えば、文字列「aaa」の「aa」を「b」に置き換えると、「ab」ではなく「ba」になります。

## カテゴリ

文字列

## 関数の構文

`replaceAll(<parameters>)`

## パラメーター

| パラメーター | タイプ |
|-----------|--------------|
| base（ベース文字列） | 文字列 |
| target（ターゲット文字列） | 文字列（RegExp） |
| replacement（置換文字列） | 文字列 |

## シグネチャと戻り値のタイプ

`replaceAll(<baseString>,<sourceString>,<replacementString>)`

文字列を返します。

## 例{#example}

`replaceAll("Hello World", "l", "x")`

「Hexxo Worxd」を返します。

ターゲットパラメーターは RegExp なので、置き換える文字列に応じて、一部の文字をエスケープする必要が生じる場合があります。 例については、[このページ](../functions/functionreplace.md#example_2)を参照してください。
