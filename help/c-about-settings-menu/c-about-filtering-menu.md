---
description: Verwenden Sie das Menü "Filtern", um Skripten zu verwenden, die den Inhalt eines Webdokuments ändern, bevor es indiziert wird.
seo-description: Verwenden Sie das Menü "Filtern", um Skripten zu verwenden, die den Inhalt eines Webdokuments ändern, bevor es indiziert wird.
seo-title: Über das Menü "Filtern"
solution: Target
subtopic: Filtering
title: Über das Menü "Filtern"
topic: Settings,Site search and merchandising
uuid: ebb08fa8-4e17-417d-868b-11fc2af9f284
translation-type: tm+mt
source-git-commit: f21a3f7fe0aeaab517a5ca36da43594873b3e69a

---


# Über das Menü &quot;Filtern&quot;{#about-the-filtering-menu}

Verwenden Sie das Menü &quot;Filtern&quot;, um Skripten zu verwenden, die den Inhalt eines Webdokuments ändern, bevor es indiziert wird.

## Grundlagen zum Filtern von Skripten {#concept_E56B73D625854AB2A899EF2D56CFCB47}

Sie können den Inhalt eines Webdokuments ändern, bevor es indiziert [!DNL Filtering Script] wird.

Sie können HTML-Tags einfügen, irrelevante Inhalte entfernen und sogar neue HTML-Metadaten erstellen, die auf der URL, dem MIME-Typ und dem vorhandenen Inhalt eines Dokuments basieren. Das Filterskript ist ein Perl-Skript, das eine leistungsstarke Zeichenfolgenbearbeitung und die Flexibilität bei der Suche nach regulären Ausdrücken bietet. Sie verwenden das Filterskript mit einem Initialisierungsskript, einem Terminierungsskript, einem URL-Masken-Skript und einer Test-URL.

Das Filterskript wird jedes Mal ausgeführt, wenn ein Dokument von Ihrer Website gelesen wird. Das Skript läuft als Standardfilter, d. h. liest Daten aus STDIN, transformiert diese Daten in irgendeiner Weise und schreibt die Ergebnisse in STDOUT. Sie können das Filterskript verwenden, um Statusmeldungen vom Filterskript zum Indexprotokoll zu drucken. Sie drucken die Nachrichten entweder an STDERR oder über die `_search_debug_log()` Unterroutine.

Zu den GNU-Diff-Optionen, die Sie im **[!UICONTROL Expert (diff)]** Modus auf der Seite &quot;Staged Filterung Script&quot;verwenden können, zählen:

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
   <td colname="col1"> <p> <span class="codeph"> -C-Linien </span> </p> </td> 
   <td colname="col2"> <p> Verwendet das Ausgabeformat "Kontext", zeigt Zeilen (eine Ganzzahl) mit Kontext an oder drei, wenn keine Zeilen angegeben werden. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> -i </span> </p> </td> 
   <td colname="col2"> <p> Änderungen im Einzelfall ignorieren; die Entsprechung von Groß- und Kleinbuchstaben berücksichtigen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> -f </span> </p> </td> 
   <td colname="col2"> <p> Stellt eine Ausgabe dar, die ähnlich wie ein ed-Skript aussieht, jedoch Änderungen in der Reihenfolge enthält, in der sie in der Datei angezeigt wird. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> -n </span> </p> </td> 
   <td colname="col2"> <p> Gibt RCS-Dateien aus; like <span class="codeph"> -f </span> , außer dass jeder Befehl die Anzahl der betroffenen Zeilen angibt. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>-u </p> </td> 
   <td colname="col2"> <p> Verwendet das einheitliche Ausgabeformat mit drei Zeilen Kontext. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> -U Zeilen </span> </p> </td> 
   <td colname="col2"> <p> Verwendet das einheitliche Ausgabeformat, zeigt Zeilen (eine Ganzzahl) des Kontexts an oder drei, wenn keine Zeilen angegeben werden. </p> </td> 
  </tr> 
 </tbody> 
</table>

Sie können lokale Variablen, globale Variablen oder beides in diesen Skripten verwenden. Allen globalen Variablen wird der Namespace &quot;main::&quot; vorangestellt. Wenn das Filterskript gestartet wird, enthält seine Umgebung die folgenden standardmäßigen Datei-Handles:

* STDIN - nichts (gibt beim Lesen sofort EOF zurück)
* STDOUT - Ersatz-HTML (wenn Daten in STDOUT gedruckt werden, werden sie anstelle des Originaldokuments verwendet)
* STDERR - an STDERR gedruckte Daten werden als Fehler im Indexprotokoll gedruckt

Außerdem können Sie mithilfe der `_search_debug_log()` UnterRoutine benutzerdefinierte Meldungen in das Indexprotokoll schreiben, wie im folgenden Beispiel:

```
# Log information to the Index Log 
_search_debug_log("Done processing document: " . $main::search_url);
```

Diese Meldungen werden mit dem Wort `DEBUG` als Vorwort angezeigt und nicht als Fehler protokolliert.

Im Folgenden finden Sie ein Beispiel für die Filterung. Webseiten- `<title>` Felder beginnen oft mit dem Firmennamen. Obwohl diese Informationen für die Navigation auf der Site nützlich sind, sind sie bei der Suche nicht relevant. Wenn die Titel aller MegaCorp-Webseiten mit einer gemeinsamen Zeichenfolge beginnen, z. B.:

