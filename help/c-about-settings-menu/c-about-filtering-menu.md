---
description: Verwenden Sie das Menü "Filtern", um Skripten zu verwenden, die den Inhalt eines Web-Dokuments ändern, bevor es indiziert wird.
solution: Target
subtopic: Filtering
title: Über das Menü "Filtern"
topic: Settings,Site search and merchandising
uuid: ebb08fa8-4e17-417d-868b-11fc2af9f284
translation-type: tm+mt
source-git-commit: d015154efdccbb4c6a39a56907c0c337ec065c9f
workflow-type: tm+mt
source-wordcount: '4008'
ht-degree: 1%

---


# Informationen zum Filtermenü{#about-the-filtering-menu}

Verwenden Sie das Menü &quot;Filtern&quot;, um Skripten zu verwenden, die den Inhalt eines Web-Dokuments ändern, bevor es indiziert wird.

## Informationen zum Filtern von Skript {#concept_E56B73D625854AB2A899EF2D56CFCB47}

Sie können [!DNL Filtering Script] verwenden, um den Inhalt eines Web-Dokuments zu ändern, bevor es indiziert wird.

Sie können HTML-Tags einfügen, irrelevante Inhalte entfernen und sogar neue HTML-Metadaten erstellen, die auf der URL, dem MIME-Typ und bestehenden Inhalten eines Dokuments basieren. Das Filterskript ist ein Perl-Skript, das eine leistungsstarke Zeichenfolgenbearbeitung und die Flexibilität bei der regelmäßigen Ausdruck-Übereinstimmung bietet. Sie verwenden das Filterskript mit einem Initialisierungsskript, einem Terminierungsskript, einem URL-Masken-Skript und einer Test-URL.

Das Filterskript wird jedes Mal ausgeführt, wenn ein Dokument von Ihrer Website gelesen wird. Das Skript läuft als Standardfilter, d. h. liest Daten aus STDIN, transformiert diese Daten in irgendeiner Weise und schreibt die Ergebnisse in STDOUT. Sie können das Filterskript verwenden, um Statusmeldungen vom Filterskript zum Indexprotokoll zu drucken. Sie drucken die Nachrichten entweder an STDERR oder über die `_search_debug_log()` UnterRoutine.

Einige GNU-Diff-Optionen, die Sie im **[!UICONTROL Expert (diff)]**-Modus auf der Seite &quot;Staged Filtering Script&quot;verwenden können, beinhalten Folgendes:

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>GNU-Diff-Option </p> </th> 
   <th colname="col2" class="entry"> <p>Beschreibung </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> -b </span> </p> </td> 
   <td colname="col2"> <p> Ignoriert Änderungen an der Größe des Leerraums. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> -B </span> </p> </td> 
   <td colname="col2"> <p> Ignoriert Änderungen, die leere Zeilen einfügen oder löschen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> -c </span> </p> </td> 
   <td colname="col2"> <p> Verwendet das Ausgabeformat "Kontext"und zeigt drei Zeilen Kontext an. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> -C-Linien  </span> </p> </td> 
   <td colname="col2"> <p> Verwendet das Ausgabeformat "Kontext", zeigt Zeilen (eine Ganzzahl) mit Kontext an oder drei, wenn keine Zeilen angegeben werden. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> -i </span> </p> </td> 
   <td colname="col2"> <p> Änderungen im Einzelfall ignorieren; die Entsprechung von Groß- und Kleinbuchstaben berücksichtigen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> -f  </span> </p> </td> 
   <td colname="col2"> <p> Stellt eine Ausgabe dar, die ähnlich wie ein ed-Skript aussieht, jedoch Änderungen in der Reihenfolge enthält, in der sie in der Datei angezeigt wird. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> -n </span> </p> </td> 
   <td colname="col2"> <p> Gibt RCS-Dateien aus; wie <span class="codeph"> -f </span>, außer dass jeder Befehl die Anzahl der betroffenen Zeilen angibt. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>-u </p> </td> 
   <td colname="col2"> <p> Verwendet das einheitliche Ausgabeformat mit drei Zeilen Kontext. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> -U Zeilen  </span> </p> </td> 
   <td colname="col2"> <p> Verwendet das einheitliche Ausgabeformat, zeigt Zeilen (eine Ganzzahl) des Kontexts an oder drei, wenn keine Zeilen angegeben werden. </p> </td> 
  </tr> 
 </tbody> 
</table>

Sie können lokale Variablen, globale Variablen oder beides in diesen Skripten verwenden. Allen globalen Variablen wird der Namensraum &quot;main::&quot;vorangestellt. Wenn das Filterskript gestartet wird, enthält seine Umgebung die folgenden Standarddateihandler:

* STDIN - nichts (gibt beim Lesen sofort EOF zurück)
* STDOUT - Ersatz-HTML (wenn Daten in STDOUT gedruckt werden, wird sie anstelle des ursprünglichen Dokuments verwendet)
* STDERR - an STDERR gedruckte Daten werden als Fehler im Indexprotokoll gedruckt

Zusätzlich können Sie mit der UnterRoutine `_search_debug_log()` benutzerdefinierte Meldungen in das Indexprotokoll schreiben, wie im folgenden Beispiel:

```
# Log information to the Index Log 
_search_debug_log("Done processing document: " . $main::search_url);
```

Diese Meldungen werden mit dem Wort `DEBUG` als Vorwort angezeigt und nicht als Fehler protokolliert.

Im Folgenden finden Sie ein Beispiel für die Filterung. Webseiten-Felder `<title>` beginnen oft mit dem Namen der Firma. Obwohl diese Informationen für die Navigation auf der Site nützlich sind, sind sie bei der Suche nicht relevant. Wenn die Titel aller MegaCorp-Webseiten mit einer gemeinsamen Zeichenfolge wie der folgenden Beginn enthalten:

```
<title>MegaCorp -- meaningful title 
here</title>
```

