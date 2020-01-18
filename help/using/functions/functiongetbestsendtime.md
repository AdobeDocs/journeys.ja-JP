---
title: getBestSendTime
description: 関数getBestSendTimeについて
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
source-git-commit: d6360d616199d597255610959432c7b93fd4e25c

---


# getBestSendTime {#getBestSendTime}

個人に電子メールを配信するのに最適な予測時間を提供します。

この関数は、プラットフォームで計算されたスコアを使用します。 スコアは、過去の行動に基づいて、将来的に電子メールをクリックまたは開く傾向を計算します。 スコアを計算するアルゴリズムは、動作する特定の量のデータを必要とします。 その結果、十分なデータがない場合は、デフォルトの時間が適用されます。 For more information, see [](../building-journeys/wait-activity.md).

この関数を使用するには、名前空間 [が必要](../event/selecting-the-namespace.md) です。

>[!NOTE]
>
>計算を実行するのに十分なデータがない場合は、最適な送信時間スコアを使用できないことに注意してください。 この場合、発行時に、デフォルトの時刻が適用されることが通知されます。

## カテゴリ

Adobe Experience Platform

## 関数の構文

`getBestSendTime(<parameters>)`

## パラメーター

| パラメーター | 説明 | タイプ |
|--- |--- |--- |
| 時間 | 現在の時間から考慮する時間数(最大：168)電子メール送信を最適化する場合 | `<integer>` |
| 最適化タイプ | &quot;open&quot;または&quot;click&quot; | `<string>` |
| 待機する時間のデフォルト時間 | 予測送信時間スコアが使用できない場合 | `<integer>` |

## 署名と戻り値の型

`getBestSendTime(<integer>,<string>,<integer>)`

dateTimeを返します。

## 例

getBestSendTime(12,&quot;open&quot;,8)

説明：

この関数は、ジャーニーインスタンス内の個人がメッセージを開く確率を最適化するために、次の12時間以内にメッセージを送信するのに最適な時間を返します。 計算を実行するのに十分なデータがない場合、返される時間は現在の時間から8時間です。
