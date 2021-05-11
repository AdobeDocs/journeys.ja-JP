---
product: adobe campaign
solution: Journey Orchestration
title: シンプルなユースケースについて
description: ジャーニーのシンプルなユースケースの詳細を説明します
feature: ジャーニー
role: Business Practitioner
level: Intermediate
exl-id: 11858c7a-fdb3-43a4-af28-0d5c23fa2468
translation-type: tm+mt
source-git-commit: 8ab3951f9c97a0a964f5c123978ed256d3aedc45
workflow-type: tm+mt
source-wordcount: '176'
ht-degree: 100%

---

# シンプルなユースケースについて{#concept_grh_vby_w2b}

## 目的 {#purpose}

Marlton というホテルブランドの例を見てみましょう。彼らのホテルでは、ロビー、客室階、レストラン、ジム、プールなどの全戦略エリアの近くにビーコン装置を配置しています。

このユースケースでは、スパの近くに配置されたビーコンの隣を歩く人に、リアルタイムでパーソナライズされたメッセージを送信する方法を見ていきます。

女性の場合に限りメッセージを送信し、メッセージは、数秒以内に受信される必要があります。

![](../assets/journeyuc1_16.png)

## 前提条件 {#prerequisites}

このユースケースでは、Adobe Campaign Standard で 1 つの電子メールトランザクションメッセージテンプレートを設計しました。イベントトランザクションメッセージテンプレートを使用します。この[ページ](https://docs.adobe.com/content/help/ja-JP/campaign-standard/using/communication-channels/transactional-messaging/about-transactional-messaging.html)を参照してください。

Adobe Campaign Standard は E メールを送信するように設定されています。

ビーコンの近くで検出された顧客の携帯電話から、イベントが送信されます。顧客の携帯電話から Mobile SDK にイベントを送信するモバイルアプリをデザインする必要があります。
