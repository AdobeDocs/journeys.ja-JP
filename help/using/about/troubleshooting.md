---
product: adobe campaign
title: トラブルシューティング
description: トラブルシューティングの詳細を説明します
feature: Journeys
role: User
level: Intermediate
exl-id: c678ba01-c868-49f2-99f3-1abe0302779e
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '1093'
ht-degree: 95%

---

# トラブルシューティング{#concept_nlv_bcv_2fb}


>[!CAUTION]
>
>**Adobe Journey Optimizerをお探しですか** Journey Optimizerのドキュメントについては、[ こちら ](https://experienceleague.adobe.com/ja/docs/journey-optimizer/using/ajo-home){target="_blank"} をクリックしてください。
>
>
>_このドキュメントでは、Journey Optimizerに置き換えられた従来のJourney Orchestration マテリアルについて説明します。 Journey OrchestrationやJourney Optimizerへのアクセスに関するご質問は、アカウントチームにお問い合わせください。_



この節では、テストまたは公開の前にジャーニーをトラブルシューティングする方法を説明します。以下に示すチェックはすべて、ジャーニーがテストモードの場合、またはジャーニーがライブの場合に実行できます。レコメンデーションは、テストモードで以下のすべてのチェックを行い、公開に進むことです。[このページ](../building-journeys/testing-the-journey.md)を参照してください。

## テスト前のエラーチェック{#section_h3q_kqk_fhb}

ジャーニーをテストおよび公開する前に、すべてのアクティビティが正しく設定されていることを確認します。システムでエラーが検出される場合は、テストまたは公開を実行できません。

エラーは、キャンバス上のアクティビティ自体に警告記号と共に表示されます。感嘆符にマウスポインターを合わせると、エラーメッセージが表示されます。アクティビティをクリックすると、エラーのある行と警告が表示されます。例えば、必須フィールドが空の場合は、エラーが表示されます。

![](../assets/journey63.png)

例えば、キャンバスで 2 つのアクティビティが切断されると、警告が表示されます。

![](../assets/canvas-disconnected.png)

「**[!UICONTROL テスト]**」切替スイッチと「**[!UICONTROL 公開]**」ボタンの横に、警告記号が表示される場合があります。この警告記号は、システムで検出されたエラーを表示して、テストモードのアクティベーションやジャーニーの公開を防ぎます。ほとんどの場合、システムで検出されたエラーは、アクティビティに表示されるエラーにリンクされますが、その他の問題にリンクされることもあります。この場合、エラーを表示し、エラーの説明を使用して問題を特定できます。問題を特定できない場合は、詳細をコピーして管理者またはサポートに送信できます。テストをブロックするエラーと公開をブロックするエラーは似ています。

システムは、エラーと警告の 2 種類の問題を検出します。エラーは、公開とテストアクティベーションをブロックします。警告は、テストのアクティベーションや公開をブロックしない、潜在的な問題を示します。問題の説明と、タイプ ERR_XXX_XXX の問題ログ ID が表示されます。これは、テクニカルサポートが問題を特定するのに役立ちます。

「**[!UICONTROL テスト]**」切替スイッチと「**[!UICONTROL 公開]**」ボタンの隣の記号は、2 種類の色で表示されます。エラーの場合は、記号は赤で表示されます。警告の場合は、オレンジ色で表示されます。

![](../assets/journey75.png)

ジャーニー全体にわたるエラーと警告は、リストの最初に表示されます。特定のアクティビティに関連するエラーと警告はその後に、アクティビティの順序や表示順によって左から右に表示されます。「**[!UICONTROL 詳細をコピー]**」ボタンは、サポートチームがトラブルシューティングに使用できるジャーニーに関するテクニカル情報をコピーします。

アクションまたは条件でエラーが発生すると、個人のジャーニーが停止します。続行するには、「**[!UICONTROL タイムアウトまたはエラーの場合に代替パスを追加]**」チェックボックスをオンにするだけです。[この節](../building-journeys/using-the-journey-designer.md#paths)を参照してください。

## イベントが適切に送信されているかを確認する{#section_rqz_11t_dgb}

ジャーニーの開始点は常にイベントです。Postman などのツールを使用してテストを実行できます。

これらのツールを介して送信する API 呼び出しが正しく送信されているかどうかを確認できます。エラーが返された場合は、呼び出しに問題があるということです。ペイロード、ヘッダー（特に組織 ID）、宛先の URL を再度確認します。ヒットするのに適した URL を管理者に問い合わせることができます。

イベントは、ソースから [!DNL Journey Orchestration] に直接プッシュされるわけではありません。実際のところ、[!DNL Journey Orchestration] はAdobe Experience Platformのストリーミング取得 API に依存しています。 そのため、イベントに関する問題が発生した場合は、[このページ](https://experienceleague.adobe.com/docs/experience-platform/ingestion/streaming/troubleshooting.html?lang=ja)でストリーミング取り込み API のトラブルシューティングを確認してください。

## ジャーニーへのエントリを確認する{#section_x4v_zzs_dgb}

[!DNL Journey Orchestration] レポートでは、ジャーニーへのエントリがリアルタイムで測定されます。

イベントが正常に送信されたにもかかわらず、ジャーニーへのエントリが確認できない場合は、ジャーニーのイベント送信とイベント受信の間に何か問題があることになります。

管理者は、次の点を確認してください。

* イベントを受信するジャーニーが、テストモードまたはライブになっているか。
* ペイロードプレビューからペイロードをコピーする前にイベントを保存したか。
* イベントペイロードにイベント ID が含まれているか。
* 正しい URL をヒットしたか。
* イベント設定ペインのペイロード構造プレビューを使用して、ストリーミング取り込み API のペイロード構造に従ったか。[このページ](../event/previewing-the-payload.md)を参照してください。
* イベントのヘッダーに使用したキーと値のペアは適切か？

  ```
  X-gw-ims-org-id - your ORGID
  Content-type - application/json
  ```

## ジャーニーの進行状況を確認する{#section_l5y_yzs_dgb}

[!DNL Journey Orchestration] レポートは、ジャーニーでの個人の進行状況を測定します。ユーザーがどこで、なぜ停止したのかを容易に特定できます。

以下に、確認すべき点をいくつか示します。

* 停止の原因が、該当するユーザーを除外する条件であるか。例えば、条件が「性別 = 男性」で、ユーザーが女性の場合。このチェックは、条件が複雑すぎない場合、ビジネスユーザーが実行できます。
* データソースへの呼び出しが応答しないためか。この情報は、ジャーニーのテスト中にテストモードログに表示されます。このジャーニーがライブになると、管理者はデータソースへの直接呼び出しをテストし、受け取った回答を確認できます。管理者は、このジャーニーを複製してテストすることもできます。

## メッセージが正常に送信されたかを確認する{#section_qb1_yzs_dgb}

個人がジャーニーを適切に進んでいるのに、受信すべきメッセージが届いていない場合は、以下の点を確認します。

* トランザクションメッセージで、メッセージの送信リクエストが正しく考慮されているかを確認します。ビジネスユーザーは、送信予定のトランザクションメッセージにアクセスし、最新の実行時刻が、そのジャーニーの実行時刻と一致するかを確認できます。また、トランザクションメッセージングで受け取った最新の API 呼び出し／イベントも確認できます。
* トランザクションメッセージングが正常にメッセージを送信したか確認します。トランザクションメッセージの送信ログで、各実行のステータスを確認できます。ステータスの色（緑または赤）、および問題の詳細を確認できます。ビジネスユーザーはこの画面にアクセスし、詳細な調査のためにログを管理者に送信できます。

カスタムアクションを介して送信されたメッセージの場合、ジャーニーテストで確認できるのは、カスタムアクションのシステムを呼び出すことでエラーが発生するかどうかだけです。カスタムアクションに関連付けられた外部システムへの呼び出しがエラーにならず、それでもメッセージが送信されない場合は、外部システム側で調査する必要があります。
