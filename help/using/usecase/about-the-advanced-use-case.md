---
title: 高度な使用例について
description: 高度な使用事例の詳細
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: tm+mt
source-git-commit: bcb8a71a27e2b9e37af7d0260cec04ed0fda24ee
workflow-type: tm+mt
source-wordcount: '418'
ht-degree: 6%

---


# 高度な使用例について{#concept_vzy_ncy_w2b}

## 目的 {#purpose}

マールトンというホテルブランドの例を見てみましょう 彼らのホテルでは、ビーコン装置を全戦略エリアの近くに配置している。ロビー、床、レストラン、ジム、プールなど

>[!NOTE]
>
>この場合、Adobe Campaign Standardを使用してメッセージを送信します。

この使用事例では、訪問者が特定のビーコンの近くを歩いたときに、リアルタイムでパーソナライズされたメッセージを送信する方法を見ていきます。

まず、マールトンのホテルに入るとすぐにメッセージを送りたい。 この24時間以内に連絡がなかった場合にのみメッセージを送信します。

次に、2つの条件を確認します。

* このユーザーが忠誠度メンバーでない場合は、ロイヤルティメンバーシップオファーに参加するための電子メールを送信します。
* この人が既に忠誠度のあるメンバーである場合は、部屋の予約があるかどうかを確認します。
   * もし彼が来なかったら、私たちは彼に部屋料金のプッシュ通知を送る。
   * もし彼がそうなら、私たちは彼に歓迎のプッシュ通知を送る。 そして、彼が6時間以内にレストランに入ったら、私たちは彼に食事の割引のあるプッシュ通知を送る。

![](../assets/journeyuc2_29.png)

この使用例では、2つのイベントを作成する必要があります( [このページを参照](../usecase/configuring-the-events.md))。

* 客がホテルに入るとシステムにプッシュされるロビービーコンイベント。
* 顧客がレストランに入るとプッシュされるレストランビーコンイベント。

2つのデータソースへの接続を設定する必要があります( [このページを参照](../usecase/configuring-the-data-sources.md))。

* 組み込みのAdobe Experience Platformデータソース。2つの条件（忠誠度のメンバーシップと最終連絡先の日付）の情報と、メッセージのパーソナライズ情報を取得します。
* ホテル予約システムは、予約状況情報を検索する。

## 前提条件 {#prerequisites}

使用事例では、Adobe Campaign Standardのトランザクションメッセージングテンプレートを3つ設計しました。 イベントのトランザクションメッセージングテンプレートを使用しています。 この[ページ](https://docs.adobe.com/content/help/ja-JP/campaign-standard/using/communication-channels/transactional-messaging/about-transactional-messaging.html)を参照してください。

Adobe Campaign Standardは、電子メールおよびプッシュ通知を送信するように設定されています。

Experience CloudIDは、ホテル予約システムで顧客を識別するためのキーとして使用されます。

イベントは、ビーコンの近くで検出されると、顧客の携帯電話から送信されます。 顧客の携帯電話からMobile SDKにイベントを送信するモバイルアプリをデザインする必要があります。

Loyalty memberフィールドは、カスタムフィールドで、特定の組織IDに対してXDMに追加されました。
