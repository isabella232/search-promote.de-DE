---
description: Sie können Inkrementellen Index verwenden, um "Teile"Ihrer Live- oder Stage-Website zu indizieren, z. B. eine Sammlung häufig geänderter Seiten.
seo-description: Sie können Inkrementellen Index verwenden, um "Teile"Ihrer Live- oder Stage-Website zu indizieren, z. B. eine Sammlung häufig geänderter Seiten.
seo-title: Info zu Inkrementalindex
solution: Target
subtopic: Incremental Index
title: Info zu Inkrementalindex
topic: Index,Site search and merchandising
uuid: b1ee9b08-dcbe-4ffe-b0b4-d379daaac9b5
translation-type: tm+mt
source-git-commit: 552f93f1f630c64bbe3d5c8a87c4f5895ae6868c
workflow-type: tm+mt
source-wordcount: '1377'
ht-degree: 1%

---


# Info zu Inkrementalindex{#about-incremental-index}

Sie können Inkrementellen Index verwenden, um &quot;Teile&quot;Ihrer Live- oder Stage-Website zu indizieren, z. B. eine Sammlung häufig geänderter Seiten.

## Inkrementellen Index verwenden {#concept_A7770F0552D14C47B3DDB65DB78FFFEE}

Ein inkrementeller Index dauert nur wenige Sekunden und ist nützlich auf Websites mit großer Kapazität, die viele Stunden bis zur vollständigen Indexierung dauern können.

Wenn Sie einen inkrementellen Index generieren, werden Statusinformationen angezeigt, wie z. B. die Beginn-, Verstrichzeit- und Fehlermeldungen während der Indexierung. Informationen zum Status des letzten Index werden ebenfalls angezeigt.

Sie können den inkrementellen Indexierungsvorgang jederzeit beenden oder neu starten.

Während der neue inkrementelle Index für Ihre Live-Website erstellt wird, können Kunden Ihre Site weiterhin mit Ihrem letzten inkrementellen Index suchen.

## Konfigurieren eines inkrementellen Indexes einer gestaffelten Website {#task_46A367B0786C4C90BFFA5D3F95FD86C0}

Sie können festlegen, welche Webseiten in den inkrementellen Index aufgenommen werden sollen, indem Sie URLs und URL-Masken für Websites angeben.

**So konfigurieren Sie einen inkrementellen Index einer gestaffelten Website**

