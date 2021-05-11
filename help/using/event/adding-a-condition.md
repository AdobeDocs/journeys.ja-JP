---
product: adobe campaign
solution: Journey Orchestration
title: 条件の追加
description: 条件を追加する方法を説明します。
feature: ジャーニー
role: Business Practitioner
level: Intermediate
exl-id: 09cda689-6953-4ea6-a446-cb4e1d8ad8e4
translation-type: tm+mt
source-git-commit: 8ab3951f9c97a0a964f5c123978ed256d3aedc45
workflow-type: tm+mt
source-wordcount: '206'
ht-degree: 4%

---

# 条件の追加 {#concept_rbg_gqt_52b}

システム生成イベントの場合、イベント条件を定義して、イベントの処理をフィルタリングできます。 条件がtrueの場合、イベントが処理されます。 条件がtrueでない場合、イベントは無視されます。

イベントの条件は、イベントペイロードで渡されたデータに基づく場合にのみ指定できます。 イベントレベルで定義された条件は、マーケターがキャンバス上で変更することはできません。 このイベントを使用する際に、この条件を強化する必要があります。 例えば、買い物かごの値が小さすぎる場合に買い物かごの放棄イベントをマーケターが使用したくない場合、「買い物かごの値」イベントフィールドに条件を作成し、100ドルを超える値を課すことができます。

イベントに条件を設定するには、単純な式エディターまたは高度な式エディターを使用します。 [このページ](../expression/expressionadvanced.md)を参照してください。

例えば、特定のイベントタイプのイベントのみを処理し、他のタイプは無視する条件を定義できます。 または、イベントが買い物かご放棄で、ペイロードに買い物かご値フィールドが含まれている場合、買い物かご値が100ドルを超える場合にのみイベントを処理するイベント条件を定義できます。

![](../assets/journey78.png)