```
<title>MegaCorp -- meaningful title 
here</title>
```

Sie sollten &quot; `MegaCorp --`&quot;am Anfang jedes Dokumenttitels entfernen und jedes mit dem Filterskript verarbeitete Dokument zählen. Dazu können Sie das folgende Skript verwenden:

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
| `$main::search_crawl_type` | Der Wert von `$main::search_crawl_type` gibt den Typ des laufenden Indexvorgangs an.  Veraltetes Formular: Zu `$main::ws_crawl_type` den Indexvorgängen und den zugehörigen Werten gehören: <ul><li>Vollständiger Index: Manuell - `manual`</li><li>Vollständiger Index: Geplant - `auto`</li><li>Vollständiger Index: Fernsteuerung - `CGI`</li><li>Inkrementeller Index: Manuell - `manual-incremental`</li><li>Inkrementeller Index: Geplant - `auto-incremental` </li><li>Inkrementeller Index: Fernsteuerung - `CGI-incremental`</li><li>Skriptindex: Manuell - `manual-indexlist.txt` </li><li>Skriptindex: Geplant - `auto-indexlist.txt`</li><li>Skriptindex: Fernsteuerung - `CGI-indexlist.txt`</li><li>Regenerieren - `manual-upgrade`</li></ul> |
| `$main::search_clear_cache` | Der Wert gibt an, ob die Indexierungsoption &quot;Index-Cache leeren&quot;für den aktuellen Indexvorgang angefordert wurde. Wenn &quot;Index-Cache leeren&quot;angefordert wurde, `$main::search_clear_cache` lautet der Wert &quot; `1`&quot;.  Veraltete Form: `$main::ws_clear_cache` |
| `$main::search_fields` | Der Wert enthält eine tabulatorgetrennte Liste der Metadatenfelder, die im Konto definiert sind. Standardmäßig lautet der Wert:   Veraltetes `url title desc keys target body alt date charset language` Formular: `$main::ws_fields` |
| `$main::search_collections` | Der Wert enthält eine tabulatorgetrennte Liste der Sammlungen, die im Konto definiert sind.  Veraltete Form: `$main::ws_collections` |
| `$main::search_url` | Der Wert ist die vollständig qualifizierte URL des Dokuments.  Veraltete Form: `$main::ws_url` |
| `$main::search_content_type` | Der Wert ist der Inhaltstyp des Dokuments, der vom http-equiv-Meta-Tag abgerufen wird. Ein typischer Wert ist &quot;text/html&quot;. charset=iso-8859-1&quot;.  Veraltete Form: `$main::ws_content_type` |
| `$main::search_content_class` | Der Wert ist die Inhaltsklasse des Dokuments, die vom Feld &quot;content-type&quot;abgeleitet ist.  Veraltete Form: `$main::ws_content_class` |
| `$main::search_syntax_check` | Der Wert spiegelt die Verwendung der Schaltfläche &quot;Syntax überprüfen&quot;wider. Wenn darauf geklickt wird, ist der Wert 1 (1); Andernfalls ist der Wert 0 (null).  Veraltete Form: `$main::ws_syntax_check` |
| `$main::search_last_mod_date` | Wenn dieser Wert vom Webserver bereitgestellt wird, enthält er die Epochendarstellung (Sekunden seit dem 1. Januar 1970) des zuletzt geänderten Datums des Dokuments.  Sie können diesen Wert mithilfe des Perl localtime()-Bibliotheksaufrufs formatieren. |

### QuickInfos {#section_89A5C16911744AF98E232DF608C6A1F5}

* Allen globalen Variablen wird der Namespace &quot;main::&quot; vorangestellt: `$main::doc_count = 0;`
* Alle lokalen Variablen werden mit &quot;my&quot;deklariert: `my $i = 0;`
* Unterroutinen werden im Initialisierungsskript definiert. Sie benötigen keinen expliziten Namespace &quot;main::&quot;: `sub my_sub {`  `...`

   `}`

* Testen Sie die Datei, `$main::search_content_type` bevor Sie Änderungen an einer Datei vornehmen. Beim Testen können Sie unvorsichtige Änderungen an Binärdateien wie SWF- oder PDF-Dateien vermeiden:

   `if ($main::search_content_type =~ /^text\/html/) { ...`

* Der `$main::search_content_type` vollständige Content-Type-Header wird von Ihrem Server bereitgestellt. Es kann manchmal einen einfachen MIME-Typ enthalten, z. B. &quot;text/html&quot;. Sie kann auch einen MIME-Typ gefolgt von weiteren Informationen wie der Zeichensatzkodierung des Dokuments wie &quot;text/html&quot; enthalten. charset=iso-8859-1&quot;.
* Für jeden Typ von Nicht-HTML-Dokumenten können verschiedene Werte verwendet `$main::search_content_type` werden. Der Test für jeden Wert in Ihrem Skript wird schwerfällig. Einige Word-Dokumente haben beispielsweise die Inhaltstypwerte &quot;application/msword&quot;, &quot;application/vnd.ms-word&quot;oder &quot;application/x-msword&quot;. In solchen Fällen `$main::search_content_class` können die folgenden Werte verwendet werden:

   * html
   * pdf
   * word
   * excel
   * powerpoint
   * mp3
   * text