1. Klicken Sie im Produktmenü auf **[!UICONTROL Index]** > **[!UICONTROL Incremental Index]** > **[!UICONTROL Configuration]**.
1. Verwenden Sie auf der **[!UICONTROL Incremental Index Configuration]** Seite die verschiedenen Felder, um anzugeben, welche Seiten Sie indizieren möchten.

   <table> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> <p>Feld </p> </th> 
      <th colname="col2" class="entry"> <p>Beschreibung </p> </th> 
      </tr> 
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <p>hinzufügen oder Aktualisieren von URLs </p> </td> 
      <td colname="col2"> <p>Geben Sie URLs an. </p> <p>Der Suchroboter indiziert nur die angegebenen Dokumente, die sich seit der letzten Indexierung geändert haben. </p> <p>Darüber hinaus folgt der Suchroboter Links, die in den angegebenen Dokumenten enthalten sind, und indiziert nur die Dokumente, die sich geändert haben. </p> <p>Dieses Feld darf nur Dokument-URLs und keine Masken enthalten, wie im folgenden Beispiel dargestellt: </p> <p> 
        <code>
          https://www.mydomain.com/products/new.html 
        </code> </p> <p>Sie können die folgenden Suchbegriffe mit der URL verwenden: </p> <p> 
        <ul id="ul_62D1082ACBD547D092B10D72C56A3A1E"> 
          <li id="li_32C2B21DE75C4459908384CC44822F7D"> 
          <code>
            noindex 
          </code> <p>Wenn Sie den Text auf der Seite, der mit einer angegebenen URL übereinstimmt, nicht indizieren möchten, aber die Links der Seite befolgen möchten, fügen Sie ihn <code>
              noindex 
            </code> nach der URL wie im folgenden Beispiel hinzu: </p> <p> 
            <code>
              https://www.mydomain.com/products/new.html noindex 
            </code> </p> <p>Achten Sie darauf, dass Sie <code>
              noindex 
            </code> von der URL mit einem Leerzeichen getrennt sind. Komma ist kein gültiges Trennzeichen. </p> </li> 
          <li id="li_33AB62B669084BF7B976F4308715E435"> 
          <code>
            nofollow 
          </code> <p>Wenn Sie den Text auf der Seite indizieren möchten, der mit der angegebenen URL übereinstimmt, aber nicht den Links der Seite folgen möchten, fügen Sie ihn <code>
              nofollow 
            </code> nach der URL wie im folgenden Beispiel hinzu: </p> <p> 
            <code>
              https://www.mydomain.com/products/new.html nofollow 
            </code> </p> <p> Achten Sie darauf, dass Sie <code>
              nofollow 
            </code> von der URL mit einem Leerzeichen getrennt sind. Komma ist kein gültiges Trennzeichen. </p> </li> 
        </ul> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Suchen und Aktualisieren von URL-Masken </p> </td> 
      <td colname="col2"> <p>Geben Sie einfache URL-Masken an - vollständigen Pfad, partiellen Pfad oder Pfade, die Platzhalter oder reguläre Ausdruck verwenden. </p> <p>Der Suchroboter findet alle passenden Dokumente und Indizes nur diejenigen Dokumente, die sich seit der letzten Indexierung geändert haben. </p> <p>Darüber hinaus folgt der Suchroboter Links, die in den entsprechenden Dokumenten und Indizes enthalten sind, nur denen, die sich geändert haben. Beispiel: </p> <p> 
      <code>
        https://www.mydomain.com/products/household/*.html 
      </code> </p> <p>Sie können auch reguläre Ausdruck wie im folgenden Beispiel verwenden: </p> <p> 
      <code>
        regexp ^https://www\.mydomain\.com/products/household/.*\.html$ 
      </code> </p> <p>Siehe <a href="../c-appendices/r-regular-expressions.md#reference_B5BA7D61D82E4109A01D2A2D964E3A6A" type="reference" format="dita" scope="local"> Reguläre Ausdrücke</a>. </p> <p>Sie können auch die Suchbegriffe <code>
        nofollow 
      </code> und <code>
        noindex 
      </code> wie in <span class="uicontrol"> Hinzufügen oder Aktualisieren von URLs </span> oben beschrieben verwenden. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>URL-Masken einschließen und ausschließen </p> </td> 
      <td colname="col2"> <p>Geben Sie einfache URL-Masken ein- oder ausschließen an - vollständigen Pfad, partiellen Pfad oder Pfade, die Platzhalter oder reguläre Ausdruck verwenden. </p> <p>Der Suchroboter findet und indiziert ("einschließen") oder ignoriert ("ausschließen") Dokumente auf Basis des angegebenen Maskentyps. </p> <p> Beim Indizieren einer Site werden die Anweisungen in der Reihenfolge des Erscheinungsbilds befolgt. Beispielsweise die folgende Liste von Masken: </p> <p> 
      <code>
        include https://www.mydomain.com/products/household/lightbulbs*.html 
      </code> </p> <p> 
      <code>
        exclude https://www.mydomain.com/products/ 
      </code> </p> <p>indiziert die Seiten <code>
        lightbulbs1.html 
      </code> und <code>
        lightbulbs2.html 
      </code>. Es werden jedoch keine anderen Seiten indiziert, die im Produktverzeichnis aufgeführt sind. </p> <p>Eine zuerst angezeigte URL-Maske hat immer Vorrang vor einer URL, die später in der Liste angezeigt wird. Wenn der Suchroboter außerdem auf ein Dokument trifft, das sowohl einer Einschluss- als auch einer Ausschlussmaske entspricht, hat die zuerst aufgeführte Maske Vorrang. </p> <p>Sie können auch die Suchbegriffe <code>
        nofollow 
      </code> und <code>
        noindex 
      </code> wie in <span class="uicontrol"> Hinzufügen oder Aktualisieren von URLs </span> oben beschrieben verwenden. </p> <p>Siehe <a href="../c-about-settings-menu/c-about-crawling-menu.md#concept_8039DFC53FF3410AA494D602F71BA164" type="concept" format="dita" scope="local"> Informationen zu URL-Masken</a>. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Datumsmasken einschließen und ausschließen </p> </td> 
      <td colname="col2"> <p>Geben Sie einfach Datenmasken ein- oder ausschließen an - vollständigen Pfad, partiellen Pfad oder Pfade, die Platzhalter oder reguläre Ausdruck verwenden. </p> <p>Der Suchroboter findet und indiziert ("einschließen") oder ignoriert ("ausschließen") Dokumente, die sowohl auf der URL als auch dem Datum der Dokumente basieren. </p> <p>Sie können die folgenden Arten von Datumsmasken verwenden: </p> <p> 
      <ul id="ul_8958ED54C8EF405AA259236595ED3ABA"> 
      <li id="li_0A7841767E004F088CA6FA42E99B9F32"> 
      <code>
        include-days NNN 
      </code> <p>Der Suchroboter indiziert alle Dokumente, die mit der angegebenen URL-Maske übereinstimmen und mindestens NN Tage alt sind. </p> <p>Sie können der URL-Maske einen oder mehrere der folgenden Suchbegriffe folgen: 
        <ul id="ul_22A38D5F38B344ABB02B16EB1865813B"> 
        <li id="li_B89CC37DC2A1428185E86FFCB9DDB193">nofollow </li> 
        <li id="li_C2579B3A338D4AF987C3F518806734B0">noindex </li> 
        <li id="li_0527BF7103F34B83AC3E684069B899F7">server-date </li> 
        </ul> </p> <p>Beispielsweise enthält die folgende Maske alle Dokumente im Ordner /archive/support, die 0 Tage oder älter sind: </p> <p> 
        <code>
          include-days 0 https://www.mydomain.com/archive/support/ 
        </code> </p> </li> 
      <li id="li_7663ABED40DD4E159F746E4F92BB6407"> 
      <code>
        include-date YYYY-MM-DD 
      </code> <p>Der Suchroboter indiziert alle Dokumente, die mit der angegebenen URL-Maske übereinstimmen und älter als das Datum JJJJ-MM-TT sind. </p> <p>Sie können der URL-Maske einen oder mehrere der folgenden Suchbegriffe folgen: </p> <p> 
        <ul id="ul_57BF37A413BB4A4D962863DACE56F395"> 
        <li id="li_88CAB9AB583B4754A5C53478BD1108FF">nofollow </li> 
        <li id="li_999E1CD34FDE4A1B9C332B4AA8C2887D">noindex </li> 
        <li id="li_05646FACF3524D2A9E201A23770E357F"> server-date </li> 
        </ul> </p> <p>Im folgenden Maskenbeispiel werden alle Dokumente im Ordner "/archive/"mit Datum vor dem 25. Juli 2011 aufgeführt: </p> <p> 
        <code>
          include-date 2011-07-25 https://www.mydomain.com/archive/ 
        </code> </p> </li> 
      <li id="li_172692DEDA8744B3AA492701D24C2D80"> 
      <code>
        exclude-days NNN 
      </code> <p>Deaktivieren Sie die Indexierung aller Dokumente, die mit der angegebenen URL-Maske übereinstimmen und mindestens NN Tage alt sind. </p> <p>Optional können Sie der URL-Maske nach dem Suchbegriff folgen <code>
          server-date 
        </code>. </p> <p>Im folgenden Maskenbeispiel werden alle PDF-Dateien ausgeschlossen, die mindestens 90 Tage alt sind: </p> <p> 
        <code>
          exclude-days 90 *.pdf 
        </code> </p> </li> 
      <li id="li_26078517744D4AECBE1351008926CBAE"> 
      <code>
        exclude-date YYYY-MM-DD 
      </code> <p>Deaktivieren Sie die Indexierung aller Dokumente, die der angegebenen URL-Maske entsprechen und älter als das Datum JJJ-MM-TT sind. </p> <p>Optional können Sie der URL-Maske nach dem Suchbegriff folgen <code>
          server-date 
        </code>. </p> <p>Im folgenden Maskenbeispiel werden alle Dokumente im Ordner /archive/ vom 23. April 2004 oder früher ausgeschlossen: </p> <p> 
        <code>
          exclude-date 2004-04-23 https://www.mydomain.com/archive/ 
        </code> </p> </li> 
      </ul> </p> <p>Siehe <a href="../c-about-settings-menu/c-about-crawling-menu.md#concept_F4F1F58A646F4A86B8650EC46FDCEF66" type="concept" format="dita" scope="local"> Info zu Datumsmasken</a>. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>URLs löschen </p> </td> 
      <td colname="col2"> <p>Geben Sie URLs an. </p> <p>Der Suchroboter findet und löscht die angegebenen Dokumente aus Ihrem Suchindex. Wenn sich eine bestimmte Seite bereits in Ihrem Suchindex befindet, löscht der Roboter sie, bevor er andere Seiten hinzufügt oder aktualisiert. </p> <p>Dieses Feld darf nur Dokument-URLs und keine Masken enthalten. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>URL-Masken suchen und löschen </p> </td> 
      <td colname="col2"> <p>Geben Sie einfache URL-Masken an - vollständigen Pfad, partiellen Pfad oder Masken, die Platzhalter oder reguläre Ausdruck verwenden. </p> <p>Wenn die angegebene URL-Maske mit Seiten im Suchindex übereinstimmt, löscht der Suchroboter die Seiten, bevor er andere Seiten hinzufügt oder aktualisiert. Beispiel: </p> <p> 
      <code>
        https://www.mydomain.com/products/1998/household/* 
      </code> </p> <p>Sie können auch reguläre Ausdruck wie im folgenden Beispiel verwenden: </p> <p> 
      <code>
        regexp ^https://www\.mydomain\.com/products/199[567]/.*$ 
      </code> </p> <p>Siehe <a href="../c-appendices/r-regular-expressions.md#reference_B5BA7D61D82E4109A01D2A2D964E3A6A" type="reference" format="dita" scope="local"> Reguläre Ausdrücke</a>. </p> </td> 
      </tr> 
    </tbody> 
    </table>

