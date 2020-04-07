---
title: ユーザーインターフェイス
description: ユーザーインターフェイスの詳細
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: tm+mt
source-git-commit: e579936cfe5eb43caf72627004f98a5746c7abb1

---


# ユーザーインターフェイス{#concept_rcq_lqt_52b}

>[!NOTE]
>
>Gureny Orchestrationを最大限に活用するには、Chromeをインターネットブラウザーとして使用することをお勧めします。
>
>このドキュメントは、製品の最近の変更を反映して頻繁に更新されます。 ただし、一部のスクリーンショットは、製品のインターフェイスと少し異なる場合があります。

## Jargeny Orchestrationへのアクセス{#accessing_journey_orchestration}

Jureny Orchestrationのインターフェイスにアクセスするには、右上のアイ **[!UICONTROL App Selector]** コンをクリックします。 次に、右 **[!UICONTROL Journey Orchestration]**&#x200B;側の「エクスペリエンスプラットフォーム」の下のをクリックします。

![](../assets/journey1.png)

セクション内のExperience CloudホームページからもJureny Orchestrationにアクセスでき **[!UICONTROL Quick access]** ます。

![](../assets/journey1bis.png)

## インターフェイスの検出{#section_jsq_zr1_ffb}

>[!CONTEXTUALHELP]
>id="jo_home"
>title="ジャーニーリスト"
>abstract="この旅行リストを使用すると、すべての旅行を一度に表示し、そのステータスを確認し、基本的な行動をとることができます。 ジャーニーを重複、停止または削除できます。 旅程によっては、特定のアクションが使用できない場合があります。 例えば、完了したジャーニーを削除したり再開したりすることはできません。 新しいバージョンを作成するか、新しいバージョンを重複できます。 検索バーを使用して、旅行を検索することもできます。"
>additional-url="https://images-tv.adobe.com/mpcv3/38af62cb-9390-4bc0-a576-d336849adb97_1574809570.1920x1080at3000_h264.mp4" text="デモビデオを見る"

上部のメニューを使用すると、Jureny Orchestrationの様々な機能を操作できます。 **[!UICONTROL Home]**（旅行）**[!UICONTROL Data Sources]**、 **[!UICONTROL Events]**、 **[!UICONTROL Actions]**、

![](../assets/journey2.png)

画面の右 ![](../assets/icon-context.png) 上隅にあるアイコンをクリックして、コンテキストヘルプを表示します。 これは、様々なJureny Orchestrationリスト画面(ジャーニー、イベント、アクション、データソース)で使用できます。 これにより、現在の機能の表示を簡単に説明し、関連する記事やビデオにアクセスできます。

![](../assets/journey2bis.png)

## 検索とフィルタリング{#section_lgm_hpz_pgb}

、 **[!UICONTROL Home]**、および&#x200B;**[!UICONTROL Data Sources]****[!UICONTROL Events]****[!UICONTROL Actions]** リストで、項目を検索できます。

アクセ **[!UICONTROL Filters]** スするには、アイコンの左上にあるフィルターアイコンをクリックします。リスト [フィルター]メニューを使用すると、表示される要素を異なる条件に従ってフィルタリングできます。 特定のタイプまたはステータスの要素、作成した要素、または過去30日間に変更された要素のみを表示するように選択できます。

、および **[!UICONTROL Data Sources]****[!UICONTROL Events]** リスト **[!UICONTROL Actions]** で、作成フィルター **を使用して** 、作成日とユーザーをフィルタします。 例えば、過去30日間に作成したイベントのみを表示するように選択できます。

ジャーニーリスト(下 **[!UICONTROL Home]**)では、に加えて、表示され **[!UICONTROL Creation filters]**&#x200B;たジャーニーをステータスとバージョン(**[!UICONTROL Status and version filters]**)に従ってフィルタリングできます。 また、特定のイベント、フィールドグループ、またはアクション(および&#x200B;**[!UICONTROL Activity filters]** )を使用するジャーニーのみを表示するように選択することもできます。 **[!UICONTROL Data filters]** ANDを使用 **[!UICONTROL Publication filters]** すると、発行日またはユーザーを選択できます。 例えば、昨日公開された最新バージョンのライブジャーニーのみを表示するように選択できます。 [](../building-journeys/using-the-journey-designer.md)を参照してください。

>[!NOTE]
>
>表示される列は、列の右上にある設定ボタンを使用してパーソナライズできます。リスト パーソナライゼーションは、各ユーザーに対して保存されます。

列と列 **[!UICONTROL Last update]** を使 **[!UICONTROL Last update by]** 用すると、最後にジャーニーが更新された日時と、どのユーザーがジャーニーを操作したかを表示できます。

