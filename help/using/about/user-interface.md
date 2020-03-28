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
source-git-commit: bc5b29eefa4d787cd448352252823a616489d8c8

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

また、セクション内のExperience CloudホームページからJureny Orchestrationにアクセスすることもで **[!UICONTROL Quick access]** きます。

![](../assets/journey1bis.png)

## インターフェイスの検出{#section_jsq_zr1_ffb}

>[!CONTEXTUALHELP]
>id=&quot;jo_home&quot;
>title=&quot;ジャーニーリストについて&quot;
>abstract=&quot;The journey list all your journey at once, see their status and perform basic actions. ジャーニーは複製、停止または削除できます。 旅程によっては、特定のアクションが使用できない場合があります。 例えば、完了したジャーニーを削除したり再開したりすることはできません。 新しいバージョンを作成したり、複製したりできます。 検索バーを使用して、旅行を検索することもできます。」
>additional-url=&quot;https://images-tv.adobe.com/mpcv3/38af62cb-9390-4bc0-a576-d336849adb97_1574809570.1920x1080at3000_h264.mp4&quot; text=&quot;デモビデオを見る&quot;

上部のメニューを使用すると、Jureny Orchestrationの様々な機能を操作できます。 **[!UICONTROL Home]**（旅行）**[!UICONTROL Data Sources]**、 **[!UICONTROL Events]**、 **[!UICONTROL Actions]**、

![](../assets/journey2.png)

画面の右 ![](../assets/icon-context.png) 上隅にあるアイコンをクリックして、コンテキストヘルプを表示します。 これは、様々なJureny Orchestrationリスト画面（ジャーニー、イベント、アクション、データソース）で使用できます。 これにより、現在の機能の簡単な説明を表示し、関連する記事やビデオにアクセスできます。

![](../assets/journey2bis.png)

## 検索とフィルタリング{#section_lgm_hpz_pgb}

、 **[!UICONTROL Home]**、およびリス&#x200B;**[!UICONTROL Data Sources]**&#x200B;トで **[!UICONTROL Events]****[!UICONTROL Actions]** は、検索バーを使用して項目を検索できます。

リスト **[!UICONTROL Filters]** の左上にあるフィルターアイコンをクリックして、にアクセスできます。 フィルターメニューを使用すると、様々な条件に従って表示される要素をフィルターできます。 特定のタイプまたはステータスの要素、作成した要素、または過去30日間に変更された要素のみを表示するように選択できます。

、およびのリ **[!UICONTROL Data Sources]**&#x200B;スト **[!UICONTROL Events]** で、 **[!UICONTROL Actions]** 作成フィルタ **を使用して** 、作成日とユーザに基づいてフィルタリングします。 例えば、過去30日間に作成したイベントのみを表示するように選択できます。

ジャーニーリスト(の下 **[!UICONTROL Home]**)では、の他に、表示されたジ **[!UICONTROL Creation filters]**&#x200B;ャーニーを、ステータスとバージョン(**[!UICONTROL Status and version filters]**)に従ってフィルタリングできます。 また、特定のイベント、フィールドグループ、またはアクション(および&#x200B;**[!UICONTROL Activity filters]** )を使用するジャーニーのみを表示するように選択することもできます。この場合、発行日 **[!UICONTROL Data filters]****[!UICONTROL Publication filters]** やユーザーを選択できます。 例えば、昨日公開された最新バージョンのライブジャーニーのみを表示するように選択できます。 [](../building-journeys/using-the-journey-designer.md)を参照してください。

>[!NOTE]
>
>表示される列は、リストの右上にある設定ボタンを使用してパーソナライズできます。 パーソナライゼーションは、各ユーザーに対して保存されます。

列と列 **[!UICONTROL Last update]** を使 **[!UICONTROL Last update by]** 用すると、最後にジャーニーが更新された日時と、どのユーザーがジャーニーを操作したかを表示できます。

![](../assets/journey74.png)

イベント、データソース、およびアクションの設定パネルでは、このフィー **[!UICONTROL Used in]** ルドに、特定のイベント、フィールドグループまたはアクションを使用するジャーニーの数が表示されます。 ボタンをクリックする **[!UICONTROL View journeys]** と、対応するジャーニーのリストが表示されます。

![](../assets/journey3bis.png)