* In diesem Beispiel stimmen Tests `$main::search_content_class` auf &quot;word&quot;mit einem der drei möglichen Content-Type-Werte überein.
* Wenn aus dem Filterskript nichts in STDOUT gedruckt wird, wird das Dokument genau so verwendet, wie es heruntergeladen wurde. Das heißt, wenn Sie nichts in einem Dokument ändern müssen, müssen Sie STDIN für dieses Dokument nicht in STDOUT kopieren.
* Wenn Sie den gesamten Text aus einem Dokument entfernen möchten, drucken Sie eine gültige STDOUT-Datei. Um beispielsweise den gesamten Text vollständig aus einem HTML-Dokument zu entfernen, führen Sie folgende Schritte aus: `print "<html></html>";`

## Hinzufügen eines Filterskripts {#task_0AB84FD1133F47F9AA069A79BEA13A22}

Das Filterskript ist ein Perl-Skript, das für jedes Dokument ausgeführt wird, das von Ihrer Website heruntergeladen wird.

Sie verwenden das Filterskript in Verbindung mit einem Initialisierungsskript, einem Terminierungsskript und einem URL-Masken-Skript.

Stellen Sie sicher, dass Sie Ihren Site-Index neu erstellen, damit die Ergebnisse Ihres Filterskripts für Ihre Kunden sichtbar sind.

Siehe [Konfigurieren eines inkrementellen Indexes einer gestaffelten Website](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0).

**So fügen Sie ein Filterskript hinzu**

1. Klicken Sie im Produktmenü auf **[!UICONTROL Settings]** > **[!UICONTROL Filtering]** > **[!UICONTROL Filtering Script]**.
1. (Optional) Geben Sie auf der [!DNL Filtering Script] Seite im [!DNL Test URL] Feld die URL eines Dokuments auf Ihrer Website ein.

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
      <td colname="col2"> <p>Ermöglicht die Eingabe der URL eines Dokuments auf Ihrer Website. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Test </p> </td> 
      <td colname="col2"> <p>Prüft die URL auf die Filterskripte und URL-Masken. </p> <p>Das Dokument für die Test-URL wird heruntergeladen und dann als STDIN-Eingabe für das Filterskript verwendet. Anschließend werden die Skripten für Initialisierung, Filterung und Beendigung ausgeführt. Wenn eine STDOUT-Ausgabe aus dem Filterskript vorhanden ist, wird diese Ausgabe in einem neuen Browserfenster angezeigt. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Nur testen </p> </td> 
      <td colname="col2"> <p>Testt nur den Vorgang des Skripts. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Vorschau </p> </td> 
      <td colname="col2"> <p>Hiermit können Sie die Seite anzeigen. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Vollständige Visualisierung </p> </td> 
      <td colname="col2"> <p>Erzeugt eine vollständige Vor- und Nach-Tabellen-Ansicht der Dokumente. </p> </td> 
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

   Zu den GNU-Diff-Optionen, die Sie im **[!UICONTROL Expert (diff)]** Modus auf der Seite &quot;Staged Filterung Script&quot;verwenden können, zählen:

   <table> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> <p>GNU-Diff-Befehlszeilenoption </p> </th> 
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
      <td colname="col1"> <p> <span class="codeph"> -C-Linien </span> </p> </td> 
      <td colname="col2"> <p> Verwendet das Ausgabeformat "Kontext", zeigt Zeilen (eine Ganzzahl) mit Kontext an oder drei, wenn keine Zeilen angegeben werden. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p> <span class="codeph"> -i </span> </p> </td> 
      <td colname="col2"> <p> Änderungen im Einzelfall ignorieren; die Entsprechung von Groß- und Kleinbuchstaben berücksichtigen. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p> <span class="codeph"> -f </span> </p> </td> 
      <td colname="col2"> <p> Stellt eine Ausgabe dar, die ähnlich wie ein ed-Skript aussieht, jedoch Änderungen in der Reihenfolge enthält, in der sie in der Datei angezeigt wird. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p> <span class="codeph"> -n </span> </p> </td> 
      <td colname="col2"> <p> Gibt RCS-Dateien aus; like <span class="codeph"> -f </span> , außer dass jeder Befehl die Anzahl der betroffenen Zeilen angibt. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>-u </p> </td> 
      <td colname="col2"> <p> Verwendet das einheitliche Ausgabeformat mit drei Zeilen Kontext. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p> <span class="codeph"> -U Zeilen </span> </p> </td> 
      <td colname="col2"> <p> Verwendet das einheitliche Ausgabeformat, zeigt Zeilen (eine Ganzzahl) des Kontexts an oder drei, wenn keine Zeilen angegeben werden. </p> </td> 
      </tr> 
    </tbody> 
    </table>

1. Klicken Sie **[!UICONTROL Test]** auf , um den Test mit den Filterskripten und URL-Masken durchzuführen.

   Durch Klicken auf **[!UICONTROL Test]** wird das Filterskript nicht aktualisiert und gespeichert.
1. Fügen Sie im [!DNL Filtering Script] Feld Ihr Skript ein.
1. (Optional) Klicken Sie **[!UICONTROL Check Syntax]** auf , um durch Ausführen der Filter-, Initialisierungs- und Terminierungsskripte eine schnelle Syntaxprüfung des Skripts durchzuführen.

   **[!UICONTROL Check Syntax]** aktualisiert und speichert Ihr Skript nicht.
