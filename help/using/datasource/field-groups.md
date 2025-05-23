---
product: adobe campaign
title: フィールドグループ
description: フィールドグループについて学ぶ
feature: Journeys
role: User
level: Intermediate
exl-id: 6f7f2673-9080-4274-afa3-a0255798f78d
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '505'
ht-degree: 63%

---

# フィールドグループ {#concept_ntl_ypt_52b}


>[!CAUTION]
>
>**Adobe Journey Optimizerをお探しですか** Journey Optimizerのドキュメントについては、[ こちら ](https://experienceleague.adobe.com/ja/docs/journey-optimizer/using/ajo-home){target="_blank"} をクリックしてください。
>
>
>_このドキュメントでは、Journey Optimizerに置き換えられた従来のJourney Orchestration マテリアルについて説明します。 Journey OrchestrationやJourney Optimizerへのアクセスに関するご質問は、アカウントチームにお問い合わせください。_


フィールドグループは、データソースから取得し、ジャーニーで使用できるフィールドのセットです。

## フィールドグループの定義 {#section_dsz_kjd_fjb}

データソースごとに、複数のフィールドグループを定義できます。

例えば、電話番号、メール、名前、プロファイルのアドレスを使用してフィールドグループを作成できます。その後、このデータをジャーニーで使用して条件を作成できます。例えば、プロファイルの電話番号が空でない場合に限り、SMS を送信することができます。空の場合は、メールを送信できます。

デフォルト名は自動的に追加されますが、フィールドグループには名前を付けることをお勧めします。フィールドグループ名は、[!DNL Journey Orchestration] 内の他のユーザーに表示されます。フィールドグループに関連性の高い名前を付けることをお勧めします。

ジャーニーでデータソースフィールドを使用すると、システムはそのフィールドグループに定義されているすべてのフィールドを取得します。したがって、ジャーニーに必要なフィールドのみを選択することをお勧めします。これにより、ジャーニーでのリクエストの待ち時間が短縮され、パフォーマンスが向上します。フィールドグループには、後から簡単にフィールドを追加できます。

フィールドグループを使用するジャーニーの数は、「**[!UICONTROL 使用されている場所]**」フィールドに表示されます。「**[!UICONTROL ジャーニーを表示]**」ボタンをクリックすると、このフィールドグループを使用するジャーニーのリストが表示されます。

>[!NOTE]
>
>フィールドグループにフィールドがない場合は、式エディターに表示されません。

![](../assets/journey3bis.png)

## フィールドグループのライフサイクル {#section_abk_njd_fjb}

ドラフトやライブジャーニーで使用されていないフィールドグループに対しては、フィールドの追加や削除をおこなうことができます。

1 つ以上のドラフトまたはライブジャーニーで使用されているフィールドグループからは、フィールドを追加できても、削除することはできません。これにより、ジャーニーが中断するのを回避します。

1 つ以上のジャーニーで使用されているフィールドグループからフィールドを削除するには、次の手順に従います。例えば、「フィールドグループ A」という名前のフィールドグループがあるとします。

1. フィールドグループのリストで、「フィールドグループ A」にカーソルを置き、右側にある **[!UICONTROL 複製]** アイコンをクリックします。 例えば、複製したフィールドグループに「フィールドグループ B」という名前を付けます。
1. 「フィールドグループ B」で、不要になったフィールドを削除します。
1. 「フィールドグループ A」で、このフィールドグループが使用される場所を確認します。 この情報は、「**[!UICONTROL 使用]**」フィールドに表示されます。
1. 「フィールドグループ A」を使用するすべてのジャーニーを開きます。
1. これらのジャーニーそれぞれの新しいバージョンを作成します。「フィールドグループ A」を使用してすべてのアクティビティを編集し、「フィールドグループ B」を選択します。
1. 「フィールドグループ A」を使用する、ジャーニーの古いバージョンを停止します。 すると、「フィールドグループ A」を使用するジャーニーはなくなります。
1. 「フィールドグループ A」はもう使用しないので、削除します。
