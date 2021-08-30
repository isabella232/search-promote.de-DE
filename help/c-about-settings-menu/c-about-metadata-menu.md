---
description: Verwenden Sie das Menü Metadaten , um Suchdefinitionen und Indexinjektionen anzupassen.
solution: Target
subtopic: Metadata
title: Über das Menü "Metadaten"
topic-legacy: Settings,Site search and merchandising
uuid: f12fc863-a140-45e8-b219-3dbfdef099cd
exl-id: 53d62da9-c5bd-4c4a-bb89-743704f66f7f
source-git-commit: 95bf92df17d7832df72e8d883a22f9063e53a18d
workflow-type: tm+mt
source-wordcount: '8028'
ht-degree: 1%

---

# Über das Menü &quot;Metadaten&quot;{#about-the-metadata-menu}

Verwenden Sie das Menü Metadaten , um Suchdefinitionen und Indexinjektionen anzupassen.

## Über Definitionen {#concept_AE48035C210145169BE067D396975620}

Sie können [!DNL Definitions] verwenden, um den Inhalt und die Relevanz der HTML- und Metadatenfelder anzupassen, die beim Senden einer Suchanfrage durch einen Kunden berücksichtigt werden.

Sie können die bereits vordefinierten Felder bearbeiten. Sie können auch neue benutzerdefinierte Felder erstellen, die auf Metadaten-Tag-Inhalten basieren. Jede Definition wird in einer einzelnen Zeile auf der Seite [!DNL Staged Definitions] angezeigt.