![](../assets/journey74.png)

イベント、データソース、およびアクションの設定パネルでは、 **[!UICONTROL Used in]** このフィールドに、特定のイベント、フィールドグループまたはアクションを使用するジャーニーの数が表示されます。 ボタンをクリックすると、 **[!UICONTROL View journeys]** 対応するジャーニーのリストを表示できます。

![](../assets/journey3bis.png)

様々な要素で、各リストに対して基本的なアクションを実行できます。 例えば、アイテムの重複や削除が可能です。

![](../assets/journey4.png)

## データプラットフォームフィールドの参照 {#friendly-names-display}

[イベントペイロード](../event/defining-the-payload-fields.md)、フィール [ドグループペイロード](../datasource/field-groups.md) 、式エディタでフィールドを選択すると [](../expression/expressionadvanced.md)、フィールド名に加えて表示名が表示されます。 この情報は、エクスペリエンスデータモデルのスキーマ定義から取得されます。

スキーマの設定時に「xdm:alternateDisplayInfo」などの記述子が指定された場合、表示名はユーザーにわかりやすい名前に置き換えられます。 これは、「eVar」および汎用フィールドを扱う場合に特に便利です。API呼び出しを使用して、わかりやすい名前記述子を設定できます。 詳しくは、『 [スキーマレジストリ開発ガイド](https://docs.adobe.com/content/help/en/experience-platform/xdm/api/getting-started.html)』

![](../assets/xdm-from-descriptors.png)

わかりやすい名前が使用できる場合、フィールドはとして表示されま `<friendly-name>(<name>)`す。 わかりやすい名前がない場合は、表示名などが表示されます `<display-name>(<name>)`。 いずれも定義されていない場合は、フィールドの技術的な名前のみが表示されま `<name>`す。

>[!NOTE]
>
>わかりやすい名前は、複数のフィールドからフィールドを選択した場合には和集合されません。

## 様々なショートカットの使用{#section_ksq_zr1_ffb}

以下に、Jureny Orchestrationのインターフェイスで使用できる様々なショートカットを示します。

_ジャーニー、リスト、データソースまたはイベント:_

* cを押 **して** 、新しい遍歴、アクション、データソース、またはイベントを作成します。

_遍歴でアクティビティを設定する場合：_

キャンバスは自動的に保存されます。 キャンバスの左上に、保存ステータスが表示されます。

* Escキーを **押して** 、設定ペインを閉じ、変更を破棄します。 これはボタンと同じで **[!UICONTROL Cancel]** す。
* 設定ペ **[!UICONTROL Enter]** インを閉じるには、ペインの外側を押すか、またはクリックします。 変更が保存されます。 これはボタンと同じで **[!UICONTROL Ok]** す。
* BackSpaceキーを押すと **[!UICONTROL Delete]** 、を押して削 ******[!UICONTROL Enter]** 除を確定できます。

_ポップアップ内：_

* Escキーを **押して** 、閉じます(「キャンセル」ボタン **と同じ** )。
* を押し **[!UICONTROL Enter]** て、保存または確認します(またはボ **[!UICONTROL Ok]** タンと同 **[!UICONTROL Save]** じです)。

_イベント、データソースまたはアクションの設定ペインで、次の操作を行います。_

* Escキーを **押すと** 、保存せずに設定ウィンドウが閉じます。
* を押し **[!UICONTROL Enter]** て変更を保存し、設定ペインを閉じます。
* 設定する **異なるフィールド間を移動するには** 、Tabキーを押します。

_シンプル式エディタ_

* 重複で左側のフィールドをクリックし、クエリを追加します（ドラッグ&amp;ドロップと同じです）。

_XDMフィールドを閲覧する場合：_

* 「node」をチェックすると、ノードのすべてのフィールドが選択されます。

_すべてのテキスト領域：_

* テキストを **選択するには、Ctrl/Command** + Aキーの組み合わせを使用します。 ペイロードプレビューでペイロードを選択する。

_検索バーのある画面で、次の操作を行います。_

* 検索バーを **選択するには、Ctrl/Command** + Fキーの組み合わせを使用します。

_旅のキャンバスで：_

* Ctrl/Command **+ Aキーの組み合わせを使用して** 、すべてのオプションをアクティビティします。
* 1つまたは複数のアクティビティを選択したら、BackSpaceキ **[!UICONTROL Delete]** ーを押 **すか** 、削除します。 その後、確認ポッ **[!UICONTROL Enter]** プアップでを押して確認します。
* 重複が左のアクティビティをクリックすると、最初に使用可能な位置（上から下）に追加されます。
