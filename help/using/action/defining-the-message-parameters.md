---
product: adobe campaign
title: アクションパラメーターの定義
description: アクションパラメーターの定義方法を説明します
feature: Journeys
role: User
level: Intermediate
exl-id: ea9cdb1d-dde6-4080-8f35-7f8cd3cf3644
product_v2:
  - id: cf67d108-ecf9-4fde-af49-3a3c39083bc8
    internal-label: Journey Orchestration
feature_v2:
  - id: 7de3230f-9523-5ba5-8d5c-2313288b27ef
    internal-label: Journeys
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
source-git-commit: 255cd6677e7c9ebff63ea9a1028a042c19e63ecc
workflow-type: tm+mt
source-wordcount: '281'
ht-degree: 97%
---
# アクションパラメーターの定義 {#concept_wy4_bf1_2gb}


>[!CAUTION]
>
>**Adobe Journey Optimizer をお探しですか**？ Journey Optimizer のドキュメントについて詳しくは、[こちら](https://experienceleague.adobe.com/ja/docs/journey-optimizer/using/ajo-home){target="_blank"}をクリックしてください。
>
>
>_このドキュメントは、Journey Optimizer に置き換えられた従来の Journey Orchestration 資料を参照しています。 Journey Orchestration または Journey Optimizer へのアクセスについてご質問がある場合は、アカウントチームにお問い合わせください。_


![](../assets/messageparameterssection.png)

「**[!UICONTROL アクションパラメーター]**」セクションに、外部サービスに送信する JSON ペイロードの例を貼り付けます。

![](../assets/customactionpayloadmessage.png)

>[!NOTE]
>
>ペイロード内のフィールド名に「.」を含めることはできません。 文字。 文字「$」で始めることはできません。

パラメーターのタイプ（例：文字列、整数など）を定義できます。

また、パラメーターが定数か変数かを指定することもできます。

* 「定数」は、パラメーターの値が、技術担当者によって「アクション設定」ペインで定義されることを意味します。 この値は、ジャーニーをまたいで常に同じになります。 ジャーニーでカスタムアクションを使用する場合、この値は変わらず、マーケターには表示されません。 例えば、サードパーティのシステムが予期する ID を指定できます。 この場合、「定数／変数」切替スイッチの右側にあるフィールドの値が渡されます。
* 変数は、パラメーターの値が変化することを意味します。 ジャーニーでこのカスタムアクションを使用するマーケターは、必要な値を渡したり、このパラメーターの値を取得する場所（例：イベント、Adobe Experience Platform など）を指定したりできます。 この場合、「定数／変数」切替スイッチの右側にあるフィールドは、ジャーニーでマーケターがこのパラメーターに名前を付ける際に表示されるラベルです。

![](../assets/customactionpayloadmessage2.png)
