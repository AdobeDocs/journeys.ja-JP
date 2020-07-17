---
title: セグメント資格イベント
description: セグメントクオリフィケーションのイベントについて学ぶ
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
source-git-commit: 78c486c3e43b0bbda666afba9cf36ba34b362a03
workflow-type: tm+mt
source-wordcount: '658'
ht-degree: 1%

---


# セグメント資格イベント {#segment-qualification}

## セグメントクオリフィケーションのイベントについて{#about-segment-qualification}

このアクティビティを使用すると、個々の人を旅に出たり進めたりするために、Adobe Experience Platformセグメントでのプロファイルの出入り口を聞くことができます。 For more information on segment creation, refer to this [section](../segment/about-segments.md).

「シルバー顧客」セグメントがあるとします。 このアクティビティを使うと、新しい銀の顧客全員を旅に出させ、パーソナライズされた一連のメッセージを送ることができます。

このタイプのイベントは、遍歴の最初または後半に配置できます。

セグメントに「高周波オーディエンス」Adobe Experience Platformがストリーミングされる場合、入口と出口がリアルタイムでリッスンされます。 セグメントがストリーミングされない場合は、セグメントの計算時に入口と出口が考慮されます。

1. 「 **[!UICONTROL イベント]** 」カテゴリを展開し、「 **[!UICONTROL セグメント資格]** 」アクティビティをキャンバスにドロップします。

   ![](../assets/segment5.png)

1. アクティビティ追加の **[!UICONTROL ラベル]** 。 この手順はオプションです。

1. [ **[!UICONTROL セグメント]** ]フィールドをクリックし、活用するセグメントを選択します。

   ![](../assets/segment6.png)

1. 「 **[!UICONTROL 動作]** 」フィールドで、セグメントへの参加、出口、またはその両方をリッスンするかを選択します。

1. 名前空間を選択. これは、イベントが旅の最初のステップとして位置付けられている場合にのみ必要です。

   ![](../assets/segment7.png)

ペイロードには次のコンテキスト情報が含まれ、これらは条件とアクションで使用できます。

* 行動（入口、出口）
* 認定のタイムスタンプ
* セグメントid

式エディターを使用して、 **[!UICONTROL セグメントクオリフィケーション]** アクティビティに従う条件や操作を実行する場合は、SegmentQuolification **** ノードにアクセスできます。 「 **[!UICONTROL 最後のクオリフィケーション時間]** 」と「 **[!UICONTROL ステータス]** （入口または出口）」のいずれかを選択できます。

「 [条件アクティビティ](../building-journeys/condition-activity.md#about_condition)」を参照してください。

![](../assets/segment8.png)

## セグメントのベストプラクティス {#best-practices-segments}

セグメン **[!UICONTROL ト資格]** アクティビティを使用すると、Adobe Experience Platformセグメントから資格を得た個人、または資格を得ない個人の遍歴を即座に開始できます。

この情報の受信速度は高い。 測定した値は、1秒あたり10,000イベントの受信速度を示します。 その結果、入り口のピークがどのように起こるか、どのようにしてそれらを避けるか、またどのようにしてそれらを目指すかを理解する必要があります。

### バッチセグメント{#batch-speed-segment-qualification}

バッチセグメントに対してセグメントクオリフィケーションを使用する場合、入口のピークは毎日の計算時に発生することに注意してください。 ピークのサイズは、セグメントを1日に開始（または終了）した個人の数によって異なります。

また、バッチセグメントを新たに作成し、即座に遍歴に使用した場合、最初のバッチの計算で非常に多くの人がこの旅に参加する可能性があります。

### ストリームセグメント{#streamed-speed-segment-qualification}

ストリームセグメントに対してセグメントクオリフィケーションを使用する場合、セグメントの継続的な評価により、入口/出口のピークが大きくなるリスクが少なくなります。 ただし、セグメント定義によって大量の顧客が同時に資格を得る場合は、ピークも生じる可能性があります。

### オーバーロードを回避する方法{#overloads-speed-segment-qualification}

ジャーニーで使用するシステム(データソース、カスタムアクション、Adobe Campaign Standardアクション)の過負荷を回避するのに役立つ、いくつかのベストプラクティスを示します。

セグメントクオリフィケーション **** アクティビティでは、バッチセグメントの作成直後にそのセグメントを使用しないでください。 最初の計算のピークは回避されます。 まだ計算されていないセグメントを使用しようとすると、ジャーニーキャンバスに黄色の警告が表示されます。

![](../assets/segment-error.png)

データソースおよびジャーニーで使用されるアクションに対する制限規則を設定し、データソースの過負荷を回避します(この [節を参照](../api/capping.md))。 キャッピング規則には再試行がないことに注意してください。 再試行する必要がある場合は、タイムアウトや条件やアクションのエラーが発生した場合に別のパス **[!UICONTROL をチェックし追加、別のパスを使用する必要があります]** 。

実稼働用の遍歴でセグメントを使用する前に、必ず、このセグメントに対して毎日資格を持つ個人の数量を最初に評価します。 そのためには、Adobe Experience Platformの **[!UICONTROL セグメント]** (Segments)セクションを確認し、右側のグラフを確認します。

![](../assets/segment-overload.png)
