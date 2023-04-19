---
product: adobe campaign
user-guide-title: Journey Orchestration
title: Journey Orchestration ガイド
user-guide-description: ジャーニーの実装方法や構築方法を説明します。
index: true
feature: Journeys
source-git-commit: 137637a753ba44cc4f8e397b77c3fc076ec3de3f
workflow-type: ht
source-wordcount: '447'
ht-degree: 100%

---


# [!DNL Journey Orchestration] ガイド {#using}

+ [製品ドキュメント](journey-orchestration-home.md)
+ 最新情報 {#release-notes}
   + [リリースノート](using/release-notes/release-notes.md)
   + [ドキュメントの更新](using/release-notes/documentation-updates.md)
   + [Journey Optimizer へのアップグレード](using/release-notes/upgrade-to-ajo.md)
+ [!DNL Journey Orchestration] の概要{#starting-with-journeys}
   + [ [!DNL Journey Orchestration] について](using/about/about-journey-orchestration.md)
   + [制限事項](using/about/limitations.md)
   + [基本を学ぶ](using/about/get-started.md)
   + [ユーザーインターフェイス](using/about/user-interface.md)
   + [アクセス管理](using/about/access-management.md)
   + [トラブルシューティング](using/about/troubleshooting.md)
   + [外部システムとの統合](using/about/external-systems.md)
+ イベントの設定 {#events-journeys}
   + イベントについて {#about-events}
      + [一般原則](using/event/about-events.md)
      + [データサイクル](using/event/about-data-cycle.md)
      + [イベントの作成](using/event/about-creating.md)
      + [Adobe Analytics の活用](using/event/about-analytics.md)
      + [ExperienceEvent スキーマについて](using/event/experience-event-schema.md)
      + [イベントを送信するための追加手順](using/event/additional-steps-to-send-events-to-journey-orchestration.md)
   + [ペイロードフィールドの定義](using/event/defining-the-payload-fields.md)
   + [名前空間の選択](using/event/selecting-the-namespace.md)
   + [イベントキーの定義](using/event/defining-the-event-key.md)
   + [ペイロードのプレビュー](using/event/previewing-the-payload.md)
+ データソースの設定 {#data-source-journeys}
   + [データソースについて](using/datasource/about-data-sources.md)
   + [フィールドグループ](using/datasource/field-groups.md)
   + [Adobe Experience Platform のデータソース](using/datasource/adobe-experience-platform-data-source.md)
   + [外部データソース](using/datasource/external-data-sources.md)
+ アクションの設定 {#action-journeys}
   + [アクションについて](using/action/action.md)
   + [Adobe Campaign Standard の使用](using/action/working-with-adobe-campaign.md)
   + [Adobe Campaign v7／v8 の使用](using/action/acc-action.md)
   + サードパーティシステムの使用 {#action-third-party}
      + [カスタムアクション設定について](using/action/about-custom-action-configuration.md)
      + [URL 設定](using/action/url-configuration.md)
      + [アクションパラメーターの定義](using/action/defining-the-message-parameters.md)
+ セグメントの使用 {#configuring-segment}
   + [セグメントについて](using/segment/about-segments.md)
   + [セグメントの作成](using/segment/creating-a-segment.md)
   + [条件でのセグメントの使用](using/segment/using-a-segment.md)
+ ジャーニーの構築 {#building-journeys}
   + ジャーニー構築について {#about-journey-building}
      + [ジャーニーの作成](using/building-journeys/journey.md)
      + [ジャーニーデザイナーの使用](using/building-journeys/using-the-journey-designer.md)
      + [プロパティの変更](using/building-journeys/changing-properties.md)
      + [ジャーニーのバージョン](using/building-journeys/journey-versions.md)
      + [ジャーニーの終了](using/building-journeys/terminating-a-journey.md)
      + [タイムゾーン管理](using/building-journeys/timezone-management.md)
      + [テストプロファイル](using/building-journeys/creating-test-profiles.md)
   + アクティビティ {#about-journey-building}
      + イベントアクティビティ {#events-activities}
         + [イベントアクティビティについて](using/building-journeys/event-activities.md)
         + [一般イベント](using/building-journeys/general-events.md)
         + [反応イベント](using/building-journeys/reaction-events.md)
         + [セグメントの選定イベント](using/building-journeys/segment-qualification-events.md)
      + オーケストレーションアクティビティ {#orchestration-activities}
         + [オーケストレーションアクティビティについて](using/building-journeys/about-orchestration-activities.md)
         + [条件アクティビティ](using/building-journeys/condition-activity.md)
         + [終了アクティビティ](using/building-journeys/end-activity.md)
         + [待機アクティビティ](using/building-journeys/wait-activity.md)
      + アクションアクティビティ {#action-activities}
         + [アクションアクティビティについて](using/building-journeys/about-action-activities.md)
         + [Adobe Campaign Standard の使用](using/building-journeys/using-adobe-campaign-actions.md)
         + [Adobe Campaign v7／v8 の使用](using/building-journeys/using-adobe-campaign-classic.md)
         + [カスタムアクションの使用](using/building-journeys/using-custom-actions.md)
         + [ジャーニー間でのジャンプ](using/building-journeys/jump.md)
         + [プロファイルの更新](using/building-journeys/update-profiles.md)
   + [ジャーニーのテスト](using/building-journeys/testing-the-journey.md)
   + [ジャーニーの公開](using/building-journeys/publishing-the-journey.md)
   + Adobe Experience Platform でのジャーニー手順の共有 {#sharing-journey-steps}
      + [ジャーニーステップ共有の概要](using/building-journeys/sharing-overview.md)
      + [ステップイベントフィールドのリスト](using/building-journeys/sharing-field-list.md)
      + レガシーステップイベントのフィールド {#legacy-step-event-fields}
         + [レガシーフィールドについて](using/building-journeys/sharing-legacy-fields.md)
         + [journeySteps イベントの共通フィールド](using/building-journeys/sharing-common-fields.md)
         + [journeyStep イベントのアクション実行フィールド](using/building-journeys/sharing-execution-fields.md)
         + [journeyStep イベントのデータ取得フィールド](using/building-journeys/sharing-fetch-fields.md)
         + [journeyStep イベントの ID フィールド](using/building-journeys/sharing-identity-fields.md)
         + [ジャーニーのフィールド](using/building-journeys/sharing-journey-fields.md)
      + [クエリの例](using/building-journeys/query-examples.md)
+ 式の作成 {#building-advanced-conditions-journeys}
   + [概要](using/expression/expressionadvanced.md)
   + 構文 {#syntax}
      + [一般規則](using/expression/generalities.md)
      + [条件付き命令](using/expression/conditional-instruction.md)
      + [データタイプ](using/expression/data-types.md)
      + [フィールド参照](using/expression/field-references.md)
      + [コレクション管理関数](using/expression/collection-management-functions.md)
      + [演算子](using/expression/operators.md)
      + [ジャーニーのプロパティ](using/expression/journey-properties.md)
      + [例](using/expression/advanced-editor-use-cases.md)
   + 関数 {#main-functions-journey}
      + [主な関数](using/expression/functions.md)
      + Adobe Experience Platform {#adobe-experience-platform}
         + [inSegment](using/functions/functioninsegment.md)
      + 集計 {#aggregation}
         + [avg](using/functions/functionavg.md)
         + [count](using/functions/functioncount.md)
         + [countOnlyNull](using/functions/functioncountonlynull.md)
         + [countWithNull](using/functions/functioncountwithnull.md)
         + [distinctCount](using/functions/functiondistinctcount.md)
         + [distinctCountWithNull](using/functions/functiondistinctcountwithnull.md)
         + [max](using/functions/functionmax.md)
         + [min](using/functions/functionmin.md)
         + [sum](using/functions/functionsum.md)
      + コンバージョン {#conversion}
         + [toBool](using/functions/functiontobool.md)
         + [toDateOnly](using/functions/functiontodateonly.md)
         + [toDateTime](using/functions/functiontodatetime.md)
         + [toDateTimeOnly](using/functions/functiontodatetimeonly.md)
         + [toDecimal](using/functions/functiontodecimal.md)
         + [toDuration](using/functions/functiontoduration.md)
         + [toInteger](using/functions/functiontointeger.md)
         + [toString](using/functions/functiontostring.md)
      + 日付 {#date}
         + [currentTime&#x200B;InMillis](using/functions/functioncurrenttimeinmillis.md)
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
         + [updateTimeZone](using/functions/functionupdatetimezone.md)
      + リスト {#list}
         + [distinct](using/functions/functiondistinct.md)
         + [distinctWithNull](using/functions/functiondistinctwithnull.md)
         + [filter](using/functions/functionfilter.md)
         + [getListItem](using/functions/functiongetlistitem.md)
         + [in](using/functions/functionin.md)
         + [intersect](using/functions/functionintersect.md)
         + [制限](using/functions/functionlimit.md)
         + [listSize](using/functions/functionlistsize.md)
         + [serializeList](using/functions/functionserializelist.md)
         + [sort](using/functions/functionsort.md)
      + 数学 {#math}
         + [random](using/functions/functionrandom.md)
         + [round](using/functions/functionround.md)
      + 文字列 {#string}
         + [concat](using/functions/functionconcat.md)
         + [contain](using/functions/functioncontain.md)
         + [containIgnoreCase](using/functions/functioncontainwithignorecase.md)
         + [endWith](using/functions/functionendwith.md)
         + [endWithIgnorecase](using/functions/functionendwithignorecase.md)
         + [equalIgnoreCase](using/functions/functionequalignorecase.md)
         + [indexOf](using/functions/functionindexof.md)
         + [isEmpty](using/functions/functionisempty.md)
         + [isNotEmpty](using/functions/functionisnotempty.md)
         + [lastIndexOf](using/functions/functionlastindexof.md)
         + [length](using/functions/functionlength.md)
         + [lower](using/functions/functionlower.md)
         + [matchRegExp](using/functions/functionmatchregexp.md)
         + [notequalIgnoreCase](using/functions/functionnotequalignorecase.md)
         + [replace](using/functions/functionreplace.md)
         + [replaceAll](using/functions/functionreplaceall.md)
         + [split](using/functions/functionsplit.md)
         + [startWith](using/functions/functionstartwith.md)
         + [startWithIgnoreCase](using/functions/functionstartwithignorecase.md)
         + [substr](using/functions/functionsubstr.md)
         + [trim](using/functions/functiontrim.md)
         + [upper](using/functions/functionupper.md)
         + [uuid](using/functions/functionuuid.md)
+ レポートの作成{#journey-reports}
   + [ジャーニーレポートについて](using/reporting/about-journey-reports.md)
   + [ジャーニーレポートの作成](using/reporting/creating-your-journey-reports.md)
   + [指標およびディメンション](using/reporting/metrics-and-dimensions.md)
+ インテリジェントサービスとの統合{#use-case-advanced}
   + [AI 統合について](using/ai-services/ai-services-overview.md)
   + [顧客 AI の活用](using/ai-services/leveraging-customer-ai.md)
+ ユースケース{#use-cases-journeys}
   + パーソナライズされた電子メールの送信{#use-case-simple}
      + [シンプルなユースケース](using/usecase/about-the-simple-use-case.md)
      + [イベントの設定](using/usecase/configuring-the-event.md)
      + [データソースの設定](using/usecase/configuring-the-data-source.md)
      + [ジャーニーの構築](using/usecase/simple-uc-building-the-journey.md)
   + クロスチャネルジャーニーの構築{#use-case-advanced}
      + [高度なユースケース](using/usecase/about-the-advanced-use-case.md)
      + [イベントの設定](using/usecase/configuring-the-events.md)
      + [データソースの設定](using/usecase/configuring-the-data-sources.md)
      + [ジャーニーの構築](using/usecase/building-the-journey.md)
   + [Campaign v7 または v8 を使用したメッセージの送信](using/usecase/campaign-classic-use-case.md)
   + [カスタムアクションを使用したコレクションの動的な受け渡し](using/usecase/collections.md)
+ API の操作{#working-with-apis}
   + [ジャーニー API の基本を学ぶ](using/api/journeys-apis.md)
   + [Capping API](using/api/capping.md)
   + [Throttling API](using/api/throttling.md)
