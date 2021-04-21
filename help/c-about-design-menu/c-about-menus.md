---
description: Sie können Menüs verwenden, um Ihre Präsentationsebene anzupassen.
solution: Target
subtopic: Navigation
title: Menüs
topic-legacy: Design,Site search and merchandising
uuid: 011050cd-21b6-4150-9503-18fa3f771626
exl-id: bd9611c0-4bb6-4869-ae92-fb52722026dd
translation-type: tm+mt
source-git-commit: 7559f5f7437d46e3510d4659772308666425ec96
workflow-type: tm+mt
source-wordcount: '752'
ht-degree: 1%

---

# Über Menüs{#about-menus}

Sie können Menüs verwenden, um Ihre Präsentationsebene anzupassen.

## Verwenden von Menüs {#concept_68123CE5CF4447B59217B5D721424E32}

hinzufügen Menüs, die den Einstellungen in Ihrer Suche zugeordnet sind. Jedes Element in einem Menü gibt den Wert für die Einstellung des Menüs an. Sie können die Menübeschriftungen auch anpassen.

In Ihrer Präsentationsvorlage können Sie auf die definierten Menüs verweisen. Sie können sie dann in jede gewünschte HTML-Komponente einfügen, z. B. ein Select-Steuerelement. Diese Kombination ermöglicht es Benutzern, ihre Suchergebnisse anzupassen. Es werden drei Menütypen unterstützt: Sortieren, Zählen und Navigation.

## Hinzufügen eines neuen Menüs {#task_EE171532D3AE477FAFE8C2F4077A6D73}

Sie können Menüs hinzufügen, die den Einstellungen in Ihren Suchergebnissen zugeordnet sind.

<!-- 

t_adding_a_new_menu.xml

 -->

>[!NOTE]
>
>Verweisen Sie auf das Menü in Ihrer Präsentationsvorlage, damit es auf der Website angezeigt wird.

**So fügen Sie ein neues Menü hinzu**