Sie sollten &quot; `MegaCorp --`&quot;am Anfang jedes Dokument-Titels entfernen und jedes mit dem Filterskript verarbeitete Dokument zählen. Dazu können Sie das folgende Skript verwenden:

```
# Make sure this is an HTML document. 
if ($main::ws_content_type =~ /^text\/html/) { 
    # Read the entire document into a local scalar variable. 
    my @docarray = <>; 
    my $doc = join("", @docarray); 
 
    # Remove "MegaCorp -- " from the title. 
    $doc =~ s/(<TITLE>)MegaCorp -- /$1/gis; 
 
    # Print the resulting document. 
    print $doc; 
 
    # Count that we've filtered one more document. 
    $main::doc_count++; 
}
```

## Globale Variablen {#global-variables}

Sie können die folgenden Variablen in jedem Filterskript verwenden:

| Variable | Beschreibung |
|--- |--- |
| `$main::search_crawl_type` | Der Wert von `$main::search_crawl_type` gibt den Typ des laufenden Indexvorgangs an.  Veraltetes Formular: `$main::ws_crawl_type` Die Indexvorgänge und die zugehörigen Werte umfassen Folgendes: <ul><li>Vollständiger Index: Manuell - `manual`</li><li>Vollständiger Index: Geplant - `auto`</li><li>Vollständiger Index: Remote Control - `CGI`</li><li>Inkrementeller Index: Manuell - `manual-incremental`</li><li>Inkrementeller Index: Geplant - `auto-incremental` </li><li>Inkrementeller Index: Remote Control - `CGI-incremental`</li><li>Skriptindex: Manuell - `manual-indexlist.txt` </li><li>Skriptindex: Geplant - `auto-indexlist.txt`</li><li>Skriptindex: Remote Control - `CGI-indexlist.txt`</li><li>Erneut erzeugen - `manual-upgrade`</li></ul> |
| `$main::search_clear_cache` | Der Wert gibt an, ob die Indexierungsoption &quot;Index-Cache leeren&quot;für den aktuellen Indexvorgang angefordert wurde. Wenn &quot;Index-Cache leeren&quot;angefordert wurde, lautet der Wert von `$main::search_clear_cache` &quot;`1`&quot;.  Veraltete Form: `$main::ws_clear_cache` |
| `$main::search_fields` | Der Wert enthält eine tabulatorgetrennte Liste der Metadatenfelder, die im Konto definiert sind. Standardmäßig lautet der Wert:   `url title desc keys target body alt date charset language` Veraltetes Formular: `$main::ws_fields` |
| `$main::search_collections` | Der Wert enthält eine tabulatorgetrennte Liste der im Konto definierten Sammlungen.  Veraltete Form: `$main::ws_collections` |
| `$main::search_url` | Der Wert ist die vollständig qualifizierte URL des Dokuments.  Veraltete Form: `$main::ws_url` |
| `$main::search_content_type` | Der Wert ist der Inhaltstyp des Dokuments, der vom http-equiv-Meta-Tag abgerufen wird. Ein typischer Wert ist &quot;text/html&quot;. charset=iso-8859-1&quot;.  Veraltete Form: `$main::ws_content_type` |
| `$main::search_content_class` | Der Wert ist die Inhaltsklasse des Dokuments, wie sie aus dem Feld &quot;content-type&quot;abgeleitet ist.  Veraltete Form: `$main::ws_content_class` |
| `$main::search_syntax_check` | Der Wert spiegelt die Verwendung der Schaltfläche &quot;Syntax überprüfen&quot;wider. Wenn darauf geklickt wird, ist der Wert 1 (1); Andernfalls ist der Wert 0 (null).  Veraltete Form: `$main::ws_syntax_check` |
| `$main::search_last_mod_date` | Wenn dieser vom Webserver bereitgestellt wird, enthält dieser Wert die Epochendarstellung (Sekunden seit dem 1. Januar 1970) des letzten Änderungsdatums des Dokuments.  Sie können diesen Wert mithilfe des Perl localtime()-Bibliotheksaufrufs formatieren. |

### QuickInfos {#section_89A5C16911744AF98E232DF608C6A1F5}

* Allen globalen Variablen wird der Namensraum &quot;main::&quot; vorangestellt: `$main::doc_count = 0;`
* Alle lokalen Variablen werden mit &quot;my&quot;deklariert: `my $i = 0;`
* Unterroutinen werden im Initialisierungsskript definiert. Sie benötigen keinen expliziten &quot;main:&quot;-Namensraum: `sub my_sub {` `...`

   `}`

* Testen Sie das `$main::search_content_type`, bevor Sie Änderungen an einer Datei vornehmen. Beim Testen können Sie unvorsichtige Änderungen an Binärdateien wie SWF- oder PDF-Dateien vermeiden:

   `if ($main::search_content_type =~ /^text\/html/) { ...`

* `$main::search_content_type` ist der vollständige Content-Type-Header, der von Ihrem Server bereitgestellt wird. Es kann manchmal einen einfachen MIME-Typ enthalten, z. B. &quot;text/html&quot;. Sie kann auch einen MIME-Typ gefolgt von anderen Informationen wie der Zeichensatzkodierung des Dokuments wie &quot;text/html&quot;enthalten. charset=iso-8859-1&quot;.
* Für jeden Typ von Nicht-HTML-Dokument können `$main::search_content_type` verschiedene Werte annehmen. Der Test für jeden Wert in Ihrem Skript wird schwerfällig. Einige Word-Dokumente haben beispielsweise die Inhaltstypwerte &quot;application/msword&quot;, &quot;application/vnd.ms-word&quot;oder &quot;application/x-msword&quot;. In solchen Fällen kann `$main::search_content_class` die folgenden Werte annehmen:

   * html
   * pdf
   * word
   * excel
   * powerpoint
   * mp3
   * text

