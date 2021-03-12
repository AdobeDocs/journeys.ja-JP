---
product: adobe campaign
solution: Journey Orchestration
title: セグメントの選定イベント
description: セグメントクオリフィケーションのイベントについて学ぶ
feature: ジャーニー
role: 開業医
level: 中級
translation-type: tm+mt
source-git-commit: a99ad6a589bcd1f3083eabbcac35dd5c0497093d
workflow-type: tm+mt
source-wordcount: '786'
ht-degree: 2%

---


# セグメントの選定イベント {#segment-qualification}

## セグメントクオリフィケーションイベントについて{#about-segment-qualification}

このアクティビティを使用すると、ジャーニーがAdobe Experience Platformのセグメントでプロファイルの出入り口をリッスンして、個人がジャーニーに入るか、前に進むようにできます。 セグメントの作成について詳しくは、[](../segment/about-segments.md)を参照してください。

「シルバー顧客」セグメントがあるとします。 このアクティビティを使用すると、新しいシルバーの顧客全員にジャーニーを送り込み、パーソナライズされた一連のメッセージを送ることができます。

このタイプのイベントは、ジャーニーの最初または後半に配置できます。

>[!IMPORTANT]
>
>Adobe Experience Platformセグメントは、1日に1回（**バッチ**&#x200B;セグメント）、またはリアルタイム（**ストリーム**&#x200B;セグメント）で計算されます(Adobe Experience Platformの「高周波オーディエンス」オプションを使用)。
>
>選択したセグメントがストリーミングされる場合、このセグメントに属する個人がリアルタイムでジャーニーに入る可能性があります。 セグメントがバッチの場合、新たにこのセグメントに適格となった訪問者は、セグメントの計算がAdobe Experience Platformで実行される際に、ジャーニーを入力する可能性があります。


1. **[!UICONTROL イベント]**&#x200B;カテゴリを展開し、**[!UICONTROL セグメントの条件]**&#x200B;アクティビティをキャンバスにドロップします。

   ![](../assets/segment5.png)

1. アクティビティ追加に対する&#x200B;**[!UICONTROL ラベル]**。 この手順はオプションです。

1. [**[!UICONTROL セグメント]**]フィールドをクリックし、活用するセグメントを選択します。

   >[!NOTE]
   >
   >リストに表示される列はカスタマイズして並べ替えることができます。

   ![](../assets/segment6.png)

   セグメントが追加されると、「**[!UICONTROL コピー]**」ボタンを使用して、セグメントの名前とIDをコピーできます。

   `{"name":"Loyalty membership“,”id":"8597c5dc-70e3-4b05-8fb9-7e938f5c07a3"}`

   ![](../assets/segment-copy.png)

1. 「**[!UICONTROL 動作]**」フィールドで、セグメントへの参加、出口、またはその両方をリッスンするかを選択します。

   >[!NOTE]
   >
   >**[!UICONTROL 入口]**&#x200B;と&#x200B;**[!UICONTROL 出口]**&#x200B;は、Adobe Experience Platformからの&#x200B;**実現**&#x200B;と&#x200B;**出口**&#x200B;セグメントパーティシペーションのステータスに対応します。 セグメントの評価方法について詳しくは、[Segmentation Serviceドキュメント](https://experienceleague.adobe.com/docs/experience-platform/segmentation/tutorials/evaluate-a-segment.html?lang=en#interpret-segment-results)を参照してください。

1. 名前空間を選択. これは、イベントがジャーニーの最初のステップとして位置付けられている場合にのみ必要です。

   ![](../assets/segment7.png)

ペイロードには次のコンテキスト情報が含まれ、これらは条件とアクションで使用できます。

* 行動（入口、出口）
* 認定のタイムスタンプ
* セグメントid

**[!UICONTROL セグメントクオリフィケーション]**&#x200B;アクティビティに続く条件または操作で式エディターを使用する場合、**[!UICONTROL SegmentQuolification]**&#x200B;ノードにアクセスできます。 **[!UICONTROL 前回の資格日時]**&#x200B;と&#x200B;**[!UICONTROL ステータス]**&#x200B;のどちらかを選択できます（入力または終了）。

[条件のアクティビティ](../building-journeys/condition-activity.md#about_condition)を参照してください。

![](../assets/segment8.png)

## ベストプラクティス{#best-practices-segments}

**[!UICONTROL セグメント資格]**&#x200B;アクティビティは、Adobe Experience Platformセグメントから資格を得たり資格を失ったりする個人のジャーニーに、すぐに入ることを可能にします。

この情報の受信速度は高い。 測定した値は、1秒あたり10,000イベントの受信速度を示します。 その結果、入り口のピークがどのように発生するか、どのように避けるか、ジャーニーを準備するかを理解する必要があります。

### バッチセグメント{#batch-speed-segment-qualification}

バッチセグメントに対してセグメントクオリフィケーションを使用する場合、入口のピークは毎日の計算時に発生することに注意してください。 ピークのサイズは、セグメントを1日に開始（または終了）した個人の数によって異なります。

また、バッチセグメントを新たに作成して、即座にジャーニーで使用する場合は、最初のバッチの計算によって、非常に多くの人がジャーニーに入る可能性があります。

### ストリームセグメント{#streamed-speed-segment-qualification}

ストリームセグメントに対してセグメントクオリフィケーションを使用する場合、セグメントの継続的な評価により、入口/出口のピークが大きくなるリスクが少なくなります。 ただし、セグメント定義によって大量の顧客が同時に資格を得る場合は、ピークも生じる可能性があります。

ストリーミングセグメント化について詳しくは、[ページ](https://experienceleague.adobe.com/docs/experience-platform/segmentation/api/streaming-segmentation.html#api)を参照してください。

### オーバーロードを回避する方法{#overloads-speed-segment-qualification}

ジャーニーで使用するシステム(データソース、カスタムアクション、Adobe Campaign Standardアクション)の過負荷を回避するのに役立つ、いくつかのベストプラクティスを示します。

**[!UICONTROL セグメントクオリフィケーション]**&#x200B;アクティビティでは、作成直後のバッチセグメントを使用しないでください。 最初の計算のピークは回避されます。 まだ計算されていないセグメントを使用しようとすると、ジャーニーキャンバスに黄色の警告が表示されます。

![](../assets/segment-error.png)

データソースとジャーニーで使用されるアクションの制限規則を設定し、データソースの過負荷を回避します（[](../api/capping.md)を参照）。 キャッピング規則には再試行がないことに注意してください。 再試行する必要がある場合は、条件やアクションでタイムアウトやエラー&#x200B;]**が発生した場合に、**[!UICONTROL &#x200B;代替パスをチェックして、ジャーニー内追加の代替パスを使用する必要があります。

実稼働ジャーニーでセグメントを使用する前に、必ず、このセグメントに対して毎日資格を持つ個人の数量を最初に評価します。 これを行うには、Adobe Experience Platformの&#x200B;**[!UICONTROL セグメント]**&#x200B;セクションを確認し、右側のグラフを確認します。

![](../assets/segment-overload.png)
