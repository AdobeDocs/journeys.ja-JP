---
product: adobe campaign
title: セグメントの選定イベント
description: セグメントの選定イベントについて説明します
feature: ジャーニー
role: Business Practitioner
level: Intermediate
exl-id: e8e54dbd-8178-4c70-907c-68eb4dc54da7
source-git-commit: 51915ac931c0c4af03b49140c20e1b0939beff65
workflow-type: tm+mt
source-wordcount: '824'
ht-degree: 1%

---

# セグメントの選定イベント {#segment-qualification}

## セグメントの選定イベントについて{#about-segment-qualification}

このアクティビティを使用すると、ジャーニーは、Adobe Experience Platformセグメント内のプロファイルのエントリと離脱をリッスンして、個人がジャーニーにエントリしたり、ジャーニーを進めたりできるようになります。 セグメントの作成について詳しくは、この[節](../segment/about-segments.md)を参照してください。

「シルバー顧客」セグメントがあるとします。 このアクティビティを使用すると、新しいシルバーの顧客をすべてジャーニーにエントリさせ、パーソナライズされた一連のメッセージを送信できます。

このタイプのイベントは、ジャーニーの最初のステップとして配置することも、後で配置することもできます。

>[!IMPORTANT]
>
>Adobe Experience Platformセグメントは、1日に1回（**バッチ**&#x200B;セグメント）またはリアルタイム(**ストリーミング**&#x200B;セグメント(Adobe Experience Platformの「High Frequency Audiences」オプションを使用)で計算されます。
>
>選択したセグメントがストリーミングされると、このセグメントに属する個人は、潜在的にリアルタイムでジャーニーにエントリします。 セグメントがバッチの場合、新しくこのセグメントの対象として認定されたユーザーは、セグメントの計算がAdobe Experience Platformで実行されると、ジャーニーに入る可能性があります。


1. 「**[!UICONTROL イベント]**」カテゴリを展開し、「**[!UICONTROL セグメント認定]**」アクティビティをキャンバスにドロップします。

   ![](../assets/segment5.png)

1. アクティビティに&#x200B;**[!UICONTROL ラベル]**&#x200B;を追加します。 この手順はオプションです。

1. 「**[!UICONTROL セグメント]**」フィールドをクリックし、活用するセグメントを選択します。

   >[!NOTE]
   >
   >リストに表示される列をカスタマイズし、並べ替えることができます。

   ![](../assets/segment6.png)

   セグメントを追加したら、「**[!UICONTROL コピー]**」ボタンを使用して、セグメントの名前とIDをコピーできます。

   `{"name":"Loyalty membership“,”id":"8597c5dc-70e3-4b05-8fb9-7e938f5c07a3"}`

   ![](../assets/segment-copy.png)

1. 「**[!UICONTROL 動作]**」フィールドで、セグメントのエントリ、出口、またはその両方をリッスンするかを選択します。

   >[!NOTE]
   >
   >**[!UICONTROL Enter]**&#x200B;と&#x200B;**[!UICONTROL Exit]**&#x200B;は、Adobe Experience Platformの&#x200B;**Realized**&#x200B;と&#x200B;**Exited**&#x200B;セグメントパーティシペーションステータスに対応しています。 セグメントの評価方法について詳しくは、[セグメント化サービスのドキュメント](https://experienceleague.adobe.com/docs/experience-platform/segmentation/tutorials/evaluate-a-segment.html?lang=en#interpret-segment-results)を参照してください。

1. 名前空間を選択. これは、イベントがジャーニーの最初のステップとして配置されている場合にのみ必要です。

   ![](../assets/segment7.png)

ペイロードには、次のコンテキスト情報が含まれ、条件とアクションで使用できます。

* 動作（入口、出口）
* 資格のタイムスタンプ
* セグメントid

**[!UICONTROL Segment qualification]**&#x200B;アクティビティに続く条件やアクションで式エディターを使用する場合は、**[!UICONTROL SegmentQualification]**&#x200B;ノードにアクセスできます。 **[!UICONTROL 最終認定時間]**&#x200B;と&#x200B;**[!UICONTROL ステータス]**（入力または終了）から選択できます。

[条件アクティビティ](../building-journeys/condition-activity.md#about_condition)を参照してください。

![](../assets/segment8.png)

セグメントの選定イベントを含む新しいジャーニーは、公開してから10分後に動作します。 この期間は、専用サービスのキャッシュ更新間隔に対応します。 したがって、このジャーニーを使用する前に10分待つ必要があります。

## ベストプラクティス {#best-practices-segments}

**[!UICONTROL セグメント認定]**&#x200B;アクティビティを使用すると、Adobe Experience Platformセグメントから資格を得る、または資格を失う個人のジャーニーに即座に入ることができます。

この情報の受信速度は高い。 作成された測定は、1秒あたりに10,000個のイベントを受信した速度を示します。 その結果、入り口のピークがどのように発生するか、どのように避けるか、そして、どのようにして彼らのための旅を準備するかを理解する必要があります。

### バッチセグメント{#batch-speed-segment-qualification}

バッチセグメントにセグメント認定を使用する場合、入口のピークは日次計算の時点で発生することに注意してください。 ピーク時のサイズは、1日にセグメントに入る（または出る）個人の数によって異なります。

さらに、バッチセグメントが新しく作成され、即座にジャーニーで使用される場合、最初の計算バッチでは、非常に多くの人がジャーニーにエントリする可能性があります。

### ストリーミングセグメント{#streamed-speed-segment-qualification}

ストリーミングセグメントにセグメント認定を使用する場合、セグメントの継続的な評価が原因で、入口/出口のピークが大きくなるリスクが低くなります。 ただし、セグメント定義によって大量の顧客が同時に認定される場合は、ピークが発生する可能性もあります。

ストリーミングセグメント化について詳しくは、[ページ](https://experienceleague.adobe.com/docs/experience-platform/segmentation/api/streaming-segmentation.html#api)を参照してください。

### オーバーロードを回避する方法{#overloads-speed-segment-qualification}

ジャーニーで使用するシステム(データソース、カスタムアクション、Adobe Campaign Standardアクション)の過負荷を回避するのに役立つ、いくつかのベストプラクティスを紹介します。

**[!UICONTROL Segment Qualification]**&#x200B;アクティビティでは、バッチセグメントの作成直後にはを使用しないでください。 最初の計算のピークを回避します。 まだ計算されていないセグメントを使用しようとすると、ジャーニーキャンバスに黄色い警告が表示されます。

![](../assets/segment-error.png)

ジャーニーで使用するデータソースやアクションに対して制限ルールを設定し、過度の読み込みを回避します（この[節](../api/capping.md)を参照）。 キャッピングルールには再試行はありません。 再試行が必要な場合は、条件やアクションでタイムアウトまたはエラー&#x200B;]**の場合に「**[!UICONTROL &#x200B;代替パスを追加 」チェックボックスをオンにして、ジャーニーで代替パスを使用する必要があります。

実稼動ジャーニーでセグメントを使用する前に、は常に、このセグメントの対象となる個人の数を毎日最初に評価します。 そのためには、Adobe Experience Platformの「**[!UICONTROL セグメント]**」セクションを確認し、右側のグラフを確認します。

![](../assets/segment-overload.png)
