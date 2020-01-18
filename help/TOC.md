---
product: Journeys
audience: end-user
user-guide-title: Journey Orchestration Help
index: true
translation-type: tm+mt
source-git-commit: 22569d66acb1637efc346f77864302b9e2cb6070

---


# ジャーニーオーケストレーションヘルプ {#using}

+ [製品ドキュメント](journey-orchestration-home.md)
+ What&#39;s new {#release-notes}
   + [リリースノート](using/release-notes/release-notes.md)
   + [ドキュメントの更新](using/release-notes/documentation-updates.md)
+ Jargeny Orchestrationから開始 {#starting-with-journeys}
   + [Jargeny Orchestrationについて](using/about/about-journey-orchestration.md)
   + [はじめに](using/about/get-started.md)
   + [ユーザーインターフェイス](using/about/user-interface.md)
   + [アクセス管理](using/about/access-management.md)
   + [トラブルシューティング](using/about/troubleshooting.md)
+ イベントの設定 {#events-journeys}
   + [イベントについて](using/event/about-events.md)
   + [ペイロードフィールドの定義](using/event/defining-the-payload-fields.md)
   + [名前空間の選択](using/event/selecting-the-namespace.md)
   + [イベントキーの定義](using/event/defining-the-event-key.md)
   + [条件の追加](using/event/adding-a-condition.md)
   + [ペイロードのプレビュー](using/event/previewing-the-payload.md)
   + [イベントを送信するための追加手順](using/event/additional-steps-to-send-events-to-journey-orchestration.md)
+ データソースの設定 {#data-source-journeys}
   + [データソースについて](using/datasource/about-data-sources.md)
   + [フィールドグループ](using/datasource/field-groups.md)
   + [Adobe Experience Platformデータソース](using/datasource/adobe-experience-platform-data-source.md)
   + [外部データソース](using/datasource/external-data-sources.md)
+ アクションの設定 {#action-journeys}
   + [アクションについて](using/action/action.md)
   + [Adobe Campaignの使用](using/action/working-with-adobe-campaign.md)
   + サードパーティ製システムの使用 {#action-third-party}
      + [カスタムアクション設定について](using/action/about-custom-action-configuration.md)
      + [カスタムアクションの制限](using/action/custom-action-limitations.md)
      + [URL設定](using/action/url-configuration.md)
      + [メッセージパラメーターの定義](using/action/defining-the-message-parameters.md)
+ 旅行の構築 {#building-journeys}
   + 旅のビルディングについて {#about-journey-building}
      + [旅行の作成](using/building-journeys/journey.md)
      + [ジャーニーデザイナーの使用](using/building-journeys/using-the-journey-designer.md)
      + [プロパティの変更](using/building-journeys/changing-properties.md)
      + [ジャーニーバージョン](using/building-journeys/journey-versions.md)
      + [旅の終了](using/building-journeys/terminating-a-journey.md)
      + [タイムゾーン管理](using/building-journeys/timezone-management.md)
   + アクティビティ {#about-journey-building}
      + [イベントアクティビティ](using/building-journeys/event-activities.md)
      + オーケストレーション活動 {#orchestration-activities}
         + [オーケストレーションアクティビティについて](using/building-journeys/about-orchestration-activities.md)
         + [条件アクティビティ](using/building-journeys/condition-activity.md)
         + [アクティビティの終了](using/building-journeys/end-activity.md)
         + [待機アクティビティ](using/building-journeys/wait-activity.md)
      + アクションアクティビティ {#action-activities}
         + [アクションアクティビティについて](using/building-journeys/about-action-activities.md)
         + [Adobe Campaignアクションの使用](using/building-journeys/using-adobe-campaign-actions.md)
         + [カスタムアクションの使用](using/building-journeys/using-custom-actions.md)
   + [旅のテスト](using/building-journeys/testing-the-journey.md)
   + [旅の公開](using/building-journeys/publishing-the-journey.md)
+ 高度な式エディターの使用 {#building-advanced-conditions-journeys}
   + [高度な式エディターについて](using/expression/expressionadvanced.md)
   + 構文 {#syntax}
      + [一般論](using/expression/generalities.md)
      + [条件付き命令](using/expression/conditional-instruction.md)
      + [データタイプ](using/expression/data-types.md)
      + [フィールド参照](using/expression/field-references.md)
      + [収集管理機能](using/expression/collection-management-functions.md)
      + [オペレーター](using/expression/operators.md)
   + 関数 {#main-functions-journey}
      + [主な関数](using/expression/functions.md)
      + Adobe Experience Platform {#adobe-experience-platform}
         + [getBestSendTime](using/functions/functiongetbestsendtime.md)
         + [inSegment](using/functions/functioninsegment.md)
      + 集計 {#aggregation}
         + [平均](using/functions/functionavg.md)
         + [count](using/functions/functioncount.md)
         + [countOnlyNull](using/functions/functioncountonlynull.md)
         + [countWithNull](using/functions/functioncountwithnull.md)
         + [distinctCount](using/functions/functiondistinctcount.md)
         + [distinctCountWithNull](using/functions/functiondistinctcountwithnull.md)
         + [max](using/functions/functionmax.md)
         + [分](using/functions/functionmin.md)
         + [sum](using/functions/functionsum.md)
      + コンバージョン {#conversion}
         + [toBool](using/functions/functiontobool.md)
         + [toDateTime](using/functions/functiontodatetime.md)
         + [toDateTimeOnly](using/functions/functiontodatetimeonly.md)
         + [toDecimal](using/functions/functiontodecimal.md)
         + [toDuration](using/functions/functiontoduration.md)
         + [toInteger](using/functions/functiontointeger.md)
         + [toString](using/functions/functiontostring.md)
      + 日付 {#date}
         + [currentTime &#x200B; inMillis](using/functions/functioncurrenttimeinmillis.md)
         + [inLastDays](using/functions/functioninlastdays.md)
         + [inLastHours](using/functions/functioninlasthours.md)
         + [inLastMonths](using/functions/functioninlastmonths.md)
         + [inLastYears](using/functions/functioninlastyears.md)
         + [inNextDays](using/functions/functioninnextdays.md)
         + [inNextHours](using/functions/functioninnexthours.md)
         + [inNextMonths](using/functions/functioninnextmonths.md)
         + [inNextYears](using/functions/functioninnextyears.md)
         + [now](using/functions/functionnow.md)
         + [nowWithDelta](using/functions/functionnowwithdelta.md)
         + [setHours](using/functions/functionsethours.md)
         + [setDays](using/functions/functionsetdays.md)
      + リスト {#list}
         + [異なる](using/functions/functiondistinct.md)
         + [distinctWithNull](using/functions/functiondistinctwithnull.md)
         + [-](using/functions/functionin.md)
         + [listSize](using/functions/functionlistsize.md)
         + [serializeList](using/functions/functionserializelist.md)
         + [並べ替え](using/functions/functionsort.md)
      + 数学 {#math}
         + [ランダム](using/functions/functionrandom.md)
         + [round](using/functions/functionround.md)
      + 文字列 {#string}
         + [concat](using/functions/functionconcat.md)
         + [contain](using/functions/functioncontain.md)
         + [containWithIgnoreCase](using/functions/functioncontainwithignorecase.md)
         + [endWith](using/functions/functionendwith.md)
         + [endWithIgnorecase](using/functions/functionendwithignorecase.md)
         + [equalWithIgnoreCase](using/functions/functionequalignorecase.md)
         + [indexOf](using/functions/functionindexof.md)
         + [isEmpty](using/functions/functionisempty.md)
         + [isNotEmpty](using/functions/functionisnotempty.md)
         + [lastIndexOf](using/functions/functionlastindexof.md)
         + [length](using/functions/functionlength.md)
         + [lower](using/functions/functionlower.md)
         + [matchRegExp](using/functions/functionmatchregexp.md)
         + [notEqualWithIgnoreCase](using/functions/functionnotequalignorecase.md)
         + [置換](using/functions/functionreplace.md)
         + [replaceAll](using/functions/functionreplaceall.md)
         + [startWith](using/functions/functionstartwith.md)
         + [startWithIgnoreCase](using/functions/functionstartwithignorecase.md)
         + [substr](using/functions/functionsubstr.md)
         + [trim](using/functions/functiontrim.md)
         + [upper](using/functions/functionupper.md)
         + [uuid](using/functions/functionuuid.md)
+ レポートの作成{#journey-reports}
   + [ジャーニーレポートについて](using/reporting/about-journey-reports.md)
   + [ジャーニーレポートの作成](using/reporting/creating-your-journey-reports.md)
   + [指標とディメンション](using/reporting/metrics-and-dimensions.md)
+ 使用例{#use-cases-journeys}
   + 簡単な使用例{#use-case-simple}
      + [簡単な使用例について](using/usecase/about-the-simple-use-case.md)
      + [イベントの設定](using/usecase/configuring-the-event.md)
      + [データソースの設定](using/usecase/configuring-the-data-source.md)
      + [旅の構築](using/usecase/simple-uc-building-the-journey.md)
   + 高度な使用例{#use-case-advanced}
      + [高度な使用例について](using/usecase/about-the-advanced-use-case.md)
      + [イベントの設定](using/usecase/configuring-the-events.md)
      + [データソースの設定](using/usecase/configuring-the-data-sources.md)
      + [旅の構築](using/usecase/building-the-journey.md)
   + [疲労スコアの活用](using/usecase/leveraging-fatigue-scores.md)

