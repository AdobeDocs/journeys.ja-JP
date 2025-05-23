---
product: adobe campaign
title: 指標およびディメンション
description: Journey Orchestrationで使用可能なディメンションと指標について説明します
feature: Journeys
role: User
level: Intermediate
exl-id: f6897011-0a5e-4094-a18e-ba2aa25f902c
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '1083'
ht-degree: 5%

---

# 指標およびディメンション {#concept_rfj_wpt_52b}


>[!CAUTION]
>
>**Adobe Journey Optimizerをお探しですか** Journey Optimizerのドキュメントについては、[ こちら ](https://experienceleague.adobe.com/ja/docs/journey-optimizer/using/ajo-home){target="_blank"} をクリックしてください。
>
>
>_このドキュメントでは、Journey Optimizerに置き換えられた従来のJourney Orchestration マテリアルについて説明します。 Journey OrchestrationやJourney Optimizerへのアクセスに関するご質問は、アカウントチームにお問い合わせください。_


>[!NOTE]
>
>配信データは、Adobe Campaign Standardがある場合にのみ入力されます。

ここでは、動的レポートで使用できるすべてのコンポーネントのリストとその定義を確認できます。

次の表に、ジャーニーレポートで使用されるディメンションとその定義のリストを示します。

ディメンションと指標の互換性について詳しくは、[ このページ ](../assets/do-not-localize/dynamic_report_compatibility_journey.pdf) を参照してください。

## ジャーニーの寸法 {#MBE_table_wk4_bnj_w2b}

次の表に、ジャーニーレポートで使用されるディメンションのリスト、その定義および数式を示します。

| ディメンション | 定義 |
|--- |--- |
| **アクション** | ジャーニーで使用されるすべてのアクション（**アクション名 – アクションラベル**）のリスト （例：プッシュ – チェックアウト確認、メール – 報酬忠実性）。 |
| **データソース** | ジャーニーでデータのエンリッチメントに使用するデータソース （**データソース名**）のリスト （例：Adobe Experience Platform、予約システム）。 |
| **[!UICONTROL イベント]** | ジャーニーで使用されるすべてのイベント（**イベント名 – イベントラベル**）のリスト（例：Geometrixx イベント - Geometrixx チェックアウト）。 |
| **フィールドグループ** | ジャーニーでデータのエンリッチメントに使用するフィールドグループ （**フィールドグループ名**）のリスト （例：プロファイルフィールドグループ、Geometrixx予約システム）。 |
| **ジャーニー** | テストモードおよびライブのすべてのジャーニー（**ジャーニー名**）のリスト （例：カート放棄、ホテル予約通知）。 |
| **ジャーニーのバージョン** | ジャーニーのすべての公開済みバージョン（**ジャーニー名+ バージョン番号**）のリスト（買い物かごの放棄 v1、ホテルの予約通知 v2 など）。 |
| **オーケストレーション** | ジャーニーで定義および使用されるすべてのオーケストレーションアクティビティ（**条件** 終了、待機）のリスト。 |

## 配信ディメンション {#delivery-dimensions}

次の表に、ジャーニーレポートで使用される配信ディメンション、その定義および数式のリストを示します。

| ディメンション | 定義 |
|--- |--- |
| **ブラウザー** | メッセージを開いた、またはクリックしたブラウザー。 |
| **配信名** | 配信のラベルと ID。 |
| **デバイス** | メール / SMS / プッシュ通知が開封/表示/クリックされた元のデバイス。 |
| **メッセージタイプ** | メール、SMS、プッシュ通知、アプリ内など、配信に使用されるチャネル。 |
| **モバイルアプリ名** | モバイルアプリケーションの名前 |
| **プラットフォーム** | メッセージが開封、表示、クリックされたデバイスのプラットフォーム。 |
| **[!UICONTROL プッシュプラットフォーム]** | プッシュ通知を開いたデバイスのプラットフォーム（iOS、Androidなど）。 |
| **受信者ドメイン** | メールを開くために使用されるドメイン。 |
| **トラッキング URL** | ユーザーがメッセージからクリックした URL。 |
| **トラッキング URL カテゴリ** | トラッキング URL に割り当てられたカテゴリ。 |
| **トラッキング URL ラベル** | ミラーページ、お問い合わせ、オープンなど、URL に付与されるラベル。 |
| **バリアント** | A/B テストの場合の E メールのバリアント。 |

## ジャーニー指標 {#MBE_p_p22_c4j_w2b}

次の表に、ジャーニーレポートで使用される指標のリスト、その定義および数式を示します。

| 指標 | 定義 |
|--- |---|
| **完了** | ジャーニーで通常どおり終了した個人の合計数。 |
| **完了率** | ジャーニーにエントリした個人の合計数に対して、ジャーニーが正常に終了した個人の合計数。 |
| **現在** | 現在ジャーニーにいる個人の合計数（エントリした人数から退出した人物、エラー、タイムアウトした人物を差し引いた数）。 |
| **現在のレート** | ジャーニーにエントリした個人の数に対する、現在ジャーニーにいる個人の合計数。 |
| **入力済み** | ジャーニーの個々のエントリを開始するために発生したイベントの合計数。 |
| **エラー** | ジャーニー中に発生し、ジャーニーの成功を妨げなかったエラーの合計数。 |
| **アクションのエラー** | アクションで発生したエラーの合計数。 |
| **エンリッチメントのエラー** | データソース/フィールドグループの呼び出し時にデータエンリッチメントに対して発生したエラーの合計数。 |
| **イベントのエラー** | イベントで発生したエラーの合計数。 |
| **エラー率** | ジャーニー内の発生の合計数に対して、ジャーニー中に発生したエラーの合計数。 |
| **実行されたアクション** | ジャーニーで実行されたアクションの合計数。 |
| **実行したエンリッチメント** | 特定のフィールドグループを取得するためにデータソースを呼び出すことによって実行されたエンリッチメントの合計数。 |
| **実行されたイベント** | ジャーニーで実行されたアクションの合計数。 |
| **実行されたオーケストレーション** | ジャーニーに対して実行されたオーケストレーションオブジェクト（終了、待機、条件）の合計数。 |
| **失敗** | 正常に実行されなかったジャーニーの合計数。 |
| **失敗率** | 実行されたジャーニー数に対する、正常に実行されなかったジャーニーの合計数。 |

## 配信指標 {#delivery-metrics}

次の表に、ジャーニーで使用される指標のリストを示します
レポート、その定義および式。

| 指標 | 定義 |
|--- |--- |
| **ブロックリスト時** | E メールをスパムまたはジャンクとして宣言した受信者の数。 |
| **ブロックリスト率** | 送信されたメッセージに対する、ブロックリスト上のメッセージの合計数。 |
| **バウンス + エラー** | 送信されたメッセージの合計数に対して、配信および自動返信処理の間に発生したエラーの累計。 |
| **バウンス率+ エラー率** | 送信メッセージに対するバウンスメッセージの合計数。 |
| **クリック** | 配信でコンテンツがクリックされた回数。 |
| **クリックスルー率** | 配信されたメッセージ数に対する、配信でのクリック総数の割合。 |
| **配信** | 送信されたメッセージの総数に対して、正常に送信されたメッセージの数。 |
| **配信率** | 送信されたメッセージに対する、正常に配信されたメッセージの合計数。 |
| **エラー** | ジャーニー中に発生し、ジャーニーの成功を妨げなかったエラーの合計数。 |
| **ハードバウンス** | 永続的なエラー（メールアドレスの間違いなど）の合計数。 |
| **ハードバウンス率** | 送信されたメッセージに対して、永続的なエラーが原因で失敗した配信の合計数。 |
| **ミラーページ** | ミラーページのリンクをクリックした受信者の数。 |
| **ミラーページ率** | 配信されたメッセージ総数に対する、ミラーページリンクのクリック総数の割合。 |
| **オープン** | 配信でメッセージが開かれた回数。 |
| **開封率** | 配信されたメッセージ数に対する、開封されたメッセージの合計数。 |
| **検疫** | バウンスしてアドレスの強制隔離に至ったメッセージの数。 |
| **検疫率** | 送信されたメッセージに対する強制隔離の合計数。 |
| **却下** | SMTP サーバーによってスパムとして分類されたメッセージの数。 |
| **却下率** | 送信されたメッセージに対して、拒否とマークされたメッセージの合計数。 |
| **処理済み/送信** | 配信に対する送信の合計数。 |
| **ソフトバウンス** | 一時的なエラー（インボックスがいっぱいであるなど）の合計数。 |
| **ソフトバウンス率** | 送信されたメッセージと比較した、一時的な理由で失敗した配信の合計数。 |
| **ユニーククリック数** | 配信のコンテンツをクリックした受信者の数。 |
| **ユニーク開封数** | 配信されたメッセージを開いた受信者の数。 |
| **購読解除済み** | 購読解除リンクのクリック数。 |
| **登録解除率** | 配信されたメッセージに対する、受信者ごとの購読解除の合計数。 |
