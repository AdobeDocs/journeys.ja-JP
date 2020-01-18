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
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 54b54a64ad2822eec96008ac4a2e16c208a4a3ab

---


# 高度な使用例について{#concept_vzy_ncy_w2b}

## 目的 {#purpose}

マールトンというホテルブランドの例を見てみましょう 彼らのホテルでは、すべての戦略エリアの近くにビーコン装置を配置しています。ロビー、床、レストラン、ジム、プールなど

>[!NOTE]
>
>この使用例では、Adobe Campaign Standardを使用してメッセージを送信します。

この使用例では、特定のビーコンに近づいた顧客にリアルタイムでパーソナライズされたメッセージを送信する方法を見ていきます。

まず、マールトンのホテルに来たらすぐにメッセージを送りたい。 この24時間以内に連絡を受け取っていない場合にのみメッセージを送信します。

次に、2つの条件を確認します。

* このユーザーが忠誠度メンバーでない場合は、ロイヤルティメンバーシップオファーに参加するための電子メールを送信します。
* この人が既に忠誠度を持っている場合は、部屋の予約があるかどうかを確認します。
   * もし彼が居なければ、私たちは彼に部屋料金のプッシュ通知を送る。
   * もし彼がそうであれば、私たちは彼にウェルカムプッシュ通知を送ります。 6時間以内に店に入ったら食事割引のプッシュ通知を送ります

![](../assets/journeyuc2_29.png)

この使用例では、2つのイベントを作成する必要があります(を参照してく [](../usecase/configuring-the-events.md)ださい)。

* 顧客がホテルに入ったときにシステムにプッシュされるロビービーコンイベント。
* 顧客がレストランに入ったときにプッシュされるレストランビーコンイベント。

2つのデータソースへの接続を設定する必要があります(を参照してく [](../usecase/configuring-the-data-sources.md)ださい)。

* 組み込みのExperience Platformデータソース。2つの条件（忠誠度のメンバーシップと最終連絡日）の情報と、メッセージのパーソナライゼーション情報を取得します。
* ホテル予約システムは、予約状況情報を検索する。

## 前提条件 {#prerequisites}

使用例に応じて、3つのAdobe Campaign Standardトランザクションメッセージングテンプレートを設計しました。 イベントトランザクションメッセージングテンプレートを使用しています。 この[ページ](https://docs.adobe.com/content/help/en/campaign-standard/using/communication-channels/transactional-messaging/about-transactional-messaging.html)を参照してください。

Adobe Campaign Standardは、電子メールおよびプッシュ通知を送信するように設定されています。

Experience Cloud IDは、ホテルの予約システムで顧客を識別するためのキーとして使用されます。

イベントは、顧客の携帯電話がビーコンの近くで検出した場合に送信されます。 顧客の携帯電話からMobile SDKにイベントを送信するには、モバイルアプリケーションを設計する必要があります。

Loyalty memberフィールドはカスタムフィールドで、特定の組織IDに対してXDMに追加されました。
