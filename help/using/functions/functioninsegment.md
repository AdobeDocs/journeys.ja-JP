---
product: adobe campaign
title: inSegment
description: inSegment 関数について説明します
feature: Journeys
role: Developer
level: Experienced
exl-id: 7f756ec5-d787-4024-aaf8-5b4f1d4ddece
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
source-wordcount: '204'
ht-degree: 100%
---
# inSegment {#inSegment}

個人が特定のセグメントに属しているかどうかを確認します。

>[!NOTE]
>
>最大 100 個のセグメントを取得できます。

セグメント名は、文字列定数である必要があります。 フィールド参照や式は使用できません。

セグメントは [Adobe Experience Platform](https://platform.adobe.com/segment/overview) で定義されます。 式エディターには、自動入力されたセグメントリストが表示されます。

セグメントには次の 3 つのステータスがあります。

* 既存：エンティティが引き続きセグメント内に存在します。
* 実現：エンティティがセグメントにエントリします。
* 離脱：エンティティがセグメントから離脱します。

セグメント参加ステータスが&#x200B;**実現**&#x200B;と&#x200B;**既存**&#x200B;の個人のみが、セグメントのメンバーと見なされます。 セグメントの評価方法について詳しくは、[セグメント化サービスのドキュメント](https://experienceleague.adobe.com/docs/experience-platform/segmentation/tutorials/evaluate-a-segment.html?lang=ja#interpret-segment-results)を参照してください。

`IF inSegment('segmentName') == true` は、セグメントメンバーシップがエントリまたは既存のステータスになっていることを意味します。

`ELSE inSegment('segmentName') == false` は、離脱ステータスのセグメントメンバーシップがあることを意味します。

## カテゴリ

Adobe Experience Platform

## 関数の構文

`inSegment(<parameter>)`

## パラメーター

| パラメーター | 説明 | タイプ |
|--- |--- |--- |
| セグメント | セグメント名 | `<string>` |

## シグネチャと戻り値のタイプ

`inSegment(<string>)`

ブール値を返します。

## 例

`inSegment("men over 50")`

説明：

ジャーニーインスタンス内の個人が「men over 50」という名前の Adobe Experience Platform セグメントに属している場合、この関数は **[!UICONTROL true]** を返します。それ以外の場合は **[!UICONTROL false]** を返します。
