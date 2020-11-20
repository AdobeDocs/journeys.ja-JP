---
product: adobe campaign
solution: Journey Orchestration
title: inSegment
description: inSegment関数について説明します。
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '108'
ht-degree: 11%

---


# inSegment {#inSegment}

個々の人が特定のセグメントに属しているかどうかを確認します。

セグメント名は文字列定数である必要があります。 フィールド参照や式は使用できません。

セグメントは [Adobe Experience Platformで定義されます](https://platform.adobe.com/segment/overview)。 式エディターには、セグメントの自動入力リストが用意されています。

>[!NOTE]
>
>最大100個のセグメントを取得できます。

## カテゴリ

Adobe Experience Platform

## 関数の構文

`inSegment(<parameter>)`

## パラメーター

| パラメーター | 説明 | タイプ |
|--- |--- |--- |
| セグメント | セグメント名 | `<string>` |

## 署名と戻り値の型

`inSegment(<string>)`

ブール値を返します。

## 例

`inSegment("men over 50")`

説明：

この関数は、ジャーニーインスタンス内の個人が「men over 50」という名前のAdobe Experience Platformセグメントの一部である場合は **[!UICONTROL true]** 、それ以外の場合は **[!UICONTROL falseを返します]** 。