1. Klicken **[!UICONTROL Save Changes]**.
1. (Optional) Führen Sie einen der folgenden Schritte aus:

   * Klicken Sie auf **[!UICONTROL History]** , um alle vorgenommenen Änderungen wiederherzustellen.

      Siehe [Verwenden der Option](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)Verlauf.

   * Klicken **[!UICONTROL Live]**.

      Siehe [Live-Einstellungen](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)anzeigen.

   * Klicken **[!UICONTROL Push Live]**.

      Siehe [Pushing-Einstellungen](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Einstellen des Zeitplans für den inkrementellen Index für eine Live-Website {#task_2A46BA189ECC4317A9D5C6E99A336F33}

Sie können die Häufigkeit des inkrementellen Index und die Basiszeit auswählen, die zum Durchsuchen und Aktualisieren des inkrementellen Index verwendet wird.

Die von Ihnen ausgewählte Zeit ist lokal gemäß der Zeitzone, die in den Kontoeinstellungen konfiguriert ist.

Siehe [Konfigurieren der Kontoeinstellungen](../c-about-settings-menu/c-about-account-options-menu.md#task_80A38D0C8E4F453395BD67B81E4B45D9).

Webserver sollen oft mitten in der Nacht zur Wartung aussteigen. Wenn Ihr Server während einer geplanten Indexzeit ausfällt, schlägt der Indexierungsvorgang fehl. Stellen Sie sicher, dass Sie eine Tageszeit auswählen, zu der der Webserver verfügbar ist.

Der Index-Plan gilt nur für Ihren Live-Index. Sie können keine Stage-Indizes planen.

**So legen Sie den inkrementellen Indexzeitplan für eine Live-Website fest**

1. Klicken Sie im Produktmenü auf **[!UICONTROL Index]** > **[!UICONTROL Incremental Index]** > **[!UICONTROL Live Schedule]**.
1. Wählen Sie auf der **[!UICONTROL Incremental Index Schedule]** Seite &quot;In&quot;in der **[!UICONTROL Incrementally Index]** Dropdown-Liste die Indexierungsfrequenz in Stunden oder Minuten aus.
1. Wählen Sie in der **[!UICONTROL Base Time]** Dropdown-Liste die Startzeit aus, zu der Sie einen neuen Inkrementalindex neu generieren möchten.
1. Klicken **[!UICONTROL Save Changes]**.

## Ausführen eines inkrementellen Indexes einer Live- oder Staged-Website {#task_9BFB6157F3884B2FAECB7E0E9CA318CB}

Sie können Inkrementellen Index verwenden, um &quot;Teile&quot;Ihrer Live- oder Stage-Website zu indizieren, z. B. eine Sammlung häufig geänderter Seiten.

**So führen Sie einen inkrementellen Index einer Live- oder Stage-Website aus**

1. Führen Sie im Produktmenü einen der folgenden Schritte aus:

   * Klicken Sie auf **[!UICONTROL Index]** > **[!UICONTROL Incremental Index]** > **[!UICONTROL Live Index]**.

   * Klicken Sie auf **[!UICONTROL Index]** > **[!UICONTROL Incremental Index]** > **[!UICONTROL Staged Index]**.

1. Klicken **[!UICONTROL Incremental Index Now]**.
1. (Optional) Wenn Indizierungsfehler aufgetreten sind, klicken Sie auf **[!UICONTROL View Errors]** , um das zugehörige Protokoll Ansicht.

## Anzeigen des inkrementellen Indexprotokolls einer Live- oder Stage-Website {#task_E668E1F1240C476DAA1CA783DC728232}

Wenn ein inkrementeller Index oder ein gestaffelter inkrementeller Index abgeschlossen ist, können Sie das zugehörige Protokoll zur Fehlerbehebung für eingetretene Fehler Ansicht haben.


Protokolle können weder exportiert noch gespeichert werden. Das Protokoll bleibt bis zum Auftreten des neuen Indexes zur Ansicht verfügbar.

**Zur Ansicht des inkrementellen Indexprotokolls einer Live- oder Stage-Website**

1. Führen Sie im Produktmenü einen der folgenden Schritte aus:

   * Klicken Sie auf **[!UICONTROL Index]** > **[!UICONTROL Incremental Index]** > **[!UICONTROL Live Log]**.

   * Klicken Sie auf **[!UICONTROL Index]** > **[!UICONTROL Incremental Index]** > **[!UICONTROL Staged Log]**.

1. Führen Sie auf der Protokollseite oben oder unten einen der folgenden Schritte aus:

   * Verwenden Sie die Navigationsoptionen **[!UICONTROL First]**, **[!UICONTROL Prev]**, **[!UICONTROL Next]**, **[!UICONTROL Last]** oder **[!UICONTROL Go to line]** , um durch das Protokoll zu navigieren.

   * Verwenden Sie die Anzeigeoptionen **[!UICONTROL Errors only]**, **[!UICONTROL Wrap line]** oder **[!UICONTROL Show]** , um Ihre Anzeige zu verfeinern.

