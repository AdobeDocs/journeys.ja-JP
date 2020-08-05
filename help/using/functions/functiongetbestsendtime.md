---
title: getBestSendTime
description: 関数getBestSendTimeについて学習します。
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
source-git-commit: eb4474313d3c0470448f9959ed757902ef0ecd2a
workflow-type: tm+mt
source-wordcount: '239'
ht-degree: 4%

---


# getBestSendTime {#getBestSendTime}

個人に電子メールを配信するのに最適な予測時間を提供します。

この関数では、Adobe Experience Platformで計算されたスコアを使用します。 スコアは、過去の行動に基づいて、将来的に電子メールをクリックしたり開いたりする傾向を計算します。 スコアを計算するアルゴリズムは、ある程度のデータ量を必要とします。 その結果、十分なデータがない場合は、デフォルトの時間が適用されます。 For more information, see [](../building-journeys/wait-activity.md).

この関数を使用するには、 [名前空間](../event/selecting-the-namespace.md) が必要です。

>[!NOTE]
>
>Note that the best send time score can be unavailable if there is not enough data to perform the calculation. この場合、発行時に、デフォルトの時刻が適用されることを通知します。

## カテゴリ

Adobe Experience Platform

## 関数の構文

`getBestSendTime(<parameters>)`

## パラメーター

| パラメーター | 説明 | タイプ |
|--- |--- |--- |
| 時間 | 現在の時刻から考慮する時間数(最大： 168)電子メール送信を最適化する | `<integer>` |
| 最適化タイプ | &quot;open&quot;または&quot;click&quot; | `<string>` |
| 待機する時間のデフォルト時間 | 予測送信時間スコアが利用できない場合 | `<integer>` |

## 署名と戻り値の型

`getBestSendTime(<integer>,<string>,<integer>)`

dateTimeを返します。

## 例

getBestSendTime(12,&quot;open&quot;,8)

説明：

関数は、次の12時間にメッセージを送信するのに最適な時間を返します。これは、ジャーニーインスタンス内の個人がメッセージを開く確率を最適化するためです。 計算を実行するのに十分なデータがない場合、返される時間は現在の時間から8時間です。
