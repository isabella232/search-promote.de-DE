---
description: Die Ansichten der Daten zeigen die Suchergebnisse mit den Metadatenfeldern an. Jede Spalte ist ein Metadatenfeld und jede Zeile wird aus einer Abfrage der Suche generiert. Passen Sie die Ansichten an, indem Sie Spalten auswählen und neu anordnen. Data Ansichten können auch benutzerdefinierte Titel und Beschreibungen haben.
seo-description: Die Ansichten der Daten zeigen die Suchergebnisse mit den Metadatenfeldern an. Jede Spalte ist ein Metadatenfeld und jede Zeile wird aus einer Abfrage der Suche generiert. Passen Sie die Ansichten an, indem Sie Spalten auswählen und neu anordnen. Data Ansichten können auch benutzerdefinierte Titel und Beschreibungen haben.
seo-title: Info zu Ansichten
solution: Target
title: Info zu Ansichten
topic: Reports,Site search and merchandising
uuid: 18930551-960d-40c2-b5b7-0807a2e11134
translation-type: tm+mt
source-git-commit: 7af85dd37f06fe506e5f57e28a25385ca7ab3db5
workflow-type: tm+mt
source-wordcount: '1063'
ht-degree: 1%

---


# Info zu Data Ansichten{#about-data-views}

Die Ansichten der Daten zeigen die Suchergebnisse mit den Metadatenfeldern an. Jede Spalte ist ein Metadatenfeld und jede Zeile wird aus einer Abfrage der Suche generiert. Passen Sie die Ansichten an, indem Sie Spalten auswählen und neu anordnen. Data Ansichten können auch benutzerdefinierte Titel und Beschreibungen haben.

## Verwenden von Data Ansichten {#concept_DCA897D074464BC1861AA47B40CC86C3}

Jedes Konto bietet die Möglichkeit, mehrere Ansichten zu erstellen. Verwenden Sie die Seite &quot;Ansichten&quot;, um diese Ansichten zu erstellen und zu bearbeiten.

Nachdem Sie eine Daten-Ansicht hinzugefügt haben, müssen Sie sie bearbeiten, um die Ansicht zu konfigurieren und anzupassen.