様々なリストで、各要素に対して基本的なアクションを実行できます。 例えば、アイテムを複製または削除できます。

![](../assets/journey4.png)

## データプラットフォームフィールドの参照 {#friendly-names-display}

イベントペイ [ロード](../event/defining-the-payload-fields.md)、フィールドグ [ループペイロード](../datasource/field-groups.md) 、式エディターでフィールドを選択すると [](../expression/expressionadvanced.md)、フィールド名に加えて表示名が表示されます。 この情報は、エクスペリエンスデータモデルのスキーマ定義から取得されます。

スキーマの設定時に「xdm:alternateDisplayInfo」などの記述子が指定された場合、表示名はユーザーにわかりやすい名前に置き換えられます。 これは、「eVar」および汎用フィールドを扱う場合に特に便利です。API呼び出しを使用して、わかりやすい名前記述子を設定できます。 詳しくは、「 [Schema Registry developer guide」を参照してください](https://www.adobe.io/apis/experienceplatform/home/xdm/xdmservices.html#!api-specification/markdown/narrative/technical_overview/schema_registry/schema_registry_developer_guide.md)。

![](../assets/xdm-from-descriptors.png)

わかりやすい名前が使用できる場合、フィールドはとして表示されま `<friendly-name>(<name>)`す。 わかりやすい名前がない場合は、表示名（例：）が表示されます `<display-name>(<name>)`。 いずれも定義されていない場合は、フィールドの技術的な名前のみが表示されま `<name>`す。

>[!NOTE]
>
>スキーマの結合からフィールドを選択した場合、わかりやすい名前は取得されません。

## 様々なショートカットの使用{#section_ksq_zr1_ffb}

以下に、Jureny Orchestrationのインターフェイスで使用できる様々なショートカットを示します。

_ジャーニー、アクション、データソースまたはイベントのリスト：_

* cを押 **して** 、新しい遍歴、アクション、データソース、またはイベントを作成します。

_遍歴でアクティビティを設定する場合：_

キャンバスは自動的に保存されます。 キャンバスの左上に、保存ステータスが表示されます。

* Escキーを **押して** 、設定ペインを閉じ、変更を破棄します。 これはボタンと同じで **[!UICONTROL Cancel]** す。
* 設定ペ **[!UICONTROL Enter]** インを閉じるには、ペインの外側を押すか、またはクリックします。 変更が保存されます。 これはボタンと同じで **[!UICONTROL Ok]** す。
* BackSpaceキーを押すと **[!UICONTROL Delete]** 、を押して削 ******[!UICONTROL Enter]** 除を確定できます。

_ポップアップ内：_

* Escキーを **押して** 、閉じます(「キャンセル」ボタン **と同じ** )。
* を押し **[!UICONTROL Enter]** て、保存または確認します(またはボ **[!UICONTROL Ok]** タンと同 **[!UICONTROL Save]** じです)。

_イベントで、データソースまたはアクションの設定ペイン：_

* Escキーを **押すと** 、保存せずに設定ウィンドウが閉じます。
* を押し **[!UICONTROL Enter]** て変更を保存し、設定ペインを閉じます。
* 設定する **異なるフィールド間を移動するには** 、Tabキーを押します。

_シンプルエクスプレッションエディター_

* 左側のフィールドをダブルクリックして、クエリを追加します（ドラッグ&amp;ドロップと同じ）。

_XDMフィールドを閲覧する場合：_

* 「node」をチェックすると、ノードのすべてのフィールドが選択されます。

_すべてのテキスト領域：_

* テキストを **選択するには、Ctrl/Command** + Aキーの組み合わせを使用します。 ペイロードプレビューで、ペイロードを選択します。

_検索バーのある画面で、次の操作を行います。_

* 検索バーを **選択するには、Ctrl/Command** + Fキーの組み合わせを使用します。

_旅のキャンバスで：_

* すべてのアクテ **ィビティを選択するには、Ctrl/Command** + Aキーの組み合わせを使用します。
* 1つまたは複数のアクティビティを選択したら、BackSpaceキ **[!UICONTROL Delete]** ーを押す **か** 、削除します。 その後、確認ポッ **[!UICONTROL Enter]** プアップでを押して確認します。
* 左のパレットでアクティビティをダブルクリックし、最初に使用可能な位置（上から下）に追加します。
