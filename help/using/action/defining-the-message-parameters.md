---
product: adobe campaign
solution: Journey Orchestration
title: メッセージパラメーターの定義
description: メッセージパラメーターの定義方法を学びます
feature: ジャーニー
role: Business Practitioner
level: Intermediate
exl-id: ea9cdb1d-dde6-4080-8f35-7f8cd3cf3644
translation-type: tm+mt
source-git-commit: 8ab3951f9c97a0a964f5c123978ed256d3aedc45
workflow-type: tm+mt
source-wordcount: '213'
ht-degree: 4%

---

# メッセージパラメーターの定義 {#concept_wy4_bf1_2gb}

![](../assets/messageparameterssection.png)

**[!UICONTROL Message parameters]**&#x200B;セクションに、外部サービスに送信するJSONペイロードの例を貼り付けます。

![](../assets/customactionpayloadmessage.png)

パラメーターのタイプを定義できます(例：文字列、整数など)。

また、パラメーターが定数か変数かを指定することもできます。

* 「定数」は、パラメーターの値が、アクション設定ウィンドウで技術的な人物によって定義されることを意味します。 この値は、ジャーニー間で常に同じになります。 ジャーニーでカスタムアクションを使用する場合、この値は変わらず、マーケティング担当者には表示されません。 例えば、サードパーティのシステムが予期するIDを指定できます。 この場合、トグル定数/変数の右側にあるフィールドが渡される値です。
* 変数は、パラメーターの値が変化することを意味します。 ジャーニーでこのカスタムアクションを使用するマーケターは、自由に、必要な値を渡したり、このイベントーの値を取得する場所を指定したりできます(例：パラメーター、Adobe Experience Platformなど)。 この場合、トグル定数/変数の右側にあるフィールドが、ジャーニーーに表示されるラベルで、このパラメーターに名前を付けます。

![](../assets/customactionpayloadmessage2.png)
