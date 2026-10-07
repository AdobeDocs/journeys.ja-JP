---
product: adobe campaign
title: Adobe Analytics データについて
description: Adobe Analytics データの活用方法について説明します
feature: Journeys
role: User
level: Intermediate
exl-id: e9b128be-9411-4b68-935e-4cc09eae3ef6
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
source-wordcount: '251'
ht-degree: 87%
---
# Adobe Analyticsのデータを活用して{#analytics-data}


>[!CAUTION]
>
>**Adobe Journey Optimizer をお探しですか**？ Journey Optimizer のドキュメントについて詳しくは、[こちら](https://experienceleague.adobe.com/ja/docs/journey-optimizer/using/ajo-home){target="_blank"}をクリックしてください。
>
>
>_このドキュメントは、Journey Optimizer に置き換えられた従来の Journey Orchestration 資料を参照しています。 Journey Orchestration または Journey Optimizer へのアクセスについてご質問がある場合は、アカウントチームにお問い合わせください。_


>[!NOTE]
>
>この節は、ルールベースのイベントと、Adobe Analytics データを使用する必要があるお客様にのみ当てはまります。

ジャーニーをトリガーし顧客向けのエクスペリエンスを自動化するために、既にキャプチャして Platform にストリーミングしている Adobe Analytics のあらゆる行動イベントデータを活用できます。

そのためには、利用するレポートスイートを Adobe Experience Platform で有効化する必要があります。

1. Adobe Experience Platform の「Adobe Analytics」セクションで、「**[!UICONTROL ソース]**」を選択してから「**[!UICONTROL データを追加]**」を選択します。 使用可能な Adobe Analytics レポートスイートのリストが表示されます。

1. 有効にするレポートスイートを選択し、「**[!UICONTROL 次へ]**」をクリックして、「**[!UICONTROL 終了]**」をクリックします。

1. ソースデータ IDをAlpha プログラムの連絡先と共有します。

これにより、そのレポートスイートの Analytics ソースコネクタが有効になります。 データが入ってくるたびに、データはエクスペリエンスイベントに変換され、Adobe Experience Platform に送信されます。

![](../assets/alpha-event9.png)

Adobe Analytics ソースコネクタについて詳しくは、[ ドキュメント ](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=ja)および[ チュートリアル ](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=ja)を参照してください。