* In diesem Beispiel stimmen die Tests von `$main::search_content_class` für &quot;word&quot;mit allen drei möglichen Werten des Inhaltstyps überein.
* Wenn aus dem Filterskript nichts an STDOUT gedruckt wird, wird das Dokument genau so verwendet, wie es heruntergeladen wurde. Das heißt, wenn Sie nichts in einem Dokument ändern müssen, dann müssen Sie STDIN für dieses Dokument nicht in STDOUT kopieren.
* Wenn Sie den gesamten Text aus einem Dokument entfernen möchten, drucken Sie eine gültige STDOUT-Datei. Um beispielsweise den gesamten Text vollständig aus einem HTML-Dokument zu entfernen, führen Sie folgende Schritte aus: `print "<html></html>";`

## Hinzufügen eines Filterskripts {#task_0AB84FD1133F47F9AA069A79BEA13A22}

Das Filterskript ist ein Perl-Skript, das für jedes von Ihrer Website heruntergeladene Dokument ausgeführt wird.

Sie verwenden das Filterskript in Verbindung mit einem Initialisierungsskript, einem Terminierungsskript und einem URL-Masken-Skript.

Stellen Sie sicher, dass Sie Ihren Site-Index neu erstellen, damit die Ergebnisse Ihres Filterskripts für Ihre Kunden sichtbar sind.

Siehe [Konfigurieren eines inkrementellen Indexes einer gestaffelten Website](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0).

**So fügen Sie ein Filterskript hinzu**

1. Klicken Sie im Produktmenü auf **[!UICONTROL Settings]** > **[!UICONTROL Filtering]** > **[!UICONTROL Filtering Script]**.
1. (Optional) Geben Sie auf der Seite [!DNL Filtering Script] im Feld [!DNL Test URL] die URL eines Dokuments auf Ihrer Website ein.

   Klicken Sie auf eine Testoption, um Änderungen am HTML-Rohtext anzuzeigen.

   <table> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> <p>Option </p> </th> 
      <th colname="col2" class="entry"> <p>Beschreibung </p> </th> 
      </tr> 
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <p>URL-Feld testen </p> </td> 
      <td colname="col2"> <p>Hier können Sie die URL eines Dokuments auf Ihrer Website eingeben. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Test </p> </td> 
      <td colname="col2"> <p>Prüft die URL auf die Filterskripte und URL-Masken. </p> <p>Das Test-URL-Dokument wird heruntergeladen und dann als STDIN-Eingabe für das Filterskript verwendet. Anschließend werden die Skripten für Initialisierung, Filterung und Beendigung ausgeführt. Wenn eine STDOUT-Ausgabe aus dem Filterskript vorhanden ist, wird diese Ausgabe in einem neuen Browserfenster angezeigt. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Nur testen </p> </td> 
      <td colname="col2"> <p>Testt nur den Vorgang des Skripts. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Vorschau </p> </td> 
      <td colname="col2"> <p>Ermöglicht die Ansicht der Seite. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Vollständige Visualisierung </p> </td> 
      <td colname="col2"> <p>Erstellt eine vollständige Ansicht der Dokumente vor und nach der Tabelle. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Kurz visuell </p> </td> 
      <td colname="col2"> <p>Zeigt nur die Unterschiede zwischen den Vor- und Nach-Ansichten an. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Expert (Diff) </p> </td> 
      <td colname="col2"> <p>Zeigt die Rohausgabe des GNU diff-Befehls an, der zum Vergleichen der Dateien mithilfe der bereitgestellten Befehlszeilenoptionen verwendet wird. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Filtern von Skript </p> </td> 
      <td colname="col2"> <p>Ermöglicht das Einfügen des Filterskripts in das bereitgestellte Feld. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Änderungen speichern </p> </td> 
      <td colname="col2"> <p>Speichert das Filterskript. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Syntax prüfen </p> </td> 
      <td colname="col2"> <p>Ermöglicht eine schnelle Syntaxprüfung des Skripts durch Ausführen der Initialisierungs-, Filter- und Terminierungsskripte. Das Skript wird nicht aktualisiert und gespeichert. </p> <p>Alle Perl-Compilerfehler und -Warnungen sowie alle STDERR-Ausgaben werden gedruckt. </p> <p>Bevor die Auswirkungen des Skripts für Kunden sichtbar sind, müssen Sie Ihren Site-Index neu erstellen. </p> </td> 
      </tr> 
    </tbody> 
    </table>

   **GNU-Diff-Befehlszeilenoptionen**

   Einige GNU-Diff-Optionen, die Sie im **[!UICONTROL Expert (diff)]**-Modus auf der Seite &quot;Staged Filtering Script&quot;verwenden können, beinhalten Folgendes:

   <table> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> <p>GNU-Diff-Befehlszeilenoption </p> </th> 
      <th colname="col2" class="entry"> <p>Beschreibung </p> </th> 
      </tr> 
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <p> <span class="codeph"> -b  </span> </p> </td> 
      <td colname="col2"> <p> Ignoriert Änderungen an der Größe des Leerraums. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p> <span class="codeph"> -B  </span> </p> </td> 
      <td colname="col2"> <p> Ignoriert Änderungen, die leere Zeilen einfügen oder löschen. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p> <span class="codeph"> -c  </span> </p> </td> 
      <td colname="col2"> <p> Verwendet das Ausgabeformat "Kontext"und zeigt drei Zeilen Kontext an. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p> <span class="codeph"> -C-Linien  </span> </p> </td> 
      <td colname="col2"> <p> Verwendet das Ausgabeformat "Kontext", zeigt Zeilen (eine Ganzzahl) mit Kontext an oder drei, wenn keine Zeilen angegeben werden. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p> <span class="codeph"> -i  </span> </p> </td> 
      <td colname="col2"> <p> Änderungen im Einzelfall ignorieren; die Entsprechung von Groß- und Kleinbuchstaben berücksichtigen. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p> <span class="codeph"> -f  </span> </p> </td> 
      <td colname="col2"> <p> Stellt eine Ausgabe dar, die ähnlich wie ein ed-Skript aussieht, jedoch Änderungen in der Reihenfolge enthält, in der sie in der Datei angezeigt wird. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p> <span class="codeph"> -n  </span> </p> </td> 
      <td colname="col2"> <p> Gibt RCS-Dateien aus; wie <span class="codeph"> -f </span>, außer dass jeder Befehl die Anzahl der betroffenen Zeilen angibt. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>-u </p> </td> 
      <td colname="col2"> <p> Verwendet das einheitliche Ausgabeformat mit drei Zeilen Kontext. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p> <span class="codeph"> -U Zeilen  </span> </p> </td> 
      <td colname="col2"> <p> Verwendet das einheitliche Ausgabeformat, zeigt Zeilen (eine Ganzzahl) des Kontexts an oder drei, wenn keine Zeilen angegeben werden. </p> </td> 
      </tr> 
    </tbody> 
    </table>

