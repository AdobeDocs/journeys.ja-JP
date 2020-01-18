---
title: 簡単な使用例について
description: 簡単な使用事例をより活用
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 54b54a64ad2822eec96008ac4a2e16c208a4a3ab

---


# 簡単な使用例について{#concept_grh_vby_w2b}

## 目的 {#purpose}

マールトンというホテルブランドの例を見てみましょう 彼らのホテルでは、すべての戦略エリアの近くにビーコン装置を配置しています。ロビー、床、レストラン、ジム、プールなど

この使用例では、スパの近くに配置されたビーコンの隣を歩く人に、リアルタイムでパーソナライズされたメッセージを送信する方法を確認します。

私たちはその人が女性の場合にのみメッセージを送りたい。 メッセージは、数秒以内に受信する必要があります。

![](../assets/journeyuc1_16.png)

## 前提条件 {#prerequisites}

使用例に応じて、Adobe Campaign Standardで1つの電子メールトランザクションメッセージングテンプレートを設計しました。 イベントトランザクションメッセージングテンプレートを使用しています。 この[ページ](https://docs.adobe.com/content/help/en/campaign-standard/using/communication-channels/transactional-messaging/about-transactional-messaging.html)を参照してください。

Adobe Campaign Standardは電子メールを送信するように設定されています。

イベントは、顧客の携帯電話がビーコンの近くで検出されると送信されます。 顧客の携帯電話からMobile SDKにイベントを送信するには、モバイルアプリケーションを設計する必要があります。