Siehe auch [Über Datenansichten](../c-about-reports-menu/c-about-data-views.md#concept_DCA897D074464BC1861AA47B40CC86C3).

## Hinzufügen eines neuen Meta-Tag-Felds {#task_6DF188C0FC7F4831A4444CA9AFA615E5}

Sie können Ihre eigenen Metadaten-Tag-Felder definieren und hinzufügen.

Bevor die Auswirkungen der neuen Meta-Tag-Definition für Kunden sichtbar sind, müssen Sie Ihren Site-Index neu erstellen.

**So fügen Sie ein neues Meta-Tag-Feld hinzu**

1. Klicken Sie im Produktmenü auf **[!UICONTROL Settings]** > **[!UICONTROL Metadata]** > **[!UICONTROL Definitions]**.
1. Klicken Sie auf der Seite [!DNL Definitions] auf **[!UICONTROL Add New Field]**.
1. Legen Sie auf der Seite [!DNL Add Field] die gewünschten Optionen fest.

   <table> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> <p>Option </p> </th> 
      <th colname="col2" class="entry"> <p>Beschreibung </p> </th> 
      </tr> 
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <p>Feldname </p> </td> 
      <td colname="col2"> <p>Gibt einen Namen an, mit dem auf das Feld verwiesen wird. </p> <p>Der Feldname muss den folgenden Regeln entsprechen: </p> <p> 
      <ul id="ul_D39D09CD7E7D41A59ECB6C5A6F4F263D"> 
      <li id="li_11CE852BE3C64CEF90FEC7A6E1079E13"> Der Name darf nur alphanumerische Zeichen enthalten. </li> 
      <li id="li_7FC340E7C58545C88CE9AF4AF09AD7AD"> Gedankenstriche sind im Namen zulässig, Leerzeichen jedoch nicht. </li> 
      <li id="li_996FF38457AB4C6DB22B15850A0830CC"> Sie können einen bis zu 20 Zeichen langen Namen eingeben. </li> 
      <li id="li_C1019E587995444D9587D5EA495D719E"> Beim Namen wird nicht zwischen Groß- und Kleinschreibung unterschieden, er wird jedoch genau bei der Eingabe angezeigt und gespeichert. </li> 
      <li id="li_E55404D6CE354EC89CFFEB1048A11F44"> Sie können die Namen, die in den vordefinierten Feldern vorhanden sind, nicht verwenden, wie in der Tabelle auf der Seite <span class="wintitle"> "Staged Definitions </span>"dargestellt. </li> 
      <li id="li_7CE328AE3B5F45A8A09E2DA7ECB62551"> Sie können das Wort "Beliebig"nicht als Wert eines benutzerdefinierten Feldnamens verwenden. </li> 
      <li id="li_9B8287EED1784E79BFCBBBA956705CD2"> Die Namen vordefinierter Felder können nicht bearbeitet werden. </li> 
      </ul> </p> <p> Beispiele für Feldnamen: </p> <p> 
      <ul id="ul_5881669913D04E35A6D4A6D31BEE7DF3"> 
        <li id="li_0AFFB8B516FE40F8A615C2F578F2CEA3"> Autor </li> 
        <li id="li_7F0ADFBFB21E4B84ACA8A1CEBFE344D1"> PublishDate </li> 
        <li id="li_6D1BEB3D19AC499E9227EC115AEB6296"> some-wild </li> 
      </ul> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Meta-Tag-Name(n) </p> </td> 
      <td colname="col2"> <p>Bestimmt den Inhalt, der mit dem definierten Feld verknüpft ist. </p> <p>Die Namensliste kann bis zu 255 Zeichen lang sein. Und der Name kann alle Zeichen enthalten, die im Attribut name eines HTML-Meta-Tags zulässig sind. </p> <p>Sie können mehrere Meta-Tags in einer Felddefinition angeben. </p> <p>Mehrere Werte müssen durch Kommas getrennt sein, und der am weitesten links befindliche Meta-Tag-Name, der auf einer bestimmten Webseite gefunden wird, hat Vorrang. </p> <p>Angenommen, Sie haben ein Feld mit dem Namen "auth"definiert. Der Feldname hat die zugehörigen Meta-Tags "author, dc.author". In diesem Fall wird der Inhalt des Meta-Tags "author"indiziert und über den Inhalt von "dc.author"gesucht, wenn beide Meta-Tags auf einer Web-Seite angezeigt werden. </p> <p>Benutzerdefinierte Felder müssen mindestens einen Meta-Tag-Namen in ihrer Definition enthalten. Vordefinierte Felder müssen nicht mit einem Meta-Tag verknüpft sein. Wenn jedoch ein oder mehrere Meta-Tags angegeben sind, überschreibt der Inhalt der Meta-Tags die aktuelle Datenquelle für jedes Tag. </p> <p>Wenn beispielsweise das Meta-Tag "dc.title"mit dem vordefinierten "title"-Feld verknüpft ist, wird der Inhalt des Meta-Tags "dc.title"über dem des 
      <code>
        &lt;title&gt; 
      </code> -Tag für ein bestimmtes Dokument. </p> <p>Als Einsatzmöglichkeiten bieten sich die folgenden Beispiele an: </p> <p> 
      <ul id="ul_0132E15FC19E4C0CA13CD5A12EA3BBEC"> 
      <li id="li_ECD3B194FECB4C2090CAEC8449320D3F"> dc.date </li> 
      <li id="li_09C76BC7AC7348859D01989697212E31"> Beschreibung </li> 
      <li id="li_9230C0450F9D424087D1F127048DA311"> proprietärer Tag </li> 
      </ul> </p> </td> 
    </tr> 
      <tr> 
      <td colname="col1"> <p>Datentyp </p> </td> 
      <td colname="col2"> <p>Jedem Feld ist ein Datentyp zugeordnet, z. B. Text, Zahl, Datum, Version, Rang oder Ort. Dieser Datentyp bestimmt, wie der Inhalt des Felds indiziert, durchsucht und optional sortiert wird. </p> <p>Nach Erstellung der Felddefinition können Sie den Datentyp nicht mehr ändern. </p> <p>Verwenden Sie die folgenden Informationen, um den Datentyp auszuwählen, der für die in dem Feld enthaltenen Informationen relevant ist. </p> <p> 
      <ul id="ul_A3AD5A0CF354410F836311F39151B8A6"> 
      <li id="li_9F412DA7D9EF497BA6E65F9CE10F3046"> <span class="uicontrol"> Datentypfelder  </span> vom Typ Text werden als Zeichenfolgen behandelt. </li> 
      <li id="li_AD78B75644AE40208F0239311015611F"> <span class="uicontrol"> Zahlendatenfelder  </span> werden als numerische Ganzzahl- oder Gleitkommawerte behandelt. </li> 
      <li id="li_0B46975C589148E9A7C32A8D250487B7"> <span class="uicontrol"> Datentypfelder  </span> vom Typ Datum werden als Datums-/Uhrzeitspezifikatoren behandelt. Sie können die zulässigen Datums-/Uhrzeitformate beim Hinzufügen oder Bearbeiten des neuen Felds anpassen. </li> 
      <li id="li_BB68CB1DBE0543AC9000B3DEDFB28E7E"> <span class="uicontrol"> Versionsdatentypfelder  </span> werden als numerische Daten in Freiform behandelt. Beispielsweise wird 1.2.3 vor 1.2.2 sortiert. </li> 
      <li id="li_0BA895B4DADA46528A7A4161EEB1521E"> <span class="uicontrol"> Rang- </span> Datentypfelder werden wie Felder vom Typ "Zahl"behandelt, allerdings beeinflussen sie zusätzlich die Rang-/Relevanzberechnungen in den Suchergebnissen. <p>Siehe <a href="../c-about-rules-menu/c-about-ranking-rules.md#concept_F555C076759B4E81B925441CFE707397" type="concept" format="dita" scope="local">Info zu Ranking Rules </a>. </p> </li> 
      <li id="li_459405DA437049AD88AA1FAC28F04720"> <span class="uicontrol"> Standortdatenfelder  </span> werden als physischer Ort an einem beliebigen Ort der Welt behandelt. Zu den zulässigen Standortformaten gehören die folgenden: <p> 
      <ul id="ul_D2CEBFA1A5504AA996BA2F7641AFB7F3"> 
      <li id="li_5283A2F2D5D84840B3D920C08D43654C"> 5- oder 9-stellige Postleitzahlen in Form von DDDD oder DDDD-DDDD, wobei jeder "D"eine 0-9-stellige Zahl ist. </li> 
      <li id="li_A5CD4DFC90164BC68183DB7D10603B7C"> Dreistellige Bereichscodes in Form von DDD. </li> 
      <li id="li_9DAEAE64BC7F4902B25043D998C8F56D"> Breiten-/Längengrad-Paare im Formular ±DD.DDD±DDD.DDDD, wobei die erste Zahl den Breitengrad und die zweite Zahl den Längengrad angibt. </li> 
      </ul> </p> </li> 
      </ul> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Zulassungslisten </p> </td> 
      <td colname="col2"> <p>Nur verfügbar, wenn der Datentyp <span class="uicontrol"> Text </span> oder <span class="uicontrol"> Zahl </span> ausgewählt ist. </p> <p>Separat durch Indexieren getrennte Werte im Metadateninhalt dieses Felds. </p> <p>Der Inhalt "Rot, Gelb, Grün, Blau"wird beispielsweise als vier separate Werte behandelt, anstatt als einer, wenn "Zulassungslisten"ausgewählt wird. Diese Behandlung ist am nützlichsten bei der Bereichssuche (mithilfe von 
      <code>
        sp_q_min 
      </code>, 
      <code>
        sp_q_max 
      </code> oder 
      <code>
        sp_q_exact 
      </code>) und mit dem 
      <code>
        &lt;search-field-value-list&gt; 
      </code>, 
      <code>
        &lt;search-field-values&gt; 
      </code> und 
      <code>
        &lt;search-display-field-values&gt; 
      </code>. </p> <p>Nicht verfügbar, wenn der Datentyp Version ausgewählt ist. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p> Dynamische Facette </p> </td> 
      <td colname="col2"> <p> 
        <!--NEW 2/2/2014--> <p>Hinweis: Diese Funktion ist standardmäßig nicht aktiviert. Wenden Sie sich an den technischen Support , um ihn für Ihre Verwendung zu aktivieren. Nach der Aktivierung wird sie in der Benutzeroberfläche angezeigt. </p> </p> <p>Legt die identifizierte Facette als dynamisch fest. </p> <p>Facets werden auf Meta-Tag-Feldern erstellt. Ein Meta-Tag-Feld ist eine einfache, zentrale Suchschicht der Adobe-Search&amp;Promote. Facetten hingegen sind Teil von GS (Guided Search), der allgemeinen Präsentationsschicht der Search&amp;Promote der Adobe. Facets verfügen über Meta-Tag-Felder. Meta-Tag-Felder wissen jedoch nichts über Facetten. </p> <p>Siehe <a href="../c-about-design-menu/c-about-dynamic-facets.md#concept_E65A70C9C2E04804BF24FBE1B3CAD899" format="dita" scope="local"> Über dynamische Facets </a>. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Deduplizierung zulassen </p> </td> 
      <td colname="col2"> <p>Aktivieren Sie diese Option, um die Deduplizierung für dieses Feld zu aktivieren. Das heißt, dass dieses Feld zur Suchzeit über die 
        <code>
          sp_dedupe_field 
        </code> Search CGI-Parameter. </p> <p>Siehe <a href="../c-appendices/c-cgiparameters.md#reference_DA27A8B0728246DA94994885E1353890" type="reference" format="dita" scope="local"> Search CGI parameters </a>. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Tabellenname </p> </td> 
      <td colname="col2"> <p>ordnet das angegebene Feld dauerhaft dem angegebenen Tabellennamen zu. </p> <p>Jedes Mal, wenn ein solches Feld in einem CGI-Hauptsuchparameter oder einem Vorlagentag erwähnt wird, wird der Tabellenname automatisch bereitgestellt. Diese Funktion ermöglicht die Auswahl dynamischer Facetten durch Tabellenübereinstimmungen, Sie können sie aber auch für nicht dynamische Facettenfelder verwenden, falls gewünscht. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Trennzeichen auflisten </p> </td> 
      <td colname="col2"> <p>Nur verfügbar, wenn <span class="uicontrol"> Zulassungslisten </span> ausgewählt ist. </p> <p>Gibt an, welche Zeichen einzelne Listenwerte trennen. Sie können mehrere Zeichen angeben, die jeweils als Trennzeichen für Werte behandelt werden. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Suche standardmäßig </p> </td> 
      <td colname="col2"> <p>Wenn diese Option aktiviert ist, wird der Feldinhalt durchsucht, selbst wenn das Feld in einer bestimmten Suchanfrage nicht explizit angegeben ist. Wenn Sie diese Option deaktivieren, wird das Feld nur bei Anforderung durchsucht. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Vertikales Aktualisierungsfeld </p> </td> 
      <td colname="col2"> <p> <p>Hinweis: Diese Funktion ist standardmäßig nicht aktiviert. Wenden Sie sich an den technischen Support , um ihn für Ihre Verwendung zu aktivieren. Nach der Aktivierung wird sie in der Benutzeroberfläche angezeigt. </p> </p> <p>Legt fest, dass das identifizierte Feld ein Feld für vertikale Aktualisierung sein soll. </p> <p>Vertikale Aktualisierungsfelder sind Kandidaten, die über den vertikalen Aktualisierungsprozess aktualisiert werden ( <span class="uicontrol"> Index </span> &gt; <span class="uicontrol"> Vertikale Aktualisierung </span>). Aufgrund der Art und Weise, wie vertikale Aktualisierungen vorgenommen werden, können Inhalte aus diesen Feldern nicht in Freitextsuchen durchsucht werden. Wenn Sie diese Option aktivieren, wird der Inhalt dieses Felds bei keiner Indexoperation zum "Wort"-Index hinzugefügt. Es ermöglicht auch die Aktualisierung dieses Felds während eines vertikalen Aktualisierungsvorgangs. </p> <p>Weitere Informationen zu vertikalen Updates finden Sie unter <a href="../c-about-index-menu/c-about-vertical-updates.md#concept_E65A70C9C2E04804BF24FBE1B3CAD899" format="dita" scope="local"> Über vertikale Aktualisierung </a>. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Relevanz </p> </td> 
      <td colname="col2"> <p>Sie können die Relevanz von vordefinierten und benutzerdefinierten Feldern bearbeiten. </p> <p>Die Relevanz wird im Maßstab 1-10 festgelegt. Eine Einstellung von 1 bedeutet, dass es am wenigsten relevant ist und 10 am relevantesten ist. Diese Werte werden berücksichtigt, wenn die Software die Abfrage in jedem Feld berücksichtigt. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Sortieren </p> </td> 
      <td colname="col2"> <p>Gibt an, wann die Ergebnisse anhand des benannten Felds mithilfe der Variablen 
        <code>
          sp_s 
        </code> Search CGI-Parameter. </p> <p>Siehe <a href="../c-appendices/c-cgiparameters.md#reference_DA27A8B0728246DA94994885E1353890" type="reference" format="dita" scope="local"> Search CGI parameters </a>. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Sprache  </p> </td> 
      <td colname="col2"> <p>Nur verfügbar, wenn der Datentyp <span class="uicontrol"> Rang </span>, <span class="uicontrol"> Zahl </span> oder <span class="uicontrol"> Datum </span> ausgewählt ist. </p> <p>Steuert die Sprach- und Gebietsschemakonventionen, die bei der Indizierung der Werte für Datum, Zahl und Rang für dieses Feld angewendet werden. </p> <p>Sie können die Kontosprache (Linguistik &gt; Wörter und Sprachen) anwenden. Sie können auch die Sprache anwenden, die mit dem Dokument verknüpft ist, das jede Zahl, jeden Datumswert oder eine bestimmte Sprache enthält. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Datumsformat(e) </p> </td> 
      <td colname="col2"> <p>Nur verfügbar, wenn der Datentyp <span class="uicontrol"> Datum </span> ausgewählt ist. </p> <p>Steuert die Datumsformate, die bei der Indizierung von Datumswerten für dieses Feld erkannt werden. </p> <p>Für jedes Datumsfeld wird eine Standardliste mit Datumsformat-Zeichenfolgen bereitgestellt. Sie können die Liste der Liste hinzufügen oder sie entsprechend den Anforderungen Ihrer eigenen Site bearbeiten. </p> <p>Siehe <a href="../c-appendices/r-date-formats.md#reference_4D1FC1F6B9F44857967188496D8D335B" type="reference" format="dita" scope="local"> Datumsformate </a>. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Testdatumsformate </p> </td> 
      <td colname="col2"> <p>Nur verfügbar, wenn der Datentyp <span class="uicontrol"> Datum </span> als Datentyp ausgewählt ist. </p> <p>Ermöglicht die Vorschau der von Ihnen angegebenen Datumsformate, um sicherzustellen, dass sie korrekt formatiert sind. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Zeitzone </p> </td> 
      <td colname="col2"> <p>Nur verfügbar, wenn der Datentyp <span class="uicontrol"> Datum </span> als Datentyp ausgewählt ist. </p> <p>Steuert die angenommene Zeitzone, die bei der Indizierung von Datumswerten für dieses Feld angewendet wird, die keine Zeitzone angeben. </p> <p>Wenn Ihre Kontozeitzone beispielsweise auf "America/Los Angeles"gesetzt ist und Sie <span class="uicontrol"> Zeitzone des Kontos verwenden </span> auswählen, wird der folgende Meta-Datumswert, der keine bestimmte Zeitzone aufweist, so behandelt, als wäre es die Pacific Time, wobei Sommerzeit berücksichtigt wird: </p> <p>&lt;meta name="dc.date" content="Mon, 05 Sep 201213:12:00"&gt; </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Wenigster wichtiger Rangwert </p> </td> 
      <td colname="col2"> <p>Nur verfügbar, wenn der Datentyp <span class="uicontrol"> Rang </span> als Datentyp ausgewählt ist. </p> <p>Steuert den Rangwert, der den Mindestrang eines Dokuments darstellt. </p> <p>Wenn Ihr Dokument-Ranking zwischen 0 für den niedrigsten Rang und 10 für den höchsten Rang liegt, legen Sie diesen Wert auf 0 fest. </p> <p>Wenn Ihr Dokumenten-Ranking zwischen 1 für den höchsten Rang und 10 für den niedrigsten Rang liegt, legen Sie diesen Wert auf 10 fest. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Standardwert für Rang </p> </td> 
      <td colname="col2"> <p>Nur verfügbar, wenn der Datentyp <span class="uicontrol"> Rang </span> als Datentyp ausgewählt ist. </p> <p>Steuert den Rang-Wert, der verwendet wird, wenn ein Dokument keine der für dieses Rang-Feld definierten Meta-Tags enthält. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Wichtigster Rangwert </p> </td> 
      <td colname="col2"> <p>Nur verfügbar, wenn der Datentyp <span class="uicontrol"> Rang </span> als Datentyp ausgewählt ist. </p> <p>Steuert den Rangwert, der den maximalen Rang eines Dokuments darstellt. </p> <p>Wenn Ihr Dokumenten-Ranking zwischen 0 für den niedrigsten Rang und 10 für den höchsten Rang liegt, legen Sie diesen Wert auf 10 fest. </p> <p>Wenn Ihr Dokument-Ranking zwischen 1 für den höchsten Rang und 10 für den niedrigsten Rang liegt, legen Sie diesen Wert auf 1 fest. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Standardeinheiten </p> </td> 
      <td colname="col2"> <p>Nur verfügbar, wenn der Datentyp <span class="uicontrol"> Speicherort </span> als Datentyp ausgewählt ist. </p> <p>Steuert die Behandlung von Entfernungswerten für Näherungssuchvorgänge. </p> <p>Wenn Sie die Standardeinheiten auf <span class="uicontrol"> Meilen </span> setzen, dann werden alle Kriterien für die minimale/maximale Entfernung der Nahbereichsuche, die auf dieses Feld angewendet werden (über die 
      <code>
        sp_q_min[_#] 
      </code> oder die 
      <code>
        sp_q_max[_#] 
      </code> CGI-Suchparameter) als Meilen behandelt, ansonsten als Kilometer. </p> <p>Diese Option steuert auch die Standardabstandseinheiten, die auf die Ausgabe der 
      <code>
        &lt;Search-Display-Field&gt; 
      </code> Vorlagentag für Suchergebnisse bei Anwendung auf ein Eingabefeld für die Näherungssuche. </p> <p>Siehe <a href="../c-appendices/r-about-proximity-search.md#reference_45AC6BB50609431ABD31DA46EE65360D" type="reference" format="dita" scope="local"> Über die Näherungssuche </a>. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Bereichsbeschreibung erstellen? </p> </td> 
      <td colname="col2"> <p>Nur verfügbar, wenn <span class="uicontrol"> Zahl </span> als Datentyp ausgewählt ist. </p> <p>Steuert die automatische Erstellung von Feldbereichsbeschreibungen zur Verwendung mit <span class="uicontrol"> Design </span> &gt; <span class="uicontrol"> Navigation </span> &gt; <span class="uicontrol"> Facets </span>. </p> <p>Siehe <a href="../c-about-design-menu/c-about-facets.md#concept_FA912B3B41EE493DB2F492D188457FF5" format="dita" scope="local"> Über Facets </a>. </p> <p> <p>Hinweis:  Wenn für dieses Feld <span class="uicontrol"> Vertikales Aktualisierungsfeld </span> aktiviert ist, wird das generierte Feldbereichsbeschreibungsfeld während einer vertikalen Aktualisierung aktualisiert. Es wird jedoch empfohlen, für das in <span class="uicontrol"> Bereichsfeld </span> identifizierte Feld auch <span class="uicontrol"> Vertikales Aktualisierungsfeld </span> aktiviert zu haben. </p> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Bereichsfeld </p> </td> 
      <td colname="col2"> <p>Nur verfügbar, wenn <span class="uicontrol"> Bereich-Beschreibung erstellen </span> aktiviert ist. </p> <p>Das Feld <span class="uicontrol"> Text </span> , das mit Bereichsbeschreibungen für das aktuelle Feld aktualisiert werden soll. Diese Liste enthält alle <span class="uicontrol"> Text </span>-Felder, die noch nicht mit anderen Feldern zur Generierung von Feldbereichen verwendet werden. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Bereichswerte </p> </td> 
      <td colname="col2"> <p>Nur verfügbar, wenn <span class="uicontrol"> Bereichsbeschreibung erstellen </span> aktiviert ist und ein Element <span class="uicontrol"> Bereichsfeld </span> ausgewählt ist. </p> <p>Eine durch Leerzeichen getrennte Liste von Datenpunkten, die beim Erstellen der Feldbereichsbeschreibungen verwendet werden sollen. Beispiel: </p> <code> 10&amp;nbsp;20&amp;nbsp;50&amp;nbsp;100&amp;nbsp;1000 </code> <p>Sie können diese Werte in beliebiger Reihenfolge eingeben. Die Werte werden sortiert und Dubletten werden vor dem Speichern entfernt. Sie können auch negative und nicht-ganzzahlige Werte angeben. </p> <p>Für jeden Wert dieses Felds gilt Folgendes: 
      <ul id="ul_C4B41AF5AADF4B84B9C489CE82FF7075"> 
      <li id="li_90736394A5AE4F5CA6B47687BCB627AA">Wenn der Wert kleiner ist als (&lt;) der kleinste Wert in <span class="uicontrol"> Bereichswerte </span>, wird das <span class="uicontrol"> "Less Than" Format </span> verwendet. </li> 
      <li id="li_A5C272B2D26A468CA07EB2046B2EA8A7">Wenn der Wert größer oder gleich (&gt;=) dem größten Wert in <span class="uicontrol"> Bereichswerte </span> ist, wird das <span class="uicontrol"> "Größer als" Format </span> verwendet. </li> 
      <li id="li_9DDFB70E1E824CF4819C57450C1A6DD2">Andernfalls wird ein "Bereich"gefunden, bei dem der Feldwert zwischen zwei aufeinander folgenden <span class="uicontrol"> Bereichswerten </span> (größer als (&gt;) dem kleineren Wert und kleiner oder gleich (&lt;=) dem größeren Wert) liegt und das <span class="uicontrol"> Zwischenformat </span> verwendet wird. </li> 
    </ul> </p> <p>Beispielsweise definiert der obige Beispielsatz mit Werten eine Reihe von Beschreibungen für Werte: 
    <ul id="ul_03ED30D5A19346AB8E6809BDD186A9A9"> 
      <li id="li_F97A6B3763954EFE9B6751F472AF7D20">weniger als 10 </li> 
      <li id="li_12B6F636A6444B8292E0BFE4F55032DF">größer als oder gleich 10 und kleiner als 20 </li> 
      <li id="li_545A2EAF5BD046B5AD59B77DB43DCD14">größer als oder gleich 20 und kleiner als 50 </li> 
      <li id="li_26A8CD2422524D2CBD36794C6908572A">größer als oder gleich 50 und kleiner als 100 </li> 
      <li id="li_05EBEEE68DC348E0821F1CC16D04D69C">größer als oder gleich 100 und kleiner als 10000 </li> 
      <li id="li_9513A6B519394780A6A41B80762A0370">größer als oder gleich 10000 </li> 
      </ul> </p> <p>Siehe <span class="uicontrol"> Test mit "Größer als". </span> , um die Durchführung dieser Tests zu ändern. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Format "Kleiner als" </p> </td> 
      <td colname="col2"> <p>Nur verfügbar, wenn <span class="uicontrol"> Bereichsbeschreibung erstellen </span> aktiviert ist und ein Element <span class="uicontrol"> Bereichsfeld </span> ausgewählt ist. </p> <p>Dies ist die Vorlage, mit der die Bereichsbeschreibung für Werte angegeben wird, die kleiner sind als der kleinste Wert, der unter <span class="uicontrol"> Bereichswerte </span> gefunden wurde. Der kleinste Wert wird mit dem numerischen Platzhalter-Token <span class="uicontrol"> ~N~ </span> dargestellt. Beispiel: </p> <code> Less&amp;nbsp;than&amp;nbsp;~N~ </code> <p>oder: </p> <code> ~N~&amp;nbsp;and&amp;nbsp;below </code> <p>Normalerweise wird der Wert "wie besehen"formatiert, d. h. für eine <span class="uicontrol">-Bereichswerte </span>-Definition von "5 10 20"und einen bereitgestellten Wert von 1, würde die generierte Bereichsbeschreibung einfach etwa "Weniger als 5"lauten. Wenn Sie stattdessen "4.99 und darunter"wünschen, setzen Sie <span class="uicontrol"> Precision </span> auf <span class="uicontrol"> 2 </span> und verwenden Sie folgendes Format: </p> <code> ~n~&amp;nbsp;and&amp;nbsp;below </code> <p>Im <span class="uicontrol"> "Less Than"-Format </span> bewirkt das Kleinbuchstaben <span class="uicontrol"> ~n~ </span>, dass der Wert gemäß der Einstellung <span class="uicontrol"> Precision </span> umgerundet wird.<i></i> </p> <p>Hinweis: , um einen beliebigen numerischen Platzhalter in die Bereichsbeschreibung einzuschließen, geben Sie ihn mit einem umgekehrten Schrägstrich (\)-Präfix an, z. B. <span class="uicontrol"> \~N~ </span> oder <span class="uicontrol"> \~n~ </span>. Um einen umgekehrten Schrägstrich einzufügen, geben Sie ihn mit einem anderen umgekehrten Schrägstrich an, z. B. <span class="uicontrol"> \\ </span>. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Zwischenformat </p> </td> 
      <td colname="col2"> <p>Nur verfügbar, wenn <span class="uicontrol"> Bereichsbeschreibung erstellen </span> aktiviert ist und ein Element <span class="uicontrol"> Bereichsfeld </span> ausgewählt ist. </p> <p>Dies ist die Vorlage, mit der die Bereichsbeschreibung für Werte angegeben wird, die irgendwo zwischen den kleinsten und größten Werten in <span class="uicontrol"> Bereichswerte </span> liegen. Für den angegebenen Bereich wird der Wert des unteren Bereichs mit dem numerischen Platzhalter-Token <span class="uicontrol"> ~L~ </span> dargestellt und der höhere Bereichswert wird mit dem Token <span class="uicontrol"> ~H~ </span> dargestellt. Beispiel: </p> <code> ~L~&amp;nbsp;to&amp;nbsp;~H~ </code> <p>oder: </p> <code> Between&amp;nbsp;~L~&amp;nbsp;and&amp;nbsp;~H~ </code> <p>oder: </p> <code> Less&amp;nbsp;than&amp;nbsp;~H~&amp;nbsp;and&amp;nbsp;greater&amp;nbsp;than&amp;nbsp;~L~ </code> <p>Normalerweise werden die Werte wie besehen formatiert, d. h. für eine <span class="uicontrol">-Bereichswerte </span>-Definition von "5 10 20"und einen bereitgestellten Wert von 8, würde die generierte Bereichsbeschreibung einfach etwa "Zwischen 5 und 10"lauten. Wenn Sie stattdessen "Zwischen 5 und 9.99"wünschen, wobei der höhere Wert <i>nach unten</i> angepasst wird, setzen Sie <span class="uicontrol"> Precision </span> auf <span class="uicontrol"> 2 </span> und verwenden Sie folgendes Format: </p> <code> Between&amp;nbsp;~L~&amp;nbsp;and&amp;nbsp;~h~ </code> <p>Ebenso kann <span class="uicontrol"> ~L~ </span> durch <span class="uicontrol"> ~l~ </span> ersetzt werden, damit der niedrigere Wert <i>upwards</i> angepasst wird, auch entsprechend der Einstellung <span class="uicontrol"> Precision </span> . Das bedeutet, dass eine Definition wie folgt lautet: </p> <code> Between&amp;nbsp;~l~&amp;nbsp;and&amp;nbsp;~H~ </code> <p>mit einem <span class="uicontrol"> Präzision </span> -Wert von <span class="uicontrol"> 2 </span> würde "Zwischen 5.01 und 10"erstellen. </p> <p>Der Kleinbuchstabe <span class="uicontrol"> ~l~ </span> bewirkt, dass der niedrigere Wert gemäß der Einstellung <span class="uicontrol"> Präzision </span> gerundet wird, und der Kleinbuchstabe <span class="uicontrol"> ~h~ </span> führt dazu, dass der höhere Wert <i>nach unten</i> gerundet wird.<i></i> </p> <p>Hinweis: , um einen beliebigen numerischen Platzhalter in die Bereichsbeschreibung einzuschließen, geben Sie ihn mit einem umgekehrten Schrägstrich (\)-Präfix an, z. B. <span class="uicontrol"> \~L~ </span> oder <span class="uicontrol"> \~h~ </span>. Um einen umgekehrten Schrägstrich einzufügen, geben Sie ihn mit einem anderen umgekehrten Schrägstrich an, z. B. <span class="uicontrol"> \\ </span>. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Format "Größer als" </p> </td> 
      <td colname="col2"> <p>Nur verfügbar, wenn <span class="uicontrol"> Bereichsbeschreibung erstellen </span> aktiviert ist und ein Element <span class="uicontrol"> Bereichsfeld </span> ausgewählt ist. </p> <p>Dies ist die Vorlage, mit der die Bereichsbeschreibung für Werte angegeben wird, die größer sind als der größte Wert in <span class="uicontrol"> Bereichswerte </span>. Der größte Wert wird mit dem numerischen Platzhalter-Token <span class="uicontrol"> ~N~ </span> dargestellt. Beispiel: </p> <code> Greater&amp;nbsp;than&amp;nbsp;~N~ </code> <p>oder: </p> <code> ~N~&amp;nbsp;and&amp;nbsp;above </code> <p>Normalerweise wird der Wert "wie besehen"formatiert, d. h. für eine <span class="uicontrol">-Bereichswerte </span>-Definition von "5 10 20"und einen bereitgestellten Wert von 30, wäre die generierte Bereichsbeschreibung einfach etwa "Größer als 20". Wenn Sie stattdessen "20.01 und höher"wünschen, setzen Sie <span class="uicontrol"> Precision </span> auf <span class="uicontrol"> 2 </span> und verwenden Sie folgendes Format: </p> <code> ~n~&amp;nbsp;and&amp;nbsp;above </code> <p>Im Format <span class="uicontrol"> "Größer als" </span> bewirkt die Kleinschreibung <span class="uicontrol"> ~n~ </span>, dass der Wert gemäß der Einstellung <span class="uicontrol"> Precision </span> gerundet wird <i>up</i>. </p> <p>Hinweis: , um einen beliebigen numerischen Platzhalter in die Bereichsbeschreibung einzuschließen, geben Sie ihn mit einem umgekehrten Schrägstrich (\)-Präfix an, z. B. <span class="uicontrol"> \~N~ </span> oder <span class="uicontrol"> \~n~ </span>. Um einen umgekehrten Schrägstrich einzufügen, geben Sie ihn mit einem anderen umgekehrten Schrägstrich an, z. B. <span class="uicontrol"> \\ </span>. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Genauigkeit </p> </td> 
      <td colname="col2"> <p>Nur verfügbar, wenn <span class="uicontrol"> Bereichsbeschreibung erstellen </span> aktiviert ist und ein Element <span class="uicontrol"> Bereichsfeld </span> ausgewählt ist. </p> <p>Ein integer -Wert, der die Anzahl der Ziffern rechts neben einem Dezimalpunkt angibt. Dies steuert auch Rundungsvorgänge. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Strip führende Nullen? </p> </td> 
      <td colname="col2"> <p>Nur verfügbar, wenn <span class="uicontrol"> Bereichsbeschreibung erstellen </span> aktiviert ist, ein Element <span class="uicontrol"> Bereichsfeld </span> ausgewählt und ein Wert ungleich null <span class="uicontrol"> Präzision </span> festgelegt wurde. </p> <p>Sollte "0.50"als ".50"angezeigt werden? </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Streichen Sie Nullen am Ende? </p> </td> 
      <td colname="col2"> <p>Nur verfügbar, wenn <span class="uicontrol"> Bereichsbeschreibung erstellen </span> aktiviert ist, ein Element <span class="uicontrol"> Bereichsfeld </span> ausgewählt und ein Wert ungleich null <span class="uicontrol"> Präzision </span> festgelegt wurde. </p> <p>Sollte "10.00"als "10"angezeigt werden? </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Zeigen Sie Tausende Trennzeichen? </p> </td> 
      <td colname="col2"> <p>Nur verfügbar, wenn <span class="uicontrol"> Bereichsbeschreibung erstellen </span> aktiviert ist und ein Element <span class="uicontrol"> Bereichsfeld </span> ausgewählt ist. </p> <p>Sollte "10000"als "10.000"angezeigt werden? Es werden gebietsschemaspezifische Werte verwendet. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Nullwerte anpassen? </p> </td> 
      <td colname="col2"> <p>Nur verfügbar, wenn <span class="uicontrol"> Bereichsbeschreibung erstellen </span> aktiviert ist und ein Element <span class="uicontrol"> Bereichsfeld </span> ausgewählt ist. </p> <p>Wenn gerundete Nullwerte angezeigt werden, sollten sie gemäß der Einstellung <span class="uicontrol"> Präzision </span> aufgerundet oder abgerundet werden? z. B. "0.01" anzeigen? </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Testen mit "Größer als"? </p> </td> 
      <td colname="col2"> <p>Nur verfügbar, wenn <span class="uicontrol"> Bereichsbeschreibung erstellen </span> aktiviert ist und ein Element <span class="uicontrol"> Bereichsfeld </span> ausgewählt ist. </p> <p>Da jeder Wert mit den Werten in <span class="uicontrol"> Bereichswerte </span> verglichen wird, die in <i><b>absteigender</b></i>-Reihenfolge verarbeitet werden, wird er standardmäßig mit dem Operator Größer als oder gleich (&gt;=) verglichen und nach erfolgreichem Test angehalten. Das bedeutet, dass mit einem Satz von <span class="uicontrol"> Bereichswerten </span> wie "10 20 50 100 1000"der Wert 100 im Bereich 100 bis 1000 fällt, da 100 tatsächlich &gt;= 100 ist. Wenn Sie es lieber im Bereich 50 bis 100 haben möchten, aktivieren Sie diese Option, wodurch stattdessen der Operator Größer als (&gt;) für die Vergleiche verwendet wird. </p> <p>Wenn diese Option aktiviert ist, beispielsweise für jeden Wert dieses Felds: 
      <ul id="ul_969621B1BD914FA5BD73ED21F8841010"> 
      <li id="li_157BEFDA7D0E44C481F4E4BC9046EF24">Wenn der Wert kleiner oder gleich (&lt;=) dem kleinsten Wert in <span class="uicontrol"> Bereichswerte </span> ist, wird das <span class="uicontrol"> "Weniger als" Format </span> verwendet </li> 
      <li id="li_737EE666CA6243A8864E17A311CF3ACC">Wenn der Wert größer ist als (&gt;) der größte Wert in <span class="uicontrol"> Bereichswerte </span>, wird das <span class="uicontrol"> "Größer als" Format </span> verwendet. </li> 
      <li id="li_353A9820F7F74CCCBB3281EC4CB48734">Andernfalls wird ein Bereich gefunden, in dem der Feldwert zwischen zwei aufeinander folgenden <span class="uicontrol"> Bereichswerten </span> (größer oder gleich (&gt;=) dem kleineren Wert und kleiner als (&lt;) dem größeren Wert) liegt und das <span class="uicontrol"> Zwischenformat </span> verwendet wird. </li> 
    </ul> </p> <p>und, wenn deaktiviert: 
    <ul id="ul_945844C33C2E4D95A598C4876E15F211"> 
      <li id="li_653B6E2934574DA3B4BCEF07D0A84527">Wenn der Wert kleiner ist als (&lt;) der kleinste Wert in <span class="uicontrol"> Bereichswerte </span>, wird das <span class="uicontrol"> "Less Than" Format </span> verwendet. </li> 
      <li id="li_AECA6880002F40FAB1820B37237550A7">Wenn der Wert größer oder gleich (&gt;=) dem größten Wert in <span class="uicontrol"> Bereichswerte </span> ist, wird das <span class="uicontrol"> "Größer als" Format </span> verwendet </li> 
      <li id="li_ECB2DF7CA592497298E9ADC708220366">Andernfalls wird ein Bereich gefunden, in dem der Feldwert zwischen zwei aufeinander folgenden <span class="uicontrol"> Bereichswerten </span> (größer als (&gt;), dem kleineren Wert und kleiner oder gleich (&lt;=) dem größeren Wert) liegt und das <span class="uicontrol"> Zwischenformat </span> verwendet wird. </li> 
      </ul> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Test </p> </td> 
      <td colname="col2"> <p>Nur verfügbar, wenn <span class="uicontrol"> Bereichsbeschreibung erstellen </span> aktiviert ist und ein Element <span class="uicontrol"> Bereichsfeld </span> ausgewählt ist. </p> <p>Geben Sie einen numerischen Beispielwert ein und drücken Sie die Schaltfläche <span class="uicontrol"> Testen </span> , um zu sehen, wie das Bereichsfeld erstellt wird. Die generierte Bereichsbeschreibung wird im Fenster angezeigt. </p> </td> 
      </tr> 
    </tbody> 
    </table>

   Siehe auch [Hinzufügen eines neuen Meta-Tag-Felds](../c-about-settings-menu/c-about-metadata-menu.md#task_6DF188C0FC7F4831A4444CA9AFA615E5).
1. Klicken **[!UICONTROL Add]**.
1. (Optional) Erstellen Sie Ihren gestaffelten Site-Index neu, wenn Sie die Ergebnisse in der Vorschau anzeigen möchten.

   Siehe [Konfigurieren eines inkrementellen Index einer gestaffelten Website](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0).
1. (Optional) Führen Sie auf der Seite [!DNL Definitions] einen der folgenden Schritte aus:

   * Klicken Sie auf **[!UICONTROL History]** , um alle Änderungen rückgängig zu machen, die Sie vorgenommen haben.

      Siehe [Verwendung der Option Verlauf](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Klicken **[!UICONTROL Live]**.

      Siehe [Anzeigen von Live-Einstellungen](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Klicken **[!UICONTROL Push Live]**.

      Siehe [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Bearbeiten von vordefinierten oder benutzerdefinierten Meta-Tag-Feldern {#task_0A7657B63596421BB6DB3ED44F827AB3}

Sie können nur bestimmte Felder in vordefinierten Meta-Tags bearbeiten oder alle Felder in benutzerdefinierten Meta-Tags bearbeiten.

Bevor die Auswirkungen Ihrer Meta-Tag-Änderungen für Kunden sichtbar sind, müssen Sie Ihren Site-Index neu erstellen.

**So bearbeiten Sie vordefinierte oder benutzerdefinierte Meta-Tag-Felder**

1. Klicken Sie im Produktmenü auf **[!UICONTROL Settings]** > **[!UICONTROL Metadata]** > **[!UICONTROL Definitions]**.
1. Klicken Sie auf der Seite [!DNL Definitions] in der Spalte [!DNL Actions] der Tabelle in der Zeile des Meta-Tag-Feldnamens, den Sie ändern möchten, auf **[!UICONTROL Edit]** .
1. Klicken Sie auf der Seite [!DNL Pinned Keyword Results Manager] in der Tabelle in der Zeile des zu ändernden Suchbegriffs auf **[!UICONTROL Edit]** .
1. Legen Sie auf der Seite [!DNL Edit Field] die gewünschten Optionen fest.

   Wenn Sie Änderungen an einem vordefinierten Meta-Tag-Feld vornehmen möchten, beachten Sie, dass nicht alle Felder bearbeitbar sind.

   Siehe Tabelle der Optionen unter [Hinzufügen eines neuen Meta-Tag-Felds](../c-about-settings-menu/c-about-metadata-menu.md#task_6DF188C0FC7F4831A4444CA9AFA615E5).
1. Klicken **[!UICONTROL Save Changes]**.
1. (Optional) Erstellen Sie Ihren gestaffelten Site-Index neu, wenn Sie die Ergebnisse in der Vorschau anzeigen möchten.

   Siehe [Konfigurieren eines inkrementellen Index einer gestaffelten Website](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0).
1. (Optional) Führen Sie auf der Seite [!DNL Definitions] einen der folgenden Schritte aus:

   * Klicken Sie auf **[!UICONTROL History]** , um alle Änderungen rückgängig zu machen, die Sie vorgenommen haben.

      Siehe [Verwendung der Option Verlauf](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Klicken **[!UICONTROL Live]**.

      Siehe [Anzeigen von Live-Einstellungen](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Klicken **[!UICONTROL Push Live]**.

      Siehe [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Löschen eines benutzerdefinierten Meta-Tag-Felds {#task_9361EF38B5E743038B6672FA6CF70FD3}

Sie können ein benutzerdefiniertes Meta-Tag-Feld löschen, das Sie nicht mehr benötigen oder verwenden.

Sie können vordefinierte Meta-Tag-Felder nicht löschen. Sie können jedoch bestimmte Felder bearbeiten.

Siehe [Bearbeiten von vordefinierten oder benutzerdefinierten Meta-Tag-Feldern](../c-about-settings-menu/c-about-metadata-menu.md#task_0A7657B63596421BB6DB3ED44F827AB3).

Bevor die Auswirkungen Ihres Meta-Tags zum Löschen für Kunden sichtbar sind, müssen Sie Ihren Site-Index neu erstellen.

**So löschen Sie ein benutzerdefiniertes Meta-Tag-Feld**

1. Klicken Sie im Produktmenü auf **[!UICONTROL Settings]** > **[!UICONTROL Metadata]** > **[!UICONTROL Definitions]**.
1. Klicken Sie auf der Seite [!DNL Definitions] im Abschnitt [!DNL User-defined fields] der Tabelle in der Zeile des Meta-Tag-Feldnamens, den Sie entfernen möchten, auf **[!UICONTROL Delete]** .
1. Klicken Sie im Bestätigungsdialogfeld auf **[!UICONTROL OK]**.
1. (Optional) Erstellen Sie Ihren gestaffelten Site-Index neu, wenn Sie die Ergebnisse in der Vorschau anzeigen möchten.

   Siehe [Konfigurieren eines inkrementellen Index einer gestaffelten Website](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0).
1. (Optional) Führen Sie auf der Seite [!DNL Definitions] einen der folgenden Schritte aus:

   * Klicken Sie auf **[!UICONTROL History]** , um alle Änderungen rückgängig zu machen, die Sie vorgenommen haben.

      Siehe [Verwendung der Option Verlauf](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Klicken **[!UICONTROL Live]**.

      Siehe [Anzeigen von Live-Einstellungen](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Klicken **[!UICONTROL Push Live]**.

      Siehe [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Über Injektionen {#concept_DA091920671948A0A893A26B3A2FAAE5}

Sie können [!DNL Injections] verwenden, um Inhalte in Ihre Webseiten einzufügen, ohne die Seiten selbst bearbeiten zu müssen.

Sie können Inhalte an bestimmte indizierte Felder wie &quot;target&quot;oder &quot;body&quot;anhängen oder indizierte Inhalte durch neue Werte ersetzen. Wenn Sie beispielsweise neuen Inhalt in das Meta-Tag-Feld &quot;Ziel&quot;eingefügt haben, werden diese Informationen genauso behandelt wie hartcodierte Seiteninhalte. Sie können den Inhalt eines beliebigen vordefinierten Meta-Tag-Felds bearbeiten, unabhängig davon, ob die Seiten Ihrer Site über entsprechenden Inhalt verfügen. Sie können beispielsweise den Inhalt der folgenden vordefinierten Meta-Tag-Feldnamen bearbeiten:

* ALT
* body
* charset
* date
* desc
* Schlüssel
* language
* Target
* Titel
* url

## Arbeiten mit Testfeldinjektionen {#section_74939EA9E6EA4D2A92E8066B3B11CF92}

Sie können optional **[!UICONTROL Test]** auf der Seite [!DNL Staged Injections] verwenden. Geben Sie einen Testfeldnamen (z. B. &quot;title&quot;oder &quot;body&quot;), den ursprünglichen Feldwert (z. B. &quot;Home Page&quot;) und eine Test-URL von Ihrer Website ein. Der resultierende Wert wird für Ihre Referenz angezeigt. Die aktuellen Werte werden während des Tests nicht geändert.

## Arbeiten mit Feldinjektionsdefinitionen {#section_C1BBF19DE8EF4A6F8CC3ED691F3953A9}

Injektionsdefinitionen haben die folgende Form:

```
append|replace field [regexp] URL value
```

Die `append|replace`, `field`, `URL`. und `value` Elemente sind obligatorisch. Sie geben eine Injektionsdefinition pro Zeile ein. Das folgende Beispiel enthält sechs verschiedene Injektionsdefinitionen.

```
replace title  https://www.yoursite.com/company/contactus.html Adobe: Contact Us 
append body https://www.yoursite.com/products/* On Sale Now! 
append target https://www.yoursite.com/news/bob_white/ Regular Weekly Feature 
append target regexp https://www.yoursite.com/travel/mr_travel/.*\column.html$ Regular Weekly Feature 
replace charset https://www.yoursite.com/japanese/intro.txt shift-jis 
replace language https://www.yoursite.com/japanese/intro.txt ja_JP
```

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Definition der Injektion </p> </th> 
   <th colname="col2" class="entry"> <p>Beschreibung </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> append|replace  </span> </p> </td> 
   <td colname="col2"> <p>Wählen Sie "append", um den Wert der Injektionsdefinition hinzuzufügen ("Adobe: Kontaktieren Sie uns" oder "Jetzt verkaufen!" in den obigen Beispielen) zum Inhalt der vorhandenen Felder. Wählen Sie "Ersetzen", um vorhandenen Feldinhalt mit dem definierten Wert zu überschreiben. Wenn ein Feld derzeit keinen Inhalt hat, wird der definierte Wert automatisch hinzugefügt, unabhängig davon, welche Option (anhängen oder ersetzen) verwendet wird. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> angeben </span> </p> </td> 
   <td colname="col2"> <p>Ein Feldname ist erforderlich. Im Folgenden finden Sie zehn vordefinierte Feldnamen, die Sie verwenden können: </p> <p> 
     <ul id="ul_B9336FA53023474EAEE399116E7FC972"> 
      <li id="li_C621203DCD2B4875A54A1DD19F0B5B90"> <span class="codeph"> Alt </span> </li> 
      <li id="li_9217E6A037254BEDBB8D006B70D7670D"> <span class="codeph"> body </span> </li> 
      <li id="li_DCDC50F93F224F02897419B745E09399"> <span class="codeph"> charset </span> </li> 
      <li id="li_D95668236B6547B99966668C82B302AB"> <span class="codeph"> date </span> </li> 
      <li id="li_D2071681274345C3B97E9ADA6D223271"> <span class="codeph"> desc  </span> </li> 
      <li id="li_26683A9209454A438D811187FB929482"> <span class="codeph"> Schlüssel </span> </li> 
      <li id="li_A5E19F81B872402CA62B5AB9497E030D"> <span class="codeph"> language </span> </li> 
      <li id="li_FD0B1CD9E6304B18B9D7F57E61015107"> <span class="codeph"> target  </span> </li> 
      <li id="li_400D7E3F3E9B47EFB2FF5C0D278DB573"> <span class="codeph"> Titel </span> </li> 
      <li id="li_449BCBEE4F64424BB69F780C10F5956C"> <span class="codeph"> url </span> </li> 
     </ul> </p> <p>Jeder Feldname entspricht Elementen auf den Seiten Ihrer Site. Wenn Sie beispielsweise den Feldnamen <span class="codeph"> desc </span> angeben, können Sie den Injektionsdefinitionswert dem Feld hinzufügen, das der Beschreibung Meta-Tags auf Ihren Seiten entspricht. </p> <p>Wenn keine Beschreibung Meta-Tag auf Ihren Seiten vorhanden ist, wird das Tag vom definierten Inhalt für Sie erstellt. Der in einer <span class="codeph"> desc </span> -Injektion angegebene Inhalt wird auf Ihrer Ergebnisseite genauso angezeigt wie hartcodierter Meta-Beschreibungsinhalt. </p> <p>Sie können auch mehrere Definitionen mit demselben Feldnamen erstellen. Angenommen, Sie haben die folgenden Injektionen: </p> <p> <code> replace&nbsp; <b>title</b>&nbsp;https://www.mysite.com/&nbsp;Welcome&nbsp;to&nbsp;My&nbsp;Site </code> </p> <p> <code> replace&nbsp; <b>title</b>&nbsp;https://www.mysite.com/company/*.html&nbsp;My&nbsp;Site:&nbsp;Contact </code> </p> <p>Alle Seiten der Website im obigen Beispiel erhalten einen injizierten Titel "Willkommen auf meiner Site". Seiten im Ordner "/company/"werden mit dem neuen Titel "My Site: Kontaktieren Sie uns" , das den vorherigen ersetzt. </p> <p>Beachten Sie, dass Injektionen in der Reihenfolge angewendet werden, in der sie im Textfeld <span class="wintitle"> Feldinjektionsdefinitionen </span> angezeigt werden. Wenn dasselbe Feld ("Titel"in diesem Beispiel) für Seiten am selben Ort mehrmals definiert ist, hat die spätere Definition Vorrang. </p> <p> <span class="codeph"> [regexp]  </span> - optional. Wenn Sie die Option <span class="codeph"> regexp </span> verwenden, wird die definierte URL als regulärer Ausdruck behandelt. </p> <p>Siehe <a href="../c-appendices/r-regular-expressions.md#reference_B5BA7D61D82E4109A01D2A2D964E3A6A" type="reference" format="dita" scope="local"> Reguläre Ausdrücke </a>. </p> <p>In der folgenden Definition: </p> <p> <code> replace&nbsp;target&nbsp; <b>regexp&amp;nbsp;^.*/products/.*\.html$</b>&nbsp;Important&nbsp;information </code> </p> <p> "Wichtige Informationen"wird in das Feld "Ziel"auf allen Seiten eingefügt, die dem regulären Ausdruck <span class="codeph"> ^ entsprechen.*/products/.*\.html$ </span>. </p> <p>Daher haben Sie Folgendes: </p> <p> <code> https://www.mydomain.com/products/page1.html 
      &nbsp;&nbsp;&nbsp;&nbsp;(Will&nbsp;receive&nbsp;"target"&nbsp;content) </code> </p> <p> <code> https://www.mydomain.com/product/oldstuff.html 
      &nbsp;&nbsp;&nbsp;&nbsp;(Will&nbsp;not&nbsp;receive&nbsp;"target"&nbsp;content) </code> </p> <p>Im folgenden Beispiel: </p> <p> <code> append&amp;nbsp;title&amp;nbsp;regexp&amp;nbsp;^.*\.pdf$&amp;nbsp;Millennium&amp;nbsp;Science </code> </p> <p>Durch die Injektion wird "Millennium Science"an den "title"-Inhalt aller Seiten angehängt, die mit einer ".pdf"-Dateinamenerweiterung enden. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> URL </span> </p> </td> 
   <td colname="col2"> <p>Eine URL ist erforderlich und gibt an, welche Dokumente eingefügt werden. </p> <p>Die URL ist eine der folgenden URL: </p> <p> 
     <ul id="ul_C5C74F6D5EA943B293742989EB822751"> 
      <li id="li_382392DB778D4E14BFFC96D35A861951"> Ein vollständiger Pfad, wie in https://www.mydomain.com/products.html </li> 
      <li id="li_EA2BD0FB66A44CD0844613316F6174D4"> Ein partieller Pfad, wie in https://www.mydomain.com/products </li> 
      <li id="li_D5E0D6D897C8493ABBFC65517CD4A7DB"> Eine URL, die Platzhalter verwendet, wie in https://www.mydomain.com/*.html </li> 
     </ul> </p> <p>Der URL-Wert darf keine Leerzeichen enthalten. Wenn die Option <span class="codeph"> regexp </span> verwendet wird, wird die URL wie ein regulärer Ausdruck behandelt. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> value </span> </p> </td> 
   <td colname="col2"> <p>Ein Wert ist erforderlich und wird verwendet, um vorhandenen Feldinhalt zu ersetzen oder hinzuzufügen. Sie können mehrere Werte für denselben Feldnamen angeben. Beispiel: </p> <p>append <b>keys</b> https://www.mysite.com/travel/ <b>summer</b>, <b>strand</b>, <b>sand</b> </p> <p>append <b>keys</b> https://www.mysite.com/travel/fare/*.html <b>billige Tickets</b> </p> <p>Im obigen Beispiel werden die Wörter "Sommer, Strand, Sand"auf allen Seiten im Verzeichnis "/travel/"an das Feld "Schlüssel"angehängt. Die Wörter "billige Tickets" werden auch an das Feld "Schlüssel" auf allen Seiten im Verzeichnis "/travel/fare/" angehängt. </p> </td> 
  </tr> 
 </tbody> 
</table>

Siehe auch [Auswahl der zu durchsuchenden und zu indizierenden Inhaltstypen](../c-about-settings-menu/c-about-crawling-menu.md#task_CCAC5C67C8BF4AB7B79D34A1495D5EE8).

## Hinzufügen von Feldeinspritzungsdefinitionen {#task_E86566FA1FF74CF68115C0ADA05172AE}

Sie können [!DNL Injections] verwenden, um Inhalte in Ihre Webseiten einzufügen, ohne die Seiten selbst bearbeiten zu müssen.

Sie können optional **[!UICONTROL Test]** auf der Seite [!DNL Injections] verwenden. Geben Sie einen Testfeldnamen (z. B. &quot;title&quot;oder &quot;body&quot;), den ursprünglichen Feldwert (z. B. &quot;Home Page&quot;) und eine Test-URL von Ihrer Website ein. Der resultierende Wert wird für Ihre Referenz angezeigt. Die aktuellen Werte werden während des Tests nicht geändert.

**So fügen Sie Feldinjektionsdefinitionen hinzu**

1. Klicken Sie im Produktmenü auf **[!UICONTROL Settings]** > **[!UICONTROL Metadata]** > **[!UICONTROL Injections]**.
1. (Optional) Geben Sie auf der Seite [!DNL Injections] im Bereich [!DNL Test Field Injections] das Testfeld, den ursprünglichen Testwert und die Test-URL ein und klicken Sie dann auf **[!UICONTROL Test]**.
1. Geben Sie im Feld [!DNL Field Injection Definitions] eine Injektionsdefinition pro Zeile ein.
1. Klicken **[!UICONTROL Save Changes]**.
1. (Optional) Führen Sie einen der folgenden Schritte aus:

   * Klicken Sie auf **[!UICONTROL History]** , um alle Änderungen rückgängig zu machen, die Sie vorgenommen haben.

      Siehe [Verwendung der Option Verlauf](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Klicken **[!UICONTROL Live]**.

      Siehe [Anzeigen von Live-Einstellungen](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Klicken **[!UICONTROL Push Live]**.

      Siehe [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Über Attributlader {#concept_9EF38E98811B42CDA41996432B9AD209}

Verwenden Sie [!DNL Attribute Loader], um zusätzliche Eingabequellen zu definieren, um von einer Website durchsuchte Daten zu ergänzen.

>[!NOTE]
>
>Um Attributlader zu verwenden, müssen Sie ihn möglicherweise in Ihrem Konto von Ihrem Kundenbetreuer für Adobe oder vom Support für Adoben aktivieren lassen.

Sie können eine Datenquelle für Daten-Feeds verwenden, um auf Inhalte zuzugreifen, die in einem Formular gespeichert sind, das sich von dem unterscheidet, was normalerweise auf einer Website erkannt wird. Verwenden Sie dazu eine der verfügbaren Crawl-Methoden. Daten aus diesen Quellen können dann in Daten aus durchsuchten Inhalten eingefügt werden.

Nachdem Sie der Seite [!DNL Staged Attribute Loader Definitions] eine Definition für Attributlader hinzugefügt haben, können Sie alle Konfigurationseinstellungen mit Ausnahme der Werte &quot;Name&quot;und &quot;Typ&quot;ändern

Die Seite [!DNL Attribute Loader] enthält folgende Informationen:

* Der Name der definierten Attribute Loader-Konfiguration, die Sie konfiguriert und hinzugefügt haben.
* Einer der folgenden Datenquellentypen für jeden Connector, den Sie hinzugefügt haben:

   * **Text**  - Einfache &quot;flache&quot;Dateien, kommagetrennte, tabulatorgetrennte oder andere konsistent getrennte Formate.
   * **Feed**  - XML-Feeds.

* Gibt an, ob die Konfiguration für das nächste Durchsuchen und Indizieren aktiviert ist.
* Die Adresse der Datenquelle.

Siehe auch [Wie der Attributinjektionsprozess für Text und Feed funktioniert ...](../c-about-settings-menu/c-about-metadata-menu.md#section_E059A33D61EE4DB0972A37B8A35E9E16)

Siehe auch [Informationen zum Konfigurieren mehrerer Attributlader](../c-about-settings-menu/c-about-metadata-menu.md#section_4CC49C74EF294608A184E233F215ADFF)

Siehe auch [Über die Verwendung der Vorschau beim Hinzufügen eines Attributs ...](../c-about-settings-menu/c-about-metadata-menu.md#section_E9CAB000A94C4D9189786C1EDB1CDB46)

## Funktionsweise des Attributinjektionsprozesses für Text- und Feed-Konfigurationen in Attributlader {#section_E059A33D61EE4DB0972A37B8A35E9E16}

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Schritt </p> </th> 
   <th colname="col2" class="entry"> <p>Prozess </p> </th> 
   <th colname="col3" class="entry"> <p>Beschreibung </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>1 </p> </td> 
   <td colname="col2"> <p>Laden Sie die Datenquelle herunter. </p> </td> 
   <td colname="col3"> <p>Bei Text- und Feed-Konfigurationen handelt es sich um einen einfachen Dateidownload. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>2 </p> </td> 
   <td colname="col2"> <p>Schlüsseln Sie die heruntergeladene Datenquelle in einzelne Pseudo-Dokumente auf. </p> </td> 
   <td colname="col3"> <p>Für <span class="uicontrol"> Text </span> entspricht jede durch Zeilenumbruch getrennte Textzeile einem einzelnen Dokument und wird mithilfe des angegebenen Trennzeichens wie einem Komma oder einer Registerkarte analysiert. </p> <p>Für <span class="uicontrol"> Feed </span> werden die Daten jedes Dokuments mithilfe eines Musters für reguläre Ausdrücke wie folgt extrahiert: </p> <p> <code class="syntax js"> &lt;${Itemtag}&gt;(.*?)&lt;/${Itemtag}&gt; </code> </p> <p>Erstellen Sie mit <span class="uicontrol"> Zuordnung </span> auf der Seite <span class="wintitle"> Attribut-Lader Fügen Sie </span> eine zwischengespeicherte Kopie der Daten und erstellen Sie dann eine Liste von Links für den Crawler. Die Daten werden in einem lokalen Cache gespeichert und mit den konfigurierten Feldern gefüllt. </p> <p>Die analysierten Daten werden in den lokalen Cache geschrieben. </p> <p>Dieser Cache wird später gelesen, um die einfachen HTML-Dokumente zu erstellen, die der Crawler benötigt. Beispiel: </p> <p> <code class="syntax html"> &lt;html&gt;&lt;head&gt; 
      &lt;title&gt;{title}&lt;/title&gt; 
      &lt;meta&nbsp;name="{field}"&nbsp;content="{data}"&nbsp;/&gt; 
      ... 
      &lt;/head&gt;&lt;body&gt; 
      {body} 
      &lt;/body&gt;&lt;/html&gt; </code> </p> <p>Das Element <span class="codeph"> &lt;title&gt; </span> wird nur generiert, wenn eine Zuordnung zum Metadatenfeld "Titel"vorhanden ist. Ebenso wird das Element <span class="codeph"> &lt;body&gt; </span> nur generiert, wenn eine Zuordnung zum Metadatenfeld "Textkörper"vorhanden ist. </p> <p> <b>Wichtig</b>: Die Zuweisung von Werten zum vordefinierten URL-Meta-Tag wird nicht unterstützt. </p> <p>Bei allen anderen Zuordnungen werden <span class="codeph"> &lt;meta&gt; </span> -Tags für jedes Feld generiert, das Daten im Originaldokument enthält. </p> <p>Die Felder für jedes Dokument werden dem Cache hinzugefügt. Für jedes Dokument, das in den Cache geschrieben wird, wird wie in den folgenden Beispielen auch ein Link generiert: </p> <p> <code class="syntax html"> &lt;a&nbsp;href="index:Adobe?key=&lt;primary&nbsp;key&nbsp;field&gt;\"&nbsp;/&gt; 
      &lt;a&nbsp;href="index:Adobe?key=&lt;primary&nbsp;key&nbsp;field&gt;\"&nbsp;/&gt; 
      .... </code> </p> <p>Für die Zuordnung der Konfiguration muss ein Feld als Primärer Schlüssel identifiziert werden. Diese Zuordnung bildet den Schlüssel, der verwendet wird, wenn Daten aus dem Cache abgerufen werden. </p> <p>Der Crawler erkennt den Index der URL <span class="codeph">: </span> Schemapräfix, das dann auf die lokal zwischengespeicherten Daten zugreifen kann. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>3 </p> </td> 
   <td colname="col2"> <p>Durchsuchen Sie den zwischengespeicherten Dokumentsatz. </p> </td> 
   <td colname="col3"> <p>Der Index <span class="codeph"> : </span> Links werden der ausstehenden Liste des Crawlers hinzugefügt und in der normalen Crawl-Sequenz verarbeitet. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>4 </p> </td> 
   <td colname="col2"> <p>Verarbeiten Sie jedes Dokument. </p> </td> 
   <td colname="col3"> <p>Der Schlüsselwert jedes Links entspricht einem Eintrag im Cache, sodass das Durchsuchen der einzelnen Links dazu führt, dass die Daten dieses Dokuments aus dem Cache abgerufen werden. Anschließend wird es zu einem HTML-Bild "zusammengestellt", das verarbeitet und dem Index hinzugefügt wird. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Über die Konfiguration mehrerer Attributlader {#section_4CC49C74EF294608A184E233F215ADFF}

Sie können für jedes Konto mehrere Attribute Loader-Konfigurationen definieren.

Wenn Sie einen Attributlader hinzufügen, können Sie optional die Funktion **[!UICONTROL Setup Maps]** verwenden, um ein Beispiel Ihrer Datenquelle herunterzuladen. Die Daten werden auf Eignung geprüft.

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p> Attribut-Lader-Typ </p> </th> 
   <th colname="col2" class="entry"> <p>Beschreibung </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Text </p> </td> 
   <td colname="col2"> <p>Bestimmt den Trennzeichenwert, indem zuerst Registerkarten und dann vertikale Balken ( <span class="codeph">) versucht werden | </span>) und schließlich Kommas ( <span class="codeph"> , </span>). Wenn Sie bereits einen Trennzeichenwert angegeben haben, bevor Sie auf <span class="uicontrol"> Einrichtungskarten </span> geklickt haben, wird dieser Wert stattdessen verwendet. </p> <p>Das am besten geeignete Schema führt dazu, dass die Zuordnungsfelder mit Schätzungen zu den entsprechenden Tag- und Feldwerten ausgefüllt werden. Zusätzlich wird eine Auswahl der analysierten Daten angezeigt. Wählen Sie <span class="uicontrol"> Kopfzeilen in der ersten Zeile </span> aus, wenn Sie wissen, dass die Datei eine Kopfzeile enthält. Die Setup-Funktion verwendet diese Informationen, um die resultierenden Zuordnungseinträge besser zu identifizieren. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Feed </p> </td> 
   <td colname="col2"> <p>Lädt die Datenquelle herunter und führt einfache XML-Parsing durch. </p> <p>Die resultierenden XPath-IDs werden in den Tag-Zeilen der Map-Tabelle und in den Feldern in ähnlichen Werten angezeigt. Diese Zeilen identifizieren nur die verfügbaren Daten und generieren nicht die komplizierteren XPath-Definitionen. Es ist jedoch weiterhin hilfreich, da es die XML-Daten beschreibt und ItemTag identifiziert. </p> <p> <p>Hinweis:  Die Funktion "Setup-Maps"lädt die gesamte XML-Quelle herunter, um die Analyse durchzuführen. Wenn die Datei groß ist, kann bei diesem Vorgang eine Zeitüberschreitung auftreten. </p> </p> <p>Nach erfolgreichem Abschluss identifiziert diese Funktion alle möglichen XPath-Elemente, von denen viele nicht verwendet werden sollten. Achten Sie darauf, die resultierenden Kartendefinitionen zu untersuchen und diejenigen zu entfernen, die Sie nicht benötigen oder möchten. </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>Die Funktion &quot;Setup Maps&quot;funktioniert möglicherweise nicht für große XML-Datensätze, da der Dateiparser versucht, die gesamte Datei in den Speicher zu lesen. Daher kann es zu einer Speicherüberschreitung kommen. Wenn dasselbe Dokument jedoch zum Zeitpunkt der Indizierung verarbeitet wird, wird es nicht in den Speicher gelesen. Stattdessen werden große Dokumente &quot;unterwegs&quot;verarbeitet und zuerst nicht vollständig in den Speicher gelesen.

## Über die Verwendung der Vorschau beim Hinzufügen eines Attributladers {#section_E9CAB000A94C4D9189786C1EDB1CDB46}

Attribute Loader-Daten werden vor einem Index-Vorgang geladen.

Zum Zeitpunkt des Hinzufügens eines Attribut-Laders können Sie optional die Funktion **[!UICONTROL Preview]** verwenden, um die Daten zu validieren, so als ob Sie sie gespeichert hätten. Er führt einen Test für die Konfiguration aus, ohne die Konfiguration im Konto zu speichern. Der Test greift auf die konfigurierte Datenquelle zu. Der Download-Cache wird jedoch an einen temporären Speicherort geschrieben. Es steht nicht im Konflikt mit dem Hauptcache-Ordner, den der Indizierungs-Crawler verwendet.

Die Vorschau verarbeitet nur einen Standardwert von fünf Dokumenten, wie von **Acct:IndexConnector-Preview-Max-Documents** gesteuert. Die in der Vorschau angezeigten Dokumente werden im Quellformular angezeigt, da sie dem Indizierungs-Crawler präsentiert werden. Die Anzeige ähnelt der Funktion &quot;Quelle anzeigen&quot;in einem Webbrowser. Sie können mithilfe von Standardnavigationslinks in den Dokumenten im Vorschauset navigieren.

Die Vorschau unterstützt keine XML-Konfigurationen, da diese Dokumente direkt verarbeitet und nicht in den Cache heruntergeladen werden.

## Hinzufügen einer Attributlader-Definition {#task_A735E5EF763343A9B675E1A3B09AFDBC}

Jede Attribute Loader-Konfiguration definiert eine Datenquelle und Zuordnungen, um die für diese Quelle definierten Datenelemente mit den Metadatenfeldern im Index zu verknüpfen.

>[!NOTE]
>
>Um Attributlader zu verwenden, müssen Sie ihn möglicherweise in Ihrem Konto von Ihrem Kundenbetreuer für Adobe oder vom Support für Adoben aktivieren lassen.

Bevor die Auswirkungen der neuen und aktivierten Definition für Kunden sichtbar sind, müssen Sie Ihren Site-Index neu erstellen.

**So fügen Sie eine Definition für Attributlader hinzu**

1. Klicken Sie im Produktmenü auf **[!UICONTROL Settings]** > **[!UICONTROL Metadata]** > **[!UICONTROL Attribute Loader]**.
1. Klicken Sie auf der Seite [!DNL Stage Attribute Loader Definitions] auf **[!UICONTROL Add New Attribute Loader]**.
1. Legen Sie auf der Seite [!DNL Attribute Loader Add] die gewünschten Konfigurationsoptionen fest. Die verfügbaren Optionen hängen von der ausgewählten **[!UICONTROL Type]** ab.

   <table> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> <p>Option </p> </th> 
      <th colname="col2" class="entry"> <p>Beschreibung </p> </th> 
      </tr> 
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <p>Name </p> </td> 
      <td colname="col2"> <p>Der eindeutige Name der Attribute Loader-Konfiguration. Sie können alphanumerische Zeichen verwenden. Die Zeichen "_"und "-"sind ebenfalls zulässig. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Typ </p> </td> 
      <td colname="col2"> <p>Die Quelle Ihrer Daten. Der ausgewählte Datenquellentyp wirkt sich auf die resultierenden Optionen aus, die auf der Seite <span class="wintitle"> Attribut-Lader </span> verfügbar sind. Sie können aus folgenden Optionen wählen: </p> <p> 
      <ul id="ul_1ADC3DFBC929467385F7465BE8E13635"> 
      <li id="li_64FCD749F55442BAB316BD474128D4F9"> <span class="uicontrol"> Text </span> <p>Einfache flache Textdateien, kommagetrennte, tabulatorgetrennte oder andere konsistent getrennte Formate. Jede durch Zeilenumbrüche getrennte Textzeile entspricht einem einzelnen Dokument und wird mithilfe des angegebenen Trennzeichens analysiert. </p> <p>Sie können jeden Wert bzw. jede Spalte einem Metadatenfeld zuordnen, das durch die Spaltennummer referenziert wird, beginnend bei 1 (eins). </p> </li> 
      <li id="li_2A4F16CE6DCE4114B7F8E4FE156252BB"> <span class="uicontrol"> Feed </span> <p>Lädt ein primäres XML-Dokument herunter, das mehrere "Zeilen"mit Informationen enthält. </p> </li> 
      </ul> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p> <b>Datenquellentyp: Text</b> </p> </td> 
      <td colname="col2"> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Aktiviert </p> </td> 
      <td colname="col2"> <p>Schaltet die Konfiguration zur Verwendung "ein". Alternativ können Sie die Konfiguration deaktivieren, um zu verhindern, dass sie verwendet wird. </p> <p> <b>Hinweis</b>: Deaktivierte Attribute Loader-Konfigurationen werden ignoriert. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Hostadresse </p> </td> 
      <td colname="col2"> <p>Gibt die Adresse des Serverhosts an, auf dem sich Ihre Daten befinden. </p> <p>Bei Bedarf können Sie einen vollständigen URI-Pfad (Uniform Resource Identifier) zum Datenquellendokument wie in den folgenden Beispielen angeben: </p> <p> <code otherprops="syntax html"> https://www.somewhere.com/some_path/some_file.tsv </code> </p> <p>oder </p> <p> <code class="syntax html"> ftp://user:password@ftpserver.somewhere.com/some_path/some_file.csv </code> </p> <p>Der URI ist in die entsprechenden Einträge für die Felder Host-Adresse, Dateipfad, Protokoll und optional Benutzername und Kennwort unterteilt </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Dateipfad </p> </td> 
      <td colname="col2"> <p>Gibt den Pfad zur einfachen Textdatei mit einfach strukturiertem, kommagetrennten, tabulatorgetrennten oder anderen konsistent getrennten Formatdateien an. </p> <p>Der Pfad ist relativ zum Stammverzeichnis der Hostadresse. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Protokoll </p> </td> 
      <td colname="col2"> <p>Gibt das Protokoll an, das für den Zugriff auf die Datei verwendet wird. Sie können aus folgenden Optionen wählen: </p> <p> 
      <ul id="ul_F6BC10FD51CA4A1D855B2B3212838A9C"> 
      <li id="li_79FB7DC65E774ABBB23E57BF98AD9738"> HTTP <p>Bei Bedarf können Sie für den Zugriff auf den HTTP-Server die entsprechenden Authentifizierungsberechtigungen eingeben. </p> </li> 
      <li id="li_BAA9AD5E4B014E09B3A66C94022B7225"> HTTPS <p>Bei Bedarf können Sie für den Zugriff auf den HTTPS-Server die entsprechenden Authentifizierungsberechtigungen eingeben. </p> </li> 
      <li id="li_E716ABB169DD408BA91F1CA27F445A16"> FTP <p>Sie müssen die entsprechenden Authentifizierungsberechtigungen eingeben, um auf den FTP-Server zugreifen zu können. </p> </li> 
      <li id="li_FD7143019C5244C3B8A5B1B5AA84859A"> SFTP <p>Sie müssen die entsprechenden Authentifizierungsberechtigungen eingeben, um auf den SFTP-Server zugreifen zu können. </p> </li> 
      <li id="li_38E0036C1365419F9D00083CACA34AFB"> Datei </li> 
      </ul> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Zeitüberschreitung </p> </td> 
      <td colname="col2"> <p>Gibt die Zeitüberschreitung für FTP-, SFTP-, HTTP- oder HTTPS-Verbindungen in Sekunden an. Dieser Wert muss zwischen 30 und 300 liegen. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Weitere Zustellversuche </p> </td> 
      <td colname="col2"> <p>Gibt die maximale Anzahl weiterer Versuche für fehlgeschlagene FTP-, SFTP-, HTTP- oder HTTPS-Verbindungen an. Dieser Wert muss zwischen 0 und 10 liegen. </p> <p>Der Wert null (0) verhindert Wiederholungsversuche. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Kodierung </p> </td> 
      <td colname="col2"> <p>Gibt das Zeichencodierungssystem an, das in der angegebenen Datenquellendatei verwendet wird. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Trennzeichen </p> </td> 
      <td colname="col2"> <p>Gibt das Zeichen an, das Sie zum Trennen der einzelnen Felder in der angegebenen Datenquellendatei verwenden möchten. </p> <p>Das Komma ( <span class="codeph"> , </span>) ist ein Beispiel für ein Trennzeichen. Das Komma dient als Feldtrennzeichen, mit dem Datenfelder in der angegebenen Datenquellendatei getrennt werden können. </p> <p>Wählen Sie die Registerkarte <span class="uicontrol"> aus? </span> , um das horizontale Tabulatorzeichen als Trennzeichen zu verwenden. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Kopfzeilen in der ersten Zeile </p> </td> 
      <td colname="col2"> <p>Gibt an, dass die erste Zeile in der Datenquellendatei nur Kopfzeileninformationen und keine Daten enthält. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Statische Tage </p> </td> 
      <td colname="col2"> <p>Legt das Mindestintervall zwischen Downloads von Attribute Loader-Daten fest. Durch den Index ausgelöste Downloads, die innerhalb des Intervalls für die Download-Aktualisierungshäufigkeit auftreten, werden ignoriert. Wenn Sie diesen Wert auf den Standardwert 1 setzen, werden die Attribute Loader-Daten innerhalb eines Zeitraums von 24 Stunden nur einmal heruntergeladen. Alle Suchindizes, die innerhalb des Intervalls für die Download-Aktualisierungsfrequenz auftreten, verwenden den letzten heruntergeladenen Datensatz. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Landkarte </p> </td> 
      <td colname="col2"> <p>Gibt Zuordnungen von Spalten zu Metadaten mithilfe von Spaltennummern an. </p> <p> 
      <ul id="ul_981AE2C6D30443BDBFC6575D413732A2"> 
      <li id="li_A42CB9DFFF8C45A7BAC2D471FE96CEBE"> <span class="uicontrol"> Spalte </span> <p> Gibt eine Spaltennummer an, wobei die erste Spalte 1 (1) ist. Um für jede Spalte neue Zuordnungszeilen hinzuzufügen, klicken Sie unter <span class="wintitle"> Aktion </span> auf <span class="uicontrol"> + </span>. </p> <p>Sie müssen nicht jede Spalte in der Datenquelle referenzieren. Stattdessen können Sie Werte überspringen. </p> </li> 
      <li id="li_26E8C9554A5D4BC5A5073D6385E3626F"> <span class="uicontrol"> Feld </span> <p>Definiert den Attribut name -Wert, der für jedes generierte &lt;meta&gt; -Tag verwendet wird. </p> </li> 
      <li id="li_5DFA514B7F9549B98D6CBC095A66033C"> <span class="uicontrol"> Metadaten? </span> <p>Verursacht, dass <span class="uicontrol"> Feld </span> zu einer Dropdown-Liste wird, aus der Sie definierte Metadatenfelder für das aktuelle Konto auswählen können. </p> <p>Der Wert <span class="uicontrol"> Feld </span> kann ein nicht definiertes Metadatenfeld sein, falls gewünscht. Manchmal ist ein nicht definiertes Metadatenfeld nützlich, um Inhalte zu erstellen, die von einem <span class="wintitle"> Filterskript </span> verwendet werden. </p> <p>Siehe <a href="../c-about-settings-menu/c-about-filtering-menu.md#concept_E56B73D625854AB2A899EF2D56CFCB47" type="concept" format="dita" scope="local"> Informationen zum Filtern von Skript </a>. </p> </li> 
      <li id="li_80DB205525094CE1AA6762BFC7892C95"> <span class="uicontrol"> Primärschlüssel? </span> <p>Nur ein Feld wird als Primärschlüssel identifiziert. Dieses Feld wird als "Fremdschlüssel"verwendet, um die Attribute Loader-Daten mit dem entsprechenden Dokument im Index abzugleichen. </p> </li> 
      <li id="li_80DB205525094CE1AA6762BFC7892D96"> <span class="uicontrol"> HTML entfernen?  </span> <p>Wenn diese Option aktiviert ist, werden alle in den Daten dieses Felds gefundenen HTML-Tags entfernt. </p> </li> 
      <li id="li_359D2902859B4C5BADB0BA26F0BA4DC0"> <span class="uicontrol"> Aktion </span> <p>Ermöglicht das Hinzufügen von Zeilen zur Zuordnung oder das Entfernen von Zeilen aus der Zuordnung. Die Reihenfolge der Zeilen ist nicht wichtig. </p> </li> 
      </ul> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p> <b>Datenquellentyp: Feed</b> </p> </td> 
      <td colname="col2"> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Aktiviert </p> </td> 
      <td colname="col2"> <p>Schaltet die Konfiguration zur Verwendung "ein". Alternativ können Sie die Konfiguration deaktivieren, um zu verhindern, dass sie verwendet wird. </p> <p> <b>Hinweis</b>: Deaktivierte Attribute Loader-Konfigurationen werden ignoriert. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Hostadresse </p> </td> 
      <td colname="col2"> <p>Gibt die Adresse des Serverhosts an, auf dem sich Ihre Daten befinden. </p> <p>Bei Bedarf können Sie einen vollständigen URI-Pfad (Uniform Resource Identifier) zum Datenquellendokument wie in den folgenden Beispielen angeben: </p> <p> <code class="syntax html"> https://www.somewhere.com/some_path/some_file.tsv </code> </p> <p>oder </p> <p> <code class="syntax html"> ftp://user:password@ftpserver.somewhere.com/some_path/some_file.csv </code> </p> <p>Der URI ist in die entsprechenden Einträge für die Felder Host-Adresse, Dateipfad, Protokoll und optional Benutzername und Kennwort unterteilt. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Dateipfad </p> </td> 
      <td colname="col2"> <p>Gibt den Pfad zum primären XML-Dokument an, das mehrere "Zeilen"mit Informationen enthält. </p> <p>Der Pfad ist relativ zum Stammverzeichnis der Hostadresse. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Protokoll </p> </td> 
      <td colname="col2"> <p>Gibt das Protokoll an, das für den Zugriff auf die Datei verwendet wird. Sie können aus folgenden Optionen wählen: </p> <p> 
      <ul id="ul_976A34FD14A841F2B610C1C0CCBB82B9"> 
      <li id="li_05BBA0F670F14431A89AE4178F1A6F94"> HTTP <p>Bei Bedarf können Sie für den Zugriff auf den HTTP-Server die entsprechenden Authentifizierungsberechtigungen eingeben. </p> </li> 
      <li id="li_100446691F304572B8FC3F083F86A2CB"> HTTPS <p>Bei Bedarf können Sie für den Zugriff auf den HTTPS-Server die entsprechenden Authentifizierungsberechtigungen eingeben. </p> </li> 
      <li id="li_027088A8E30444DAA8CCCC5B0BAA74C1"> FTP <p>Sie müssen die entsprechenden Authentifizierungsberechtigungen eingeben, um auf den FTP-Server zugreifen zu können. </p> </li> 
      <li id="li_DCEF9D5C99354990B03E29083C2ED8DC"> SFTP <p>Sie müssen die entsprechenden Authentifizierungsberechtigungen eingeben, um auf den SFTP-Server zugreifen zu können. </p> </li> 
      <li id="li_44E34FF2AB0D429EB3408106E6FCF780"> Datei </li> 
      </ul> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>itemTag </p> </td> 
      <td colname="col2"> <p>Identifiziert das XML-Element, mit dem Sie einzelne XML-Zeilen in der angegebenen Datenquellendatei identifizieren können. </p> <p>Im folgenden Feed-Fragment eines Adobe XML-Dokuments lautet der ItemTag-Wert beispielsweise <span class="codeph"> record </span>: </p> <p> <code class="syntax xml"> &lt;?xml&nbsp;version="1.0"&nbsp;encoding="utf-8"?&gt; 
        &lt;!DOCTYPE&nbsp;gsafeed&nbsp;PUBLIC&nbsp;"-//Google//DTD&nbsp;GSA&nbsp;Feeds//EN"&nbsp;""&gt; 
        &lt;gsafeed&gt; 
        &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;header&gt; 
        &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;datasource&gt;marketplace&lt;/datasource&gt; 
        &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;feedtype&gt;incremental&lt;/feedtype&gt; 
        &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/header&gt; 
        &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;group&nbsp;action="add"&gt; 
        &lt;record&nbsp;url=https://www.adobe.com/cfusion/marketplace_gsa/ 
        index.cfm?event=marketplace.home&amp;amp;marketplaceid=1&nbsp;action="add"&nbsp;mimetype="text/html"displayurl="https://www.adobe.com/cfusion/marketplace/index.cfm?event=marketplace.home&amp;amp;marketplaceid=1"&gt; 
        &lt;metadata&gt; 
        &lt;meta&nbsp;name="mp_mkt"&nbsp;content="1"/&gt; 
        &lt;meta&nbsp;name="mp_logo"&nbsp;content="/images/marketplace/ 
        dbreferenced/marketplaceicons/icn_air.png"/&gt; 
        &lt;meta&nbsp;name="title"&nbsp;content="Adobe&nbsp;AIR&nbsp;Marketplace"/&gt; 
        &lt;meta&nbsp;name="description"&nbsp;content="Discover&nbsp;new&nbsp;applications&nbsp;..."/&gt; 
        &lt;/metadata&gt; 
        &lt;content&gt;&lt;![CDATA[&lt;html&gt;&lt;head&gt;&lt;title&gt;Adobe&nbsp;AIR&nbsp;Marketplace&lt;/title&gt;&lt;/head&gt;&lt;body&gt;Discover&nbsp;new&nbsp;applications&nbsp;...&lt;/body&gt;&lt;/html&gt;]]&gt;&lt;/cntent&gt; 
        &lt;/record&gt; 
        &lt;record&nbsp;url=https://www.adobe.com/cfusion/marketplace_gsa/ 
        index.cfm?event=marketplace.home&amp;amp;marketplaceid=2&nbsp;action="add"&nbsp;mimetype="text/html"&nbsp;displayurl="https://www.adobe.com/cfusion/ 
        marketplace/index.cfm?event=marketplace.home&amp;amp;marketplaceid=2"&gt; 
        &lt;metadata&gt; 
        &lt;meta&nbsp;name="mp_mkt"&nbsp;content="2"/&gt; 
        &lt;meta&nbsp;name="mp_logo"&nbsp;content="/images/marketplace/ 
        dbreferenced/marketplaceicons/icn_photoshop.png"/&gt; 
        &lt;meta&nbsp;name="title"&nbsp;content="Adobe&nbsp;Photoshop&nbsp;Marketplace"/&gt; 
        &lt;meta&nbsp;name="description"&nbsp;content="Extend&nbsp;your&nbsp;creative&nbsp;possibilities&nbsp;..."/&gt; 
        &lt;/metadata&gt; 
        &lt;content&gt;&lt;![CDATA[&lt;html&gt;&lt;head&gt;&lt;title&gt;Adobe&nbsp;Photoshop&nbsp;Marketplace&lt;/title&gt;&lt;/head&gt;&lt;body&gt;Extend&nbsp;your&nbsp;creative&nbsp;possibilities&nbsp;...&lt;/body&gt;&lt;/html&gt;]]&gt;/content&gt; 
        &lt;/record&gt; 
        ... 
        &lt;record&gt; 
        ... 
        &lt;/record&gt; 
        &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/group&gt; 
        &lt;/gsafeed&gt; 
        </code> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Querverweisfeldname </p> </td> 
      <td colname="col2"> <p>Gibt ein Metadatenfeld an, dessen Werte als Look-up-Schlüssel in den Daten der Attribute Loader-Konfiguration verwendet werden. Wenn kein Wert ausgewählt ist (<b>—None—</b>), sind die Daten dieser Konfiguration nicht zur Verwendung in Rangberechnungen verfügbar (<b>Regeln</b> &gt; <b>Rangregeln</b> &gt; <b>Regeln bearbeiten</b>). Wenn Sie einen Wert auswählen, werden die Werte dieses Felds verwendet, um die Site-Suche/Merchandising-Dokumente mit den Daten dieser Konfiguration zu vergleichen. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Statische Tage </p> </td> 
      <td colname="col2"> <p>Legt das Mindestintervall zwischen Downloads von Attribute Loader-Daten fest. Durch den Index ausgelöste Downloads, die innerhalb des Intervalls für die Download-Aktualisierungshäufigkeit auftreten, werden ignoriert. Wenn Sie diesen Wert auf den Standardwert 1 setzen, werden die Attribute Loader-Daten innerhalb eines Zeitraums von 24 Stunden nur einmal heruntergeladen. Alle Suchindizes, die innerhalb des Intervalls für die Download-Aktualisierungsfrequenz auftreten, verwenden den letzten heruntergeladenen Datensatz. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Landkarte </p> </td> 
      <td colname="col2"> <p>Ermöglicht die Angabe von XML-Element-zu-Metadaten-Zuordnungen mithilfe von XPath-Ausdrücken. </p> <p> 
      <ul id="ul_604108C0277C4892AE8A40CA39889ABD"> 
      <li id="li_0AF92270AE9F4BA8B2C7EE41FABC0F34"> <span class="uicontrol"> Tag </span> <p>Gibt eine XPath-Darstellung der analysierten XML-Daten an. Unter Verwendung des obigen Beispieldokuments für die Adobe XML unter der Option ItemTag kann es mit der folgenden Syntax zugeordnet werden: </p> <p> <code class="syntax xml"> /record/@displayurl&nbsp;-&gt;&nbsp;page-url 
        /record/metadata/meta[@name='title']/@content&nbsp;-&gt;&nbsp;title 
        /record/metadata/meta[@name='description']/@content&nbsp;-&gt;&nbsp;desc 
        /record/metadata/meta[@name='description']/@content&nbsp;-&gt;&nbsp;body </code> </p> <p>Die obige Syntax lautet wie folgt: </p> <p> 
        <ul id="ul_6400EBD08D424EADA1612FE4F7EFB640"> 
        <li id="li_9958F9B40D42434195597DBA9F2AF28F"> <code class="syntax xml"> /record/@displayurl&amp;nbsp;-&gt;&amp;nbsp;page-url </code> <p>Das Attribut <span class="codeph"> displayURL </span> des Elements <span class="codeph"> record </span> ist dem Metadatenfeld <span class="codeph"> page-url </span> zugeordnet. </p> </li> 
        <li id="li_759013EA02CD48BE971A55B0A6A11424"> <code class="syntax xml"> /record/metadata/meta[@name='title']/@content&amp;nbsp;-&gt;&amp;nbsp;title </code> <p>Das Attribut <span class="codeph"> content </span> jedes <span class="codeph"> meta </span> -Elements, das in einem <span class="codeph"> -Metadatenelement </span> enthalten ist, das in einem <span class="codeph"> -Datensatz </span>-Element enthalten ist, dessen Namensattribut <span class="codeph"> title </span> ist, wird dem Metadatenfeld <span class="codeph"> title &lt;a11 zugeordnet/&gt;.</span> </p> </li> 
        <li id="li_E741CA59197D462EB2946EDE874AFDC8"> <code class="syntax xml"> /record/metadata/meta[@name='description']/@content&amp;nbsp;-&gt;&amp;nbsp;desc </code> <p>Das Attribut <span class="codeph"> content </span> jedes <span class="codeph"> meta </span> -Elements, das in einem <span class="codeph"> -Metadatenelement </span> enthalten ist, das innerhalb des Elements <span class="codeph"> record </span> enthalten ist, dessen Namensattribut <span class="codeph"> description </span> ist, wird dem Metadatenfeld <span class="codeph"> desc &lt;a1 zugeordnet 1/&gt;.</span> </p> </li> 
        <li id="li_E35EAE3D284D46D485D9064D7BB6AB13"> <code class="syntax xml"> /record/metadata/meta[@name='description']/@content&amp;nbsp;-&gt;&amp;nbsp;body </code> <p>Das Attribut <span class="codeph"> content </span> jedes <span class="codeph"> meta </span> -Elements, das in einem <span class="codeph"> -Metadatenelement </span> enthalten ist, das im Element <span class="codeph"> Datensatz </span> enthalten ist, dessen Namensattribut <span class="codeph"> description </span> ist, wird dem Metadatenfeld <span class="codeph"> body &lt;a1 zugeordnet/&gt;.</span> </p> </li> 
        </ul> </p> <p>XPath ist eine relativ komplizierte Notation. Weitere Informationen finden Sie unter: </p> <p>Siehe <a href="https://www.w3schools.com/xml/xpath_intro.asp" scope="external" format="html"> https://www.w3schools.com/xml/xpath_intro.asp </a> </p> </li> 
      <li id="li_8147075D7ACD4811A7ED335F23FE62A6"> <span class="uicontrol"> Feld </span> <p>Definiert den Attribut name -Wert, der für jedes generierte Tag <span class="codeph"> &lt;meta&gt; </span> verwendet wird. </p> </li> 
      <li id="li_2380199D63BF425A919606D8232FA6E2"> <span class="uicontrol"> Metadaten? </span> <p>Verursacht, dass <span class="uicontrol"> Feld </span> zu einer Dropdown-Liste wird, aus der Sie definierte Metadatenfelder für das aktuelle Konto auswählen können. </p> <p>Der Wert <span class="uicontrol"> Feld </span> kann ein nicht definiertes Metadatenfeld sein, falls gewünscht. Manchmal ist ein nicht definiertes Metadatenfeld nützlich, um Inhalte zu erstellen, die von <span class="wintitle"> Filterskript </span> verwendet werden. </p> <p>Siehe <a href="../c-about-settings-menu/c-about-filtering-menu.md#concept_E56B73D625854AB2A899EF2D56CFCB47" type="concept" format="dita" scope="local"> Informationen zum Filtern von Skript </a>. </p> <p>Wenn Attribute Loader XML-Dokumente mit mehreren Treffern in einem Zuordnungsfeld verarbeitet, werden die verschiedenen Werte im resultierenden zwischengespeicherten Dokument zu einem einzigen Wert verkettet. Standardmäßig werden diese Werte mit einem Kommatrennzeichen kombiniert. Angenommen, der entsprechende Wert <span class="wintitle"> Feld </span> ist ein definiertes Metadatenfeld. Darüber hinaus ist für dieses Feld das Attribut <span class="wintitle"> Zulassungslisten </span> festgelegt. In diesem Fall wird der Wert "Listentrennzeichen"des Felds, das erste definierte Trennzeichen, in der Verkettung verwendet. </p> </li> 
      <li id="li_DEA24003E97E406DA2510C43CCFDC70E"> <span class="uicontrol"> Primärschlüssel? </span> <p>Nur ein Feld wird als Primärschlüssel identifiziert. Dieses Feld wird als "Fremdschlüssel"verwendet, um die Attribute Loader-Daten mit dem entsprechenden Dokument im Index abzugleichen. </p> </li> 
      <li id="li_80D6AF130FCE40AC972FE4B605B86BF6"> <span class="uicontrol"> HTML entfernen?  </span> <p>Wenn diese Option aktiviert ist, werden alle in den Daten dieses Felds gefundenen HTML-Tags entfernt. </p> </li> 
      <li id="li_D40E2F9AD8AD49FC9AC4B8C75BA31E28"> <span class="uicontrol"> Aktion </span> <p>Ermöglicht das Hinzufügen von Zeilen zur Zuordnung oder das Entfernen von Zeilen aus der Zuordnung. Die Reihenfolge der Zeilen ist nicht wichtig. </p> </li> 
      </ul> </p> </td> 
      </tr> 
    </tbody> 
    </table>

1. (Optional) Klicken Sie auf **[!UICONTROL Setup Maps]** , um ein Beispiel Ihrer Datenquelle herunterzuladen. Die Daten werden auf Eignung geprüft.
1. Klicken Sie auf **[!UICONTROL Add]** , um die Konfiguration zur Seite [!DNL Attribute Loader Definitions] hinzuzufügen.
1. Klicken Sie auf der Seite [!DNL Attribute Loader Definitions] auf **[!UICONTROL rebuild your staged site index]**.
1. (Optional) Führen Sie auf der Seite [!DNL Attribute Loader Definitions] einen der folgenden Schritte aus:

   * Klicken Sie auf **[!UICONTROL History]** , um alle Änderungen rückgängig zu machen, die Sie vorgenommen haben.

      Siehe [Verwendung der Option Verlauf](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Klicken **[!UICONTROL Live]**.

      Siehe [Anzeigen von Live-Einstellungen](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Klicken **[!UICONTROL Push Live]**.

      Siehe [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Bearbeiten einer Attributlader-Definition {#task_AA2D1B2BCAFA44A6A0C59A0318274E80}

Sie können einen von Ihnen definierten Attributlader bearbeiten.

>[!NOTE]
>
>Um Attributlader zu verwenden, müssen Sie ihn möglicherweise in Ihrem Konto von Ihrem Kundenbetreuer für Adobe oder vom Support für Adoben aktivieren lassen.

Es sind nicht alle Attributlader-Optionen verfügbar, die Sie ändern können, z. B. der Attributladerame oder -typ aus der Dropdownliste [!DNL Type] .

**So bearbeiten Sie eine Definition für Attributlader**

1. Klicken Sie im Produktmenü auf **[!UICONTROL Settings]** > **[!UICONTROL Metadata]** > **[!UICONTROL Attribute Loader]**.
1. Klicken Sie auf der Seite [!DNL Attribute Loader] unter der Spaltenüberschrift [!DNL Actions] für einen Attributlader-Definitionsnamen, dessen Einstellungen Sie ändern möchten, auf **[!UICONTROL Edit]** .
1. Legen Sie auf der Seite [!DNL Attribute Loader Edit] die gewünschten Optionen fest.

   Siehe Tabelle der Optionen unter [Definition eines Attribut-Laders](../c-about-settings-menu/c-about-metadata-menu.md#task_A735E5EF763343A9B675E1A3B09AFDBC) hinzufügen.
1. Klicken **[!UICONTROL Save Changes]**.
1. (Optional) Klicken Sie auf der Seite [!DNL Attribute Loader Definitions] auf **[!UICONTROL rebuild your staged site index]**.
1. (Optional) Führen Sie auf der Seite [!DNL Attribute Loader Definitions] einen der folgenden Schritte aus:

   * Klicken Sie auf **[!UICONTROL History]** , um alle Änderungen rückgängig zu machen, die Sie vorgenommen haben.

      Siehe [Verwendung der Option Verlauf](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Klicken **[!UICONTROL Live]**.

      Siehe [Anzeigen von Live-Einstellungen](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Klicken **[!UICONTROL Push Live]**.

      Siehe [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Kopieren einer Attribute Loader-Definition {#task_9B40D5ECFC81411E9480F62A0FD5F2E0}

Sie können eine vorhandene Attribute Loader-Definition kopieren, um sie als Grundlage für einen neuen Attribut-Lader zu verwenden, den Sie erstellen möchten.

>[!NOTE]
>
>Um Attributlader zu verwenden, müssen Sie ihn möglicherweise in Ihrem Konto von Ihrem Kundenbetreuer für Adobe oder vom Support für Adoben aktivieren lassen.

Beim Kopieren einer Attribut-Lader-Definition ist die kopierte Definition standardmäßig deaktiviert. Um die Definition zu aktivieren oder zu aktivieren, müssen Sie sie auf der Seite [!DNL Attribute Loader Edit] bearbeiten und **[!UICONTROL Enable]** auswählen.

Siehe [Bearbeiten einer Attribut-Lader-Definition](../c-about-settings-menu/c-about-metadata-menu.md#task_AA2D1B2BCAFA44A6A0C59A0318274E80).

**So kopieren Sie eine Definition für Attributlader**

1. Klicken Sie im Produktmenü auf **[!UICONTROL Settings]** > **[!UICONTROL Metadata]** > **[!UICONTROL Attribute Loader]**.
1. Klicken Sie auf der Seite [!DNL Attribute Loader] unter der Spaltenüberschrift [!DNL Actions] auf **[!UICONTROL Copy]** für einen Namen für die Attributlader-Definition, dessen Einstellungen Sie duplizieren möchten.
1. Geben Sie auf der Seite [!DNL Attribute Loader Copy] den neuen Namen der Definition ein.
1. Klicken **[!UICONTROL Copy]**.
1. (Optional) Führen Sie auf der Seite [!DNL Attribute Loader Definitions] einen der folgenden Schritte aus:

   * Klicken Sie auf **[!UICONTROL History]** , um alle Änderungen rückgängig zu machen, die Sie vorgenommen haben.

      Siehe [Verwendung der Option Verlauf](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Klicken **[!UICONTROL Live]**.

      Siehe [Anzeigen von Live-Einstellungen](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Klicken **[!UICONTROL Push Live]**.

      Siehe [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Umbenennen einer Attributlader-Definition {#task_58D5DFD7EBC04111BCB91118E4440DB4}

Sie können den Namen einer vorhandenen Attribute Loader-Definition ändern.

>[!NOTE]
>
>Um Attributlader zu verwenden, müssen Sie ihn möglicherweise in Ihrem Konto von Ihrem Kundenbetreuer für Adobe oder vom Support für Adoben aktivieren lassen.

**So benennen Sie eine Definition für Attributlader um**

1. Klicken Sie im Produktmenü auf **[!UICONTROL Settings]** > **[!UICONTROL Metadata]** > **[!UICONTROL Attribute Loader]**.
1. Klicken Sie auf der Seite [!DNL Attribute Loader] unter der Spaltenüberschrift [!DNL Actions] für den Definitionsnamen des Attributladers, den Sie ändern möchten, auf **[!UICONTROL Rename]** .
1. Geben Sie auf der Seite [!DNL Attribute Loader Rename] im Feld [!DNL Name] den neuen Namen der Definition ein.
1. Klicken **[!UICONTROL Rename]**.
1. (Optional) Führen Sie auf der Seite [!DNL Attribute Loader Definitions] einen der folgenden Schritte aus:

   * Klicken Sie auf **[!UICONTROL History]** , um alle Änderungen rückgängig zu machen, die Sie vorgenommen haben.

      Siehe [Verwendung der Option Verlauf](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Klicken **[!UICONTROL Live]**.

      Siehe [Anzeigen von Live-Einstellungen](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Klicken **[!UICONTROL Push Live]**.

      Siehe [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Laden von Attribute Loader-Daten {#task_2F3C55189B0A4049AB2113F2291CC181}

Sie können die konfigurierten Attribute Loader-Daten in Site-Suche/Merchandising herunterladen.

Auf der Seite [!DNL Data Load] finden Sie die folgenden Informationen zum Status Ihres letzten Datenladevorgangs für Attributlader:

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Statusfeld </p> </th> 
   <th colname="col2" class="entry"> <p>Beschreibung </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Status </p> </td> 
   <td colname="col2"> <p>Gibt den Erfolg oder Misserfolg des letzten Datenladeversuchs an. Oder es zeigt den Status eines bereits ausgeführten Datenladevorgangs an. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Startzeit </p> </td> 
   <td colname="col2"> <p>Zeigt das Datum und die Uhrzeit des letzten Ladevorgangs an. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Stoppzeit </p> </td> 
   <td colname="col2"> <p>Zeigt das Datum und die Uhrzeit des letzten Datenladevorgangs an. Oder sie zeigt an, dass der aktuelle Datenladevorgang noch läuft. </p> </td> 
  </tr> 
 </tbody> 
</table>

**So laden Sie Attribute Loader-Daten**

1. Klicken Sie im Produktmenü auf **[!UICONTROL Settings]** > **[!UICONTROL Metadata]** > **[!UICONTROL Attribute Loader]**.
1. Klicken Sie auf der Seite [!DNL Attribute Loader Definitions] auf **[!UICONTROL Load Attribute Loader Data]**.
1. Führen Sie auf der Seite **[!UICONTROL Attribute Loader Data Load]** einen der folgenden Schritte aus:

   * Klicken Sie auf **[!UICONTROL Start Load]** , um den Ladevorgang zu starten.

      Während eines Datenladevorgangs stellt die Zeile **Progress** Informationen zum Fortschritt bereit.

   * Klicken Sie auf **[!UICONTROL Stop Load]** , um den Ladevorgang zu beenden.

1. Klicken Sie auf **[!UICONTROL Close]** , um zur Seite [!DNL Attribute Loader Definitions] zurückzukehren.

## Vorschau von Attribute Loader-Daten {#task_735CDCC1D8174B7B9F5B8E0AFA5F0CA0}

Sie können die Vorschau verwenden, um Ihre zuletzt geladenen Attribute Loader-Daten anzuzeigen.

Die Spalte Zeile in der Tabelle zeigt die Zahl für jede Datenzeile an und gibt die ursprüngliche Reihenfolge an, in der die Attribute Loader-Werte geladen wurden.

Die übrigen Spalten zeigen die Werte an, die mit jedem Eintrag verknüpft sind.

Wenn die Tabelle leer ist, bedeutet dies, dass Sie noch keine Attribute Loader-Daten geladen haben. Sie können die Seite [!DNL Attribute Loader Data Preview] schließen und dann Attribute Loader-Daten laden.

Siehe [Laden von Attribute Loader-Daten](../c-about-settings-menu/c-about-metadata-menu.md#task_2F3C55189B0A4049AB2113F2291CC181).

**Vorschau von Attributladereadaten anzeigen**

1. Klicken Sie im Produktmenü auf **[!UICONTROL Settings]** > **[!UICONTROL Metadata]** > **[!UICONTROL Attribute Loader]**.
1. Klicken Sie auf der Seite [!DNL Attribute Loader Definitions] unter der Spalte [!DNL Actions] für die Konfiguration, deren heruntergeladene Daten Sie anzeigen möchten, auf **[!UICONTROL Preview]** .
1. Verwenden Sie auf der Seite [!DNL Attribute Loader Data Preview] die Navigations- und Anzeigeoptionen oben und unten auf der Seite, um die Daten anzuzeigen.

   Klicken Sie auf eine beliebige Spaltenüberschrift in der Tabelle, um die Daten in auf- oder absteigender Reihenfolge zu sortieren.
1. Führen Sie einen der folgenden Schritte aus:

   * Klicken Sie auf **[!UICONTROL Download to Desktop]** , um die Tabelle als .xlt-Datei herunterzuladen und zu speichern.
   * Schließen Sie die Seite, wenn Sie die Vorschau der Attribute Loader-Daten abgeschlossen haben, und kehren Sie zur zuvor angezeigten Seite zurück.

## Anzeigen der Einstellungen einer Attributlader-Definition {#task_EA99A9694FE948ADA82C1DBA0667851B}

Sie können die Konfigurationseinstellungen einer vorhandenen Attribute Loader-Definition überprüfen.

Nachdem der Seite [!DNL Attribute Loader Definitions] eine Definition für Attributlader hinzugefügt wurde, können Sie deren Einstellung Typ nicht ändern. Stattdessen müssen Sie die Definition löschen und dann eine neue hinzufügen.

>[!NOTE]
>
>Um Attributlader zu verwenden, müssen Sie ihn möglicherweise in Ihrem Konto von Ihrem Kundenbetreuer für Adobe oder vom Support für Adoben aktivieren lassen.

**So zeigen Sie die Einstellungen einer Attribute Loader-Definition an**

1. Klicken Sie im Produktmenü auf **[!UICONTROL Settings]** > **[!UICONTROL Metadata]** > **[!UICONTROL Attribute Loader]**.
1. Klicken Sie auf der Seite [!DNL Attribute Loader] unter der Spaltenüberschrift [!DNL Actions] auf **[!UICONTROL Edit]** für den Namen einer Attributlader-Definition, deren Einstellungen Sie überprüfen oder bearbeiten möchten.

## Anzeigen des Protokolls aus dem letzten Laden der Attribute Loader-Daten {#task_9C7D6E34BB6C4A40B7CA3EE36ACB0837}

Sie können [!DNL View Log] verwenden, um die Datenprotokolldatei von Attribut Loader des letzten Download-Prozesses zu untersuchen. Sie können auch die Protokollansicht verwenden, um einen laufenden Download zu überwachen.

Siehe [Laden von Attribute Loader-Daten](../c-about-settings-menu/c-about-metadata-menu.md#task_2F3C55189B0A4049AB2113F2291CC181).

**So zeigen Sie das Protokoll aus dem letzten Laden der Attribute Loader-Daten an**

1. Klicken Sie im Produktmenü auf **[!UICONTROL Settings]** > **[!UICONTROL Metadata]** > **[!UICONTROL Attribute Loader]**.
1. Klicken Sie auf der Seite [!DNL Attribute Loader Definitions] auf **[!UICONTROL View Log]**. Protokollseite,
1. Verwenden Sie auf der Seite [!DNL Attribute Loader Data Log] die Navigations- und Anzeigeoptionen oben und unten auf der Seite, um die Protokollinformationen anzuzeigen.
1. Wenn Sie fertig sind, schließen Sie die Seite, um zur Seite [!DNL Attribute Loader Definitions] zurückzukehren.

## Löschen einer Definition für Attributlader {#task_E8980F66888B476E98C228C1D307EDF8}

Sie können eine vorhandene Attribute Loader-Definition löschen, die Sie nicht mehr benötigen oder verwenden.

>[!NOTE]
>
>Um Attributlader zu verwenden, müssen Sie ihn möglicherweise in Ihrem Konto von Ihrem Kundenbetreuer für Adobe oder vom Support für Adoben aktivieren lassen.

**So löschen Sie eine Definition für Attributlader**

1. Klicken Sie im Produktmenü auf **[!UICONTROL Settings]** > **[!UICONTROL Metadata]** > **[!UICONTROL Attribute Loader]**.
1. Klicken Sie auf der Seite [!DNL Attribute Loader Definitions] unter der Spaltenüberschrift [!DNL Actions] für den Definitionsnamen des Attributladers, den Sie entfernen möchten, auf **[!UICONTROL Delete]** .
1. Klicken Sie auf der Seite [!DNL Attribute Loader Delete] auf **[!UICONTROL Delete]**.
