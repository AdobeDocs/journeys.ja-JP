---
title: シンプルな使用例について
description: 簡単な使用事例の幅を広げる
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: tm+mt
source-git-commit: b852c08a488a1bec02b8b31a1fccf1a8773b99af
workflow-type: tm+mt
source-wordcount: '175'
ht-degree: 14%

---


# シンプルな使用例について{#concept_grh_vby_w2b}

## 目的 {#purpose}

マールトンというホテルブランドの例を見てみましょう 彼らのホテルでは、ビーコン装置を全戦略エリアの近くに配置している。ロビー、床、レストラン、ジム、プールなど

この使用事例では、スパの近くに配置されたビーコンの隣を歩く人に、リアルタイムでパーソナライズされたメッセージを送信する方法を見ていきます。

女性の場合に限りメッセージを送りたい。 メッセージは、数秒以内に受信する必要があります。

![](../assets/journeyuc1_16.png)

## 前提条件 {#prerequisites}

使用事例では、Adobe Campaign Standardで1つの電子メールトランザクションメッセージングテンプレートを設計しました。 イベントトランザクションメッセージングテンプレートを使用しています。 この[ページ](https://docs.adobe.com/content/help/ja-JP/campaign-standard/using/communication-channels/transactional-messaging/about-transactional-messaging.html)を参照してください。

Adobe Campaign Standardは電子メールを送信するように設定されています。

イベントは、ビーコンの近くで検出された場合に、顧客の携帯電話から送信されます。 顧客の携帯電話からMobile SDKにイベントを送信するモバイルアプリをデザインする必要があります。