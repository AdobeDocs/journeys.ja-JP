---
title: 反応イベント
description: 反応のイベントについて学ぶ
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
source-git-commit: 2b44cd9db7732c5e272b69e2583a5f81b4580d11
workflow-type: tm+mt
source-wordcount: '409'
ht-degree: 0%

---


# 反応イベント {#section_dhx_gss_dgb}

パレットに用意されている様々なイベントアクティビティの中には、組み込みの **[!UICONTROL Reactions]** イベントがあります。 このアクティビティにより、電子メール、SMS、またはプッシュアクティビティと共に送信されるメッセージに関連する追跡データに同じ遍歴内で対応できます。 この情報は、Adobe Campaign Standardでのトランザクションメッセージングから得られます。 この情報は、Adobe Experience Platformと共有された時点でリアルタイムに取り込まれます。 プッシュ通知では、クリック、送信または失敗したメッセージに対応できます。 SMSメッセージの場合、送信されたメッセージや失敗したメッセージに対して反応を示すことができます。 電子メールの場合、クリック、送信、開いたメッセージ、失敗したメッセージに対応できます。

このメカニズムを使用して、メッセージに対する反応がない場合にアクションを実行することもできます。 これを行うには、リアクションアクティビティに平行な第2のパスを作成し、待機アクティビティを追加します。 待機アクティビティで定義された期間中に反応がない場合は、2番目のパスが選択されます。 例えば、フォローアップメッセージを送信することができます。

キャンバスには、以前に電子メール、プッシュ、またはSMSアクティビティがある場合にのみ、リアクションアクティビティを使用できます。

See [About action activities](../building-journeys/about-action-activities.md).

![](../assets/journey45.png)

以下に、反応イベントを設定するための様々な手順を示します。

1. 反応追加の **[!UICONTROL ラベル]** 。 この手順はオプションです。
1. ドロップダウンリストから、反応させるアクションアクティビティを選択します。 パスの前のステップに配置されている任意のアクションアクティビティを選択できます。
1. 選択した操作（電子メール、SMS、またはプッシュ通知）に応じて、反応の対象を選択します。
1. 条件をオプションの手順として定義できます。 例えば、電子メールアクションの後で、2つのパスを作成することを決定できます。1つはVIP顧客のクリックのみを追跡するリアクションイベントを持ち、もう1つは女性が実行したクリックを追跡するリアクションイベントを持ちます。

>[!NOTE]
>
>反応イベントはAdobe Campaign Standardと連携し、AWSサーバーまたはAzureサーバーにデプロイされているかどうかに関係なく機能します。
>
>リアクションイベントは、電子メール、SMS、またはプッシュ操作を追跡できません。
>
>リアクションイベントは、「追跡」タイプのリンクのクリックを追跡します(この [ページを参照](https://docs.adobe.com/content/help/en/campaign-standard/using/designing-content/links.html#about-tracked-urls))。 購読解除とミラーページのリンクは考慮されません。

>[!IMPORTANT]
>
>Gmailなどの電子メールクライアントでは、画像のブロックが許可されます。 電子メールの開封は、電子メールに含まれる0ピクセルの画像を使用して追跡されます。 画像がブロックされると、電子メールの開封は考慮されません。
