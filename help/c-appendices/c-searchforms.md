---
description: Erfahren Sie mehr über Suchformulare in Search&amp;Promote
solution: Target
title: Suchformulare
topic-legacy: Appendices,Site search and merchandising
uuid: 91153e3a-c437-47f3-8c2a-d9ac02965b8c
exl-id: 9771a19d-86a8-41db-9c80-d734fbd10ab7
source-git-commit: 95bf92df17d7832df72e8d883a22f9063e53a18d
workflow-type: tm+mt
source-wordcount: '2899'
ht-degree: 0%

---

# Suchformulare{#search-forms}

## Verwenden von Sammlungen in Suchformularen {#reference_5A079AEEEFB84457892EF0870D0605C3}

Mit Sammlungen können Ihre Kunden bestimmte Bereiche Ihrer Website durchsuchen. Je nachdem, ob Sie eine Dropdown-Liste oder eine Liste von Kontrollkästchen implementieren, können Sie Ihren Kunden die Suche in einer oder mehreren Sammlungen ermöglichen.

Siehe auch [Über Sammlungen](../c-about-settings-menu/c-about-searching-menu.md#concept_62E42ACE53D54EEE9273433B86259127).

Das folgende Beispiel zeigt vier verschiedene Sammlungsnamen und die zugehörigen Bereiche der Website, die sie abdecken:

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Name der Kollektion </p> </th> 
   <th colname="col2" class="entry"> <p> </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Produkte </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_7AE70789C0914EBFBCCC7695C6F53B9E"> 
      <li id="li_72525BAA34E2442D86152F2FD8CA83D5"> https://www.mycompany.com/products.htm </li> 
      <li id="li_5CA4152239124BDBB251E6C94B15D45B"> https://www.mycompany.com/publish/ </li> 
      <li id="li_6E266736B3494696A3AFD841C4AFEC57"> https://www.mycompany.com/search/ </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Bekannte </p> </td> 
   <td colname="col2"> <p>https://www.mycompany.com/customers/ </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Nachrichten </p> </td> 
   <td colname="col2"> <p>https://www.mycompany.com/news/ </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Über Adoben </p> </td> 
   <td colname="col2"> <p>https://www.mycompany.com/company/ </p> </td> 
  </tr> 
 </tbody> 
</table>

In der Dropdown-Liste des Suchformulars können Benutzer eine Sammlung auswählen. Sie sieht wie folgt aus:

![](assets/DropdownsearchformUI.png)

Das Dropdown-Suchformular wird mit dem folgenden HTML-Code generiert:

```
<select name="sp_k"> 
<option value="">All of Adobe</option> 
<option value="Products">Products</option> 
<option value="Customers">Customers</option> 
<option value="News">News</option> 
<option value="About Adobe">About Adobe</option> 
</select>
```

Alternativ können Sie eine Gruppe von Kontrollkästchen in Ihrem Suchformular verwenden, damit Besucher mehrere Sammlungen auswählen können:

![](assets/checkboxes.png)

Das Kontrollkästchen-Suchformular wird mit dem folgenden HTML-Code generiert:

```
<input type="checkbox" name="sp_k" value="">All of Adobe<br> 
<input type="checkbox" name="sp_k" value="Products">Products<br> 
<input type="checkbox" name="sp_k" value="Customers">Customers<br> 
<input type="checkbox" name="sp_k" value="News">News<br> 
<input type="checkbox" name="sp_k" value="About Adobe">About Adobe<br>
```

## Suchergebnisse {#section_BBDD5B44E2B349BC88D937F44583D350}

Das Suchvorlagentag `<search-input-collections>` generiert das Erfassungslistenfeld HTML in den Suchergebnissen und wählt automatisch die Sammlung aus, die in der Suche angegeben ist. Wenn Sie stattdessen Kontrollkästchen generieren möchten, verwenden Sie das Tag `<search-input>` anstelle des Tags `<input>` wie folgt:

```
<search-input type="checkbox" name="sp_k" value="">All of Adobe<br> 
<search-input type="checkbox" name="sp_k" value="Products">Products<br> 
<search-input type="checkbox" name="sp_k" value="Customers">Customers<br> 
<search-input type="checkbox" name="sp_k" value="News">News<br> 
<search-input type="checkbox" name="sp_k" value="About Adobe">About Adobe<br>
```

Das Tag `<search-input>` gibt ein `<input>` -Tag aus und schließt das Attribut `checked` ein, wenn die Sammlung bei der Suche angegeben wurde.

## Verwenden von Frames mit Formularen {#reference_82CDDDA1E37042E4849EBF7EA05407C5}

Sie können Ihre Fragmente so konfigurieren, dass sie mit der Site-Suche/dem Merchandising funktionieren.

<!-- 404 DEAD LINK To learn more about HTML frames and the HTML frameset element, see the following URL:

[https://www.w3schools.com/html/html_frames.asp](https://www.w3schools.com/html/html_frames.asp) -->

Wenn Ihre Site Frames verwendet, können Sie einen Zielrahmen für Suchergebnislinks angeben. Das Standardziel lautet _self , wodurch Links im aktuellen Frame oder Browser-Fenster geöffnet werden. Sie können stattdessen Site-spezifische oder browserspezifische Ziele angeben:

* Die Ergebnisse _top (Browser-reserviert) werden im aktuellen Browserfenster geöffnet und ersetzen alle aktuellen Frames.
* _blank (Browser-reserviert) Ergebnisse werden in einem neuen Browserfenster geöffnet.
* Die Ergebnisse _parent (Browser-reserviert) werden im übergeordneten Frame des aktuellen Frames geöffnet.
* frame2 (Site-spezifisch) Ergebnisse werden in einem Frame mit dem Namen &quot;frame2&quot;geöffnet. Sie können den Namen eines beliebigen Bildes als Wert angeben (z. B. &quot;main&quot;oder &quot;content&quot;).

Wenn Ihre Site keine Frames verwendet, sollten Sie den Standardzielnamen wahrscheinlich nicht ändern.

Wenn Sie eine benutzerdefinierte Suchergebnisvorlage für Ihre Website erstellen, können Sie die angegebene Einstellung überschreiben, indem Sie das Attribut `target` des Tags `<search-link>` verwenden.

Die Konfiguration von Fragmenten erfolgt wie folgt:

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Prozessschritt </p> </th> 
   <th colname="col02" class="entry"> <p>Prozessbeschreibung </p> </th> 
   <th colname="col2" class="entry"> <p>Link </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>1 </p> </td> 
   <td colname="col02"> <p>Fügen Sie das Formular zum gewünschten Frame auf Ihrer Webseite hinzu. </p> </td> 
   <td colname="col2"> <p> <a href="#section_BAA8A502BB2243F8B5FF9783CDF2BFFD" type="section" format="dita" scope="local"> Hinzufügen des Suchformular-Codes zu einem Frame in Ihrem ...  </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>2 </p> </td> 
   <td colname="col02"> <p>Legen Sie den Zielrahmen für die Suchergebnisseite fest. </p> </td> 
   <td colname="col2"> <p> <a scope="local" href="#section_532CACB90888467093D95EACB64FDFA1" type="section" format="dita"> Festlegen des Zielrahmens für die Suchergebnisseite  </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>3 </p> </td> 
   <td colname="col02"> <p>Legen Sie das Ziel für Links fest, die über die Suchergebnisseite erstellt werden. </p> </td> 
   <td colname="col2"> <p> <a scope="local" href="#section_523248C5AC424D878321C21A23A5CD66" type="section" format="dita"> Ziel für Links aus den Suchergebnissen festlegen..  </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>4 </p> </td> 
   <td colname="col02"> <p>Bearbeiten Sie die Navigations-Frame-Seiten, um zu verhindern, dass sie indiziert werden. </p> </td> 
   <td colname="col2"> <p> <a scope="local" href="#section_C62E5F0EE1294D5EBD97E123E54433FC" type="section" format="dita"> Bearbeiten der Navigations-Frame-Seiten, um zu verhindern, dass sie ...  </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>5 </p> </td> 
   <td colname="col02"> <p>Testen Sie das Suchformular. </p> </td> 
   <td colname="col2"> <p> <a scope="local" href="#section_43D8D4A7BF524DC480DFE5442F6A2E3C" type="section" format="dita"> Testen des Suchformulars  </a> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Hinzufügen des Suchformularcodes zu einem Frame auf Ihrer Webseite {#section_BAA8A502BB2243F8B5FF9783CDF2BFFD}

1. Klicken Sie im Produktmenü auf **[!UICONTROL Design]** > **[!UICONTROL Auto-Complete]** > **[!UICONTROL Form Source]**.

   Der HTML-Suchformularcode sieht in etwa wie folgt aus:

   ```
   <!-- Adobe Target HTML for [your customer name] --> 
   <form method="get" action="https://search.atomz.com/search/"> 
   <input size=15 name="sp_q"><br> 
   <input type=submit value="Search"> 
   <input type=hidden name="sp_a" value="[your account number]"> 
   </form>
   ```

1. Wählen Sie auf der Seite [!DNL Standard Form Source] den HTML-Suchformularcode aus, der im Textfeld angezeigt wird, und kopieren Sie ihn.
1. Fügen Sie den Suchformularcode in den gewünschten Frame im Fragment ein.

   Im folgenden Beispiel wird der Suchformularcode in den Navigationsrahmen eingefügt - den schmalen vertikalen Rahmen auf der linken Bildschirmseite.

   ![](assets/frames1.gif)

## Festlegen des Zielrahmens für die Suchergebnisseite {#section_532CACB90888467093D95EACB64FDFA1}

Wenn Sie Ihren Suchformularcode wie oben in den vertikalen Navigationsrahmen platziert haben, können Sie die Suchergebnisse im größeren Hauptframe anzeigen. In diesem Beispiel rufen Sie den Hauptframe &quot;body&quot;auf und legen ihn als Zielframe fest.

![](assets/frames2.gif)

1. Um den Zielrahmen für die Ergebnisseite anzugeben, fügen Sie eine Zielgruppe und einen Wert zum Formular hinzu, indem Sie die folgende Zeile im Suchformularcode wie folgt ändern:

   `<form method="get" action="https://search.atomz.com/search/">`

   wie folgt:

   `<form target="body" method="get" action="https://search.atomz.com/search/">`

   Stellen Sie sicher, dass Sie Anführungszeichen um den Formularzielwert setzen.

Wenn ein Kunde eine Suche auf Ihrer Website durchführt, werden die Suchergebnisse im Hauptteil der Webseite angezeigt.

## Festlegen des Ziels für auf der Suchergebnisseite vorgenommene Links {#section_523248C5AC424D878321C21A23A5CD66}

Sie können den Zielrahmen festlegen, indem Sie die Vorlage direkt bearbeiten.

Wenn Ihre Suchergebnisse im &quot;body&quot;-Frame angezeigt werden, sollen die Links wahrscheinlich auch im &quot;body&quot;-Frame geöffnet werden. Da es sich um denselben Frame handelt, also um den Zielwert `"_self"`, der die Standardeinstellung ist, müssen Sie keine Änderungen vornehmen.

Sie können auch den Zielrahmen für Ergebnislinks festlegen. Im Folgenden finden Sie einige Beispiele für die Möglichkeiten:

* Legen Sie unterschiedliche Frames für die Suchergebnisse und deren Links fest, sodass die Suchergebnisse in ihrem eigenen Frame aktiv bleiben, während jedes angeklickte Ergebnis in einem separaten Frame geöffnet wird.
* Geben Sie an, dass die Suchergebnisse in einem neuen leeren Fenster geöffnet werden, sodass Ihr altes Fenster mit seinem ursprünglichen Inhalt aktiv bleibt, wodurch auch die Suchergebnisse beibehalten werden.

Der Zielname kann entweder der Name eines in Ihrem HTML-Code angegebenen Frames sein oder einer der folgenden HTML-Standardwerte sein:

* `target="_blank"` Öffnen Sie Links in einem neuen, leeren, unbenannten Fenster.

* `target="_self"` Standard. Öffnen Sie Links im selben Fenster, in dem sich die Suchergebnisse befinden. In diesem Fall das Fenster mit den ursprünglichen Suchergebnissen. Verwenden Sie diese Option, um ein global zugewiesenes Basisziel zu überschreiben.

* `target="_parent"` Öffnen Sie Links im übergeordneten Fragment der Link-Seite . Wenn das Dokument kein übergeordnetes Dokument hat, funktioniert dies standardmäßig wie `"_self"`.

* `target="_top"` Öffnen Sie Links im vollständigen Fenster. Wenn sich das Dokument bereits oben befindet, funktioniert dies standardmäßig wie `"_self"`. Verwenden Sie diese Option, um aus einer willkürlich tiefen Rahmenverschachtelung auszubrechen.

Um beispielsweise den Zielframe `_blank` festzulegen, können Sie die Vorlage wie folgt bearbeiten:

1. Klicken Sie im Produktmenü auf **[!UICONTROL Design]** > **[!UICONTROL Templates]**.

1. Klicken Sie auf der Seite [!DNL Staged Templates] in der Tabelle auf den Namen der Vorlage mit dem Ziel-Frame.
1. Suchen Sie das Tag `<search-link>` . Ihr standardmäßiges `<search-link>` -Tag sollte in etwa wie folgt aussehen:

   `<search-link><search-title length=100></search-link>`

1. Fügen Sie das Frame-Ziel zum Tag `<search-link>` hinzu. Geben Sie im obigen Beispiel `target="_blank"` ein. Stellen Sie sicher, dass Sie den Unterstrich und die Anführungszeichen um den Zielwert einfügen.

   Das Tag `<search-link>` wird nun wie folgt angezeigt:

   `<search-link target="_blank"><search-title length=100></search-link>`

Wenn ein Site-Besucher einen Link zu den Suchergebnissen auswählt, wird die verknüpfte Seite jetzt in einem neuen, leeren Fenster geöffnet.

## Bearbeiten der Navigations-Frame-Seiten, um deren Indizierung zu verhindern {#section_C62E5F0EE1294D5EBD97E123E54433FC}

Normalerweise möchten Sie Ihre Navigationsrahmen von der Indexierung mit Ihren Suchergebnissen ausschließen. Um diese Funktion zu erreichen, können Sie diesen Seiten `noindex` Meta-Tag hinzufügen.

1. Öffnen Sie die HTML-Seitenquelle für Ihren Navigationsrahmen.
1. Fügen Sie das folgende Meta-Tag im Abschnitt `<head>` Ihrer HTML-Datei hinzu:

   `<meta name="robots" content="noindex">`

   Beispiel:

   ```
   <html> 
   <head> 
   <title>This page is a frameset that I do not want indexed</title> 
   <meta http-equiv="Content-Type" content="text/html; charset=iso-8859-1"> 
   <meta name="robots" content="noindex"> 
   </head>
   ```

## Testen des Suchformulars {#section_43D8D4A7BF524DC480DFE5442F6A2E3C}

1. Navigieren Sie auf Ihrer Website zu einem Formular.
1. Geben Sie im Suchfeld einige Suchbegriffe ein und klicken Sie dann auf **[!UICONTROL Search]**.

   Folgendes ist wahr:

   * Die Suchergebnisseite wird im angegebenen Zielframe angezeigt.
   * Die Links aus Ihren Suchergebnissen befinden sich im angegebenen Zielframe.
   * Ergebnisse von Navigationsrahmen werden nicht angezeigt.

   Wenn nach dem Testen des Suchformulars Probleme mit Frames auftreten, wenden Sie sich an den Support.

## Beispiel für ein erweitertes Suchformular {#reference_82E1051918744EBA88A01E9E6AE42C4A}

Sie können den erweiterten Formularcode an Ihre Design- und Inhaltsanforderungen anpassen oder zusätzliche Suchparameter hinzufügen oder entfernen.

Ihre Homepage eignet sich gut zum Einfügen eines erweiterten Suchformulars, da viele Kunden dort Suchfunktionen erwarten. Sie können auch eine HTML-Seite erstellen, die das Suchformular und andere hilfreiche Informationen enthält, und dann auf Ihrer gesamten Website einen Link zu dieser Seite erstellen.

Wenn Sie sichere Inhalte indizieren, können Sie die Suchergebnisse von sicheren Suchwebservern erhalten lassen. Ändern Sie die URL im Aktionsattribut für Suchformulare in: action=&quot;https://search.atomz.com/search/&quot; zu diesem Zweck.

>[!NOTE]
>
>Einige HTML-Editoren haben Probleme beim Einfügen von HTML-Code aus anderen Anwendungen. Wenn der HTML-Code auf Ihrer Webseite als Text erscheint, kopieren Sie den Suchcode in einen einfachen Texteditor wie Notepad unter Windows oder Simple Text unter Mac und kopieren Sie ihn dann erneut aus dem einfachen Texteditor in Ihren HTML-Editor.

Suchparameter werden im erweiterten Suchformularcode verwendet, um Optionsfelder, Kontrollkästchen und Listenfelder zu erstellen, die Kunden zur Anpassung einzelner Suchvorgänge verwenden können. Kunden können die Anzahl der angezeigten Suchergebnisse angeben, z. B. einen Datumsbereich, oder festlegen, ob Zusammenfassungen mit Suchergebnissen angezeigt werden, die alle über Optionen auf den erweiterten Suchformularen angezeigt werden.

Im folgenden Beispiel für ein erweitertes Suchformular wird im Rest dieses Themas gezeigt, wie jede Option im Formular mithilfe von Suchparametern erstellt wird.

![](assets/advancedsearchform.png)

Sie können den gesamten HTML-Code des erweiterten Suchformulars des obigen Beispiels anzeigen.

Siehe [Erweiterter HTML-Code für Suchformulare](#reference_9AAD4A46B68D4D48865508982CB86DB9).

Siehe [Konfigurieren des automatischen Ausfüllens von CSS](../c-about-auto-complete.md#task_EECE35DEB6C94F4A8A5B42B4DED76D96).

Siehe [Kopieren des HTML-Codes des Suchformulars in den ...](../c-about-auto-complete.md#task_A3A01EA800F24C0AA33902387E0362C7).

<table> 
 <thead> 
  <tr> 
   <th colname="col2" class="entry"> <p>Position im Formular </p> </th> 
   <th colname="col1" class="entry"> <p>Parameter </p> </th> 
   <th colname="col3" class="entry"> <p>HTML-Code </p> </th> 
   <th colname="col4" class="entry"> <p>Beschreibung </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col2"> <p>Erweiterte Suchformularoptionen aktivieren (ausgeblendetes Feld) </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> sp_advanced  </span> </p> </td> 
   <td colname="col3"> <p> <span class="syntax html codeph"> &lt;input type="hidden" name="sp_advanced" value="1"&gt; </span> </p> </td> 
   <td colname="col4"> <p>Erweiterte Suchoptionen aktivieren oder deaktivieren. Sie können beispielsweise ein Standardsuchformular auf Ihrer Startseite mit einem Link zu einer zweiten Seite einfügen, die ein erweitertes Formular enthält. In diesem Fall würden Sie eine Kopie Ihres Standardformulars in <span class="codeph"> &lt;search-if-not-advanced&gt; einfügen..&lt;/search-if-not-advanced&gt; </span> Vorlagen-Tags. </p> <p>Ein Kunde, der eine Suche aus dem Standardformular durchführt, sieht ein Standardsuchformular, wenn die Suchergebnisse angezeigt werden. Im Bildschirm des erweiterten Suchformulars fügen Sie das Tag <span class="codeph"> &lt;input type=hidden name="sp_advanced" value=1&gt; </span> mit den anderen erweiterten Formularoptionen ein. </p> <p>Sie fügen auch eine Kopie des erweiterten Suchformulars in die Vorlagentags &lt;search-if-advanced&gt;... &lt;/search-if-advanced&gt; ein. Ein Kunde, der eine Suche aus Ihrem erweiterten Suchformular ausführt, sieht ein erweitertes Suchformular, wenn Suchergebnisse angezeigt werden. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p> Übereinstimmung mit beliebigen, allen oder Wortgruppen </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> sp_p  </span> </p> <p> </p> </td> 
   <td colname="col3"> <p> <code class="syntax html"> &lt;!--&nbsp;Allow&nbsp;"any,"&nbsp;"all,"&nbsp;or&nbsp;"phrase"&nbsp;--&gt; 
      &lt;input&nbsp;type=radio&nbsp;name="sp_p"&nbsp;value="any"&gt;Any&nbsp;word 
      &lt;input&nbsp;type=radio&nbsp;name="sp_p"&nbsp;value="all"&nbsp;checked&gt;All&nbsp;words 
      &lt;input&nbsp;type=radio&nbsp;name="sp_p"&nbsp;value="phrase"&gt;Exact&nbsp;phrase </code> </p> </td> 
   <td colname="col4"> <p>Erlauben Sie Ihrem Kunden, anzugeben, dass "beliebiges Wort", "alle Wörter"oder "der genaue Satz"vorhanden sein müssen, damit ein Dokument übereinstimmt. Wenn der Parameter <span class="codeph"> sp_p </span> angegeben ist, müssen Kunden weder "+" noch "-"oder beides in der Suchabfrage verwenden. </p> <p> Wenn der Parameter <span class="codeph"> sp_p </span> weggelassen wird oder auf ""oder "any"festgelegt ist, können Kunden weiterhin die Spezifikatoren "+"und "-"verwenden. Wenn der Parameter <span class="codeph"> sp_p </span> auf "all"oder "Satz"gesetzt ist, werden die angegebenen Werte "+"und "-"ignoriert. </p> <p>Weitere Informationen zur Verwendung von "+"und "-"bei einer Suche. </p> <p>Siehe <a href="../c-about-settings-menu/c-about-searching-menu.md#concept_207105CF26B1448F8A3D223787C56AB8" type="concept" format="dita" scope="local">Info zu Suchen</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p> Klangalike-Abgleich </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> sp_w  </span> </p> <p>und </p> <p> <span class="codeph"> sp_w_control  </span> </p> <p> </p> </td> 
   <td colname="col3"> <p> <code class="syntax html"> &lt;!--&nbsp;Checkbox&nbsp;enables&nbsp;sound-alike&nbsp;matching&nbsp;--&gt; 
      &lt;input&nbsp;type=hidden&nbsp;name="sp_w_control"&nbsp;value=1&gt; 
      &lt;input&nbsp;type=checkbox&nbsp;name="sp_w"&nbsp;value="alike"&gt;&nbsp;Sound-alike&nbsp;matching </code> </p> </td> 
   <td colname="col4"> <p>Kunden können die Abstimmung von Geräuschen aktivieren oder deaktivieren. Durch die intelligente Abstimmung können falsch geschriebene Suchanfragen mit Wörtern übereinstimmen, die in Ihren Dokumenten "ähnlich klingen". </p> <p>Wenn der Parameter <span class="codeph"> sp_w_control </span> auf 1 gesetzt und der Parameter <span class="codeph"> sp_w </span> auf "alike"gesetzt ist, wird das generierte Kontrollkästchen aktiviert, wodurch standardmäßig eine Klangalike-Übereinstimmung aktiviert wird. </p> <p>Wenn der Parameter <span class="codeph"> sp_w </span> auf ""festgelegt ist, wird das Kontrollkästchen nicht aktiviert. </p> <p>Wenn Sie während der letzten Indizierung keine Klangalike-Übereinstimmung aktiviert haben, ist eine Klangalike-Übereinstimmung nicht möglich und der Parameter <span class="codeph"> sp_w </span> wird ignoriert. Um die Klangübereinstimmung zu aktivieren, klicken Sie im Produktmenü auf <span class="uicontrol"> Linguistik </span> &gt; <span class="uicontrol"> Wörter und Sprache </span> &gt; <span class="uicontrol"> Klangähnliche Übereinstimmung </span>. </p> <p>Sie können die Parameter <span class="codeph"> sp_w </span> und <span class="codeph"> sp_w_control </span> wie folgt zuweisen: </p> <p> <code class="syntax html"> &lt;!--&nbsp;Checkbox&nbsp;disables&nbsp;sound-alike&nbsp;matching&nbsp;--&gt; 
      &lt;input&nbsp;type=hidden&nbsp;name="sp_w_control"&nbsp;value=0&gt; 
      &lt;input&nbsp;type=checkbox&nbsp;name="sp_w"&nbsp;value="exact"&gt; 
      No&nbsp;sound-alike&nbsp;matching </code> </p> <p>Wenn in diesem Fall der Parameter <span class="codeph"> sp_w_control </span> auf 0 gesetzt und der Parameter <span class="codeph"> sp_w </span> auf "exakt"gesetzt ist, ist die Abstimmung von Klangähnchen standardmäßig deaktiviert. Wenn der Parameter <span class="codeph"> sp_w </span> auf ""gesetzt ist, wird die Abstimmung von Geräuschen aktiviert. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>Datumsbereich passend </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> sp_d  </span> </p> <p> </p> </td> 
   <td colname="col3"> <p> <code class="syntax html"> &lt;!--Specifies&nbsp;type&nbsp;of&nbsp;date&nbsp;range&nbsp;searching&nbsp;to&nbsp;perform.--&gt; 
      &lt;input&nbsp;type=radio&nbsp;name="sp_d"&nbsp;value="custom"&nbsp;checked&gt; 
      &lt;input&nbsp;type=radio&nbsp;name="sp_d"&nbsp;value="specific"&gt; </code> </p> </td> 
   <td colname="col4"> <p>Der Parameter <span class="codeph"> sp_d </span> gibt einen benutzerdefinierten Datenbereich an, der mit der Leistung übereinstimmt, oder einen bestimmten Datumsbereich, der mit der Leistung übereinstimmt. </p> <p>Im standardmäßigen erweiterten Suchformular wird diese Option als Optionsfeldgruppe mit einer Dropdown-Liste von "benutzerdefinierten"Datumsbereichen angezeigt, wie mit dem Parameter <span class="codeph"> sp_date_range </span> generiert. Es enthält auch und eine Gruppe "spezifischer" Start- und Enddaten, die mit <span class="codeph"> sp_start_day </span>, <span class="codeph"> sp_start_month </span>, <span class="codeph"> sp_start_year </span>, <span class="codeph"> sp_end_day </span>, <span class="codeph"> sp_end_month&gt; und </span> generiert werden a10/&gt; sp_end_year </span> Parameter.<span class="codeph"> </span></p> <p>Ein "benutzerdefinierter"Datumsbereich ist ein benannter Datumsbereich, der durchsucht werden soll. Beispiel: "Jederzeit", "Heute", "Innerhalb des letzten Jahres"usw. </p> <p>Ein "spezifischer"Datumsbereich besteht aus einem Start- und einem Enddatum. Beispiel: von "8. September 2009 bis 18. Oktober 2011". </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>Datumsbereichsübereinstimmung: benutzerdefinierter Datumsbereich </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> sp_date_range  </span> </p> <p> </p> </td> 
   <td colname="col3"> <p> <code class="syntax html"> &lt;!--Selection&nbsp;list&nbsp;for&nbsp;custom&nbsp;date&nbsp;range.--&gt; 
      &lt;select&nbsp;name="sp_date_range"&nbsp;size=1&gt; 
      &lt;option&nbsp;value=-1&nbsp;selected&gt;Anytime&lt;/option&gt; 
      &lt;option&nbsp;value=7&gt;Within&nbsp;the&nbsp;last&nbsp;week&lt;/option&gt; 
      &lt;option&nbsp;value=14&gt;Within&nbsp;the&nbsp;last&nbsp;2&nbsp;weeks&lt;/option&gt; 
      &lt;option&nbsp;value=30&gt;Within&nbsp;the&nbsp;last&nbsp;30&nbsp;days&lt;/option&gt; 
      &lt;option&nbsp;value=60&gt;Within&nbsp;the&nbsp;last&nbsp;60&nbsp;days&lt;/option&gt; 
      &lt;option&nbsp;value=90&gt;Within&nbsp;the&nbsp;last&nbsp;90&nbsp;days&lt;/option&gt; 
      &lt;option&nbsp;value=180&gt;Within&nbsp;the&nbsp;last&nbsp;180&nbsp;days&lt;/option&gt; 
      &lt;option&nbsp;value=365&gt;Within&nbsp;the&nbsp;last&nbsp;year&lt;/option&gt; 
      &lt;option&nbsp;value=730&gt;Within&nbsp;the&nbsp;last&nbsp;two&nbsp;years&lt;/option&gt; 
      &lt;/select&gt; </code> </p> </td> 
   <td colname="col4"> <p>Der Parameter <span class="codeph"> sp_date_range </span> wird verwendet, um einen "benutzerdefinierten"Datumsbereich zu erstellen. Beispiel: "Anytime", "Today", "Within the last year"usw. </p> <p>Werte größer oder gleich null geben die Anzahl der Tage an, die vor dem aktuellen Datum durchsucht werden sollen. Beispielsweise gibt der Wert 0 den Wert "Heute"an, der Wert "1"den Wert "Heute und Gestern", der Wert "30"den Wert "In den letzten 30 Tagen"usw. Werte kleiner als null geben einen benutzerdefinierten Bereich wie folgt an: </p> <p> 
     <ul id="ul_E65DDE33883F441F9730F315E485AD98"> 
      <li id="li_83E9466AB9D7438A8544001F6B007186"> <p>-1 = "Anytime", identisch mit der Angabe eines Datumsbereichs. </p> </li> 
      <li id="li_38AB8D97179A47F9B860A96EA09119BB"> <p>-2 = "Diese Woche", die von Sonntag bis Samstag der aktuellen Woche durchsucht. </p> </li> 
      <li id="li_F4C3A8658428418A8A06FBAAB4733C68"> <p>-3 = "Letzte Woche", die von Sonntag bis Samstag der Woche vor der aktuellen Woche durchsucht wird. </p> </li> 
      <li id="li_DF2D0B043A4E4DE9BE8D82E69A76E793"> <p>-4 = "Dieser Monat", der Datumsangaben innerhalb des aktuellen Monats durchsucht. </p> </li> 
      <li id="li_76BC4C2CED574E2A81448158828BFF1B"> <p>-5 = "Letzter Monat", der Datumsangaben innerhalb des Monats vor dem aktuellen Monat durchsucht. </p> </li> 
      <li id="li_17FF849384FB46D58AF6FF1D3BC408C8"> <p>-6 = "Dieses Jahr", das Daten innerhalb des aktuellen Jahres durchsucht. </p> </li> 
      <li id="li_E2B8B4DFF3914BBDB86D0EB77F52B305"> <p>-7 = "Letztes Jahr", das Daten innerhalb des Jahres durchsucht, das dem aktuellen Jahr vorausgeht. </p> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>Datumsbereichsübereinstimmung: Anfangsdaten </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> sp_start_day, sp_start_month, sp_start_year  </span> </p> <p> </p> </td> 
   <td colname="col3"> </td> 
   <td colname="col4"> <p>Dieses Triplet numerischer Werte gibt das Anfangsdatum eines bestimmten Datumsbereichs an, der durchsucht werden soll. Achten Sie darauf, alle drei Werte anzugeben, da ein teilweise angegebenes Datum ignoriert wird. </p> <p>Es ist zulässig, nur das Startdatum, nur das Enddatum oder sowohl das Start- als auch das Enddatum anzugeben. Wenn nur das Startdatum angegeben ist, enthält die Suche übereinstimmende Dokumente, die am oder nach dem Startdatum datiert sind. Wenn nur das Enddatum angegeben ist, enthält die Suche übereinstimmende Dokumente am oder vor dem Enddatum. Wenn sowohl das Start- als auch das Enddatum angegeben sind, enthält die Suche übereinstimmende Dokumente vom Startdatum bis zum Enddatum. </p> <p>Alle Daten werden relativ zur Greenwich Mean Time gesucht. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p> Datumsbereichsübereinstimmung: Enddaten </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> sp_end_day, sp_end_month, sp_end_year  </span> </p> <p> </p> </td> 
   <td colname="col3"> </td> 
   <td colname="col4"> <p>Dieser Tripel numerischer Werte gibt das Enddatum des jeweiligen zu suchenden Datumsbereichs an. Achten Sie darauf, alle drei Werte anzugeben, da ein teilweise angegebenes Datum ignoriert wird. </p> <p>Es ist zulässig, nur das Startdatum, nur das Enddatum oder sowohl das Start- als auch das Enddatum anzugeben. Wenn nur das Startdatum angegeben ist, enthält die Suche übereinstimmende Dokumente, die am oder nach dem Startdatum datiert sind. Wenn nur das Enddatum angegeben ist, enthält die Suche übereinstimmende Dokumente am oder vor dem Enddatum. Wenn sowohl das Start- als auch das Enddatum angegeben sind, enthält die Suche übereinstimmende Dokumente vom Startdatum bis zum Enddatum. </p> <p>Alle Daten werden relativ zur Greenwich Mean Time gesucht. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>Innerhalb des Suchfelds </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> sp_x  </span> </p> </td> 
   <td colname="col3"> <p> <code class="syntax html"> &lt;!--&nbsp;List&nbsp;box&nbsp;selects&nbsp;the&nbsp;search&nbsp;field&nbsp;--&gt; 
      Within&nbsp;&lt;select&nbsp;name="sp_x"&nbsp;size=1&gt; 
      &lt;option&nbsp;value="any"&nbsp;selected&gt;Anywhere&lt;/option&gt; 
      &lt;option&nbsp;value="title"&gt;Title&lt;/option&gt; 
      &lt;option&nbsp;value="desc"&gt;Description&lt;/option&gt; 
      &lt;option&nbsp;value="keys"&gt;Keywords&lt;/option&gt; 
      &lt;option&nbsp;value="body"&gt;Body&lt;/option&gt; 
      &lt;option&nbsp;value="alt"&gt;Alternate&nbsp;text&lt;/option&gt; 
      &lt;option&nbsp;value="url"&gt;URL&lt;/option&gt; 
      &lt;option&nbsp;value="target"&gt;Target&lt;/option&gt; 
      &lt;option&nbsp;value="date"&gt;Date&lt;/option&gt;* 
      &lt;/select&gt; </code> </p> </td> 
   <td colname="col4"> <p>Mit dem Listenfeld <span class="codeph"> sp_x </span> können Ihre Kunden das Feld angeben, in dem nach den Abfragezeichenfolgen gesucht werden soll. </p> <p>Der Kunde kann entweder alle Felder, den Titel, die Dokumentbeschreibung, die Dokumentschlüsselwörter, den Text, den alternativen Text, die URL, das Datum oder die Zielkeywords des Dokuments auswählen. </p> <p>Wenn der Parameter <span class="codeph"> sp_x </span> verwendet wird, müssen Kunden nicht "title:", "desc:", "keys:", "body:", "alt:", "url:"und "target:"in Suchabfragezeichenfolgen angeben. </p> <p>Wenn der Parameter <span class="codeph"> sp_x </span> weggelassen wird oder auf ""oder "any"festgelegt ist, können Kunden weiterhin die Feldspezifikations-Zeichenfolgen verwenden. Wenn der Parameter <span class="codeph"> sp_x </span> auf ein bestimmtes Feld gesetzt ist, werden alle anderen Feldspezifikations-Zeichenfolgen ignoriert. </p> <p>Siehe <a href="../c-about-settings-menu/c-about-searching-menu.md#concept_207105CF26B1448F8A3D223787C56AB8" type="concept" format="dita" scope="local">Info zu Suchen</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>Ergebnisanzahl anzeigen </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> sp_c  </span> </p> </td> 
   <td colname="col3"> <p> <code class="syntax html"> &lt;!--&nbsp;List&nbsp;box&nbsp;selects&nbsp;number&nbsp;of&nbsp;results&nbsp;to&nbsp;show&nbsp;per&nbsp;page&nbsp;--&gt; 
      Show&nbsp;&lt;select&nbsp;name="sp_c"&nbsp;size=1&gt; 
      &lt;option&nbsp;value=5&gt;5&lt;/option&gt; 
      &lt;option&nbsp;value=10&nbsp;selected&gt;10&lt;/option&gt; 
      &lt;option&nbsp;value=25&gt;25&lt;/option&gt; 
      &lt;option&nbsp;value=50&gt;50&lt;/option&gt; 
      &lt;option&nbsp;value=100&gt;100&lt;/option&gt; 
      &lt;/select&gt;&nbsp;results </code> </p> </td> 
   <td colname="col4"> <p>Ermöglicht es Kunden, die Anzahl der Suchergebnisse auszuwählen, die auf jeder Suchergebnisseite angezeigt werden. </p> <p>Sie können so viele oder so wenige Auswahlmöglichkeiten im Formular haben, wie Sie möchten. Stellen Sie sicher, dass der Wert "value="mit dem angezeigten Wert übereinstimmt. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>Anzeigen oder Ausblenden von Zusammenfassungen </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> sp_m  </span> </p> </td> 
   <td colname="col3"> <p> <code class="syntax html"> &lt;!--&nbsp;Show&nbsp;or&nbsp;hide&nbsp;summaries&nbsp;in&nbsp;search&nbsp;results&nbsp;--&gt; 
      &lt;select&nbsp;name="sp_m"&nbsp;size=1&gt; 
      &lt;option&nbsp;value=1&nbsp;selected&gt;with&lt;/option&gt; 
      &lt;option&nbsp;value=0&gt;without&lt;/option&gt; 
      &lt;/select&gt;&nbsp;summaries&nbsp; </code> </p> </td> 
   <td colname="col4"> <p>Kunden können auswählen, ob für jede Übereinstimmung Zusammenfassungstext angezeigt wird. </p> <p>Setzen Sie den Wert auf 1, wenn Sie Zusammenfassungen anzeigen möchten. Setzen Sie den Wert auf 0 , wenn Sie Zusammenfassungen ausblenden möchten. Sie können den Parameter auch mit einer Reihe von Optionsfeldern verwenden, wie im folgenden Beispiel gezeigt: </p> <p> <code class="syntax html"> &lt;!--&nbsp;Show&nbsp;or&nbsp;hide&nbsp;summaries&nbsp;in&nbsp;search&nbsp;results&nbsp;--&gt; 
      &lt;input&nbsp;type=radio&nbsp;name="sp_m"&nbsp;value=1&nbsp;selected&gt;Show&nbsp;summaries 
      &lt;input&nbsp;type=radio&nbsp;name="sp_m"&nbsp;value=0&gt;Hide&nbsp;summaries </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>Nach Ergebnissen sortieren </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> sp_s  </span> </p> </td> 
   <td colname="col3"> <p> <code class="syntax html"> &lt;!--&nbsp;Sort&nbsp;results&nbsp;by&nbsp;relevance&nbsp;or&nbsp;by&nbsp;date&nbsp;--&gt; 
      Sort&nbsp;by&nbsp;&lt;select&nbsp;name="sp_s"&nbsp;size=1&gt; 
      &lt;option&nbsp;value=0&nbsp;selected&gt;relevance&lt;/option&gt; 
      &lt;option&nbsp;value=1&gt;date&lt;/option&gt; 
      &lt;/select&gt; </code> </p> </td> 
   <td colname="col4"> <p>Kunden können wählen, ob die Ergebnisse in der Reihenfolge ihrer Relevanz oder ihres Datums aufgelistet werden. </p> <p>Wenn der Wert auf 1 festgelegt ist, werden die Ergebnisse aus dem zuletzt geänderten Dokument in das am wenigsten geänderte Dokument aufgeführt. Wenn der Wert auf 0 gesetzt ist, werden die Ergebnisse aus den relevantesten in die am wenigsten relevanten aufgelistet. Sie können diesen Parameter auch mit Optionsfeldern wie im folgenden Beispiel verwenden: </p> <p> <code class="syntax html"> &lt;!--&nbsp;Sort&nbsp;results&nbsp;by&nbsp;relevance&nbsp;or&nbsp;by&nbsp;date&nbsp;--&gt; 
      &lt;input&nbsp;type=radio&nbsp;name="sp_s"&nbsp;value=0&nbsp;selected&gt;Sort&nbsp;by&nbsp;relevance 
      &lt;input&nbsp;type=radio&nbsp;name="sp_s"&nbsp;value=1&gt;Sort&nbsp;by&nbsp;date </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Erweiterter HTML-Code für Suchformulare {#reference_9AAD4A46B68D4D48865508982CB86DB9}

Der HTML-Formularcode, der zum Erstellen des erweiterten Suchformulars verwendet wird, das oben im Thema Beispiel für ein erweitertes Suchformular angezeigt wird.

Siehe [Beispiel für ein erweitertes Suchformular](#reference_82E1051918744EBA88A01E9E6AE42C4A).

Wenn Sie diesen Code verwenden, denken Sie daran, den `sp_a` -Wert von `sp99999999` durch Ihre tatsächliche Kontonummer zu ersetzen.

Um Ihre Kundennummer zu finden, klicken Sie im Produktmenü auf **[!UICONTROL Settings]** > **[!UICONTROL Account Options]** > **[!UICONTROL Account Settings]**.

```
<form method="get" action="https://search.atomz.com/search/"> 
<table cellspacing=0 cellpadding=0 border=0> 
<tr><td colspan=4> 
<b>Search For:</b><br> 
<input size=35 name="sp_q"> 
<!-- The "Search" button --> 
<input type=submit value="Search"> 
<input type=hidden name="sp_a" value="sp99999999"> 
<input type=hidden name="sp_f" value="ISO-8859-1"> 
</td></tr> 
<input type=hidden name="sp_advanced" value=1> 
<!-- Allow "any," "all," or "phrase" --> 
<tr><td valign=top> 
<b>Match: </b> 
</td><td colspan=4> 
<input type=radio name="sp_p" value="any">Any word 
<input type=radio name="sp_p" value="all" checked>All words 
<input type=radio name="sp_p" value="phrase">Exact phrase<br> 
<!-- Checkbox enables sound-alike matching --> 
<input type=hidden name="sp_w_control" value=1> 
<input type=checkbox name="sp_w" value="alike" checked> 
Sound-alike matching 
</td></tr> 
<!-- Date range criteria --> 
<tr><td><b>Dated:</b></td><td colspan=4> 
<input type=radio name="sp_d" value="custom" checked> 
<select name="sp_date_range" size=1> 
<option value=-1 selected>Anytime</option> 
<option value=7>Within the last week</option> 
<option value=14>Within the last 2 weeks</option> 
<option value=30>Within the last 30 days</option> 
<option value=60>Within the last 60 days</option> 
<option value=90>Within the last 90 days</option> 
<option value=180>Within the last 180 days</option> 
<option value=365>Within the last year</option> 
<option value=730>Within the last two years</option> 
</select> 
</td></tr> 
<tr><td></td><td rowspan=2> 
<input type=radio name="sp_d" value=specific> 
</td><td align=right>From:</td><td> 
<select name="sp_start_month" size=1> 
<option value=0 selected></option> 
<option value=1>January</option> 
<option value=2>February</option> 
<option value=3>March</option> 
<option value=4>April</option> 
<option value=5>May</option> 
<option value=6>June</option> 
<option value=7>July</option> 
<option value=8>August</option> 
<option value=9>September</option> 
<option value=10>October</option> 
<option value=11>November</option> 
<option value=12>December</option> 
</select> 
<select name="sp_start_day" size=1> 
<option value=0 selected></option> 
<option value=1>1</option> 
<option value=2>2</option> 
<option value=3>3</option> 
<option value=4>4</option> 
<option value=5>5</option> 
<option value=6>6</option> 
<option value=7>7</option> 
<option value=8>8</option> 
<option value=9>9</option> 
<option value=10>10</option> 
<option value=11>11</option> 
<option value=12>12</option> 
<option value=13>13</option> 
<option value=14>14</option> 
<option value=15>15</option> 
<option value=16>16</option> 
<option value=17>17</option> 
<option value=18>18</option> 
<option value=19>19</option> 
<option value=20>20</option> 
<option value=21>21</option> 
<option value=22>22</option> 
<option value=23>23</option> 
<option value=24>24</option> 
<option value=25>25</option> 
<option value=26>26</option> 
<option value=27>27</option> 
<option value=28>28</option> 
<option value=29>29</option> 
<option value=30>30</option> 
<option value=31>31</option> 
</select> 
<!--comma-->, 
<input size=4 name="sp_start_year"> 
</td></tr> 
<tr><td></td> 
<td align=right>To:</td><td> 
<select name="sp_end_month" size=1> 
<option value=0 selected></option> 
<option value=1>January</option> 
<option value=2>February</option> 
<option value=3>March</option> 
<option value=4>April</option> 
<option value=5>May</option> 
<option value=6>June</option> 
<option value=7>July</option> 
<option value=8>August</option> 
<option value=9>September</option> 
<option value=10>October</option> 
<option value=11>November</option> 
<option value=12>December</option> 
</select> 
<select name="sp_end_day" size=1> 
<option value=0 selected></option> 
<option value=1>1</option> 
<option value=2>2</option> 
<option value=3>3</option> 
<option value=4>4</option> 
<option value=5>5</option> 
<option value=6>6</option> 
<option value=7>7</option> 
<option value=8>8</option> 
<option value=9>9</option> 
<option value=10>10</option> 
<option value=11>11</option> 
<option value=12>12</option> 
<option value=13>13</option> 
<option value=14>14</option> 
<option value=15>15</option> 
<option value=16>16</option> 
<option value=17>17</option> 
<option value=18>18</option> 
<option value=19>19</option> 
<option value=20>20</option> 
<option value=21>21</option> 
<option value=22>22</option> 
<option value=23>23</option> 
<option value=24>24</option> 
<option value=25>25</option> 
<option value=26>26</option> 
<option value=27>27</option> 
<option value=28>28</option> 
<option value=29>29</option> 
<option value=30>30</option> 
<option value=31>31</option> 
</select> 
<!--comma-->, 
<input size=4 name="sp_end_year"> 
</td></tr> 
<!-- List box selects the search field --> 
<tr><td valign=top> 
<b>Within: </b> 
</td><td colspan=4><select name="sp_x" size=1> 
<option value="any" selected>Anywhere</option> 
<option value="title">Title</option> 
<option value="desc">Description</option> 
<option value="keys">Keywords</option> 
<option value="body">Body</option> 
<option value="alt">Alternate text</option> 
<option value="url">URL</option> 
<option value="target">Target</option> 
</select> 
</td></tr> 
<!-- List box selects number of results to show per page --> 
<tr><td valign=top> 
<b>Show: </b> 
</td><td colspan=4><select name="sp_c" size=1> 
<option value=5>5</option> 
<option value=10 selected>10</option> 
<option value=25>25</option> 
<option value=50>50</option> 
<option value=100>100</option> 
</select> results  
<!-- Show or hide summaries in search results --> 
<select name="sp_m" size=1> 
<option value=1 selected>with</option> 
<option value=0>without</option> 
</select> summaries<br> 
</td></tr> 
<!-- Sort results by relevance or by date --> 
<tr><td valign=top> 
<b>Sort by: </b> 
</td><td colspan=4><select name="sp_s" size=1> 
<option value=0 selected>relevance</option> 
<option value=1>date</option> 
</select> 
</td></tr> 
</table> 
</form>
```

## Vorlagencode für erweiterte Suchformulare {#reference_D762C22E754E462DBEECD88D2C3FA579}

Sie können den HTML-Code des erweiterten Suchformulars zu Ihrer Vorlage hinzufügen, sodass die Standardauswahl für jeden Parameter mit der vorherigen Suche übereinstimmt.

Mit anderen Worten: Wenn ein Kunde auf das Optionsfeld **[!UICONTROL Exact phrase]** klickt, können Sie sicherstellen, dass das Optionsfeld bei der Anzeige der Suchergebnisse standardmäßig ausgewählt ist.

Diese Funktion wird erreicht, indem alle &quot;aktivierten&quot;oder &quot;ausgewählten&quot;Operatoren aus den Standard-HTML-Tags entfernt und die folgenden HTML-Tags ersetzt werden:

* `<input>`
* `<select>`
* `<option>`
* `</option>`
* `</select>`

mit den folgenden Vorlagen-Tags:

* `<search-input>`
* `<search-select>`
* `<search-option>`
* `</search-option>`
* `</search-select>`

Verwenden Sie dazu den folgenden Code als `<form>` -Tag in Ihrer Suchvorlage.

```
<!-- Adobe Target results section.--> 
 
<!-- Show heading and logo graphic. --> 
<SEARCH-IF-RESULTS> 
<b>SEARCH RESULTS <SEARCH-LOWER> - <SEARCH-UPPER></b> 
of <SEARCH-TOTAL> total results for <b><SEARCH-QUERY></b><br> 
</SEARCH-IF-RESULTS> 
<SEARCH-IF-NOT-RESULTS> 
<b>SEARCH RESULTS</b> for <b><SEARCH-QUERY></b><br> 
</SEARCH-IF-NOT-RESULTS> 
<SEARCH-LOGO><br> 
 
<!-- Display Results. --> 
<SEARCH-RESULTS LENGTH=160> 
<p><b><SEARCH-LINK><SEARCH-TITLE LENGTH=160></SEARCH-LINK></b><br> 
<SEARCH-IF-SHOW-SUMMARIES> 
<SEARCH-IF-CONTEXT LENGTH=240><SEARCH-CONTEXT><br></SEARCH-IF-CONTEXT> 
<font size="-1"><SEARCH-URL LENGTH=60></font><br> 
</SEARCH-IF-SHOW-SUMMARIES> 
</SEARCH-RESULTS> 
 
<!-- If no results, show a message. --> 
<SEARCH-IF-NOT-RESULTS><p> 
Sorry, no matches were found containing <b><SEARCH-QUERY>.</b> 
</SEARCH-IF-NOT-RESULTS> 
<!-- Show By Relevance, By Date links, Show/Hide Summaries links. --> 
<SEARCH-IF-RESULTS><p> 
<SEARCH-IF-SORT-BY-DATE> 
<b><SEARCH-SORT-BY-SCORE COUNT=10>Sort By Relevance</SEARCH-SORT-BY-SCORE></b> 
</SEARCH-IF-SORT-BY-DATE> 
<SEARCH-IF-SORT-BY-SCORE> 
<b><SEARCH-SORT-BY-DATE COUNT=10>Sort By Date</SEARCH-SORT-BY-DATE></b> 
</SEARCH-IF-SORT-BY-SCORE> 
| <b> 
<SEARCH-IF-SHOW-SUMMARIES> 
<SEARCH-HIDE-SUMMARIES COUNT=20>Hide Summaries</SEARCH-HIDE-SUMMARIES> 
</SEARCH-IF-SHOW-SUMMARIES> 
<SEARCH-IF-HIDE-SUMMARIES> 
<SEARCH-SHOW-SUMMARIES COUNT=10>Show Summaries</SEARCH-SHOW-SUMMARIES> 
</SEARCH-IF-HIDE-SUMMARIES> 
</b><br> 
</SEARCH-IF-RESULTS> 
 
<!-- Display Prev & Next links. --> 
<SEARCH-IF-RESULTS> 
<SEARCH-IF-PREV-COUNT> 
<b><SEARCH-PREV>Prev <SEARCH-PREV-COUNT></SEARCH-PREV></b> 
<SEARCH-IF-NEXT-COUNT> | </SEARCH-IF-NEXT-COUNT> 
</SEARCH-IF-PREV-COUNT> 
<SEARCH-IF-NEXT-COUNT> 
<b><SEARCH-NEXT>Next <SEARCH-NEXT-COUNT></SEARCH-NEXT></b><br> 
</SEARCH-IF-NEXT-COUNT><p> 
</SEARCH-IF-RESULTS> 
 
<!-- Put up the next form. --> 
<form method="get" action="https://search.atomz.com/search/"> 
<SEARCH-IF-NOT-ADVANCED> 
<SEARCH-INPUT-ACCOUNT> 
<SEARCH-INPUT-GALLERY> 
<SEARCH-INPUT-QUERY SIZE=25> 
<SEARCH-INPUT type=hidden name=sp_p> 
<input type=submit value="New Search"> 
<SEARCH-IF-INPUT-COLLECTIONS> 
<br><SEARCH-INPUT-COLLECTIONS> 
</SEARCH-IF-INPUT-COLLECTIONS> 
</SEARCH-IF-NOT-ADVANCED> 
<SEARCH-IF-ADVANCED> 
<table cellspacing=0 cellpadding=0 border=0> 
<tr><td colspan=4> 
<b>Search For:</b><br> 
<SEARCH-INPUT-QUERY SIZE=35> 
 
<!-- The "Search" button --> 
<input type=submit value="New Search"> 
<SEARCH-INPUT-ACCOUNT> 
<SEARCH-INPUT-GALLERY> 
</td></tr> 
<SEARCH-IF-INPUT-COLLECTIONS> 
<!-- Collections --> 
<tr><td> 
<b>In: </b> 
</td><td colspan=4> 
<SEARCH-INPUT-COLLECTIONS> 
</td></tr> 
</SEARCH-IF-INPUT-COLLECTIONS> 
<input type=hidden name="sp_advanced" value=1> 
 
<!-- Allow "any," "all," or "phrase" --> 
<tr><td valign=top> 
<b>Match: </b> 
</td><td colspan=4> 
<SEARCH-INPUT type=radio name="sp_p" value="any">Any word 
<SEARCH-INPUT type=radio name="sp_p" value="all">All words 
<SEARCH-INPUT type=radio name="sp_p" value="phrase">Exact phrase<br> 
<!-- Checkbox enables sound-alike matching --> 
<input type=hidden name="sp_w_control" value=1> 
<SEARCH-INPUT type=checkbox name="sp_w" value="alike">Sound-alike matching 
</td></tr> 
 
<!-- Date range section --> 
<tr> 
<td><b>Dated:</b></td> 
<td colspan=3> 
<SEARCH-INPUT type=radio name="sp_d" value="custom"> 
<SEARCH-SELECT name="sp_date_range" size=1> 
<SEARCH-OPTION value=-1>Anytime</SEARCH-OPTION> 
<SEARCH-OPTION value=7>Within the last week</SEARCH-OPTION> 
<SEARCH-OPTION value=14>Within the last 2 weeks</SEARCH-OPTION> 
<SEARCH-OPTION value=30>Within the last 30 days</SEARCH-OPTION> 
<SEARCH-OPTION value=60>Within the last 60 days</SEARCH-OPTION> 
<SEARCH-OPTION value=90>Within the last 90 days</SEARCH-OPTION> 
<SEARCH-OPTION value=180>Within the last 180 days</SEARCH-OPTION> 
<SEARCH-OPTION value=365>Within the last year</SEARCH-OPTION> 
<SEARCH-OPTION value=730>Within the last two years</SEARCH-OPTION> 
</SEARCH-SELECT> 
</td></tr> 
<tr><td></td><td rowspan=2> 
<SEARCH-INPUT type=radio name="sp_d" value=specific></td> 
<td align=right>From:</td><td> 
<SEARCH-SELECT name="sp_start_month" size=1> 
<SEARCH-OPTION value=0></SEARCH-OPTION> 
<SEARCH-OPTION value=1>January</SEARCH-OPTION> 
<SEARCH-OPTION value=2>February</SEARCH-OPTION> 
<SEARCH-OPTION value=3>March</SEARCH-OPTION> 
<SEARCH-OPTION value=4>April</SEARCH-OPTION> 
<SEARCH-OPTION value=5>May</SEARCH-OPTION> 
<SEARCH-OPTION value=6>June</SEARCH-OPTION> 
<SEARCH-OPTION value=7>July</SEARCH-OPTION> 
<SEARCH-OPTION value=8>August</SEARCH-OPTION> 
<SEARCH-OPTION value=9>September</SEARCH-OPTION> 
<SEARCH-OPTION value=10>October</SEARCH-OPTION> 
<SEARCH-OPTION value=11>November</SEARCH-OPTION> 
<SEARCH-OPTION value=12>December</SEARCH-OPTION> 
</SEARCH-SELECT> 
<SEARCH-SELECT name="sp_start_day" size=1> 
<SEARCH-OPTION value=0></SEARCH-OPTION> 
<SEARCH-OPTION value=1>1</SEARCH-OPTION> 
<SEARCH-OPTION value=2>2</SEARCH-OPTION> 
<SEARCH-OPTION value=3>3</SEARCH-OPTION> 
<SEARCH-OPTION value=4>4</SEARCH-OPTION> 
<SEARCH-OPTION value=5>5</SEARCH-OPTION> 
<SEARCH-OPTION value=6>6</SEARCH-OPTION> 
<SEARCH-OPTION value=7>7</SEARCH-OPTION> 
<SEARCH-OPTION value=8>8</SEARCH-OPTION> 
<SEARCH-OPTION value=9>9</SEARCH-OPTION> 
<SEARCH-OPTION value=10>10</SEARCH-OPTION> 
<SEARCH-OPTION value=11>11</SEARCH-OPTION> 
<SEARCH-OPTION value=12>12</SEARCH-OPTION> 
<SEARCH-OPTION value=13>13</SEARCH-OPTION> 
<SEARCH-OPTION value=14>14</SEARCH-OPTION> 
<SEARCH-OPTION value=15>15</SEARCH-OPTION> 
<SEARCH-OPTION value=16>16</SEARCH-OPTION> 
<SEARCH-OPTION value=17>17</SEARCH-OPTION> 
<SEARCH-OPTION value=18>18</SEARCH-OPTION> 
<SEARCH-OPTION value=19>19</SEARCH-OPTION> 
<SEARCH-OPTION value=20>20</SEARCH-OPTION> 
<SEARCH-OPTION value=21>21</SEARCH-OPTION> 
<SEARCH-OPTION value=22>22</SEARCH-OPTION> 
<SEARCH-OPTION value=23>23</SEARCH-OPTION> 
<SEARCH-OPTION value=24>24</SEARCH-OPTION> 
<SEARCH-OPTION value=25>25</SEARCH-OPTION> 
<SEARCH-OPTION value=26>26</SEARCH-OPTION> 
<SEARCH-OPTION value=27>27</SEARCH-OPTION> 
<SEARCH-OPTION value=28>28</SEARCH-OPTION> 
<SEARCH-OPTION value=29>29</SEARCH-OPTION> 
<SEARCH-OPTION value=30>30</SEARCH-OPTION> 
<SEARCH-OPTION value=31>31</SEARCH-OPTION> 
</SEARCH-SELECT><!--comma-->, 
<SEARCH-INPUT size=4 name="sp_start_year"> 
</td></tr> 
<tr><td></td> 
<td align=right>To:</td><td> 
<SEARCH-SELECT name="sp_end_month" size=1> 
<SEARCH-OPTION value=0></SEARCH-OPTION> 
<SEARCH-OPTION value=1>January</SEARCH-OPTION> 
<SEARCH-OPTION value=2>February</SEARCH-OPTION> 
<SEARCH-OPTION value=3>March</SEARCH-OPTION> 
<SEARCH-OPTION value=4>April</SEARCH-OPTION> 
<SEARCH-OPTION value=5>May</SEARCH-OPTION> 
<SEARCH-OPTION value=6>June</SEARCH-OPTION> 
<SEARCH-OPTION value=7>July</SEARCH-OPTION> 
<SEARCH-OPTION value=8>August</SEARCH-OPTION> 
<SEARCH-OPTION value=9>September</SEARCH-OPTION> 
<SEARCH-OPTION value=10>October</SEARCH-OPTION> 
<SEARCH-OPTION value=11>November</SEARCH-OPTION> 
<SEARCH-OPTION value=12>December</SEARCH-OPTION> 
</SEARCH-SELECT> 
<SEARCH-SELECT name="sp_end_day" size=1> 
<SEARCH-OPTION value=0></SEARCH-OPTION> 
<SEARCH-OPTION value=1>1</SEARCH-OPTION> 
<SEARCH-OPTION value=2>2</SEARCH-OPTION> 
<SEARCH-OPTION value=3>3</SEARCH-OPTION> 
<SEARCH-OPTION value=4>4</SEARCH-OPTION> 
<SEARCH-OPTION value=5>5</SEARCH-OPTION> 
<SEARCH-OPTION value=6>6</SEARCH-OPTION> 
<SEARCH-OPTION value=7>7</SEARCH-OPTION> 
<SEARCH-OPTION value=8>8</SEARCH-OPTION> 
<SEARCH-OPTION value=9>9</SEARCH-OPTION> 
<SEARCH-OPTION value=10>10</SEARCH-OPTION> 
<SEARCH-OPTION value=11>11</SEARCH-OPTION> 
<SEARCH-OPTION value=12>12</SEARCH-OPTION> 
<SEARCH-OPTION value=13>13</SEARCH-OPTION> 
<SEARCH-OPTION value=14>14</SEARCH-OPTION> 
<SEARCH-OPTION value=15>15</SEARCH-OPTION> 
<SEARCH-OPTION value=16>16</SEARCH-OPTION> 
<SEARCH-OPTION value=17>17</SEARCH-OPTION> 
<SEARCH-OPTION value=18>18</SEARCH-OPTION> 
<SEARCH-OPTION value=19>19</SEARCH-OPTION> 
<SEARCH-OPTION value=20>20</SEARCH-OPTION> 
<SEARCH-OPTION value=21>21</SEARCH-OPTION> 
<SEARCH-OPTION value=22>22</SEARCH-OPTION> 
<SEARCH-OPTION value=23>23</SEARCH-OPTION> 
<SEARCH-OPTION value=24>24</SEARCH-OPTION> 
<SEARCH-OPTION value=25>25</SEARCH-OPTION> 
<SEARCH-OPTION value=26>26</SEARCH-OPTION> 
<SEARCH-OPTION value=27>27</SEARCH-OPTION> 
<SEARCH-OPTION value=28>28</SEARCH-OPTION> 
<SEARCH-OPTION value=29>29</SEARCH-OPTION> 
<SEARCH-OPTION value=30>30</SEARCH-OPTION> 
<SEARCH-OPTION value=31>31</SEARCH-OPTION> 
</SEARCH-SELECT><!--comma-->, 
<SEARCH-INPUT size=4 name="sp_end_year"> 
</td></tr> 
<!-- List box selects the search field --> 
<tr><td valign=top> 
<b>Within: </b> 
</td><td colspan=4><SEARCH-SELECT name="sp_x" size=1> 
<SEARCH-OPTION value="any">Anywhere</SEARCH-OPTION> 
<SEARCH-OPTION value="title">Title</SEARCH-OPTION> 
<SEARCH-OPTION value="desc">Description</SEARCH-OPTION> 
<SEARCH-OPTION value="keys">Keywords</SEARCH-OPTION> 
<SEARCH-OPTION value="body">Body</SEARCH-OPTION> 
<SEARCH-OPTION value="alt">Alternate text</SEARCH-OPTION> 
<SEARCH-OPTION value="url">URL</SEARCH-OPTION> 
<SEARCH-OPTION value="target">Target</SEARCH-OPTION> 
</SEARCH-SELECT></td></tr> 
<!-- List box selects number of results to show per page --> 
<tr><td valign=top> 
<b>Show:</b> 
</td><td colspan=4><SEARCH-SELECT name="sp_c" size=1> 
<SEARCH-OPTION value=5>5</SEARCH-OPTION> 
<SEARCH-OPTION value=10>10</SEARCH-OPTION> 
<SEARCH-OPTION value=25>25</SEARCH-OPTION> 
<SEARCH-OPTION value=50>50</SEARCH-OPTION> 
<SEARCH-OPTION value=100>100</SEARCH-OPTION> 
</SEARCH-SELECT> results  
<!-- Show or hide summaries in search results --> 
<SEARCH-SELECT name="sp_m" size=1> 
<SEARCH-OPTION value=1>with</SEARCH-OPTION> 
<SEARCH-OPTION value=0>without</SEARCH-OPTION> 
</SEARCH-SELECT> summaries<br></td></tr> 
<!-- Sort results by relevance or by date --> 
<tr><td valign=top> 
<b>Sort by: </b> 
</td><td colspan=4><SEARCH-SELECT name="sp_s" size=1> 
<SEARCH-OPTION value=0>relevance</SEARCH-OPTION> 
<SEARCH-OPTION value=1>date</SEARCH-OPTION> 
</SEARCH-SELECT></td></tr> 
</table> 
</SEARCH-IF-ADVANCED> 
</form>
```
