---
product: adobe campaign
title: シンプルなユースケースについて
description: ジャーニーのシンプルなユースケースの詳細を説明します
feature: Journeys
role: User
level: Intermediate
exl-id: 11858c7a-fdb3-43a4-af28-0d5c23fa2468
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
source-wordcount: '236'
ht-degree: 100%
---
# シンプルなユースケースについて{#concept_grh_vby_w2b}


>[!CAUTION]
>
>**Adobe Journey Optimizer をお探しですか**？ Journey Optimizer のドキュメントについて詳しくは、[こちら](https://experienceleague.adobe.com/ja/docs/journey-optimizer/using/ajo-home){target="_blank"}をクリックしてください。
>
>
>_このドキュメントは、Journey Optimizer に置き換えられた従来の Journey Orchestration 資料を参照しています。 Journey Orchestration または Journey Optimizer へのアクセスについてご質問がある場合は、アカウントチームにお問い合わせください。_


## 目的 {#purpose}

Marlton というホテルブランドの例を見てみましょう。 彼らのホテルでは、ロビー、客室階、レストラン、ジム、プールなどの全戦略エリアの近くにビーコン装置を配置しています。

このユースケースでは、スパの近くに配置されたビーコンの隣を歩く人に、リアルタイムでパーソナライズされたメッセージを送信する方法を見ていきます。

女性の場合に限りメッセージを送信し、 メッセージは、数秒以内に受信される必要があります。

![](../assets/journeyuc1_16.png)

## 前提条件 {#prerequisites}

このユースケースでは、Adobe Campaign Standard で 1 つの電子メールトランザクションメッセージテンプレートを設計しました。 ここでは、イベントのトランザクションメッセージテンプレートを使用します。 この[ページ](https://experienceleague.adobe.com/docs/campaign-standard/using/communication-channels/transactional-messaging/getting-started-with-transactional-msg.html?lang=ja)を参照してください。

Adobe Campaign Standard はメールを送信するように設定されています。

ビーコンの近くで検出された顧客の携帯電話から、イベントが送信されます。 このため、顧客の携帯電話から Mobile SDK にイベントを送信するモバイルアプリをデザインする必要があります。
