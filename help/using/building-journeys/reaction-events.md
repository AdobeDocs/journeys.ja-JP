---
product: adobe campaign
title: 反応イベント
description: 反応イベントについて学ぶ
feature: Journeys
role: User
level: Intermediate
exl-id: 2f2a2905-1521-48d9-b593-9b31238282a5
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '455'
ht-degree: 60%

---

# 反応イベント {#section_dhx_gss_dgb}


>[!CAUTION]
>
>**Adobe Journey Optimizerをお探しですか** Journey Optimizerのドキュメントについては、[&#x200B; こちら &#x200B;](https://experienceleague.adobe.com/ja/docs/journey-optimizer/using/ajo-home){target="_blank"} をクリックしてください。
>
>
>_このドキュメントでは、Journey Optimizerに置き換えられた従来のJourney Orchestration マテリアルについて説明します。 Journey OrchestrationやJourney Optimizerへのアクセスに関するご質問は、アカウントチームにお問い合わせください。_



パレットに表示される多数のイベントアクティビティの中に、ビルトインの&#x200B;**[!UICONTROL 反応]**&#x200B;イベントがあります。
このアクティビティを使用すると、同じジャーニー内のメール、SMS またはプッシュアクティビティで送信されたメッセージに関連するトラッキングデータに反応できます。 この情報は、Adobe Campaign Standardのトランザクションメッセージから得られます。 アドビでは、この情報がAdobe Experience Platformと共有された時点で、この情報をリアルタイムで取得します。 プッシュ通知では、メッセージのクリック、送信、失敗に反応できます。SMS メッセージでは、メッセージの送信と失敗に反応できます。メールでは、メッセージのクリック、送信、開封、失敗に反応できます。

このしくみを使用して、メッセージに対する反応がない場合にアクションを実行することもできます。これには、反応アクティビティと並行して 2 つ目のパスを作成し、待機アクティビティを追加します。待機アクティビティで定義した期間に反応がない場合は、2 つ目のパスが選択されます。例えば、フォローアップメッセージを送信することもできます。

キャンバスで反応アクティビティを使用できるのは、事前にメール、プッシュまたは SMS アクティビティがおこなわれている場合のみです。

[アクションアクティビティについて](../building-journeys/about-action-activities.md)を参照してください。

![](../assets/journey45.png)

反応イベントは様々な手順で設定できます。

1. 反応に&#x200B;**[!UICONTROL ラベル]**&#x200B;を追加します。この手順はオプションです。
1. ドロップダウンリストから、反応するアクションアクティビティを選択します。パスの中で前のステップに配置されている任意のアクションアクティビティを選択できます。
1. 選択したアクション（メール、SMS またはプッシュ通知）に応じて、反応対象を選択します。
1. イベントタイムアウト（40 秒 ～ 30 日）とタイムアウトパスを定義できます。これにより、定義したデュレーション内に反応しなかった個人に対する 2 つ目のパスが作成されます。反応イベントを使用するジャーニーをテストする場合、テストモードの&#x200B;**[!UICONTROL 待機時間]**&#x200B;のデフォルト値は最小値である 40 秒です。[この節](../building-journeys/testing-the-journey.md)を参照してください。

>[!NOTE]
>
>反応イベントは、AWSと Azure サーバーのどちらにデプロイされている場合でも、Adobe Campaign Standardで機能します。
>
>反応イベントでは、別のジャーニーで発生するメール、SMS またはプッシュアクションを追跡することはできません。
>
>反応イベントは、「トラッキング対象」タイプのリンクのクリックを追跡します（この [&#x200B; ページ &#x200B;](https://experienceleague.adobe.com/docs/campaign-standard/using/designing-content/links.html?lang=ja#about-tracked-urls) を参照）。 購読解除とミラーページのリンクは考慮しません。

>[!IMPORTANT]
>
>Gmail などのメールクライアントでは、画像がブロックされる可能性があります。メールの開封は、メールに含めた 0 ピクセルの画像を使用してトラッキングします。画像がブロックされると、メールの開封は考慮できません。