1. Klicken Sie auf **[!UICONTROL Test]**, um die Filterskripte und URL-Masken zu testen.

   Durch Klicken auf **[!UICONTROL Test]** wird Ihr Filterskript nicht aktualisiert und gespeichert.
1. Fügen Sie im Feld [!DNL Filtering Script] Ihr Skript ein.
1. (Optional) Klicken Sie auf **[!UICONTROL Check Syntax]**, um eine schnelle Syntaxprüfung Ihres Skripts durchzuführen, indem Sie die Filter-, Initialisierungs- und Terminierungsskripte ausführen.

   **[!UICONTROL Check Syntax]** aktualisiert und speichert Ihr Skript nicht.
1. Klicken **[!UICONTROL Save Changes]**.
1. (Optional) Erstellen Sie Ihren Stage-Site-Index neu, wenn Sie die Vorschauen durchführen möchten.

   Siehe [Konfigurieren eines inkrementellen Indexes einer gestaffelten Website](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0).
1. (Optional) Führen Sie auf der Seite [!DNL Filtering Script] einen der folgenden Schritte aus:

   * Klicken Sie auf **[!UICONTROL History]**, um alle vorgenommenen Änderungen wiederherzustellen.

      Siehe [Verwenden der Option Verlauf](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Klicken **[!UICONTROL Live]**.

      Siehe [Live-Einstellungen anzeigen](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Klicken **[!UICONTROL Push Live]**.

      Siehe [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Info zu Initialisierungsskript {#concept_048B4C8BC9F74BE8BB6162C490C201A3}

Sie können [!DNL Initialization Script] verwenden, um den Inhalt eines Web-Dokuments zu ändern, bevor es indiziert wird.

Sie können HTML-Tags einfügen, irrelevante Inhalte entfernen und sogar neue HTML-Metadaten erstellen, die auf der URL, dem MIME-Typ und bestehenden Inhalten eines Dokuments basieren. Das Initialisierungsskript ist ein Perl-Skript, das eine leistungsstarke Zeichenfolgenbearbeitung und die Flexibilität bei der regelmäßigen Ausdruck-Übereinstimmung bietet. Sie verwenden das Initialisierungsskript mit einem Filterskript, einem Terminierungsskript, einem URL-Masken-Skript und einer Test-URL.

Das Initialisierungsskript wird einmal ausgeführt, bevor die Indexierung beginnt. Verwenden Sie dieses Skript, um alle globalen Variablen und Unterroutinen zu initialisieren, die von Ihrem Filterskript verwendet werden. Sie können das Initialisierungsskript verwenden, um Statusmeldungen vom Filterskript in das Indexprotokoll zu drucken. Sie drucken die Nachrichten entweder an STDERR oder über die `_search_debug_log()` UnterRoutine.

Einige GNU-Diff-Optionen, die Sie im **[!UICONTROL Expert (diff)]**-Modus auf der Seite &quot;Staged Initialization Script&quot;verwenden können, beinhalten Folgendes:

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>GNU-Diff-Option </p> </th> 
   <th colname="col2" class="entry"> <p>Beschreibung </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> -b  </span> </p> </td> 
   <td colname="col2"> <p> Ignoriert Änderungen an der Größe des Leerraums. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> -B  </span> </p> </td> 
   <td colname="col2"> <p> Ignoriert Änderungen, die leere Zeilen einfügen oder löschen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> -c  </span> </p> </td> 
   <td colname="col2"> <p> Verwendet das Ausgabeformat "Kontext"und zeigt drei Zeilen Kontext an. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> -C-Linien  </span> </p> </td> 
   <td colname="col2"> <p> Verwendet das Ausgabeformat "Kontext", zeigt Zeilen (eine Ganzzahl) mit Kontext an oder drei, wenn keine Zeilen angegeben werden. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> -i  </span> </p> </td> 
   <td colname="col2"> <p> Änderungen im Einzelfall ignorieren; die Entsprechung von Groß- und Kleinbuchstaben berücksichtigen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> -f  </span> </p> </td> 
   <td colname="col2"> <p> Stellt eine Ausgabe dar, die ähnlich wie ein ed-Skript aussieht, jedoch Änderungen in der Reihenfolge enthält, in der sie in der Datei angezeigt wird. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> -n  </span> </p> </td> 
   <td colname="col2"> <p> Gibt RCS-Dateien aus; wie <span class="codeph"> -f </span>, außer dass jeder Befehl die Anzahl der betroffenen Zeilen angibt. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>-u </p> </td> 
   <td colname="col2"> <p> Verwendet das einheitliche Ausgabeformat mit drei Zeilen Kontext. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> -U Zeilen  </span> </p> </td> 
   <td colname="col2"> <p> Verwendet das einheitliche Ausgabeformat, zeigt Zeilen (eine Ganzzahl) des Kontexts an oder drei, wenn keine Zeilen angegeben werden. </p> </td> 
  </tr> 
 </tbody> 
</table>

Sie können lokale Variablen, globale Variablen oder beides in diesen Skripten verwenden. Allen globalen Variablen wird der Namensraum &quot;main::&quot;vorangestellt. Wenn das Initialisierungsskript gestartet wird, enthält seine Umgebung die folgenden Standarddateihandler:

* STDIN - nichts (gibt beim Lesen sofort EOF zurück)
* STDOUT - nichts (wenn Daten auf STDOUT gedruckt werden, werden sie verworfen)
* STDERR - an STDERR gedruckte Daten werden als Fehler im Indexprotokoll gedruckt

Zusätzlich können Sie mit der UnterRoutine `_search_debug_log()` benutzerdefinierte Meldungen in das Indexprotokoll schreiben, wie im folgenden Beispiel:

```
# Log information to the Index Log 
_search_debug_log("Done processing document: " . $main::search_url);
```

Diese Meldungen werden mit dem Wort `DEBUG` als Vorwort angezeigt und nicht als Fehler protokolliert.

Ein Beispiel für ein Initialisierungsskript ist Folgendes:

```
# My subroutine to do something. 
sub my_sub_for_the_filtering_script { 
    my ($param1, $param2) = @_; 
    ... 
} 
 
# Initialize the document counter. 
$main::doc_count = 0;
```

Siehe [Globale Variablen](#global-variables)

### QuickInfos {#section_A2CC0302CAF14135BF8EF6171FB184F1}

* Allen globalen Variablen wird der Namensraum &quot;main::&quot; vorangestellt: `$main::doc_count = 0;`
* Alle lokalen Variablen werden mit &quot;my&quot;deklariert: `my $i = 0;`
* Unterroutinen werden im Initialisierungsskript definiert. Sie benötigen keinen expliziten &quot;main:&quot;-Namensraum: `sub my_sub {` `...`

   `}`

* Testen Sie das `$main::search_content_type`, bevor Sie Änderungen an einer Datei vornehmen. Beim Testen können Sie unvorsichtige Änderungen an Binärdateien wie SWF- oder PDF-Dateien vermeiden:

   `if ($main::search_content_type =~ /^text\/html/) { ...`

* `$main::search_content_type` ist der vollständige Content-Type-Header, der von Ihrem Server bereitgestellt wird. Es kann manchmal einen einfachen MIME-Typ enthalten, z. B. &quot;text/html&quot;. Sie kann auch einen MIME-Typ gefolgt von anderen Informationen wie der Zeichensatzkodierung des Dokuments wie &quot;text/html&quot;enthalten. charset=iso-8859-1&quot;.
* Für jeden Typ von Nicht-HTML-Dokument können `$main::search_content_type` verschiedene Werte annehmen. Der Test für jeden Wert in Ihrem Skript wird schwerfällig. Einige Word-Dokumente haben beispielsweise die Inhaltstypwerte &quot;application/msword&quot;, &quot;application/vnd.ms-word&quot;oder &quot;application/x-msword&quot;. In solchen Fällen kann `$main::search_content_class` die folgenden Werte annehmen:

   * html
   * pdf
   * word
   * excel
   * powerpoint
   * mp3
   * text

* In diesem Beispiel stimmen die Tests von `$main::search_content_class` für &quot;word&quot;mit allen drei möglichen Werten des Inhaltstyps überein.
* Wenn aus dem Filterskript nichts an STDOUT gedruckt wird, wird das Dokument genau so verwendet, wie es heruntergeladen wurde. Das heißt, wenn Sie nichts in einem Dokument ändern müssen, dann müssen Sie STDIN für dieses Dokument nicht in STDOUT kopieren.
* Wenn Sie den gesamten Text aus einem Dokument entfernen möchten, drucken Sie eine gültige STDOUT-Datei. Um beispielsweise den gesamten Text vollständig aus einem HTML-Dokument zu entfernen, führen Sie folgende Schritte aus: `print "<html></html>";`

## Hinzufügen eines Initialisierungsskripts {#task_5A03B8D0C46E4674B7CE88203515803B}

Das Initialisierungsskript ist ein Perl-Skript, das einmal ausgeführt wird, bevor Dokumente indiziert werden.

Sie verwenden das Initialisierungsskript in Verbindung mit einem Filterskript, einem Terminierungsskript und einem URL-Masken-Skript.

Stellen Sie sicher, dass Sie Ihren Site-Index neu erstellen, damit die Ergebnisse Ihres Initialisierungsskripts für Ihre Kunden sichtbar sind.

Siehe [Konfigurieren eines inkrementellen Indexes einer gestaffelten Website](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0).

**So fügen Sie ein Initialisierungsskript hinzu**

1. Klicken Sie im Produktmenü auf **[!UICONTROL Settings]** > **[!UICONTROL Filtering]** > **[!UICONTROL Initialization Script]**.
1. (Optional) Geben Sie auf der Seite [!DNL Initialization Script] im Feld [!DNL Test URL] die URL eines Dokuments auf Ihrer Website ein.

   Klicken Sie auf eine Testoption, um Änderungen am HTML-Rohtext anzuzeigen.

   Siehe die Tabelle mit den Filteroptionen unter **Hinzufügen eines Filterskripts**.

   Klicken Sie auf **[!UICONTROL Test]**, um die Filterskripte und URL-Masken zu testen.

   Durch Klicken auf **[!UICONTROL Test]** wird Ihr Initialisierungsskript nicht aktualisiert und gespeichert.
1. Fügen Sie im Feld [!DNL Initialization Script] Ihr Skript ein.
1. (Optional) Klicken Sie auf **[!UICONTROL Check Syntax]**, um eine schnelle Syntaxprüfung Ihres Skripts durchzuführen, indem Sie die Filter-, Initialisierungs- und Terminierungsskripte ausführen.

   **[!UICONTROL Check Syntax]** aktualisiert und speichert Ihr Skript nicht.
1. Klicken **[!UICONTROL Save Changes]**.
1. (Optional) Erstellen Sie Ihren Stage-Site-Index neu, wenn Sie die Vorschauen durchführen möchten.

   Siehe [Konfigurieren eines inkrementellen Indexes einer gestaffelten Website](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0).
1. (Optional) Führen Sie auf der Seite [!DNL Initialization Script] einen der folgenden Schritte aus:

   * Klicken Sie auf **[!UICONTROL History]**, um alle vorgenommenen Änderungen wiederherzustellen.

      Siehe [Verwenden der Option Verlauf](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Klicken **[!UICONTROL Live]**.

      Siehe [Live-Einstellungen anzeigen](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Klicken **[!UICONTROL Push Live]**.

      Siehe [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Informationen zum Terminierungsskript {#concept_AAD6B3B0E7124874AD0947096FC42F47}

Sie können [!DNL Termination Script] verwenden, um den Inhalt eines Web-Dokuments zu ändern, bevor es indiziert wird.

Sie können HTML-Tags einfügen, irrelevante Inhalte entfernen und sogar neue HTML-Metadaten erstellen, die auf der URL, dem MIME-Typ und bestehenden Inhalten eines Dokuments basieren. Das Initialisierungsskript ist ein Perl-Skript, das eine leistungsstarke Zeichenfolgenbearbeitung und die Flexibilität bei der regelmäßigen Ausdruck-Übereinstimmung bietet. Das Terminierungsskript wird mit einem Initialisierungsskript, einem Filterskript, einem Terminierungsskript, einem URL-Masken-Skript und einer Test-URL verwendet.

Das Terminierungsskript wird einmal ausgeführt, nachdem alle Dokumente indiziert wurden. Sie können das Terminierungsskript verwenden, um Statusmeldungen vom Filterskript in das Indexprotokoll zu drucken. Sie drucken die Nachrichten entweder an STDERR oder über die `_search_debug_log()` UnterRoutine.

Einige GNU-Diff-Befehlszeilenoptionen, die Sie im **[!UICONTROL Expert (diff)]**-Modus auf der Seite &quot;Staged Termination Script&quot;verwenden können, beinhalten Folgendes:

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>GNU-Diff-Befehlszeilenoption </p> </th> 
   <th colname="col2" class="entry"> <p>Beschreibung </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> -b  </span> </p> </td> 
   <td colname="col2"> <p> Ignoriert Änderungen an der Größe des Leerraums. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> -B  </span> </p> </td> 
   <td colname="col2"> <p> Ignoriert Änderungen, die leere Zeilen einfügen oder löschen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> -c  </span> </p> </td> 
   <td colname="col2"> <p> Verwendet das Ausgabeformat "Kontext"und zeigt drei Zeilen Kontext an. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> -C-Linien  </span> </p> </td> 
   <td colname="col2"> <p> Verwendet das Ausgabeformat "Kontext", zeigt Zeilen (eine Ganzzahl) mit Kontext an oder drei, wenn keine Zeilen angegeben werden. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> -i  </span> </p> </td> 
   <td colname="col2"> <p> Änderungen im Einzelfall ignorieren; die Entsprechung von Groß- und Kleinbuchstaben berücksichtigen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> -f  </span> </p> </td> 
   <td colname="col2"> <p> Stellt eine Ausgabe dar, die ähnlich wie ein ed-Skript aussieht, jedoch Änderungen in der Reihenfolge enthält, in der sie in der Datei angezeigt wird. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> -n  </span> </p> </td> 
   <td colname="col2"> <p> Gibt RCS-Dateien aus; wie <span class="codeph"> -f </span>, außer dass jeder Befehl die Anzahl der betroffenen Zeilen angibt. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>-u </p> </td> 
   <td colname="col2"> <p> Verwendet das einheitliche Ausgabeformat mit drei Zeilen Kontext. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> -U Zeilen  </span> </p> </td> 
   <td colname="col2"> <p> Verwendet das einheitliche Ausgabeformat, zeigt Zeilen (eine Ganzzahl) des Kontexts an oder drei, wenn keine Zeilen angegeben werden. </p> </td> 
  </tr> 
 </tbody> 
</table>

Sie können lokale Variablen, globale Variablen oder beides in diesen Skripten verwenden. Allen globalen Variablen wird der Namensraum &quot;main::&quot;vorangestellt. Beim Starten des Terminierungsskripts enthält die Umgebung die folgenden Standarddateihandler:

* STDIN - nichts (gibt beim Lesen sofort EOF zurück)
* STDOUT - nichts (wenn Daten auf STDOUT gedruckt werden, werden sie verworfen)
* STDERR - an STDERR gedruckte Daten werden als Fehler in das Indexprotokoll gedruckt

Zusätzlich können Sie mit der UnterRoutine `_search_debug_log()` benutzerdefinierte Meldungen in das Indexprotokoll schreiben, wie im folgenden Beispiel:

```
# Log information to the Index Log 
_search_debug_log("Done processing document: " . $main::search_url);
```

Diese Meldungen werden mit dem Wort `DEBUG` als Vorwort angezeigt und nicht als Fehler protokolliert.

Um die Anzahl der Dokumente anzuzeigen, die vom Filterskript als Fehlerzeile im Indexprotokoll verarbeitet wurden, können Sie das folgende Terminierungsskript verwenden:

```
# Print the value of the document counter. 
print STDERR "Total docs: $main::doc_count\n"; 
# Or, using the log subroutine: 
_search_debug_log("Total docs: " . $main::doc_count);
```

Siehe [Globale Variablen](#global-variables)

### QuickInfos {#section_5790EA7ACAC046CBA01F759F88E2460F}

* Allen globalen Variablen wird der Namensraum &quot;main::&quot; vorangestellt: `$main::doc_count = 0;`
* Alle lokalen Variablen werden mit &quot;my&quot;deklariert: `my $i = 0;`
* Unterroutinen werden im Initialisierungsskript definiert. Sie benötigen keinen expliziten &quot;main:&quot;-Namensraum: `sub my_sub {` `...`

   `}`

* Testen Sie das `$main::search_content_type`, bevor Sie Änderungen an einer Datei vornehmen. Beim Testen können Sie unvorsichtige Änderungen an Binärdateien wie SWF- oder PDF-Dateien vermeiden:

   `if ($main::search_content_type =~ /^text\/html/) { ...`

* `$main::search_content_type` ist der vollständige Content-Type-Header, der von Ihrem Server bereitgestellt wird. Es kann manchmal einen einfachen MIME-Typ enthalten, z. B. &quot;text/html&quot;. Sie kann auch einen MIME-Typ gefolgt von anderen Informationen wie der Zeichensatzkodierung des Dokuments wie &quot;text/html&quot;enthalten. charset=iso-8859-1&quot;.
* Für jeden Typ von Nicht-HTML-Dokument können `$main::search_content_type` verschiedene Werte annehmen. Der Test für jeden Wert in Ihrem Skript wird schwerfällig. Einige Word-Dokumente haben beispielsweise die Inhaltstypwerte &quot;application/msword&quot;, &quot;application/vnd.ms-word&quot;oder &quot;application/x-msword&quot;. In solchen Fällen kann `$main::search_content_class` die folgenden Werte annehmen:

   * html
   * pdf
   * word
   * excel
   * powerpoint
   * mp3
   * text

* In diesem Beispiel stimmen die Tests von `$main::search_content_class` für &quot;word&quot;mit allen drei möglichen Werten des Inhaltstyps überein.
* Wenn aus dem Filterskript nichts an STDOUT gedruckt wird, wird das Dokument genau so verwendet, wie es heruntergeladen wurde. Das heißt, wenn Sie nichts in einem Dokument ändern müssen, dann müssen Sie STDIN für dieses Dokument nicht in STDOUT kopieren.
* Wenn Sie den gesamten Text aus einem Dokument entfernen möchten, drucken Sie eine gültige STDOUT-Datei. Um beispielsweise den gesamten Text vollständig aus einem HTML-Dokument zu entfernen, führen Sie folgende Schritte aus: `print "<html></html>";`

## Hinzufügen eines Kündigungsskripts {#task_F0CFB412871642CFBC88132889C5B6F9}

Das Terminierungsskript ist ein Perl-Skript, das einmal ausgeführt wird, nachdem alle Dokumente indiziert wurden.

Sie verwenden das Terminierungsskript in Verbindung mit einem Filterskript, einem Terminierungsskript und einem URL-Masken-Skript.

Stellen Sie sicher, dass Sie Ihren Site-Index neu erstellen, damit die Ergebnisse Ihres Initialisierungsskripts für Ihre Kunden sichtbar sind.

Siehe [Konfigurieren eines inkrementellen Indexes einer gestaffelten Website](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0).

**So fügen Sie ein Kündigungsskript hinzu**

1. Klicken Sie im Produktmenü auf **[!UICONTROL Settings]** > **[!UICONTROL Filtering]** > **[!UICONTROL Termination Script]**.
1. (Optional) Geben Sie auf der Seite [!DNL Termination Script] im Feld [!DNL Test URL] die URL eines Dokuments auf Ihrer Website ein.

   Klicken Sie auf eine Testoption, um Änderungen am HTML-Rohtext anzuzeigen.

   Siehe die Tabelle der Filteroptionen unter **Hinzufügen eines Filterskripts**.

   Klicken Sie auf **[!UICONTROL Test]**, um die Filterskripte und URL-Masken zu testen.

   Durch Klicken auf **[!UICONTROL Test]** wird Ihr Terminierungsskript nicht aktualisiert und gespeichert.
1. Fügen Sie im Feld [!DNL Termination Script] Ihr Skript ein.
1. (Optional) Klicken Sie auf **[!UICONTROL Check Syntax]**, um eine schnelle Syntaxprüfung Ihres Skripts durchzuführen, indem Sie die Initialisierungs-, Filter- und Kündigungsskripte ausführen.

   **[!UICONTROL Check Syntax]** aktualisiert und speichert Ihr Skript nicht.
1. Klicken **[!UICONTROL Save Changes]**.
1. (Optional) Erstellen Sie Ihren Stage-Site-Index neu, wenn Sie die Vorschauen durchführen möchten.

   Siehe [Konfigurieren eines inkrementellen Indexes einer gestaffelten Website](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0).
1. (Optional) Führen Sie auf der Seite [!DNL Termination Script] einen der folgenden Schritte aus:

   * Klicken Sie auf **[!UICONTROL History]**, um alle vorgenommenen Änderungen wiederherzustellen.

      Siehe [Verwenden der Option Verlauf](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Klicken **[!UICONTROL Live]**.

      Siehe [Live-Einstellungen anzeigen](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Klicken **[!UICONTROL Push Live]**.

      Siehe [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Informationen zu URL-Masken, Skript {#concept_384F32EA18F84853A7BA99A04009330B}

Mit der Filterung können Sie den Inhalt eines Web-Dokuments ändern, bevor es indiziert wird. Sie können HTML-Tags einfügen, irrelevante Inhalte entfernen und sogar neue HTML-Metadaten erstellen, die auf der URL, dem MIME-Typ und bestehenden Inhalten eines Dokuments basieren. Das Skript &quot;URL-Masken&quot;ist ein Perl-Skript, das eine leistungsstarke Zeichenfolgenbearbeitung und die Flexibilität bei der regelmäßigen Ausdruck-Übereinstimmung bietet.

Um den Inhalt von Dokumenten zu ändern, die nur in einem bestimmten Bereich Ihrer Website vorhanden sind, können Sie URL-Masken einschließen, URL-Masken ausschließen oder beides angeben, um die entsprechenden Seiten zu definieren.

Wenn Sie nur die Dokumente unter `"https://www.mysite.com/faqs/"` ändern möchten, können Sie die folgenden Masken verwenden:

```
include https://www.mysite.com/faqs/ 
exclude *
```

Sie können auch regulären Ausdruck in einem URL-Maskenskript verwenden, wie im folgenden Beispiel:

```
include regexp ^https://www\.mysite\.com.*/faqs/.*$ 
exclude *
```

Siehe [Reguläre Ausdruck](../c-appendices/r-regular-expressions.md#reference_B5BA7D61D82E4109A01D2A2D964E3A6A).

Skriptgesteuerte URL-Masken werden in der Reihenfolge berücksichtigt, in der Sie sie im Feld [!DNL URL Masks] eingegeben haben. Wenn eine Dokument-URL mit einer Maske übereinstimmt, wird dieses Dokument je nach Maskentyp ein- oder ausgeschlossen. Wenn die URL eines Dokuments keiner URL-Maske entspricht, wird das Dokument nur einbezogen, wenn der MIME-Typ &quot;text/html&quot;ist. Alle anderen MIME-Typen sind ausgeschlossen.

## Hinzufügen eines URL-Maskenskripts {#task_D18F2A496C1C45C997B5DA650AAF5D59}

Geben Sie die URL an, um Masken einzuschließen und Masken auszuschließen, um den Inhalt von Dokumenten zu ändern, die nur in einem bestimmten Bereich Ihrer Website vorhanden sind.

Bevor die Auswirkungen der URL-Masken-Einstellungen für Besucher sichtbar sind, erstellen Sie den Site-Index neu.

**So fügen Sie ein URL-Maskenskript hinzu**

1. Klicken Sie im Produktmenü auf **[!UICONTROL Settings]** > **[!UICONTROL Filtering]** > **[!UICONTROL URL Masks]**.
1. (Optional) Geben Sie auf der Seite [!DNL URL Masks] im Feld [!DNL Test URL] eine URL eines Dokuments auf Ihrer Website ein und klicken Sie dann auf **[!UICONTROL Test]**, um die URL gegen die Filterskripte und -masken zu testen.

   Das Test-URL-Dokument wird heruntergeladen, das als STDIN-Eingabe für das Filterskript verwendet wird. Anschließend werden die Filter-, Initialisierungs- und Terminierungsskripte ausgeführt. Wenn eine STDOUT-Ausgabe aus dem Filterskript vorhanden ist, wird die Ausgabe in einem neuen Browserfenster angezeigt.

   Durch Klicken auf **[!UICONTROL Test]** wird das Skript nicht aktualisiert und gespeichert.
1. Geben Sie im Feld [!DNL URL Masks] eine URL-Maske pro Zeile ein.
1. (Optional) Klicken Sie auf **[!UICONTROL Check Syntax]**, um eine schnelle Syntaxprüfung Ihrer URL-Masken durchzuführen, indem Sie die Filter-, Initialisierungs- und Terminierungsskripte ausführen.

   **[!UICONTROL Check Syntax]** aktualisiert und speichert Ihr Skript nicht.
1. Klicken **[!UICONTROL Save Changes]**.
1. (Optional) Erstellen Sie Ihren Stage-Site-Index neu, wenn Sie die Vorschauen durchführen möchten.

   Siehe [Konfigurieren eines inkrementellen Indexes einer gestaffelten Website](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0).
1. (Optional) Führen Sie auf der Seite [!DNL URL Masks] einen der folgenden Schritte aus:

   * Klicken Sie auf **[!UICONTROL History]**, um alle vorgenommenen Änderungen wiederherzustellen.

      Siehe [Verwenden der Option Verlauf](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Klicken **[!UICONTROL Live]**.

      Siehe [Live-Einstellungen anzeigen](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Klicken **[!UICONTROL Push Live]**.

      Siehe [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Inhaltstypen in Filtern {#concept_E3EFF4A148EA4D21AFD0A5453A00427E}

Ermöglicht die Auswahl der Inhaltstypen, die für dieses Konto gefiltert werden sollen.

Der in den ausgewählten Inhaltstypen gefundene Text wird in HTML konvertiert und anschließend mithilfe des Skripts verarbeitet, das im Filterskript angegeben ist.

Siehe [Informationen zum Filtern von Skript](../c-about-settings-menu/c-about-filtering-menu.md#concept_E56B73D625854AB2A899EF2D56CFCB47).

Zu den Inhaltstypen, aus denen Sie auswählen können, gehören:

* PDF-Dokumente
* Text-Dokumente
* Adobe Flash-Filme
* Microsoft Word-Dateien
* Microsoft Office-Dateien (OpenXML)
* Microsoft Excel-Dateien
* Microsoft Powerpoint-Dateien
* Text in MP3-Musikdateien

Bevor die Auswirkungen der Einstellungen für Inhaltstypen oder Änderungen der Einstellungen für Kunden sichtbar sind, müssen Sie Ihren Site-Index neu erstellen.

## Auswählen der Inhaltstypen, die gefiltert werden {#task_C46081FA425A43EC8FDE6EA4A52A170A}

Wählen Sie die Inhaltstypen aus, die Sie an das Skript übergeben möchten, das im Filterskript angegeben ist.

Siehe [Informationen zum Filtern von Skript](../c-about-settings-menu/c-about-filtering-menu.md#concept_E56B73D625854AB2A899EF2D56CFCB47).

**So wählen Sie die gefilterten Inhaltstypen aus**

1. Klicken Sie im Produktmenü auf **[!UICONTROL Settings]** > **[!UICONTROL Filtering]** > **[!UICONTROL Content Types]**.
1. Überprüfen Sie auf der Seite [!DNL Content Types] die Inhaltstypen, die an das Filterskript übergeben werden sollen.
1. Klicken **[!UICONTROL Save Changes]**.
1. (Optional) Erstellen Sie Ihren Stage-Site-Index neu, wenn Sie die Vorschauen durchführen möchten.

   Siehe [Konfigurieren eines inkrementellen Indexes einer gestaffelten Website](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0).
1. (Optional) Führen Sie auf der Seite [!DNL Content Types] einen der folgenden Schritte aus:

   * Klicken Sie auf **[!UICONTROL History]**, um alle vorgenommenen Änderungen wiederherzustellen.

      Siehe [Verwenden der Option Verlauf](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Klicken **[!UICONTROL Live]**.

      Siehe [Live-Einstellungen anzeigen](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Klicken **[!UICONTROL Push Live]**.

      Siehe [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).