1. Klicken **[!UICONTROL Save Changes]**.
1. (Optional) Erstellen Sie Ihren Staged Site-Index neu, wenn Sie eine Vorschau der Ergebnisse anzeigen möchten.

   Siehe [Konfigurieren eines inkrementellen Indexes einer gestaffelten Website](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0).
1. (Optional) Führen Sie auf der [!DNL Filtering Script] Seite einen der folgenden Schritte aus:

   * Klicken Sie auf **[!UICONTROL History]** , um alle vorgenommenen Änderungen wiederherzustellen.

      Siehe [Verwenden der Option](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)Verlauf.

   * Klicken **[!UICONTROL Live]**.

      Siehe [Live-Einstellungen](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)anzeigen.

   * Klicken **[!UICONTROL Push Live]**.

      Siehe [Pushing-Einstellungen](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Info zum Initialisierungsskript {#concept_048B4C8BC9F74BE8BB6162C490C201A3}

Sie können den Inhalt eines Webdokuments ändern, bevor es indiziert [!DNL Initialization Script] wird.

Sie können HTML-Tags einfügen, irrelevante Inhalte entfernen und sogar neue HTML-Metadaten erstellen, die auf der URL, dem MIME-Typ und dem vorhandenen Inhalt eines Dokuments basieren. Das Initialisierungsskript ist ein Perl-Skript, das eine leistungsstarke Zeichenfolgenbearbeitung und die Flexibilität bei der Suche nach regulären Ausdrücken bietet. Sie verwenden das Initialisierungsskript mit einem Filterskript, einem Terminierungsskript, einem URL-Masken-Skript und einer Test-URL.

Das Initialisierungsskript wird einmal ausgeführt, bevor die Indexierung beginnt. Verwenden Sie dieses Skript, um alle globalen Variablen und Unterroutinen zu initialisieren, die von Ihrem Filterskript verwendet werden. Sie können das Initialisierungsskript verwenden, um Statusmeldungen vom Filterskript in das Indexprotokoll zu drucken. Sie drucken die Nachrichten entweder an STDERR oder über die `_search_debug_log()` UnterRoutine.

Zu den GNU-Diff-Optionen, die Sie im **[!UICONTROL Expert (diff)]** Modus auf der Seite &quot;Staged Initialization Script&quot;verwenden können, zählen:

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
   <td colname="col1"> <p> <span class="codeph"> -C-Linien </span> </p> </td> 
   <td colname="col2"> <p> Verwendet das Ausgabeformat "Kontext", zeigt Zeilen (eine Ganzzahl) mit Kontext an oder drei, wenn keine Zeilen angegeben werden. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> -i </span> </p> </td> 
   <td colname="col2"> <p> Änderungen im Einzelfall ignorieren; die Entsprechung von Groß- und Kleinbuchstaben berücksichtigen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> -f </span> </p> </td> 
   <td colname="col2"> <p> Stellt eine Ausgabe dar, die ähnlich wie ein ed-Skript aussieht, jedoch Änderungen in der Reihenfolge enthält, in der sie in der Datei angezeigt wird. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> -n </span> </p> </td> 
   <td colname="col2"> <p> Gibt RCS-Dateien aus; like <span class="codeph"> -f </span> , außer dass jeder Befehl die Anzahl der betroffenen Zeilen angibt. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>-u </p> </td> 
   <td colname="col2"> <p> Verwendet das einheitliche Ausgabeformat mit drei Zeilen Kontext. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> -U Zeilen </span> </p> </td> 
   <td colname="col2"> <p> Verwendet das einheitliche Ausgabeformat, zeigt Zeilen (eine Ganzzahl) des Kontexts an oder drei, wenn keine Zeilen angegeben werden. </p> </td> 
  </tr> 
 </tbody> 
</table>

Sie können lokale Variablen, globale Variablen oder beides in diesen Skripten verwenden. Allen globalen Variablen wird der Namespace &quot;main::&quot; vorangestellt. Wenn das Initialisierungsskript gestartet wird, enthält seine Umgebung die folgenden standardmäßigen Datei-Handles:

* STDIN - nichts (gibt beim Lesen sofort EOF zurück)
* STDOUT - nichts (wenn Daten auf STDOUT gedruckt werden, werden sie verworfen)
* STDERR - an STDERR gedruckte Daten werden als Fehler im Indexprotokoll gedruckt

Außerdem können Sie mithilfe der `_search_debug_log()` UnterRoutine benutzerdefinierte Meldungen in das Indexprotokoll schreiben, wie im folgenden Beispiel:

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

* Allen globalen Variablen wird der Namespace &quot;main::&quot; vorangestellt: `$main::doc_count = 0;`
* Alle lokalen Variablen werden mit &quot;my&quot;deklariert: `my $i = 0;`
* Unterroutinen werden im Initialisierungsskript definiert. Sie benötigen keinen expliziten Namespace &quot;main::&quot;: `sub my_sub {`  `...`

   `}`

* Testen Sie die Datei, `$main::search_content_type` bevor Sie Änderungen an einer Datei vornehmen. Beim Testen können Sie unvorsichtige Änderungen an Binärdateien wie SWF- oder PDF-Dateien vermeiden:

   `if ($main::search_content_type =~ /^text\/html/) { ...`

* Der `$main::search_content_type` vollständige Content-Type-Header wird von Ihrem Server bereitgestellt. Es kann manchmal einen einfachen MIME-Typ enthalten, z. B. &quot;text/html&quot;. Sie kann auch einen MIME-Typ gefolgt von weiteren Informationen wie der Zeichensatzkodierung des Dokuments wie &quot;text/html&quot; enthalten. charset=iso-8859-1&quot;.
* Für jeden Typ von Nicht-HTML-Dokumenten können verschiedene Werte verwendet `$main::search_content_type` werden. Der Test für jeden Wert in Ihrem Skript wird schwerfällig. Einige Word-Dokumente haben beispielsweise die Inhaltstypwerte &quot;application/msword&quot;, &quot;application/vnd.ms-word&quot;oder &quot;application/x-msword&quot;. In solchen Fällen `$main::search_content_class` können die folgenden Werte verwendet werden:

   * html
   * pdf
   * word
   * excel
   * powerpoint
   * mp3
   * text

* In diesem Beispiel stimmen Tests `$main::search_content_class` auf &quot;word&quot;mit einem der drei möglichen Content-Type-Werte überein.
* Wenn aus dem Filterskript nichts in STDOUT gedruckt wird, wird das Dokument genau so verwendet, wie es heruntergeladen wurde. Das heißt, wenn Sie nichts in einem Dokument ändern müssen, müssen Sie STDIN für dieses Dokument nicht in STDOUT kopieren.
* Wenn Sie den gesamten Text aus einem Dokument entfernen möchten, drucken Sie eine gültige STDOUT-Datei. Um beispielsweise den gesamten Text vollständig aus einem HTML-Dokument zu entfernen, führen Sie folgende Schritte aus: `print "<html></html>";`

## Hinzufügen eines Initialisierungsskripts {#task_5A03B8D0C46E4674B7CE88203515803B}

Das Initialisierungsskript ist ein Perl-Skript, das einmal ausgeführt wird, bevor Dokumente indiziert werden.

Sie verwenden das Initialisierungsskript in Verbindung mit einem Filterskript, einem Terminierungsskript und einem URL-Masken-Skript.

Stellen Sie sicher, dass Sie Ihren Site-Index neu erstellen, damit die Ergebnisse Ihres Initialisierungsskripts für Ihre Kunden sichtbar sind.

Siehe [Konfigurieren eines inkrementellen Indexes einer gestaffelten Website](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0).

**So fügen Sie ein Initialisierungsskript hinzu**

1. Klicken Sie im Produktmenü auf **[!UICONTROL Settings]** > **[!UICONTROL Filtering]** > **[!UICONTROL Initialization Script]**.
1. (Optional) Geben Sie auf der [!DNL Initialization Script] Seite im [!DNL Test URL] Feld die URL eines Dokuments auf Ihrer Website ein.

   Klicken Sie auf eine Testoption, um Änderungen am HTML-Rohtext anzuzeigen.

   Siehe die Tabelle mit den Filteroptionen unter **Hinzufügen eines Filterskripts**.

   Klicken Sie **[!UICONTROL Test]** auf , um den Test mit den Filterskripten und URL-Masken durchzuführen.

   Durch Klicken auf **[!UICONTROL Test]** wird das Initialisierungsskript nicht aktualisiert und gespeichert.
1. Fügen Sie im [!DNL Initialization Script] Feld Ihr Skript ein.
1. (Optional) Klicken Sie **[!UICONTROL Check Syntax]** auf , um durch Ausführen der Filter-, Initialisierungs- und Terminierungsskripte eine schnelle Syntaxprüfung des Skripts durchzuführen.

   **[!UICONTROL Check Syntax]** aktualisiert und speichert Ihr Skript nicht.
1. Klicken **[!UICONTROL Save Changes]**.
1. (Optional) Erstellen Sie Ihren Staged Site-Index neu, wenn Sie eine Vorschau der Ergebnisse anzeigen möchten.

   Siehe [Konfigurieren eines inkrementellen Indexes einer gestaffelten Website](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0).
1. (Optional) Führen Sie auf der [!DNL Initialization Script] Seite einen der folgenden Schritte aus:

   * Klicken Sie auf **[!UICONTROL History]** , um alle vorgenommenen Änderungen wiederherzustellen.

      Siehe [Verwenden der Option](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)Verlauf.

   * Klicken **[!UICONTROL Live]**.

      Siehe [Live-Einstellungen](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)anzeigen.

   * Klicken **[!UICONTROL Push Live]**.

      Siehe [Pushing-Einstellungen](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Informationen zum Kündigungsskript {#concept_AAD6B3B0E7124874AD0947096FC42F47}

Sie können den Inhalt eines Webdokuments ändern, bevor es indiziert [!DNL Termination Script] wird.

Sie können HTML-Tags einfügen, irrelevante Inhalte entfernen und sogar neue HTML-Metadaten erstellen, die auf der URL, dem MIME-Typ und dem vorhandenen Inhalt eines Dokuments basieren. Das Initialisierungsskript ist ein Perl-Skript, das eine leistungsstarke Zeichenfolgenbearbeitung und die Flexibilität bei der Suche nach regulären Ausdrücken bietet. Das Terminierungsskript wird mit einem Initialisierungsskript, einem Filterskript, einem Terminierungsskript, einem URL-Masken-Skript und einer Test-URL verwendet.

Das Terminierungsskript wird einmal ausgeführt, nachdem alle Dokumente indiziert wurden. Sie können das Terminierungsskript verwenden, um Statusmeldungen vom Filterskript in das Indexprotokoll zu drucken. Sie drucken die Nachrichten entweder an STDERR oder über die `_search_debug_log()` UnterRoutine.

Einige GNU-diff-Befehlszeilenoptionen, die Sie im **[!UICONTROL Expert (diff)]** Modus auf der Seite &quot;Staged Termination Script&quot;verwenden können, beinhalten Folgendes:

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>GNU-Diff-Befehlszeilenoption </p> </th> 
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
   <td colname="col1"> <p> <span class="codeph"> -C-Linien </span> </p> </td> 
   <td colname="col2"> <p> Verwendet das Ausgabeformat "Kontext", zeigt Zeilen (eine Ganzzahl) mit Kontext an oder drei, wenn keine Zeilen angegeben werden. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> -i </span> </p> </td> 
   <td colname="col2"> <p> Änderungen im Einzelfall ignorieren; die Entsprechung von Groß- und Kleinbuchstaben berücksichtigen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> -f </span> </p> </td> 
   <td colname="col2"> <p> Stellt eine Ausgabe dar, die ähnlich wie ein ed-Skript aussieht, jedoch Änderungen in der Reihenfolge enthält, in der sie in der Datei angezeigt wird. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> -n </span> </p> </td> 
   <td colname="col2"> <p> Gibt RCS-Dateien aus; like <span class="codeph"> -f </span> , außer dass jeder Befehl die Anzahl der betroffenen Zeilen angibt. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>-u </p> </td> 
   <td colname="col2"> <p> Verwendet das einheitliche Ausgabeformat mit drei Zeilen Kontext. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> -U Zeilen </span> </p> </td> 
   <td colname="col2"> <p> Verwendet das einheitliche Ausgabeformat, zeigt Zeilen (eine Ganzzahl) des Kontexts an oder drei, wenn keine Zeilen angegeben werden. </p> </td> 
  </tr> 
 </tbody> 
</table>

Sie können lokale Variablen, globale Variablen oder beides in diesen Skripten verwenden. Allen globalen Variablen wird der Namespace &quot;main::&quot; vorangestellt. Beim Starten des Terminierungsskripts enthält die Umgebung die folgenden Standarddateiprozeduren:

* STDIN - nichts (gibt beim Lesen sofort EOF zurück)
* STDOUT - nichts (wenn Daten auf STDOUT gedruckt werden, werden sie verworfen)
* STDERR - an STDERR gedruckte Daten werden als Fehler in das Indexprotokoll gedruckt

Außerdem können Sie mithilfe der `_search_debug_log()` UnterRoutine benutzerdefinierte Meldungen in das Indexprotokoll schreiben, wie im folgenden Beispiel:

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

* Allen globalen Variablen wird der Namespace &quot;main::&quot; vorangestellt: `$main::doc_count = 0;`
* Alle lokalen Variablen werden mit &quot;my&quot;deklariert: `my $i = 0;`
* Unterroutinen werden im Initialisierungsskript definiert. Sie benötigen keinen expliziten Namespace &quot;main::&quot;: `sub my_sub {`  `...`

   `}`

* Testen Sie die Datei, `$main::search_content_type` bevor Sie Änderungen an einer Datei vornehmen. Beim Testen können Sie unvorsichtige Änderungen an Binärdateien wie SWF- oder PDF-Dateien vermeiden:

   `if ($main::search_content_type =~ /^text\/html/) { ...`

* Der `$main::search_content_type` vollständige Content-Type-Header wird von Ihrem Server bereitgestellt. Es kann manchmal einen einfachen MIME-Typ enthalten, z. B. &quot;text/html&quot;. Sie kann auch einen MIME-Typ gefolgt von weiteren Informationen wie der Zeichensatzkodierung des Dokuments wie &quot;text/html&quot; enthalten. charset=iso-8859-1&quot;.
* Für jeden Typ von Nicht-HTML-Dokumenten können verschiedene Werte verwendet `$main::search_content_type` werden. Der Test für jeden Wert in Ihrem Skript wird schwerfällig. Einige Word-Dokumente haben beispielsweise die Inhaltstypwerte &quot;application/msword&quot;, &quot;application/vnd.ms-word&quot;oder &quot;application/x-msword&quot;. In solchen Fällen `$main::search_content_class` können die folgenden Werte verwendet werden:

   * html
   * pdf
   * word
   * excel
   * powerpoint
   * mp3
   * text

* In diesem Beispiel stimmen Tests `$main::search_content_class` auf &quot;word&quot;mit einem der drei möglichen Content-Type-Werte überein.
* Wenn aus dem Filterskript nichts in STDOUT gedruckt wird, wird das Dokument genau so verwendet, wie es heruntergeladen wurde. Das heißt, wenn Sie nichts in einem Dokument ändern müssen, müssen Sie STDIN für dieses Dokument nicht in STDOUT kopieren.
* Wenn Sie den gesamten Text aus einem Dokument entfernen möchten, drucken Sie eine gültige STDOUT-Datei. Um beispielsweise den gesamten Text vollständig aus einem HTML-Dokument zu entfernen, führen Sie folgende Schritte aus: `print "<html></html>";`

## Hinzufügen eines Kündigungsskripts {#task_F0CFB412871642CFBC88132889C5B6F9}

Das Terminierungsskript ist ein Perl-Skript, das einmal ausgeführt wird, nachdem alle Dokumente indiziert wurden.

Sie verwenden das Terminierungsskript in Verbindung mit einem Filterskript, einem Terminierungsskript und einem URL-Masken-Skript.

Stellen Sie sicher, dass Sie Ihren Site-Index neu erstellen, damit die Ergebnisse Ihres Initialisierungsskripts für Ihre Kunden sichtbar sind.

Siehe [Konfigurieren eines inkrementellen Indexes einer gestaffelten Website](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0).

**So fügen Sie ein Kündigungsskript hinzu**

1. Klicken Sie im Produktmenü auf **[!UICONTROL Settings]** > **[!UICONTROL Filtering]** > **[!UICONTROL Termination Script]**.
1. (Optional) Geben Sie auf der [!DNL Termination Script] Seite im [!DNL Test URL] Feld die URL eines Dokuments auf Ihrer Website ein.

   Klicken Sie auf eine Testoption, um Änderungen am HTML-Rohtext anzuzeigen.

   Siehe Tabelle der Filteroptionen unter **Hinzufügen eines Filterskripts**.

   Klicken Sie **[!UICONTROL Test]** auf , um den Test mit den Filterskripten und URL-Masken durchzuführen.

   Durch Klicken auf **[!UICONTROL Test]** wird Ihr Terminierungsskript nicht aktualisiert und gespeichert.
1. Fügen Sie im [!DNL Termination Script] Feld Ihr Skript ein.
1. (Optional) Klicken Sie **[!UICONTROL Check Syntax]** auf , um eine schnelle Syntaxprüfung Ihres Skripts durch Ausführen der Initialisierungs-, Filter- und Abschlussskripte durchzuführen.

   **[!UICONTROL Check Syntax]** aktualisiert und speichert Ihr Skript nicht.
1. Klicken **[!UICONTROL Save Changes]**.
1. (Optional) Erstellen Sie Ihren Staged Site-Index neu, wenn Sie eine Vorschau der Ergebnisse anzeigen möchten.

   Siehe [Konfigurieren eines inkrementellen Indexes einer gestaffelten Website](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0).
1. (Optional) Führen Sie auf der [!DNL Termination Script] Seite einen der folgenden Schritte aus:

   * Klicken Sie auf **[!UICONTROL History]** , um alle vorgenommenen Änderungen wiederherzustellen.

      Siehe [Verwenden der Option](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)Verlauf.

   * Klicken **[!UICONTROL Live]**.

      Siehe [Live-Einstellungen](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)anzeigen.

   * Klicken **[!UICONTROL Push Live]**.

      Siehe [Pushing-Einstellungen](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Grundlagen zum Skript &quot;URL-Masken&quot; {#concept_384F32EA18F84853A7BA99A04009330B}

Mit der Filterung können Sie den Inhalt eines Webdokuments ändern, bevor es indiziert wird. Sie können HTML-Tags einfügen, irrelevante Inhalte entfernen und sogar neue HTML-Metadaten erstellen, die auf der URL, dem MIME-Typ und dem vorhandenen Inhalt eines Dokuments basieren. Das Skript &quot;URL-Masken&quot;ist ein Perl-Skript, das eine leistungsstarke Zeichenfolgenbearbeitung und die Flexibilität bei der Suche nach regulären Ausdrücken bietet.

Um den Inhalt von Dokumenten zu ändern, die nur in einem bestimmten Teil Ihrer Website vorhanden sind, können Sie URL-Masken einschließen, URL-Masken ausschließen oder beides angeben, um die entsprechenden Seiten zu definieren.

Wenn Sie nur die Dokumente unter `"https://www.mysite.com/faqs/"`ändern möchten, können Sie die folgenden Masken verwenden:

```
include https://www.mysite.com/faqs/ 
exclude *
```

Sie können regulären Ausdruck auch in einem URL-Maskenskript verwenden, wie im folgenden Beispiel:

```
include regexp ^https://www\.mysite\.com.*/faqs/.*$ 
exclude *
```

Siehe [Reguläre Ausdrücke](../c-appendices/r-regular-expressions.md#reference_B5BA7D61D82E4109A01D2A2D964E3A6A).

Skriptgesteuerte URL-Masken werden in der Reihenfolge berücksichtigt, in der Sie sie in das [!DNL URL Masks] Feld eingegeben haben. Wenn eine Dokument-URL mit einer Maske übereinstimmt, wird dieses Dokument je nach Maskentyp ein- oder ausgeschlossen. Wenn die URL eines Dokuments keiner URL-Maske entspricht, wird das Dokument nur einbezogen, wenn der MIME-Typ &quot;text/html&quot;ist. Alle anderen MIME-Typen sind ausgeschlossen.

## Hinzufügen eines URL-Maskenskripts {#task_D18F2A496C1C45C997B5DA650AAF5D59}

Geben Sie URL-Adressen wie &quot;Masken einschließen&quot;und &quot;Masken ausschließen&quot;an, um den Inhalt von Dokumenten zu ändern, die nur in einem bestimmten Bereich Ihrer Website vorhanden sind.

Bevor die Auswirkungen der URL-Masken-Einstellungen für Besucher sichtbar sind, erstellen Sie Ihren Site-Index neu.

**So fügen Sie ein URL-Maskenskript hinzu**

1. Klicken Sie im Produktmenü auf **[!UICONTROL Settings]** > **[!UICONTROL Filtering]** > **[!UICONTROL URL Masks]**.
1. (Optional) Geben Sie auf der [!DNL URL Masks] Seite im [!DNL Test URL] Feld eine URL eines Dokuments auf Ihrer Website ein und klicken Sie dann auf , **[!UICONTROL Test]** um die URL gegen die Filterskripte und -masken zu testen.

   Das Dokument &quot;test URL&quot;wird heruntergeladen, das als STDIN-Eingabe für das Filterskript verwendet wird. Anschließend werden die Filter-, Initialisierungs- und Terminierungsskripte ausgeführt. Wenn eine STDOUT-Ausgabe aus dem Filterskript vorhanden ist, wird die Ausgabe in einem neuen Browserfenster angezeigt.

   Durch Klicken auf **[!UICONTROL Test]** wird das Skript nicht aktualisiert und gespeichert.
1. Geben Sie im [!DNL URL Masks] Feld eine URL-Maske pro Zeile ein.
1. (Optional) Klicken Sie **[!UICONTROL Check Syntax]** auf , um eine schnelle Syntaxprüfung Ihrer URL-Masken durchzuführen, indem Sie die Filter-, Initialisierungs- und Terminierungsskripte ausführen.

   **[!UICONTROL Check Syntax]** aktualisiert und speichert Ihr Skript nicht.
1. Klicken **[!UICONTROL Save Changes]**.
1. (Optional) Erstellen Sie Ihren Staged Site-Index neu, wenn Sie eine Vorschau der Ergebnisse anzeigen möchten.

   Siehe [Konfigurieren eines inkrementellen Indexes einer gestaffelten Website](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0).
1. (Optional) Führen Sie auf der [!DNL URL Masks] Seite einen der folgenden Schritte aus:

   * Klicken Sie auf **[!UICONTROL History]** , um alle vorgenommenen Änderungen wiederherzustellen.

      Siehe [Verwenden der Option](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)Verlauf.

   * Klicken **[!UICONTROL Live]**.

      Siehe [Live-Einstellungen](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)anzeigen.

   * Klicken **[!UICONTROL Push Live]**.

      Siehe [Pushing-Einstellungen](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Inhaltstypen in Filtern {#concept_E3EFF4A148EA4D21AFD0A5453A00427E}

Ermöglicht die Auswahl der Inhaltstypen, die für dieses Konto gefiltert werden sollen.

Der in den ausgewählten Inhaltstypen gefundene Text wird in HTML konvertiert und anschließend mithilfe des Skripts verarbeitet, das im Filterskript angegeben ist.

Siehe [Grundlagen zum Filtern von Skripten](../c-about-settings-menu/c-about-filtering-menu.md#concept_E56B73D625854AB2A899EF2D56CFCB47).

Zu den Inhaltstypen, aus denen Sie auswählen können, gehören:

* PDF-Dokumente
* Textdokumente
* Adobe Flash-Filme
* Microsoft Word-Dateien
* Microsoft Office-Dateien (OpenXML)
* Microsoft Excel-Dateien
* Microsoft Powerpoint-Dateien
* Text in MP3-Musikdateien

Bevor die Auswirkungen der Einstellungen für Inhaltstypen oder Änderungen der Einstellungen für Kunden sichtbar sind, müssen Sie Ihren Site-Index neu erstellen.

## Auswählen der gefilterten Inhaltstypen {#task_C46081FA425A43EC8FDE6EA4A52A170A}

Wählen Sie die Inhaltstypen aus, die Sie an das Skript übergeben möchten, das im Filterskript angegeben ist.

Siehe [Grundlagen zum Filtern von Skripten](../c-about-settings-menu/c-about-filtering-menu.md#concept_E56B73D625854AB2A899EF2D56CFCB47).

**So wählen Sie die gefilterten Inhaltstypen aus**

1. Klicken Sie im Produktmenü auf **[!UICONTROL Settings]** > **[!UICONTROL Filtering]** > **[!UICONTROL Content Types]**.
1. Überprüfen Sie auf der [!DNL Content Types] Seite die Inhaltstypen, die an das Filterskript übergeben werden sollen.
1. Klicken **[!UICONTROL Save Changes]**.
1. (Optional) Erstellen Sie Ihren Staged Site-Index neu, wenn Sie eine Vorschau der Ergebnisse anzeigen möchten.

   Siehe [Konfigurieren eines inkrementellen Indexes einer gestaffelten Website](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0).
1. (Optional) Führen Sie auf der [!DNL Content Types] Seite einen der folgenden Schritte aus:

   * Klicken Sie auf **[!UICONTROL History]** , um alle vorgenommenen Änderungen wiederherzustellen.

      Siehe [Verwenden der Option](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)Verlauf.

   * Klicken **[!UICONTROL Live]**.

      Siehe [Live-Einstellungen](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)anzeigen.

   * Klicken **[!UICONTROL Push Live]**.

      Siehe [Pushing-Einstellungen](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).