1. Klicken Sie im Produktmenü auf **[!UICONTROL Design]** > **[!UICONTROL Navigation]** > **[!UICONTROL Menus]**.
1. Klicken Sie auf der Seite [!DNL Menus] auf **[!UICONTROL Add New Menu]**.
1. Legen Sie auf der Seite [!DNL Add Menu] die gewünschten Optionen fest.

   Diese Einstellungen wirken sich sowohl auf das Verhalten als auch auf die Standarddarstellung eines Breadcrumbs aus. Sie können einige dieser Einstellungen mithilfe der Einstellungen der Präsentationsvorlage überschreiben.

   Siehe [Menüs](../c-about-design-menu/c-about-menus.md#concept_68123CE5CF4447B59217B5D721424E32).

   <!-- 
   r_add_menu_options.xml
   -->

   <table> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> <p>Option </p> </th> 
      <th colname="col2" class="entry"> <p>Beschreibung </p> </th> 
      </tr> 
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <p>Menüname </p> </td> 
      <td colname="col2"> <p>Name des Menüs. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Menütyp </p> </td> 
      <td colname="col2"> <p>Legt einen der folgenden drei Menütypen fest: </p> <p> 
      <ul id="ul_7E66ACC1DA494B20BEC3B0B2CCAB103A"> 
      <li id="li_D81876660A8B48AFB70D3317063FBF6F"> <span class="uicontrol"> Sortierung </span> <p>Organisiert die Suche nach einem der definierten Metadatentypen. </p> <p>Sie können beispielsweise ein Sortierungsmenü mit den folgenden Metadatentypen definieren: drei wichtige Punkte; ein benutzerdefiniertes Metadatenfeld, z. B. einen Verfügbarkeitscode; und Preis. Die drei Artikel können mit den Bezeichnungen "Sortieren nach Relevanz", "Sortieren nach Verfügbarkeit"und "Sortieren nach Preis"versehen werden. Wenn Sie dies in Ihre Präsentationsvorlage aufnehmen, kann der Kunde mit diesem Steuerelement seine Suchergebnisse sortieren. </p> </li> 
      <li id="li_63AE06B544B64DCAA8C55031B3DFFFF7"> <span class="uicontrol"> Anzahl </span> <p>Definiert die Anzahl der anzuzeigenden Suchergebnisse. Dieser Menütyp ordnet dem cgi-Parameter <span class="varname"> sp_c </span> zu. </p> <p>Siehe <a href="../c-appendices/c-cgiparameters.md#reference_582E85C3886740C98FE88CA9DF7918E8" format="dita" scope="local"> CGI-Parameter für die Backend-Suche </a>. </p> </li> 
      <li id="li_EEC810D420FF41498ECE49EBAAB33BE5"> <span class="uicontrol"> Navigation </span> <p>Gibt einen Satz statischer URLs an, die mit Menüelementen verknüpft sind. Normalerweise wird ein Navigationsmenü verwendet, um eine Navigationsleiste auf der obersten Navigationsseite Ihrer Suchergebnisseite zu erstellen. </p> <p>Sie könnten beispielsweise ein Menü erstellen, das Frauen, Männer, Jungen und Mädchen umfasst, in dem die Menüelemente wie folgt lauten: 
      <code>
        /?q1=womens;x1=gender 
      </code>, 
      <code>
        /?q1=mens;x1=gender 
      </code> </p> </li> 
      </ul> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Merchandising </p> 
        <!--DONT' KNOW WHAT THIS DOES--> </td> 
      <td colname="col2"> <p>Diese Option ist nur verfügbar, wenn Sie den Menütyp <span class="uicontrol"> Sortieren auswählen. </span> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Anzahl der Menüelemente </p> </td> 
      <td colname="col2"> <p>Gibt die Anzahl der Elemente in einem Menü an. Wenn Sie diese Einstellung ändern, werden Felder aus dem Formular hinzugefügt oder gelöscht. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Standardelement </p> </td> 
      <td colname="col2"> <p>Hier können Sie auswählen, welches Menüelement standardmäßig angezeigt wird. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Elementwert </p> </td> 
      <td colname="col2"> <p>Der Elementwert hängt vom gewählten Menütyp ab. </p> 
        <ul id="ul_2F14E6AA673640578A2D5161FD9D13EF"> 
        <li id="li_5017EC6E4ACB4B8E99E0AA61CBAAFFAE"> Sortierungsmenütyp <p>Gibt an, nach welchem Element im Menü sortiert werden soll. Die ausgewählten Elemente werden mit sortierbaren Metadatenfeldern gefüllt. </p> <p>Für ein einzelnes Element können Sie nach drei Metadatenfeldern sortieren. Die Sortierung erfolgt in der angegebenen Reihenfolge. </p> </li> 
        <li id="li_CC6BAFBF969C4367A71B55F08E0758D1"> Mengenmenütyp <p>Hier können Sie die Anzahl der Ergebnisse angeben, die zurückgegeben werden sollen, wenn der Kunde dieses Menüelement auswählt. </p> </li> 
        </ul> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Elementbezeichnung </p> </td> 
      <td colname="col2"> <p>Die Elementbeschriftung hängt vom gewählten Menütyp ab. </p> 
        <ul id="ul_957BF01235F84748B5EB7062D6AEAC41"> 
        <li id="li_03FB2E2C96134A2B8E08154F87F0CD55"> Sortierungsmenütyp <p>Identifiziert die benutzerdefinierte Bezeichnung, die der Kunde bei der Ansicht dieses Menüpunkts sehen soll. </p> </li> 
        <li id="li_C9FE2BC46D9443FB85FEB837C7CA45E1"> Mengenmenütyp <p>Identifiziert die benutzerdefinierte Bezeichnung, die Sie für dieses Menüelement anzeigen möchten. </p> </li> 
        </ul> </td> 
      </tr> 
    </tbody> 
    </table>

1. Klicken **[!UICONTROL Add]**.
1. (Optional) Führen Sie auf der Seite [!DNL Menus] einen der folgenden Schritte aus:

   * Klicken Sie auf **[!UICONTROL History]**, um alle vorgenommenen Änderungen wiederherzustellen.

      Siehe [Verwenden der Option Verlauf](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Klicken **[!UICONTROL Live]**.

      Siehe [Live-Einstellungen anzeigen](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Klicken **[!UICONTROL Push Live]**.

      Siehe [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Bearbeiten eines Menüs {#task_0770DBFD0C7046169097FB6F771B9114}

Sie können die Einstellungen jedes hinzugefügten Menüs bearbeiten.

<!-- 

t_editing_a_menu.xml

 -->

>[!NOTE]
>
>Verweisen Sie auf das Menü in Ihrer Präsentationsvorlage, damit es auf der Website angezeigt wird.

**So bearbeiten Sie ein Menü**

1. Klicken Sie im Produktmenü auf **[!UICONTROL Design]** > **[!UICONTROL Navigation]** > **[!UICONTROL Menus]**.
1. Klicken Sie auf der Seite [!DNL Menus] rechts neben dem Menünamen auf **[!UICONTROL Edit]**.
1. Legen Sie auf der Seite [!DNL Edit Menu] die gewünschten Optionen fest.

   Siehe die Tabelle der Optionen unter [Hinzufügen eines neuen Menüs](../c-about-design-menu/c-about-menus.md#task_EE171532D3AE477FAFE8C2F4077A6D73).
1. Klicken **[!UICONTROL Save Changes]**.
1. (Optional) Führen Sie auf der Seite [!DNL Menus] einen der folgenden Schritte aus:

   * Klicken Sie auf **[!UICONTROL History]**, um alle vorgenommenen Änderungen wiederherzustellen.

      Siehe [Verwenden der Option Verlauf](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Klicken **[!UICONTROL Live]**.

      Siehe [Live-Einstellungen anzeigen](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Klicken **[!UICONTROL Push Live]**.

      Siehe [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Löschen eines Menüs {#task_645E212311A045CD8D9D906878165F47}

Sie können alle hinzugefügten Menüs löschen.

<!-- 

t_deleting_a_menu.xml

 -->

**So löschen Sie ein Menü**

1. Klicken Sie im Produktmenü auf **[!UICONTROL Design]** > **[!UICONTROL Navigation]** > **[!UICONTROL Menus]**
1. Klicken Sie auf der Seite [!DNL Menus] rechts neben dem Menünamen auf **[!UICONTROL Delete]**.
1. Klicken Sie im Dialogfeld [!DNL Confirmation] auf **[!UICONTROL OK]**.
1. (Optional) Führen Sie einen der folgenden Schritte aus:

   * Klicken Sie auf **[!UICONTROL History]**, um alle vorgenommenen Änderungen wiederherzustellen.

      Siehe [Verwenden der Option Verlauf](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Klicken **[!UICONTROL Live]**.

      Siehe [Live-Einstellungen anzeigen](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Klicken **[!UICONTROL Push Live]**.

      Siehe [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).