Siehe [Bearbeiten einer Ansicht](../c-about-reports-menu/c-about-data-views.md#task_258A367896C24DD498C755925EA8F516).

Sie können eine bestehende Ansicht kopieren, um eine neue Ansicht zu erstellen.

Siehe [Kopieren einer Ansicht](../c-about-reports-menu/c-about-data-views.md#task_78D4C2799BC84677843ED4CA1CD205AF).

## Hinzufügen einer Ansicht {#task_A20FEB2E1CA1444D816D2F5F4B6E5B2D}

Sie können der Ansicht [!DNL Data Views] eine Datendatei hinzufügen, um die Werte der einzelnen Metadatenfelder mit einer Abfrage anzuzeigen.

Nachdem Sie eine Daten-Ansicht hinzugefügt haben, müssen Sie sie bearbeiten, um die Ansicht zu konfigurieren und anzupassen.

Siehe [Bearbeiten einer Ansicht](../c-about-reports-menu/c-about-data-views.md#task_258A367896C24DD498C755925EA8F516).

**So fügen Sie eine Ansicht hinzu**

1. Klicken Sie im Produktmenü auf **[!UICONTROL Reports]** > **[!UICONTROL Data Views]**.
1. Klicken Sie auf der Seite [!DNL Data Views] auf **[!UICONTROL Add New Data View]**.
1. Geben Sie im Dialogfeld [!DNL Add New Data View] im Feld [!DNL Title] den Namen der zu erstellenden Ansicht ein.
1. Klicken **[!UICONTROL Add]**.

## Bearbeiten einer Ansicht {#task_258A367896C24DD498C755925EA8F516}

Wenn Sie der Ansicht [!DNL Data Views] eine Datenbeschreibung hinzufügen, verwenden Sie Bearbeiten, um den Namen und die Beschreibung der Daten zu ändern oder die Anzeige der einzelnen Metadatenfelder zu verschieben, ein- oder auszublenden.

Sie können auch eine ausgewählte Ansicht sperren oder entsperren.

Siehe [Hinzufügen einer Ansicht](../c-about-reports-menu/c-about-data-views.md#task_A20FEB2E1CA1444D816D2F5F4B6E5B2D).

**So bearbeiten Sie eine Ansicht**

1. Klicken Sie im Produktmenü auf **[!UICONTROL Reports]** > **[!UICONTROL Data Views]**.
1. Klicken Sie auf der Seite [!DNL Data Views] in der Tabellenspalte [!DNL Actions] in der Zeile mit der zu ändernden Ansicht auf **[!UICONTROL Edit]**.
1. Legen Sie auf der Seite [!DNL Data Views Editor] die gewünschten Optionen fest.

   Der Datenfeld-Editor verfügt über alle Steuerelemente zum Ausblenden, Anzeigen und Verschieben von Feldspalten auf der Ansicht &quot;Daten&quot;.

   Bei der Ansicht einer Ansicht zeigt die Tabelle auch die folgenden zusätzlichen Spaltenfelder an, die nicht bearbeitet werden können: Rangansicht, Relevanz und Ergebnis (insgesamt). Diese drei speziellen Felder stellen die Relevanzwerte, Rankenwerte und Gesamtwerte für jedes Ergebnis dar.

   <table> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> <p>Option </p> </th> 
      <th colname="col2" class="entry"> <p>Beschreibung </p> </th> 
      </tr> 
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <p>Titel </p> </td> 
      <td colname="col2"> <p>Der Name der Daten-Ansicht. Der Name wird oben rechts bei der Ansicht der Ansicht angezeigt. </p> <p>Siehe <a href="../c-about-reports-menu/c-about-data-views.md#task_FD0D2CE53DF84CBD9220AD7CA920011F" type="task" format="dita" scope="local"> Anzeigen einer Ansicht</a>. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Beschreibung </p> </td> 
      <td colname="col2"> <p>(Optional) Enthält eine Beschreibung der Ansicht der Daten. Die Beschreibung wird zwischen dem Titellamen der Ansicht und dem Textfeld <span class="wintitle"> Neue Suche</span> angezeigt. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Suchparameter </p> </td> 
      <td colname="col2"> <p>Hier können Sie Standardsuchparameter angeben. Wenn die Ansicht der Daten zum ersten Mal angezeigt wird, werden diese CGI-Parameter automatisch angehängt. </p> <p>Ändern oder löschen Sie nicht <span class="codeph"> sp_cs</span> oder <span class="codeph"> sp_f</span>. Diese Parameter sind unabhängig vom bevorzugten Zeichensatz des Kontos für die Ansicht von Daten unverzichtbar. </p> <p>Siehe <a href="../c-appendices/c-cgiparameters.md#reference_582E85C3886740C98FE88CA9DF7918E8" type="reference" format="dita" scope="local"> CGI-Parameter für die Backend-Suche</a>. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Status sperren </p> </td> 
      <td colname="col2"> <p>Hiermit können Sie die Ansicht der Daten sperren oder entsperren. </p> <p>Sie können eine gesperrte Datendatei nur mit einem Kennwort und einem Benutzernamen Ansicht haben. Der Benutzer muss ein aktuelles Mitglied des Kontos sein. </p> <p>Auf eine nicht gesperrte Ansicht wird ohne Kennwort oder Benutzerkonto zugegriffen. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Bestellung </p> </td> 
      <td colname="col2"> <p> Hiermit können Sie die Spaltenreihenfolge ändern, indem Sie die Zahl im Textfeld <span class="wintitle"> Bestellung</span> bearbeiten. Sie können auch eine Zeile per Drag &amp; Drop verschieben, um die Spaltenreihenfolge zu ändern. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Einschließlich </p> </td> 
      <td colname="col2"> <p> Hiermit können Sie die Anzeige der Spalte aktivieren oder deaktivieren. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>URL als Bild anzeigen </p> </td> 
      <td colname="col2"> <p>Zeigt Miniaturansichten und Bilder in dieser Spalte an, wenn das Suchergebnis für diese Spalte eine URL zurückgibt. </p> <p>Die URL wird vom Schemanamen oder Protokoll entfernt, bevor sie zum Wert des Attributs <span class="codeph"> src</span> eines Image-Tags wird. </p> <p>Wenn das zurückgegebene Suchergebnis nicht wie eine URL zu einem Bild aussieht, wird eine angezeigt. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Feldlänge </p> </td> 
      <td colname="col2"> <p>Legt die Anzahl der Zeichen fest, die als Ergebnis auf der Ansicht angezeigt werden. </p> <p>Der Standardwert ist 100 Zeichen. </p> <p>Einige Felder, wie z. B. der Rang und das Datumsfeld, haben keine anpassbaren Feldlängen. </p> </td> 
      </tr> 
    </tbody> 
    </table>

1. Klicken **[!UICONTROL Save Changes]**.
1. (Optional) Führen Sie einen der folgenden Schritte aus:

   * Klicken Sie auf **[!UICONTROL History]**, um alle vorgenommenen Änderungen wiederherzustellen.

      Siehe [Verwenden der Option Verlauf](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Klicken **[!UICONTROL Live]**.

      Siehe [Live-Einstellungen anzeigen](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Klicken **[!UICONTROL Push Live]**.

      Siehe [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Kopieren einer Ansicht {#task_78D4C2799BC84677843ED4CA1CD205AF}

Sie können eine bestehende Datendatei auf der [!DNL Data Views]-Ansicht kopieren, um eine neue Ansicht zu erstellen.

Nachdem Sie eine Ansicht kopiert haben, können Sie sie durch Bearbeiten der Ansicht weiter anpassen.

Siehe [Bearbeiten einer Ansicht](../c-about-reports-menu/c-about-data-views.md#task_258A367896C24DD498C755925EA8F516).

**So kopieren Sie eine Ansicht**

1. Klicken Sie im Produktmenü auf **[!UICONTROL Reports]** > **[!UICONTROL Data Views]**.
1. Klicken Sie auf der Seite [!DNL Data Views] in der Tabellenspalte [!DNL Actions] in der Zeile mit der zu kopierenden Ansicht auf **[!UICONTROL Copy]**.
1. Geben Sie auf der Seite [!DNL Copy Data View] im Textfeld [!DNL New Title] den neuen Namen ein, dem Sie die Daten-Ansicht zuweisen möchten.
1. Klicken **[!UICONTROL Copy]**.
1. (Optional) Führen Sie einen der folgenden Schritte aus:

   * Klicken Sie auf **[!UICONTROL History]**, um alle vorgenommenen Änderungen wiederherzustellen.

      Siehe [Verwenden der Option Verlauf](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Klicken **[!UICONTROL Live]**.

      Siehe [Live-Einstellungen anzeigen](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Klicken **[!UICONTROL Push Live]**.

      Siehe [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Löschen einer Ansicht {#task_61C32F8F00A549A5A3E7EDDA6F537098}

Sie können eine Datendatei auf der [!DNL Data Views]-Ansicht löschen, die Sie nicht mehr benötigen oder verwenden.

**So löschen Sie eine Ansicht**

1. Klicken Sie im Produktmenü auf **[!UICONTROL Reports]** > **[!UICONTROL Data Views]**.
1. Klicken Sie auf der Seite [!DNL Data Views] in der Tabellenspalte [!DNL Actions] in der Zeile mit der zu entfernenden Ansicht auf **[!UICONTROL Delete]**.
1. Klicken Sie auf der Seite [!DNL Delete Data View] auf **Löschen**.
1. (Optional) Führen Sie einen der folgenden Schritte aus:

   * Klicken Sie auf **[!UICONTROL History]**, um alle vorgenommenen Änderungen wiederherzustellen.

      Siehe [Verwenden der Option Verlauf](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Klicken **[!UICONTROL Live]**.

      Siehe [Live-Einstellungen anzeigen](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Klicken **[!UICONTROL Push Live]**.

      Siehe [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Anzeigen einer Ansicht {#task_FD0D2CE53DF84CBD9220AD7CA920011F}

Sie können [!DNL View] auf der [!DNL Data Views]-Seite verwenden, um eine ausgewählte Ansicht anzuzeigen.

Die ausgewählte Ansicht wird in einem separaten Browserfenster geöffnet.

**So Ansicht einer Ansicht**

1. Klicken Sie im Produktmenü auf **[!UICONTROL Reports]** > **[!UICONTROL Data Views]**.
1. Führen Sie einen der folgenden Schritte aus:

   * Klicken Sie auf der Seite [!DNL Data Views] in der Tabellenspalte [!DNL Title] auf den Namen der Ansicht, die Sie öffnen möchten.

   * Klicken Sie auf der Seite [!DNL Data Views] in der Tabellenspalte [!DNL Actions] in der Zeile mit der zu öffnenden Ansicht auf **[!UICONTROL View]**.

