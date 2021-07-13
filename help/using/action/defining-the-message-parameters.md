---
product: adobe campaign
title: メッセージパラメーターの定義
description: メッセージパラメーターの定義方法を説明します
feature: ジャーニー
role: User
level: Intermediate
exl-id: ea9cdb1d-dde6-4080-8f35-7f8cd3cf3644
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '222'
ht-degree: 96%

---

# メッセージパラメーターの定義 {#concept_wy4_bf1_2gb}

![](../assets/messageparameterssection.png)

「**[!UICONTROL メッセージパラメーター]**」セクションに、外部サービスに送信する JSON ペイロードの例を貼り付けます。

![](../assets/customactionpayloadmessage.png)

>[!NOTE]
>
>ペイロード内のフィールド名に「。」文字を含めることはできません。

パラメーターのタイプ（例：文字列、整数など）を定義できます。

また、パラメーターが定数か変数かを指定することもできます。

* 「定数」は、パラメーターの値が、技術担当者によって「アクション設定」ウィンドウで定義されることを意味します。この値は、ジャーニーをまたいで常に同じになります。ジャーニーでカスタムアクションを使用する場合、この値は変わらず、マーケターには表示されません。例えば、サードパーティのシステムが予期する ID を指定できます。この場合、「定数／変数」トグルの右側にあるフィールドの値が渡されます。
* 変数は、パラメーターの値が変化することを意味します。ジャーニーでこのカスタムアクションを使用するマーケターは、必要な値を渡したり、このパラメーターの値を受け取る場所（例：イベント、Adobe Experience Platform など）を指定したりできます。この場合、「定数／変数」トグルの右側にあるフィールドは、ジャーニーでマーケターがこのパラメーターに名前を付ける際に表示されるラベルです。

![](../assets/customactionpayloadmessage2.png)
