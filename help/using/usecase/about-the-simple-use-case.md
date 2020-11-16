---
title: シンプルなユースケースについて
description: ジャーニーのシンプルなユースケースの詳細を説明します
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: ht
source-git-commit: b852c08a488a1bec02b8b31a1fccf1a8773b99af
workflow-type: ht
source-wordcount: '175'
ht-degree: 100%

---


# シンプルなユースケースについて{#concept_grh_vby_w2b}

## 目的 {#purpose}

Marlton というホテルブランドの例を見てみましょう。彼らのホテルでは、ロビー、客室階、レストラン、ジム、プールなどの全戦略エリアの近くにビーコン装置を配置しています。

このユースケースでは、スパの近くに配置されたビーコンの隣を歩く人に、リアルタイムでパーソナライズされたメッセージを送信する方法を見ていきます。

女性の場合に限りメッセージを送信し、メッセージは、数秒以内に受信される必要があります。

![](../assets/journeyuc1_16.png)

## 前提条件 {#prerequisites}

このユースケースでは、Adobe Campaign Standard で 1 つの E メールトランザクションメッセージテンプレートを設計しました。イベントトランザクションメッセージテンプレートを使用します。この[ページ](https://docs.adobe.com/content/help/ja-JP/campaign-standard/using/communication-channels/transactional-messaging/about-transactional-messaging.html)を参照してください。

Adobe Campaign Standard は E メールを送信するように設定されています。

ビーコンの近くで検出された顧客の携帯電話から、イベントが送信されます。顧客の携帯電話から Mobile SDK にイベントを送信するモバイルアプリをデザインする必要があります。