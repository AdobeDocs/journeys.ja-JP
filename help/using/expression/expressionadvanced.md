---
product: adobe campaign
title: 高度な式エディターについて
description: 高度な式の作成方法を学ぶ
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: f6f0004d-8a33-4671-9c16-e56edfe2a45e
source-git-commit: f0cb883a09d553bb47491b750fabde54c92f3225
workflow-type: tm+mt
source-wordcount: '567'
ht-degree: 100%

---

# 高度な式エディターについて {#concept_uyj_trt_52b}

高度な式エディターを使用すると、インターフェイスの様々な画面で高度な式を作成できます。 例えば、ジャーニーを設定して使用する場合や、データソース条件を定義する場合に、式を作成できます。
また、特定のデータ操作を必要とするアクションパラメーターを定義する必要が生じるたびに使用することもできます。イベントから取得したデータや、データソースから取得した追加情報を活用できます。ジャーニーで表示されるイベントフィールドのリストは状況に応じて異なり、ジャーニーに追加されたイベントに応じて変化します。

高度な式エディターでは、組み込みの関数と演算子が提供されるので、値を操作したり、ニーズに見合った式を定義したりできます。また、高度な式エディターでは、外部データソースパラメーターの値の定義、エクスペリエンスイベントなどのマップフィールドやコレクションの操作をおこなうこともできます。

![](../assets/journey65.png)

_高度な式エディターのインターフェイス_

高度な式エディターは次の目的に使用できます。

* データソースとイベント情報に関する[詳細な条件](../building-journeys/condition-activity.md#about_condition)の作成
* カスタム[待機アクティビティ](../building-journeys/wait-activity.md#custom)の定義
* アクションパラメーターのマッピングの定義

可能な場合は、「**[!UICONTROL 詳細設定モード]**」／「**[!UICONTROL シンプルモード」]**&#x200B;ボタンを使用して、2 つのモードを切り替えることができます。シンプルモードについては、[ここ](../building-journeys/condition-activity.md#about_condition)で説明しています。

>[!NOTE]
>
>条件は、シンプルな式エディターでも高度な式エディターでも定義できます。常にブール型を返します。
>
>アクションパラメーターは、フィールドを選択するか、高度な式エディターを使用して定義できます。式に応じて特定のデータ型を返します。

## 高度な式エディターへのアクセス {#section_fdz_4nj_cjb}

高度な式エディターには、様々な方法でアクセスできます。

* データソース条件を作成する場合は、「**[!UICONTROL 詳細設定モード]**」をクリックして高度な式エディターにアクセスできます。

  ![](../assets/journeyuc2_33.png)

* カスタムタイマーを作成すると、高度な式エディターが直接表示されます。
* アクションパラメーターをマッピングする場合は、「**[!UICONTROL 詳細設定モード]**」をクリックします。

## インターフェイスの概要{#section_otq_tnj_cjb}

この画面では、式を手動で書き込むことができます。

![](../assets/journey70.png)

画面の左側に、次の使用可能なフィールドと関数が表示されます。

* **[!UICONTROL イベント]**：受信イベントから受信したフィールドの 1 つを選択します。表示されるイベントフィールドリストは状況に応じて異なり、ジャーニーに追加されるイベントに応じて変化します。[詳細情報](../event/about-events.md)
* **[!UICONTROL セグメント]**：**[!UICONTROL セグメントの選定]**&#x200B;イベントをドロップした場合は、使用するセグメントを式で選択します。[詳細情報](../segment/using-a-segment.md)
* **[!UICONTROL データソース]**：データソースのフィールドグループにあるフィールドリストから選択します。[詳細情報](../datasource/about-data-sources.md)
* **[!UICONTROL ジャーニーのプロパティ]**：このセクションでは、特定のプロファイルのジャーニーに関連するテクニカルフィールドが再グループ化されます。[詳細情報](../expression/journey-properties.md)
* **[!UICONTROL 関数]**：複雑なフィルタリングを実行できる組み込み関数のリストから選択します。関数はカテゴリ別に整理されています。[詳細情報](../expression/functions.md)

![](../assets/journey65.png)

オートコンプリートメカニズムは、コンテキストの提案を表示します。

![](../assets/journey68.png)

構文検証メカニズムは、コードの整合性をチェックします。エラーはエディターの上部に表示されます。

![](../assets/journey69.png)

**高度な式エディターで条件を作成する場合のパラメーターの必要性**

パラメーターの呼び出しが必要な外部データソースからフィールドを選択する場合（[このページ](../datasource/external-data-sources.md)を参照）。例えば、天気関連のデータソースでは、頻繁に使用されるパラメーターは「市区町村」になります。その結果、この市区町村パラメーターを取得する場所を選択する必要があります。また、関数をパラメーターに適用して、形式の変更や連結を実行することもできます。

![](../assets/journeyuc2_19.png)

より複雑な使用例では、データソースのパラメーターをメイン式に含める場合、「params」キーワードを使用してその値を定義できます。[このページ](../expression/field-references.md)を参照してください。
