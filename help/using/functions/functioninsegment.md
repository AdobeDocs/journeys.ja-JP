---
product: adobe campaign
title: inSegment
description: inSegmentの関数について説明します。
feature: ジャーニー
role: Data Engineer
level: Experienced
exl-id: 7f756ec5-d787-4024-aaf8-5b4f1d4ddece
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '152'
ht-degree: 25%

---

# inSegment {#inSegment}

個人が特定のセグメントに属しているかどうかを確認します。

>[!NOTE]
>
>最大100個のセグメントを取得できます。

セグメント名は、文字列定数にする必要があります。 フィールド参照や式は使用できません。

セグメントは[Adobe Experience Platform](https://platform.adobe.com/segment/overview)で定義されます。 式エディターには、自動入力されたセグメントのリストが表示されます。

>[!NOTE]
>
>セグメントのメンバーとして考慮されるのは、**認識済み**&#x200B;および&#x200B;**既存の**&#x200B;セグメントパーティシペーションステータスを持つ個人のみです。 セグメントの評価方法について詳しくは、[Segmentation Service ドキュメント](https://experienceleague.adobe.com/docs/experience-platform/segmentation/tutorials/evaluate-a-segment.html?lang=ja#interpret-segment-results)を参照してください。

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

説明:

ジャーニーインスタンス内の個人が「men over 50」という名前のAdobe Experience Platformセグメントの一部である場合、**[!UICONTROL true]**&#x200B;を返し、それ以外の場合は&#x200B;**[!UICONTROL false]**&#x200B;を返します。
