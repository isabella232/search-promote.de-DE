---
description: Verwenden Sie das Crawling-Menü für Datums- und URL-Masken, Kennwörter, Content-Typen, Verbindungen, Formulardefinitionen und URL-Einstiegspunkte.
solution: Target
subtopic: Crawling
title: Über das Menü "Crawling"
topic-legacy: Settings,Site search and merchandising
uuid: a58c03bf-90f7-4b5b-91ff-988b95c246b0
exl-id: 22dbbc30-bf1c-4d51-8fb0-708115ba844b
source-git-commit: 95bf92df17d7832df72e8d883a22f9063e53a18d
workflow-type: tm+mt
source-wordcount: '11015'
ht-degree: 1%

---

# Über das Menü &quot;Crawling&quot;{#about-the-crawling-menu}

Verwenden Sie das Crawling-Menü für Datums- und URL-Masken, Kennwörter, Content-Typen, Verbindungen, Formulardefinitionen und URL-Einstiegspunkte.

## Über URL-Einstiegspunkte {#concept_5D857E3B5C124E85BC0B5AE77A509573}

Die meisten Websites verfügen über einen primären Einstiegspunkt oder eine primäre Homepage, die/die ein Kunde zunächst besucht. Dieser Haupteinstiegspunkt ist die URL-Adresse, von der aus der Suchroboter das Index-Crawling beginnt. Wenn Ihre Website jedoch mehrere Domänen oder Subdomänen hat oder Teile Ihrer Site nicht vom primären Einstiegspunkt aus verknüpft sind, können Sie URL-Einstiegspunkte verwenden, um weitere Einstiegspunkte hinzuzufügen.

Alle Website-Seiten unter jedem angegebenen URL-Einstiegspunkt werden indiziert. Sie können URL-Einstiegspunkte mit Masken kombinieren, um genau zu steuern, welche Teile einer Website Sie indizieren möchten. Sie müssen Ihren Website-Index neu erstellen, bevor die Auswirkungen der URL-Entrypoints-Einstellungen für Kunden sichtbar sind.

Der Haupteinstiegspunkt ist normalerweise die URL der Website, die Sie indizieren und suchen möchten. Sie konfigurieren diesen Haupteinstiegspunkt in den Kontoeinstellungen.

Siehe [Konfigurieren Ihrer Kontoeinstellungen](../c-about-settings-menu/c-about-account-options-menu.md#task_80A38D0C8E4F453395BD67B81E4B45D9).

Nachdem Sie den Einstiegspunkt der Haupt-URL angegeben haben, können Sie optional zusätzliche Einstiegspunkte angeben, die Sie in der richtigen Reihenfolge durchsuchen möchten. Meistens geben Sie zusätzliche Einstiegspunkte für Webseiten an, die nicht von Seiten unter dem Haupteinstiegspunkt verknüpft sind. Geben Sie zusätzliche Einstiegspunkte an, wenn Ihre Website mehr als eine Domäne umfasst, wie im folgenden Beispiel gezeigt:

`https://www.domain.com/`

`https://www.domain.com/not_linked/but_search_me_too/`

`https://more.domain.com/`

Sie qualifizieren jeden Einstiegspunkt mit einem oder mehreren der folgenden durch Leerzeichen getrennten Suchbegriffe in der unten stehenden Tabelle. Diese Suchbegriffe beeinflussen, wie die Seite indiziert wird.

**Wichtig**: Trennen Sie einen bestimmten Suchbegriff vom Einstiegspunkt und voneinander durch ein Leerzeichen. Ein Komma ist kein gültiges Trennzeichen.

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Suchbegriff </p> </th> 
   <th colname="col2" class="entry"> <p>Beschreibung </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>noindex </p> </td> 
   <td colname="col2"> <p> Wenn Sie den Text nicht auf der Einstiegspunktseite indizieren möchten, aber die Links der Seite befolgen möchten, fügen Sie 
     <code>
       noindex 
     </code> nach dem Einstiegspunkt. </p> <p>Trennen Sie das Schlüsselwort vom Einstiegspunkt durch ein Leerzeichen, wie im folgenden Beispiel gezeigt: </p> <p> <code> https://www.my-additional-domain.com/more_pages/main.html&amp;nbsp;noindex </code> </p> <p>Dieses Keyword entspricht einem Roboter-Meta-Tag mit 
     <code>
       content="noindex" 
     </code>) zwischen dem 
     <code>
       &lt;head&gt; 
     </code>... 
     <code>
       &lt;/head&gt; 
     </code> Tags der Einstiegspunktseite. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>nofollow </p> </td> 
   <td colname="col2"> <p> Wenn Sie den Text auf der Einstiegspunktseite indizieren möchten, aber keinem der Links der Seite folgen möchten, fügen Sie 
     <code>
       nofollow 
     </code> nach dem Einstiegspunkt. </p> <p>Trennen Sie das Schlüsselwort vom Einstiegspunkt durch ein Leerzeichen, wie im folgenden Beispiel gezeigt: </p> <p> <code> https://www.domain.com/not_linked/directory_listing&amp;nbsp;nofollow </code> </p> <p>Dieses Keyword entspricht einem Roboter-Meta-Tag mit 
     <code>
       content="nofollow" 
     </code> zwischen den 
     <code>
       &lt;head&gt; 
     </code>... 
     <code>
       &lt;/head&gt; 
     </code> -Tag einer Einstiegspunktseite. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Formular </p> </td> 
   <td colname="col2"> <p> Wenn der Einstiegspunkt eine Anmeldeseite ist, 
     <code>
       form 
     </code> wird normalerweise verwendet, damit der Suchroboter das Anmeldeformular senden und die entsprechenden Cookies empfangen kann, bevor er die Website durchsucht. Wenn das Keyword "form"verwendet wird, wird die Einstiegspunktseite nicht indiziert und der Suchroboter markiert die Einstiegspunktseite nicht als durchsucht. Verwendung 
     <code>
       nofollow 
     </code> , wenn Sie nicht möchten, dass der Suchroboter den Links der Seite folgt. </p> </td> 
  </tr> 
 </tbody> 
</table>

Siehe auch [Über Content-Typen](../c-about-settings-menu/c-about-crawling-menu.md#concept_6FEA1355C0374500B4C53090C34A8A07).

Siehe auch [Info über Index Connector](../c-about-settings-menu/c-about-crawling-menu.md#concept_CA6921E2FBF641F9B4F60C92B32AFA84).

## Hinzufügen mehrerer URL-Einstiegspunkte, die indiziert werden sollen {#task_2338A47387D74CFDAC4D4EF4A367ED45}

Wenn Ihre Website über mehrere Domänen oder Subdomänen verfügt und diese durchsucht werden sollen, können Sie URL-Einstiegspunkte verwenden, um weitere URLs hinzuzufügen.

Um den Einstiegspunkt Ihrer Website für die Haupt-URL festzulegen, verwenden Sie Kontoeinstellungen.

Siehe [Konfigurieren Ihrer Kontoeinstellungen](../c-about-settings-menu/c-about-account-options-menu.md#task_80A38D0C8E4F453395BD67B81E4B45D9).

**So fügen Sie mehrere URL-Einstiegspunkte hinzu, die indiziert werden sollen**

1. Klicken Sie im Produktmenü auf **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL URL Entrypoints]**.
1. Geben Sie auf der Seite [!DNL URL Entrypoints] im Feld [!DNL Entrypoints] eine URL-Adresse pro Zeile ein.
1. (Optional) Wählen Sie in der Dropdownliste **[!UICONTROL Add Index Connector Configurations]** einen Index-Connector aus, den Sie als Einstiegspunkt für die Indizierung hinzufügen möchten.

   Die Dropdown-Liste ist nur verfügbar, wenn Sie zuvor eine oder mehrere Indexverbindungsdefinitionen hinzugefügt haben.

   ![](assets/url_entrypoints_index_connector.png)

   Siehe [Hinzufügen einer Index Connector-Definition](../c-about-settings-menu/c-about-crawling-menu.md#task_96779B651A654E1F871F55D6DBBC8886).
1. Klicken **[!UICONTROL Save Changes]**.
1. (Optional) Führen Sie einen der folgenden Schritte aus:

   * Klicken Sie auf **[!UICONTROL History]** , um alle Änderungen rückgängig zu machen, die Sie vorgenommen haben.

      Siehe [Verwendung der Option Verlauf](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Klicken **[!UICONTROL Live]**.

      Siehe [Anzeigen von Live-Einstellungen](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Klicken **[!UICONTROL Push Live]**.

      Siehe [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Über URL-Masken {#concept_8039DFC53FF3410AA494D602F71BA164}

URL-Masken sind Muster, die bestimmen, welche von Ihrer Website die Suchroboterindizes dokumentiert oder nicht Indizes.

Stellen Sie sicher, dass Sie Ihren Site-Index neu erstellen, damit die Ergebnisse Ihrer URL-Masken für Ihre Kunden sichtbar sind.

Siehe [Konfigurieren eines inkrementellen Index einer gestaffelten Website](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0).

Im Folgenden finden Sie zwei Arten von URL-Masken, die Sie verwenden können:

* URL-Masken einschließen
* URL-Masken ausschließen

URL-Masken einschließen : Weisen Sie den Suchroboter an, alle Dokumente zu indizieren, die dem Muster der Maske entsprechen.

Ausschließen von URL-Masken weisen den Suchroboter an, übereinstimmende Dokumente zu indizieren.

Während der Suchroboter von einem Link zum Link durch Ihre Website reist, findet er URLs und sucht nach Masken, die mit diesen URLs übereinstimmen. Die erste Übereinstimmung bestimmt, ob diese URL in den Index aufgenommen oder daraus ausgeschlossen werden soll. Wenn keine Maske mit einer aufgefundenen URL übereinstimmt, wird diese URL aus dem Index verworfen.

URL-Masken für Einstiegspunkt-URLs einschließen werden automatisch generiert. Dadurch wird sichergestellt, dass alle auf Ihrer Website gefundenen Dokumente indiziert sind. Es entfernt auch bequem Links, die Ihre Website &quot;verlassen&quot;. Wenn beispielsweise eine indizierte Seite auf https://www.yahoo.com verweist, indiziert der Suchroboter diese URL nicht, da sie nicht mit der Einschlussmaske übereinstimmt, die automatisch von der Einstiegspunkt-URL generiert wird.

Jede URL-Maske, die Sie angeben, muss sich in einer separaten Zeile befinden.

Die Maske kann Folgendes angeben:

* Ein vollständiger Pfad wie in `https://www.mydomain.com/products.html`.
* Ein partieller Pfad wie in `https://www.mydomain.com/products`.
* Eine URL, die Platzhalter wie in `https://www.mydomain.com/*.html` verwendet.
* Ein regulärer Ausdruck (für fortgeschrittene Benutzer).

   Um eine Maske zu einem regulären Ausdruck zu machen, fügen Sie das Keyword `regexp` zwischen dem Maskentyp ( `exclude` oder `include`) und der URL-Maske ein.

Im Folgenden finden Sie ein einfaches Beispiel für eine URL-Maske zum Ausschließen:

```
exclude https://www.mydomain.com/photos
```

Da dieses Beispiel eine Ausschluss-URL-Maske ist, wird jedes Dokument, das dem Muster entspricht, nicht indiziert. Das Muster stimmt alle gefundenen Elemente, sowohl Dateien als auch Ordner, überein, sodass `https://www.mydomain.com/photos.html` und `https://www.mydomain.com/photos/index.html`, die beide mit der Ausschluss-URL übereinstimmen, nicht indiziert werden. Um nur Dateien im Ordner `/photos/` zuzuordnen, muss die URL-Maske einen Schrägstrich wie im folgenden Beispiel enthalten:

```
exclude https://www.mydomain.com/photos/
```

Im folgenden Beispiel für Ausschlussmasken wird eine Platzhalter verwendet. Er weist den Suchroboter an, Dateien mit der Erweiterung &quot;.pdf&quot;zu übersehen. Der Suchroboter fügt diese Dateien nicht zu Ihrem Index hinzu.

```
exclude *.pdf
```

Eine einfache Einschließen-URL-Maske ist:

```
include https://www.mydomain.com/news/
```

Es werden nur Dokumente indiziert, die über eine Reihe von Links von einem URL-Einstiegspunkt aus verknüpft sind oder die als URL-Einstiegspunkt selbst verwendet werden. Die bloße Auflistung der URL eines Dokuments als Einschluss-URL-Maske indiziert kein nicht verknüpftes Dokument. Um Ihrem Index nicht verknüpfte Dokumente hinzuzufügen, können Sie die Funktion URL-Einstiegspunkte verwenden.

Siehe [Über URL-Endpunkte](../c-about-settings-menu/c-about-crawling-menu.md#concept_5D857E3B5C124E85BC0B5AE77A509573).

Masken einschließen und ausschließen können zusammenarbeiten. Sie können einen großen Teil Ihrer Website aus der Indizierung ausschließen, indem Sie eine URL-Maske zum Ausschließen erstellen, jedoch eine oder mehrere der ausgeschlossenen Seiten mit einer URL-Maske zum Einschließen einschließen. Angenommen, Ihre Einstiegspunkt-URL lautet wie folgt:

```
https://www.mydomain.com/photos/
```

Der Suchroboter durchsucht und indiziert alle Seiten unter `/photos/summer/`, `/photos/spring/` und `/photos/fall/` (vorausgesetzt, es gibt Links zu mindestens einer Seite in jedem Verzeichnis aus dem Ordner `photos` ). Dieses Verhalten tritt auf, weil die Link-Pfade es dem Suchroboter ermöglichen, die Dokumente in den Ordnern `/summer/`, `/spring/` und `/fall/` zu finden, und die Ordner-URLs mit der Include-Maske übereinstimmen, die automatisch von der Einstiegspunkt-URL generiert wird.

Sie können alle Seiten im Ordner `/fall/` mit einer Ausschluss-URL-Maske ausschließen, wie im folgenden Beispiel gezeigt:

```
exclude https://www.mydomain.com/photos/fall/
```

Oder fügen Sie selektiv nur `/photos/fall/redleaves4.html` als Teil des Index mit der folgenden URL-Maske hinzu:

```
include https://www.mydomain.com/photos/fall/redleaves4.html
```

Damit die beiden oben genannten Maskenbeispiele wie gewünscht funktionieren, wird zuerst die Einschlussmaske aufgelistet, wie im folgenden Beispiel:

```
include https://www.mydomain.com/photos/fall/redleaves4.html 
exclude https://www.mydomain.com/photos/fall/
```

Da der Suchroboter den Anweisungen in der Reihenfolge folgt, in der sie aufgelistet sind, schließt der Suchroboter zunächst `/photos/fall/redleaves4.html` ein und schließt dann die restlichen Dateien im Ordner `/fall` aus.

Wenn die Anweisungen in umgekehrter Weise wie in der folgenden angegeben sind:

```
exclude https://www.mydomain.com/photos/fall/ 
include https://www.mydomain.com/photos/fall/redleaves4.html
```

Dann ist `/photos/fall/redleaves4.html` nicht enthalten, auch wenn die Maske angibt, dass sie eingeschlossen ist.

Eine URL-Maske, die zuerst angezeigt wird, hat immer Vorrang vor einer URL-Maske, die später in den Maskeneinstellungen angezeigt wird. Wenn der Suchroboter außerdem auf eine Seite trifft, die mit einer Einschluss-URL-Maske und einer Ausschluss-URL-Maske übereinstimmt, hat die zuerst aufgeführte Maske immer Vorrang.

Siehe [Konfigurieren eines inkrementellen Index einer gestaffelten Website](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0).

## Über die Verwendung von Keywords mit URL-Masken {#section_7609A7A6D79B482ABCA8900886541AAB}

Sie können jede Einschlussmaske mit einem oder mehreren durch Leerzeichen getrennten Keywords qualifizieren, die sich auf die Indexierung der übereinstimmenden Seiten auswirken.

Ein Komma ist nicht als Trennzeichen zwischen der Maske und dem Keyword gültig. Sie können nur Leerzeichen verwenden.

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Suchbegriff </p> </th> 
   <th colname="col2" class="entry"> <p>Beschreibung </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>noindex </p> </td> 
   <td colname="col2"> <p> Wenn Sie den Text nicht auf den Seiten indizieren möchten, die mit der URL-Maske übereinstimmen, aber die entsprechenden Seiten-Links befolgen möchten, fügen Sie 
     <code>
       noindex 
     </code> nach der Include URL mask. Stellen Sie sicher, dass Sie den Suchbegriff von der Maske durch ein Leerzeichen trennen, wie im folgenden Beispiel gezeigt: </p> <p> <code> include&amp;nbsp;*.swf&amp;nbsp;noindex </code> </p> <p>Das obige Beispiel gibt an, dass der Suchroboter allen Links aus Dateien mit der 
     <code>
       .swf 
     </code> -Erweiterung, aber deaktiviert die Indizierung des gesamten Textes, der in diesen Dateien enthalten ist. </p> <p>Die 
     <code>
       noindex 
     </code> Keyword entspricht einem Roboter-Meta-Tag mit 
     <code>
       content="noindex" 
     </code> zwischen den 
     <code>
       &lt;head&gt;...&lt;/head&gt; 
     </code> Tags übereinstimmender Seiten. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>nofollow </p> </td> 
   <td colname="col2"> <p> Wenn Sie den Text auf den Seiten indizieren möchten, die mit der URL-Maske übereinstimmen, aber nicht den Links der übereinstimmenden Seite folgen möchten, fügen Sie 
     <code>
       nofollow 
     </code> nach der Include URL mask. Stellen Sie sicher, dass Sie den Suchbegriff von der Maske durch ein Leerzeichen trennen, wie im folgenden Beispiel gezeigt: </p> <p> <code> include&amp;nbsp;https://www.mydomain.com/photos&amp;nbsp;nofollow </code> </p> <p>Die 
     <code>
       nofollow 
     </code> Keyword entspricht einem Roboter-Meta-Tag mit 
     <code>
       content="nofollow" 
     </code> zwischen den 
     <code>
       &lt;head&gt;...&lt;/head&gt; 
     </code> Tags übereinstimmender Seiten. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>regexp </p> </td> 
   <td colname="col2"> <p>Wird sowohl für Einschluss- als auch für Ausschlussmasken verwendet. </p> <p>Jede URL-Maske mit vorangestelltem 
     <code>
       regexp 
     </code> wird als regulärer Ausdruck behandelt. Wenn der Suchroboter auf Dokumente trifft, die mit einer URL-Maske für reguläre Ausdrücke übereinstimmen, werden diese Dokumente nicht indiziert. Wenn der Suchroboter auf Dokumente trifft, die mit einer URL-Maske für reguläre Ausdrücke übereinstimmen, werden diese Dokumente indiziert. Angenommen, Sie haben die folgende URL-Maske: </p> <p> <code> exclude&amp;nbsp;regexp&amp;nbsp;^.*/products/.*\.html$ </code> </p> <p>Der Suchroboter schließt übereinstimmende Dateien wie 
     <code>
       https://www.mydomain.com/products/page1.html 
     </code> </p> <p>Wenn Sie die folgende URL-Maske für reguläre Ausdrücke ausschließen hatten: </p> <p> <code> exclude&amp;nbsp;regexp&amp;nbsp;^.*\?..*$ </code> </p> <p>Der Suchroboter darf keine URL mit einem CGI-Parameter wie 
     <code>
       https://www.mydomain.com/cgi/prog/?arg1=val1&amp;arg2=val2 
     </code>. </p> <p>Wenn Sie über die folgende URL-Maske für reguläre Ausdrücke verfügen: </p> <p> <code> include&amp;nbsp;regexp&amp;nbsp;^.*\.swf$&amp;nbsp;noindex </code> </p> <p>Der Suchroboter folgt allen Links aus Dateien mit der Erweiterung ".swf". Die 
     <code>
       noindex 
     </code> -Keyword gibt auch an, dass der Text von übereinstimmenden Dateien nicht indiziert ist. </p> <p>Siehe <a href="../c-appendices/r-regular-expressions.md#reference_B5BA7D61D82E4109A01D2A2D964E3A6A" type="reference" format="dita" scope="local"> Reguläre Ausdrücke </a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Hinzufügen von URL-Masken zum Index oder nicht zum Indexieren von Teilen Ihrer Website {#task_E1AFC17C746048B8843013D979E082C1}

Sie können [!DNL URL Masks] verwenden, um festzulegen, welche Teile Ihrer Website durchsucht und indiziert werden sollen oder nicht.

Verwenden Sie das Feld &quot;URL-Masken testen&quot;, um zu testen, ob ein Dokument nach dem Index enthalten ist oder nicht.

Stellen Sie sicher, dass Sie Ihren Site-Index neu erstellen, damit die Ergebnisse Ihrer URL-Masken für Ihre Kunden sichtbar sind.

Siehe [Konfigurieren eines inkrementellen Index einer gestaffelten Website](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0).

**So fügen Sie URL-Masken hinzu, um Teile Ihrer Website zu indizieren oder nicht zu indizieren**

1. Klicken Sie im Produktmenü auf **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL URL Masks]**.
1. (Optional) Geben Sie auf der Seite [!DNL URL Masks] im Feld **[!UICONTROL Test URL Masks]** eine Test-URL-Maske von Ihrer Website ein und klicken Sie dann auf **[!UICONTROL Test]**.
1. Geben Sie im Feld [!DNL URL Masks] `include` ein (um eine Website hinzuzufügen, die durchsucht und indiziert werden soll) oder geben Sie `exclude` ein (um zu verhindern, dass eine Website durchsucht und indiziert wird), gefolgt von der Adresse der URL-Maske.

   Geben Sie eine URL-Maskenadresse pro Zeile ein. Beispiel:

   ```
   include https://www.mycompany.com/summer 
   include https://www.mycompany.com/spring 
   exclude regexp .*\.xml 
   exclude https://www.mycompany.com/fall
   ```

1. Klicken **[!UICONTROL Save Changes]**.
1. (Optional) Führen Sie einen der folgenden Schritte aus:

   * Klicken Sie auf **[!UICONTROL History]** , um alle Änderungen rückgängig zu machen, die Sie vorgenommen haben.

      Siehe [Verwendung der Option Verlauf](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Klicken **[!UICONTROL Live]**.

      Siehe [Anzeigen von Live-Einstellungen](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Klicken **[!UICONTROL Push Live]**.

      Siehe [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Über Datumsmasken {#concept_F4F1F58A646F4A86B8650EC46FDCEF66}

Sie können Datumsmasken verwenden, um Dateien basierend auf dem Alter der Datei aus Ihren Suchergebnissen ein- oder auszuschließen.

Stellen Sie sicher, dass Sie Ihren Site-Index neu erstellen, damit die Ergebnisse Ihrer URL-Masken für Ihre Kunden sichtbar sind.

Siehe [Konfigurieren eines inkrementellen Index einer gestaffelten Website](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0).

Im Folgenden finden Sie zwei Arten von Datumsmasken, die Sie verwenden können:

* Datumsmasken einschließen (&quot;include-days&quot;und &quot;include-date&quot;)

   Schließen Sie Datumsmasken für Indexdateien ein, die am oder vor dem angegebenen Datum datiert sind.
* Ausschließen von Datumsmasken (&quot;exclude-days&quot;und &quot;exclude-date&quot;)

   Schließen Sie Datumsmasken für Indexdateien aus, die am oder vor dem angegebenen Datum datiert sind.

Standardmäßig wird das Dateidatum anhand von Meta-Tag-Informationen bestimmt. Wenn kein Meta-Tag gefunden wird, wird das Datum einer Datei aus dem HTTP-Header bestimmt, der vom Server empfangen wird, wenn der Suchroboter eine Datei herunterlädt.

Jede von Ihnen angegebene Datumsmaske muss sich in einer separaten Zeile befinden.

Die Maske kann Folgendes angeben:

* Ein vollständiger Pfad wie in `https://www.mydomain.com/products.html`
* Ein partieller Pfad wie in `https://www.mydomain.com/products`
* Eine URL, die Platzhalter `https://www.mydomain.com/*.html` verwendet
* Ein regulärer Ausdruck. Um eine Maske zu einem regulären Ausdruck zu machen, fügen Sie das Keyword `regexp` vor der URL ein.

Datumsmasken können sowohl ein- als auch ausgeblendet werden und auf eine der beiden folgenden Arten ein Datum angeben. Die Masken werden nur angewendet, wenn die übereinstimmenden Dateien am oder vor dem angegebenen Datum erstellt wurden:

1. Anzahl Tage. Nehmen wir beispielsweise an, die Datumsmaske lautet wie folgt:

   ```
   exclude-days 30 https://www.mydomain.com/docs/archive/)
   ```

   Die Anzahl der angegebenen Tage wird zurückgezählt. Wenn die Datei am oder vor dem Datum datiert ist, an dem sie angekommen ist, wird die Maske angewendet.

1. Ein aktuelles Datum im Format JJJJ-MM-TT. Nehmen wir beispielsweise an, die Datumsmaske lautet wie folgt:

   ```
   include-date 2011-02-15 https://www.mydomain.com/docs/archive/)
   ```

   Wenn das übereinstimmende Dokument am oder vor dem angegebenen Datum datiert ist, wird die Datumsmaske angewendet.

Im Folgenden finden Sie ein einfaches Beispiel für die Ausschlussdatumsmaske:

```
exclude-days 90 https://www.mydomain.com/docs/archive
```

Da es sich um eine Ausschlussdatumsmaske handelt, wird jede Datei, die dem Muster entspricht, nicht indiziert und ist mindestens 90 Tage alt. Wenn Sie ein Dokument ausschließen, wird kein Text indiziert und von dieser Datei werden keine Links gefolgt. Die Datei wird effektiv ignoriert. In diesem Beispiel stimmen möglicherweise beide Dateien und Ordner mit dem angegebenen URL-Muster überein. Beachten Sie, dass sowohl `https://www.mydomain.com/docs/archive.html` als auch `https://www.mydomain.com/docs/archive/index.html` mit dem Muster übereinstimmen und nicht indiziert werden, wenn sie 90 Tage alt oder älter sind. Um nur Dateien im Ordner `/docs/archive/` zuzuordnen, muss die Datumsmaske einen Schrägstrich wie folgt enthalten:

```
exclude-days 90 https://www.mydomain.com/docs/archive/
```

Datumsmasken können auch mit Platzhaltern verwendet werden. Die folgende Ausschlussmaske weist den Suchroboter an, Dateien mit der Erweiterung &quot;.pdf&quot;, die am oder vor dem 15. Mai 2011 datiert sind, zu übersehen. Der Suchroboter fügt Ihrem Index keine übereinstimmenden Dateien hinzu.

```
exclude-date 2011-02-15 *.pdf
```

Die Datumsmaske einschließen sieht ähnlich aus. Nur übereinstimmende Dateien werden zum Index hinzugefügt. Im folgenden Beispiel für die einbezogene Datumsmaske wird der Suchroboter angewiesen, den Text aus allen Dateien zu indizieren, die im Bereich `/docs/archive/manual/` der Website null Tage alt oder älter sind.

```
include-days 0 https://www.mydomain.com/docs/archive/manual/
```

Masken einschließen und ausschließen können zusammenarbeiten. Sie können beispielsweise einen großen Teil Ihrer Website von der Indizierung ausschließen, indem Sie eine Ausschlussdatumsmaske erstellen, jedoch eine oder mehrere der ausgeschlossenen Seiten mit einer Einschließen-URL-Maske einschließen. Wenn Ihre Einstiegspunkt-URL die folgende ist:

```
https://www.mydomain.com/archive/
```

Der Suchroboter durchsucht und indiziert alle Seiten unter `/archive/summer/`, `/archive/spring/` und `/archive/fall/` (vorausgesetzt, es gibt Links zu mindestens einer Seite in jedem Ordner aus dem Ordner `archive` ). Dieses Verhalten tritt auf, weil die Link-Pfade es dem Suchroboter ermöglichen, die Dateien in den Ordnern `/summer/`, `/spring/` und `/fall/` zu &quot;finden&quot;, und die Ordner-URLs mit der Include-Maske übereinstimmen, die automatisch von der Einstiegspunkt-URL generiert wird.

Siehe [Über URL-Endpunkte](../c-about-settings-menu/c-about-crawling-menu.md#concept_5D857E3B5C124E85BC0B5AE77A509573).

Siehe [Konfigurieren Ihrer Kontoeinstellungen](../c-about-settings-menu/c-about-account-options-menu.md#task_80A38D0C8E4F453395BD67B81E4B45D9).

Sie können alle Seiten, die älter als 90 Tage sind, im Ordner `/fall/` mit einer Ausschlussdatumsmaske ausschließen, wie im Folgenden gezeigt:

```
exclude-days 90 https://www.mydomain.com/archive/fall/
```

Sie können nur `/archive/fall/index.html` (unabhängig davon, wie alt sie ist - alle Dateien von 0 Tagen oder älter werden abgeglichen) als Teil des Index mit der folgenden Datumsmaske einfügen:

```
include-days 0 https://www.mydomain.com/archive/fall/index.html
```

Damit die beiden oben genannten Maskenbeispiele wie gewünscht funktionieren, müssen Sie die Einschlussmaske wie folgt zuerst auflisten:

```
include-days 0 https://www.mydomain.com/archive/fall/index.html 
exclude-days 90 https://www.mydomain.com/archive/fall/
```

Da der Suchroboter den Anweisungen in der angegebenen Reihenfolge folgt, schließt der Suchroboter zunächst `/archive/fall/index.html` ein und schließt dann die restlichen Dateien im Ordner `/fall` aus.

Wenn die Anweisungen in umgekehrter Weise wie in der folgenden angegeben sind:

```
exclude-days 90 https://www.mydomain.com/archive/fall/ 
include-days 0 https://www.mydomain.com/archive/fall/index.html 
```

Dann ist `/archive/fall/index.html` nicht enthalten, obwohl die Maske angibt, dass es sein sollte. Eine zuerst angezeigte Datumsmaske hat immer Vorrang vor einer Datumsmaske, die später in den Maskeneinstellungen angezeigt wird. Wenn der Suchroboter außerdem auf eine Seite trifft, die sowohl mit einer Include-Datumsmaske als auch mit einer Ausschlussdatumsmaske übereinstimmt, hat die zuerst aufgeführte Maske immer Vorrang.

Siehe [Konfigurieren eines inkrementellen Index einer gestaffelten Website](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0).

## Über die Verwendung von Keywords mit Datumsmasken {#section_CCBB3E3FDBDE4725B2B571FD6594470C}

Sie können jede Einschlussmaske mit einem oder mehreren durch Leerzeichen getrennten Keywords qualifizieren, die sich auf die Indexierung der übereinstimmenden Seiten auswirken.

Ein Komma ist nicht als Trennzeichen zwischen der Maske und dem Keyword gültig. Sie können nur Leerzeichen verwenden.

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Suchbegriff </p> </th> 
   <th colname="col2" class="entry"> <p>Beschreibung </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>noindex </p> </td> 
   <td colname="col2"> <p> Wenn Sie den Text nicht auf den Seiten indizieren möchten, die am oder vor dem Datum datiert sind, das durch die Einschlussmaske angegeben wird, fügen Sie 
     <code>
       noindex 
     </code> nach der Datumsmaske einschließen wie in der folgenden Abbildung dargestellt: </p> <p> <code> include-days&amp;nbsp;10&amp;nbsp;*.swf&amp;nbsp;noindex </code> </p> <p>Achten Sie darauf, den Suchbegriff von der Maske durch ein Leerzeichen zu trennen. </p> <p>Das obige Beispiel gibt an, dass der Suchroboter allen Links aus Dateien mit der Erweiterung ".swf" folgt, die mindestens 10 Tage alt sind. Sie deaktiviert jedoch die Indizierung des gesamten Textes, der in diesen Dateien enthalten ist. </p> <p>Sie sollten sicherstellen, dass der Text für ältere Dateien nicht indiziert ist, aber dennoch alle Links aus diesen Dateien befolgen. Verwenden Sie in solchen Fällen eine Datumsmaske mit dem Keyword "noindex", anstatt eine Datumsmaske zum Ausschließen zu verwenden. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>nofollow </p> </td> 
   <td colname="col2"> <p> Wenn Sie den Text auf den Seiten indizieren möchten, die am oder vor dem Datum datiert sind, das von der Include-Maske angegeben wird, Sie jedoch nicht den Links der übereinstimmenden Seite folgen möchten, fügen Sie 
     <code>
       nofollow 
     </code> nach der Datumsmaske einschließen wie in der folgenden Abbildung dargestellt: </p> <p> <code> include-days&amp;nbsp;8&amp;nbsp;https://www.mydomain.com/photos&amp;nbsp;nofollow </code> </p> <p>Achten Sie darauf, den Suchbegriff von der Maske durch ein Leerzeichen zu trennen. </p> <p>Die 
     <code>
       nofollow 
     </code> Keyword entspricht einem Roboter-Meta-Tag mit 
     <code>
       content="nofollow" 
     </code> zwischen den 
     <code>
       &lt;head&gt;...&lt;/head&gt; 
     </code> Tag der übereinstimmenden Seiten. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>server-date </p> </td> 
   <td colname="col2"> <p>Wird sowohl für Einschluss- als auch für Ausschlussmasken verwendet. </p> <p>Der Suchroboter lädt im Allgemeinen jede Datei herunter und analysiert sie, bevor er die Datumsmasken überprüft. Dieses Verhalten tritt auf, da einige Dateitypen ein Datum in der Datei selbst angeben können. Beispielsweise kann ein HTML-Dokument Meta-Tags enthalten, die das Datum der Datei festlegen. </p> <p>Wenn Sie viele Dateien anhand ihres Datums ausschließen und Ihre Server nicht unnötig belasten möchten, können Sie 
     <code>
       server-date 
     </code> nach der URL in der Datumsmaske. </p> <p>Dieser Suchbegriff weist den Suchroboter an, anstelle der Analyse jeder Datei das Datum der Datei zu verwenden, die von Ihrem Server zurückgegeben wird. Die folgende Ausschlussdatumsmaske ignoriert beispielsweise Seiten, die mit der URL übereinstimmen, wenn die Dokumente 90 Tage oder älter sind. Dies hängt vom Datum ab, das vom Server in den HTTP-Headern zurückgegeben wird: </p> <p> <code> exclude-days&amp;nbsp;90&amp;nbsp;https://www.mydomain.com/docs/archive&amp;nbsp;server-date </code> </p> <p> Wenn das vom Server zurückgegebene Datum 90 Tage oder länger vergangen ist, 
     <code>
       server-date 
     </code> gibt an, dass die ausgeschlossenen Dokumente nicht von Ihrem Server heruntergeladen werden. Dies bedeutet eine schnellere Indizierungszeit für Ihre Dokumente und eine geringere Belastung Ihrer Server. Wenn 
     <code>
       server-date 
     </code> nicht angegeben ist, ignoriert der Suchroboter das Datum, das vom Server in den HTTP-Headern zurückgegeben wird. Stattdessen wird jede Datei heruntergeladen und überprüft, um festzustellen, ob das Datum angegeben ist. Wenn in der Datei kein Datum angegeben ist, verwendet der Suchroboter das vom Server zurückgegebene Datum. </p> <p>Sie sollten 
     <code>
       server-date 
     </code> , wenn Ihre Dateien Befehle enthalten, die das Serverdatum überschreiben. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>regexp </p> </td> 
   <td colname="col2"> <p> Verwendung für Masken zum Ein- und Ausschließen. </p> <p>Jede Datumsmaske, der 
     <code>
       regexp 
     </code> wird als regulärer Ausdruck behandelt. </p> <p>Wenn der Suchroboter auf Dateien trifft, die mit einer Datumsmaske für reguläre Ausdrücke übereinstimmen, werden diese Dateien nicht indiziert. </p> <p>Wenn der Suchroboter auf Dateien trifft, die mit einer Datumsmaske für reguläre Ausdrücke übereinstimmen, werden diese Dokumente indiziert. </p> <p>Angenommen, Sie haben die folgende Datumsmaske: </p> <p> <code> exclude-days&amp;nbsp;180&amp;nbsp;regexp&amp;nbsp;.*archive.* </code> </p> <p>Die Maske weist den Suchroboter an, übereinstimmende Dateien auszuschließen, die mindestens 180 Tage alt sind. Das heißt, Dateien, die das Wort "archivieren"in ihrer URL enthalten. </p> <p>Siehe <a href="../c-appendices/r-regular-expressions.md#reference_B5BA7D61D82E4109A01D2A2D964E3A6A" type="reference" format="dita" scope="local"> Reguläre Ausdrücke </a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Hinzufügen von Datumsmasken zum Index oder nicht zum Indexieren von Teilen Ihrer Website {#task_0010543C55F648D2B5DEFEFAD60FAF04}

Sie können Datumsmasken verwenden, um Dateien basierend auf dem Alter der Dateien in Kundensuchergebnissen ein- oder auszuschließen.

Verwenden Sie die Felder **[!UICONTROL Test Date]** und **[!UICONTROL Test URL]** , um zu testen, ob eine Datei nach dem Index enthalten ist oder nicht.

Stellen Sie sicher, dass Sie Ihren Site-Index neu erstellen, damit die Ergebnisse Ihrer URL-Masken für Ihre Kunden sichtbar sind.

Siehe [Konfigurieren eines inkrementellen Index einer gestaffelten Website](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0).

**So fügen Sie Datumsmasken hinzu, um Teile Ihrer Website zu indizieren oder nicht zu indizieren**

1. Klicken Sie im Produktmenü auf **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Date Masks]**.
1. (Optional) Geben Sie auf der Seite [!DNL Date Masks] im Feld **[!UICONTROL Test Date]** ein Datum ein, das als JJJJ-MM-TT formatiert ist (z. B. `2011-07-25`). Geben Sie im Feld **[!UICONTROL Test URL]** eine URL-Maske von Ihrer Website ein und klicken Sie auf **[!UICONTROL Test]**.
1. Geben Sie im Feld [!DNL Date Masks] eine Adresse für die Datumsmaske pro Zeile ein.
1. Klicken **[!UICONTROL Save Changes]**.
1. (Optional) Führen Sie einen der folgenden Schritte aus:

   * Klicken Sie auf **[!UICONTROL History]** , um alle Änderungen rückgängig zu machen, die Sie vorgenommen haben.

      Siehe [Verwendung der Option Verlauf](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Klicken **[!UICONTROL Live]**.

      Siehe [Anzeigen von Live-Einstellungen](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Klicken **[!UICONTROL Push Live]**.

      Siehe [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Über Passwörter {#concept_3EDBD731725D46B891F834D4472774DC}

Um auf Teile Ihrer Website zuzugreifen, die mit HTTP Basic Authentication geschützt sind, können Sie ein oder mehrere Passwörter hinzufügen.

Bevor die Auswirkungen der Kennworteinstellungen für Kunden sichtbar sind, müssen Sie Ihren Site-Index neu erstellen.

Siehe [Konfigurieren eines inkrementellen Index einer gestaffelten Website](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0).

Geben Sie auf der Seite [!DNL Passwords] jedes Kennwort in einer einzigen Zeile ein. Das Kennwort besteht aus einer URL oder einem Bereich, einem Benutzernamen und einem Kennwort, wie im folgenden Beispiel gezeigt:

```
https://www.mydomain.com/ myname mypassword
```

Statt einen URL-Pfad zu verwenden, wie oben gezeigt, können Sie auch einen Bereich angeben.

Um den richtigen Bereich zu bestimmen, öffnen Sie eine kennwortgeschützte Webseite mit einem Browser und sehen Sie sich das Dialogfeld &quot;Kennwort für Netzwerk eingeben&quot; an.

![](assets/realms.gif)

Der Bereichsname lautet in diesem Fall &quot;Mein Site-Bereich&quot;.

Wenn Sie den Bereichsnamen oben verwenden, könnte Ihr Kennwort wie folgt aussehen:

```
My Site Realm myusername mypassword
```

Wenn Ihre Website über mehrere Bereiche verfügt, können Sie mehrere Passwörter erstellen, indem Sie einen Benutzernamen und ein Kennwort für jeden Bereich in einer separaten Zeile eingeben, wie im folgenden Beispiel gezeigt:

```
Realm1 name1 password1 
Realm2 name2 password2 
Realm3 name3 password3
```

Sie können Kennwörter, die URLs oder Realms enthalten, miteinander kombinieren, sodass Ihre Kennwortliste wie folgt aussehen kann:

```
Realm1 name1 password1 
https://www.mysite.com/path1/path2 name2 password2 
Realm3 name3 password3 
Realm4 name4 password4 
https://www.mysite.com/path1/path5 name5 password5 
https://www.mysite.com/path6 name6 password6
```

In der obigen Liste wird das erste Kennwort verwendet, das einen Bereich oder eine URL enthält, der bzw. die der Authentifizierungsanforderung des Servers entspricht. Selbst wenn sich die Datei unter `https://www.mysite.com/path1/path2/index.html` in `Realm3` befindet, werden beispielsweise `name2` und `password2` verwendet, da das mit der URL definierte Kennwort über dem mit dem Bereich definierten angezeigt wird.

## Hinzufügen von Passwörtern für den Zugriff auf Bereiche Ihrer Website, die authentifiziert werden müssen {#task_DED19D476FF04B48BB6456D5ECB8628A}

Sie können Passwörter verwenden, um kennwortgeschützte Bereiche Ihrer Website für Crawling- und Indizierungszwecke aufzurufen.

Bevor die Auswirkungen Ihres Passworts für Kunden sichtbar sind, müssen Sie Ihren Site-Index neu erstellen

Siehe [Konfigurieren eines inkrementellen Index einer gestaffelten Website](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0).

**So fügen Sie Kennwörter für den Zugriff auf Bereiche Ihrer Website hinzu, die authentifiziert werden müssen**

1. Klicken Sie im Produktmenü auf **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Passwords]**.
1. Geben Sie auf der Seite [!DNL Passwords] im Feld **[!UICONTROL Passwords]** einen Bereich oder eine URL sowie den zugehörigen Benutzernamen und das Kennwort (durch ein Leerzeichen getrennt) ein.

   Beispiel eines Realm-Kennworts und eines URL-Kennworts in separaten Zeilen:

   ```
   Realm1 name1 password1 
   https://www.mysite.com/path1/path2 name2 password2
   ```

   Fügen Sie nur ein Kennwort pro Zeile hinzu.
1. Klicken **[!UICONTROL Save Changes]**.
1. (Optional) Führen Sie einen der folgenden Schritte aus:

   * Klicken Sie auf **[!UICONTROL History]** , um alle Änderungen rückgängig zu machen, die Sie vorgenommen haben.

      Siehe [Verwendung der Option Verlauf](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Klicken **[!UICONTROL Live]**.

      Siehe [Anzeigen von Live-Einstellungen](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Klicken **[!UICONTROL Push Live]**.

      Siehe [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Über Content-Typen {#concept_6FEA1355C0374500B4C53090C34A8A07}

Sie können [!DNL Content Types] verwenden, um auszuwählen, welche Dateitypen Sie durchsuchen und für dieses Konto indizieren möchten.

Zu den Inhaltstypen, die Sie durchsuchen und indizieren können, gehören PDF-Dokumente, Textdokumente, Adobe Flash-Filme, Dateien aus Microsoft Office-Anwendungen wie Word, Excel und Powerpoint sowie Text in MP3-Dateien. Der in den ausgewählten Inhaltstypen gefundene Text wird zusammen mit dem gesamten anderen Text auf Ihrer Website durchsucht.

Bevor die Auswirkungen der Einstellungen für Content-Typen für Kunden sichtbar sind, müssen Sie Ihren Site-Index neu erstellen.

Siehe [Konfigurieren eines inkrementellen Index einer gestaffelten Website](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0).

## Über die Indizierung von MP3-Musikdateien {#section_AD2E28BEEE3E46629E2B05C34A963673}

Wenn Sie die Option **[!UICONTROL Text in MP3 Music Files]** auf der Seite [!DNL Content Types] auswählen, wird eine MP3-Datei auf zwei Arten durchsucht und indiziert. Die erste und gängigste Methode ist ein Anker-href-Tag in einer HTML-Datei, wie im folgenden Beispiel:

```
<a href="MP3-file-URL"></a>
```

Die zweite Möglichkeit besteht darin, die URL der MP3-Datei als URL-Einstiegspunkt einzugeben.

Siehe [Über URL-Endpunkte](../c-about-settings-menu/c-about-crawling-menu.md#concept_5D857E3B5C124E85BC0B5AE77A509573).

Eine MP3-Datei wird durch den MIME-Typ &quot;audio/mpeg&quot;erkannt.

Beachten Sie, dass MP3-Musikdateien sehr groß sein können, obwohl sie normalerweise nur eine kleine Textmenge enthalten. MP3-Dateien können beispielsweise optional Dinge wie den Albumnamen, den Namen des Künstlers, den Titel des Liedes, das Musikgenre, das Jahr der Veröffentlichung und einen Kommentar speichern. Diese Informationen werden am Ende der Datei im so genannten TAG gespeichert. MP3-Dateien, die TAG-Informationen enthalten, werden wie folgt indiziert:

* Der Titel des Liedes wird wie der Titel einer HTML-Seite behandelt.
* Der Kommentar wird wie eine Beschreibung behandelt, die für eine HTML-Seite definiert ist.
* Das Genre wird wie ein Keyword behandelt, das für eine HTML-Seite definiert ist.
* Der Name des Künstlers, der Albumname und das Jahr der Veröffentlichung werden wie der Text einer HTML-Seite behandelt.

Beachten Sie, dass jede MP3-Datei, die auf Ihrer Website durchsucht und indiziert wird, als eine Seite zählt.

Wenn Ihre Website viele große MP3-Dateien enthält, können Sie die Indizierungsbyte-Grenze für Ihr Konto überschreiten. In diesem Fall können Sie die Auswahl von **[!UICONTROL Text in MP3 Music Files]** auf der Seite [!DNL Content Types] aufheben, um die Indizierung aller MP3-Dateien auf Ihrer Website zu verhindern.

Wenn Sie nur die Indizierung bestimmter MP3-Dateien auf Ihrer Website verhindern möchten, können Sie einen der folgenden Schritte ausführen:

* Umschließen Sie die Anker-Tags, die mit den MP3-Dateien verknüpft sind, mit den Tags `<nofollow>` und `</nofollow>` . Der Suchroboter folgt nicht den Verknüpfungen zwischen diesen Tags.

* Fügen Sie die URLs der MP3-Dateien als Ausschlussmasken hinzu.

   Siehe [Über URL-Masken](../c-about-settings-menu/c-about-crawling-menu.md#concept_8039DFC53FF3410AA494D602F71BA164).

## Auswahl der zu durchsuchenden und zu indizierenden Inhaltstypen {#task_CCAC5C67C8BF4AB7B79D34A1495D5EE8}

Sie können [!DNL Content Types] verwenden, um auszuwählen, welche Dateitypen Sie durchsuchen und für dieses Konto indizieren möchten.

Zu den Inhaltstypen, die Sie durchsuchen und indizieren können, gehören PDF-Dokumente, Textdokumente, Adobe Flash-Filme, Dateien aus Microsoft Office-Anwendungen wie Word, Excel und Powerpoint sowie Text in MP3-Dateien. Der in den ausgewählten Inhaltstypen gefundene Text wird zusammen mit dem gesamten anderen Text auf Ihrer Website durchsucht.

Bevor die Auswirkungen der Einstellungen für Content-Typen für Kunden sichtbar sind, müssen Sie Ihren Site-Index neu erstellen.

Siehe [Konfigurieren eines inkrementellen Index einer gestaffelten Website](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0).

Um chinesische, japanische oder koreanische MP3-Dateien zu durchsuchen und zu indizieren, führen Sie die folgenden Schritte aus. Geben Sie dann in **[!UICONTROL Settings]** > **[!UICONTROL Metadata]** > **[!UICONTROL Injections]** den Zeichensatz an, der zum Kodieren der MP3-Dateien verwendet wird.

Siehe [Über Injektionen](../c-about-settings-menu/c-about-metadata-menu.md#concept_DA091920671948A0A893A26B3A2FAAE5).

**So wählen Sie zu durchsuchende und zu indizierende Inhaltstypen aus**

1. Klicken Sie im Produktmenü auf **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Content Types]**.
1. Überprüfen Sie auf der Seite [!DNL Content Types] die Dateitypen, die Sie durchsuchen und auf Ihrer Website indizieren möchten.
1. Klicken **[!UICONTROL Save Changes]**.
1. (Optional) Führen Sie einen der folgenden Schritte aus:

   * Klicken Sie auf **[!UICONTROL History]** , um alle Änderungen rückgängig zu machen, die Sie vorgenommen haben.

      Siehe [Verwendung der Option Verlauf](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Klicken **[!UICONTROL Live]**.

      Siehe [Anzeigen von Live-Einstellungen](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Klicken **[!UICONTROL Push Live]**.

      Siehe [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Über Verbindungen {#concept_E2F3B7E7521147479E5948A94BB3A40B}

Sie können Verbindungen verwenden, um bis zu zehn HTTP-Verbindungen hinzuzufügen, die der Suchroboter zum Indizieren Ihrer Website verwendet.

Eine Erhöhung der Anzahl der Verbindungen kann die Zeit, die zum Abschließen eines Crawls und Index benötigt wird, erheblich verringern. Beachten Sie jedoch, dass jede zusätzliche Verbindung die Last auf Ihrem Server erhöht.

## Hinzufügen von Verbindungen zur Beschleunigung der Indizierung {#task_3E9B83E43C1842A19066355A15C4A6FB}

Sie können die Zeit für die Indizierung Ihrer Website verkürzen, indem Sie Verbindungen verwenden, um die Anzahl der gleichzeitigen HTTP-Verbindungen zu erhöhen, die der Crawler verwendet. Sie können bis zu zehn Verbindungen hinzufügen.

Beachten Sie, dass jede zusätzliche Verbindung die auf Ihrem Server platzierte Last erhöht.

**So fügen Sie Verbindungen hinzu, um die Indizierungsgeschwindigkeit zu erhöhen**

1. Klicken Sie im Produktmenü auf **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Connections]**.
1. Geben Sie auf der Seite [!DNL Parallel Indexing Connections] im Feld **[!UICONTROL Number of Connections]** die Anzahl der Verbindungen (1-10) ein, die hinzugefügt werden sollen.
1. Klicken **[!UICONTROL Save Changes]**.
1. (Optional) Führen Sie einen der folgenden Schritte aus:

   * Klicken Sie auf **[!UICONTROL History]** , um alle Änderungen rückgängig zu machen, die Sie vorgenommen haben.

      Siehe [Verwendung der Option Verlauf](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Klicken **[!UICONTROL Live]**.

      Siehe [Anzeigen von Live-Einstellungen](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Klicken **[!UICONTROL Push Live]**.

      Siehe [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Über die Formularübermittlung {#concept_CADD5D7CF373497DAA6F8564D7BC8502}

Sie können die Formularübermittlung verwenden, um Formulare auf Ihrer Website zu erkennen und zu verarbeiten.

Während des Crawling und der Indizierung Ihrer Website wird jedes aufgefundene Formular mit den von Ihnen hinzugefügten Formulardefinitionen verglichen. Wenn ein Formular mit einer Formulardefinition übereinstimmt, wird das Formular zur Indizierung gesendet. Wenn ein Formular mit mehreren Definitionen übereinstimmt, wird das Formular für jede übereinstimmende Definition einmal gesendet.

## Hinzufügen von Formulardefinitionen für die Indizierung von Formularen auf Ihrer Website {#task_62FBCE9E6DBE4BDA8D1249233ADFC00F}

Sie können [!DNL Form Submission] verwenden, um Formulare zu verarbeiten, die auf Ihrer Website zu Indizierungszwecken erkannt werden.

Stellen Sie sicher, dass Sie Ihren Site-Index neu erstellen, damit die Ergebnisse Ihrer Änderungen für Ihre Kunden sichtbar sind.

Siehe [Konfigurieren eines inkrementellen Index einer gestaffelten Website](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0).

**So fügen Sie Formulardefinitionen für die Indizierung von Formularen auf Ihrer Website hinzu**

1. Klicken Sie im Produktmenü auf **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Form Submission]**.
1. Klicken Sie auf der Seite [!DNL Form Submission] auf **[!UICONTROL Add New Form]**.
1. Legen Sie auf der Seite [!DNL Add Form Definition] die Optionen [!DNL Form Recognition] und [!DNL Form Submission] fest.

   Die fünf Optionen im Abschnitt [!DNL Form Recognition] auf der Seite [!DNL Form Definition] werden verwendet, um Formulare auf Ihren Webseiten zu identifizieren, die verarbeitet werden können.

   Die drei Optionen im Abschnitt [!DNL Form Submission] werden verwendet, um die Parameter und Werte anzugeben, die mit einem Formular an Ihren Webserver gesendet werden.

   Geben Sie einen Erkennungs- oder Sendeparameter pro Zeile ein. Jeder Parameter muss einen Namen und einen Wert enthalten.

   <table> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> <p>Option </p> </th> 
      <th colname="col2" class="entry"> <p>Beschreibung </p> </th> 
      </tr> 
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <p> <b>Formularanerkennung</b> </p> </td> 
      <td colname="col2"> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Seiten-URL-Maske </p> </td> 
      <td colname="col2"> <p>Identifizieren Sie die Webseiten, die das Formular enthalten. Um ein Formular zu identifizieren, das auf einer einzelnen Seite erscheint, geben Sie die URL für diese Seite wie im folgenden Beispiel ein: </p> <p> <code> https://www.mydomain.com/login.html </code> </p> <p>Um Formulare zu identifizieren, die auf mehreren Seiten angezeigt werden, geben Sie eine URL-Maske an, die die Seiten mit Platzhaltern beschreibt. Um Formulare zu identifizieren, die auf einer ASP-Seite unter <code> https://www.mydomain.com/register/ </code> gefunden wurden, geben Sie beispielsweise Folgendes an: </p> <p> <code> https://www.mydomain.com/register/*.asp&amp;nbsp; </code> </p> <p>Sie können auch einen regulären Ausdruck verwenden, um mehrere Seiten zu identifizieren. Geben Sie einfach die 
      <code>
        regexp 
      </code> vor der URL-Maske wie im folgenden Beispiel gezeigt: </p> <p> <code> regexp&amp;nbsp;^https://www\.mydomain\.com/.*/login\.html$ </code> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Action URL Mask </p> </td> 
      <td colname="col2"> <p>Identifiziert das Aktionsattribut des 
      <code>
        &lt;form&gt; 
      </code> -Tag. </p> <p>Wie bei der Seiten-URL-Maske kann die Maske der Aktions-URL in Form einer einzelnen URL, einer URL mit Platzhaltern oder eines regulären Ausdrucks dargestellt werden. </p> <p>Die URL-Maske kann wie folgt aussehen: 
      <ul id="ul_EDFE7688D3DD4C0BBACCE5D4648D8E44"> 
      <li id="li_77550A448D954EF29FF33EE5E8B5E0F5"> Ein vollständiger Pfad wie im folgenden Beispiel: <code> https://www.mydomain.com/products.html </code> </li> 
      <li id="li_F84E25553BBA41419BE153DC0709E011"> Ein partieller Pfad wie im Folgenden gezeigt: <code> https://www.mydomain.com/products </code> </li> 
      <li id="li_8DADA1C8604740FCACBA30B4AAADB2A1"> Eine URL, die Platzhalter wie in der folgenden verwendet: <code> https://www.mydomain.com/*.html </code> </li> 
      <li id="li_1EF637B450654B509AA4B618F7FD3C2B"> Ein regulärer Ausdruck wie im Folgenden: <code> regexp&amp;nbsp^https://www\.mydomain\.com/.*/login\.html$ </code> </li> 
      </ul> </p> <p>Wenn Sie den Text nicht auf Seiten indizieren möchten, die durch eine URL-Maske oder eine Aktion-URL-Maske identifiziert werden, oder wenn Sie nicht möchten, dass Links auf diesen Seiten folgen, können Sie die 
      <code>
        noindex 
      </code> und 
      <code>
        nofollow 
      </code> Suchbegriffe. Sie können diese Suchbegriffe zu Ihren Masken hinzufügen, indem Sie URL-Masken oder Einstiegspunkte verwenden. </p> <p>Siehe <a href="../c-about-settings-menu/c-about-crawling-menu.md#concept_5D857E3B5C124E85BC0B5AE77A509573" type="concept" format="dita" scope="local"> Über URL-Endpunkte </a>. </p> <p>Siehe <a href="../c-about-settings-menu/c-about-crawling-menu.md#concept_8039DFC53FF3410AA494D602F71BA164" type="concept" format="dita" scope="local"> Über URL-Masken </a>. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Formularnamenmaske </p> </td> 
      <td colname="col2"> <p>Identifiziert Formulare, wenn die 
      <code>
        &lt;form&gt; 
      </code> -Tags in Ihren Webseiten enthalten ein Namensattribut. </p> <p>Sie können einen einfachen Namen ( 
      <code>
        login_form 
      </code>), einen Namen mit einem Platzhalter ( 
      <code>
        form* 
      </code>) oder einen regulären Ausdruck ( 
      <code>
        regexp ^.*authorize.*$ 
      </code>). </p> <p>Normalerweise können Sie dieses Feld leer lassen, da Formulare normalerweise kein Namensattribut aufweisen. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Formular-ID-Maske </p> </td> 
      <td colname="col2"> <p>Identifiziert Formulare, wenn die 
      <code>
        &lt;form&gt; 
      </code> -Tags in Ihren Webseiten enthalten ein id -Attribut. </p> <p>Sie können einen einfachen Namen ( 
      <code>
        login_form 
      </code>), einen Namen mit einem Platzhalter ( 
      <code>
        form* 
      </code>) oder einen regulären Ausdruck ( 
      <code>
        regexp ^.*authorize.*$ 
      </code>). </p> <p>Normalerweise können Sie dieses Feld leer lassen, da Formulare normalerweise kein Namensattribut aufweisen. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Parameter </p> </td> 
      <td colname="col2"> <p>Identifizieren Sie Formulare, die einen benannten Parameter oder einen benannten Parameter mit einem bestimmten Wert enthalten oder nicht enthalten. </p> <p>Um beispielsweise ein Formular zu identifizieren, das einen E-Mail-Parameter enthält, der auf rick_brough@mydomain.com, einen Kennwortparameter, aber nicht einen Vorname-Parameter, vordefiniert ist, geben Sie die folgenden Parametereinstellungen an, eine pro Zeile: </p> <p> <code> email=rick_brough@mydomain.com password  not&nbsp;first-name </code> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p> <b>Formularübermittlung</b> </p> </td> 
      <td colname="col2"> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>URL der Aktion überschreiben </p> </td> 
      <td colname="col2"> <p>Geben Sie an, wann sich die Zielgruppe der Formularübermittlung von der im Aktions-Attribut des Formulars angegebenen unterscheidet. </p> <p>Beispielsweise können Sie diese Option verwenden, wenn das Formular über eine JavaScript-Funktion übermittelt wird, die einen URL-Wert erstellt, der sich von dem im Formular enthaltenen unterscheidet. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Überschreibungsmethode </p> </td> 
      <td colname="col2"> <p>Geben Sie an, wann sich die Zielgruppe der Formularübermittlung von der im Aktions-Attribut des Formulars verwendeten unterscheidet und wann das Senden-JavaScript die Methode geändert hat. </p> <p>Die Standardwerte für alle Formularparameter ( 
      <code>
        &lt;input&gt; 
      </code> -Tags, einschließlich ausgeblendeter Felder), die Standardeinstellung 
      <code>
        &lt;option&gt; 
      </code> von einer 
      <code>
        &lt;select&gt; 
      </code> -Tag und der Standardtext zwischen 
      <code>
        &lt;textarea&gt;...&lt;/textarea&gt; 
      </code> -Tags) von der Webseite aus gelesen werden. Jeder Parameter, der im Abschnitt <span class="wintitle"> Formularübermittlung </span> im Feld <span class="uicontrol"> Parameter </span> aufgeführt ist, wird jedoch durch die Formularstandardwerte ersetzt. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Parameter </p> </td> 
      <td colname="col2"> <p>Sie können Formularübermittlungsparameter mit dem Präfix 
      <code>
        not 
      </code> Keyword. </p> <p>Wenn Sie einem Parameter das Präfix 
      <code>
        not 
      </code> wird nicht als Teil der Formularübermittlung gesendet. Dieses Verhalten ist nützlich für Kontrollkästchen, die deaktiviert werden sollen. </p> <p>Angenommen, Sie möchten die folgenden Parameter übermitteln: </p> <p> 
      <ul id="ul_962D12BACF464FF189DB12BFAFCC93A6"> 
      <li id="li_830C6C3EC8D2448388A453BB8EDE5940"> Der E-Mail-Parameter mit dem Wert 
      <code>
        nobody@mydomain.com 
      </code> </li> 
      <li id="li_905497E3FACE472DBDD49392D5B45E01"> Der Kennwortparameter mit dem Wert 
      <code>
        tryme 
      </code> </li> 
      <li id="li_AAA411708ADC464793EADF0D821E282E"> Der Parameter mycheckbox ist deaktiviert. </li> 
      <li id="li_0D3DDE641E2B4BEF9F570C03FDB40ED2"> <p>Alle anderen 
      <code>
        &lt;form&gt; 
      </code> Parameter als Standardwerte </p> </li> 
      </ul> </p> <p>Ihr Formularübermittlungsparameter würde wie folgt aussehen: </p> <p> <code> email=nobody@mydomain.com 
        password=tryme 
        not&nbsp;mycheckbox </code> </p> <p>Das method -Attribut der 
      <code>
        &lt;form&gt; 
      </code> -Tag auf der Web-Seite wird verwendet, um zu entscheiden, ob die Daten mithilfe der GET- oder der POST-Methode an Ihren Server gesendet werden. </p> <p>Wenn die Variable 
      <code>
        &lt;form&gt; 
      </code> -Tag kein Methodenattribut enthält, wird das Formular mit der GET -Methode gesendet. </p> </td> 
      </tr> 
    </tbody> 
    </table>

1. Klicken **[!UICONTROL Add]**.
1. (Optional) Führen Sie einen der folgenden Schritte aus:

   * Klicken **[!UICONTROL Live]**.

      Siehe [Anzeigen von Live-Einstellungen](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Klicken **[!UICONTROL Push Live]**.

      Siehe [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Formulardefinition bearbeiten {#task_9FB34E9C8A814DFE9BF7F8F8F69BF314}

Sie können eine vorhandene Formulardefinition bearbeiten, wenn sich ein Formular auf Ihrer Website geändert hat oder Sie nur die Definition ändern müssen.

Beachten Sie, dass auf der Seite [!DNL Form Submission] keine [!DNL History]-Funktion vorhanden ist, um alle Änderungen wiederherzustellen, die Sie an einer Formulardefinition vornehmen.

Stellen Sie sicher, dass Sie Ihren Site-Index neu erstellen, damit die Ergebnisse Ihrer Änderungen für Ihre Kunden sichtbar sind.

Siehe [Konfigurieren eines inkrementellen Index einer gestaffelten Website](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0).

**So bearbeiten Sie eine Formulardefinition**

1. Klicken Sie im Produktmenü auf **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Form Submission]**.
1. Klicken Sie auf der Seite [!DNL Form Submission] rechts neben einer Formulardefinition, die Sie aktualisieren möchten, auf **[!UICONTROL Edit]** .
1. Legen Sie auf der Seite [!DNL Edit Form Definition] die Optionen [!DNL Form Recognition] und [!DNL Form Submission] fest.

   Siehe die Tabelle der Optionen unter [Hinzufügen von Formulardefinitionen für die Indizierung von Formularen auf Ihrer Website](../c-about-settings-menu/c-about-crawling-menu.md#task_62FBCE9E6DBE4BDA8D1249233ADFC00F).
1. Klicken **[!UICONTROL Save Changes]**.
1. (Optional) Führen Sie einen der folgenden Schritte aus:

   * Klicken **[!UICONTROL Live]**.

      Siehe [Anzeigen von Live-Einstellungen](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Klicken **[!UICONTROL Push Live]**.

      Siehe [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Formulardefinition löschen {#task_C350FC0CDE344F2786215D544C048B5E}

Sie können eine vorhandene Formulardefinition löschen, wenn das Formular nicht mehr auf Ihrer Website vorhanden ist oder wenn Sie ein bestimmtes Formular nicht mehr verarbeiten und indizieren möchten.

Beachten Sie, dass auf der Seite [!DNL Form Submission] keine [!DNL History]-Funktion vorhanden ist, um alle Änderungen wiederherzustellen, die Sie an einer Formulardefinition vornehmen.

Stellen Sie sicher, dass Sie Ihren Site-Index neu erstellen, damit die Ergebnisse Ihrer Änderungen für Ihre Kunden sichtbar sind.

Siehe [Konfigurieren eines inkrementellen Index einer gestaffelten Website](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0).

**So löschen Sie eine Formulardefinition**

1. Klicken Sie im Produktmenü auf **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Form Submission]**.
1. Klicken Sie auf der Seite [!DNL Form Submission] rechts neben einer Formulardefinition, die Sie entfernen möchten, auf **[!UICONTROL Delete]** .

   Achten Sie darauf, die richtige Formulardefinition zum Löschen auszuwählen. Es gibt kein Dialogfeld zur Löschbestätigung, wenn Sie im nächsten Schritt auf **[!UICONTROL Delete]** klicken.
1. Klicken Sie auf der Seite [!DNL Delete Form Definition] auf **[!UICONTROL Delete]**.
1. (Optional) Führen Sie einen der folgenden Schritte aus:

   * Klicken **[!UICONTROL Live]**.

      Siehe [Anzeigen von Live-Einstellungen](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Klicken **[!UICONTROL Push Live]**.

      Siehe [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Über Index Connector {#concept_CA6921E2FBF641F9B4F60C92B32AFA84}

Verwenden Sie [!DNL Index Connector] , um zusätzliche Eingabequellen für die Indizierung von XML-Seiten oder beliebigen Feeds zu definieren.

Sie können eine Eingabequelle für Daten-Feeds verwenden, um auf Inhalte zuzugreifen, die in einem Formular gespeichert sind, das sich von dem unterscheidet, was normalerweise auf einer Website mithilfe einer der verfügbaren Crawl-Methoden erkannt wird. Jedes durchsuchte und indizierte Dokument entspricht einer Inhaltsseite auf Ihrer Website. Ein Daten-Feed stammt jedoch entweder aus einem XML-Dokument oder aus einer durch Kommas oder Tabulatoren getrennten Textdatei und enthält die zu indizierenden Inhaltsinformationen.

Eine XML-Datenquelle besteht aus XML-Stanzas oder Datensätzen, die Informationen enthalten, die einzelnen Dokumenten entsprechen. Diese einzelnen Dokumente werden dem Index hinzugefügt. Ein Textdaten-Feed enthält einzelne, durch neue Zeilen getrennte Datensätze, die einzelnen Dokumenten entsprechen. Diese einzelnen Dokumente werden auch dem Index hinzugefügt. In beiden Fällen beschreibt eine Index-Connector-Konfiguration die Interpretation des Feeds. Jede Konfiguration beschreibt, wo sich die Datei befindet und wie die Server darauf zugreifen. In der Konfiguration werden auch Informationen zum &quot;Zuordnen&quot;beschrieben. Das heißt, wie die Elemente der einzelnen Datensätze verwendet werden, um die Metadatenfelder im resultierenden Index zu füllen.

Nachdem Sie der Seite [!DNL Staged Index Connector Definitions] eine Index Connector-Definition hinzugefügt haben, können Sie jede Konfigurationseinstellung ändern, *mit Ausnahme von* für die Werte &quot;Name&quot;oder &quot;Typ&quot;.

Die Seite [!DNL Index Connector] enthält folgende Informationen:

* Der Name der definierten Index-Connectoren, die Sie konfiguriert und hinzugefügt haben.
* Einer der folgenden Datenquellentypen für jeden Connector, den Sie hinzugefügt haben:

   * **Text**  - Einfache &quot;flache&quot;Dateien, kommagetrennte, tabulatorgetrennte oder andere konsistent getrennte Formate.
   * **Feed**  - XML-Feeds.
   * **XML**  - Sammlungen von XML-Dokumenten.

* Ob der Connector für das nächste Durchsuchen und Indizieren aktiviert ist oder nicht.
* Die Adresse der Datenquelle.

Siehe auch [Info zu Index Connector](../c-about-settings-menu/c-about-crawling-menu.md#concept_CA6921E2FBF641F9B4F60C92B32AFA84)

## Funktionsweise des Indizierungsprozesses für Text- und Feed-Konfigurationen in Index Connector {#section_E059A33D61EE4DB0972A37B8A35E9E16}

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
   <td colname="col3"> <p>Für <span class="uicontrol"> Text </span> entspricht jede durch Zeilenumbruch getrennte Textzeile einem einzelnen Dokument und wird mithilfe des angegebenen Trennzeichens wie einem Komma oder einer Registerkarte analysiert. </p> <p>Für <span class="uicontrol"> Feed </span> werden die Daten jedes Dokuments mithilfe eines Musters für reguläre Ausdrücke wie folgt extrahiert: </p> <p> <code> &lt;${Itemtag}&gt;(.*?)&lt;/${Itemtag}&gt; </code> </p> <p>Erstellen Sie mithilfe von <span class="uicontrol"> </span> auf der Seite <span class="wintitle"> Index Connector </span> eine zwischengespeicherte Kopie der Daten und erstellen Sie dann eine Liste von Links für den Crawler. Die Daten werden in einem lokalen Cache gespeichert und mit den konfigurierten Feldern gefüllt. </p> <p>Die analysierten Daten werden in den lokalen Cache geschrieben. </p> <p>Dieser Cache wird später gelesen, um die einfachen HTML-Dokumente zu erstellen, die der Crawler benötigt. Beispiel: </p> <p> <code> &lt;html&gt;&lt;head&gt; 
      &lt;title&gt;{title}&lt;/title&gt; 
      &lt;meta&nbsp;name="{field}"&nbsp;content="{data}"&nbsp;/&gt; 
      ... 
      &lt;/head&gt;&lt;body&gt; 
      {body} 
      &lt;/body&gt;&lt;/html&gt; </code> </p> <p>Das Element <span class="codeph"> &lt;title&gt; </span> wird nur generiert, wenn eine Zuordnung zum Metadatenfeld "Titel"vorhanden ist. Ebenso wird das Element <span class="codeph"> &lt;body&gt; </span> nur generiert, wenn eine Zuordnung zum Metadatenfeld "Textkörper"vorhanden ist. </p> <p> <b>Wichtig</b>: Die Zuweisung von Werten zum vordefinierten URL-Meta-Tag wird nicht unterstützt. </p> <p>Bei allen anderen Zuordnungen werden <span class="codeph"> &lt;meta&gt; </span> -Tags für jedes Feld generiert, das Daten im Originaldokument enthält. </p> <p>Die Felder für jedes Dokument werden dem Cache hinzugefügt. Für jedes Dokument, das in den Cache geschrieben wird, wird wie in den folgenden Beispielen auch ein Link generiert: </p> <p> <code> &lt;a&nbsp;href="index:Adobe?key=&lt;primary&nbsp;key&nbsp;field&gt;\"&nbsp;/&gt; 
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

## Funktionsweise des Indizierungsprozesses für XML-Konfigurationen in Index Connector {#section_7F1551EA51854C5C99F284CE260526EB}

Der Indizierungsprozess für die XML-Konfiguration ähnelt dem Prozess für Text- und Feed-Konfigurationen mit den folgenden geringfügigen Änderungen und Ausnahmen.

Da die Dokumente für XML-Crawls bereits in einzelne Dateien unterteilt sind, gelten die Schritte 1 und 2 in der obigen Tabelle nicht direkt. Wenn Sie eine URL in den Feldern **[!UICONTROL Host Address]** und **[!UICONTROL File Path]** der Seite [!DNL Index Connector Add] angeben, wird sie heruntergeladen und als normales HTML-Dokument verarbeitet. Es wird erwartet, dass das Download-Dokument eine Sammlung von `<a href="{url}"...`-Links enthält, von denen jede auf ein verarbeitetes XML-Dokument verweist. Solche Links werden in das folgende Formular konvertiert:

```
<a href="index:<ic_config_name>?url="{url}">
```

Wenn das Adobe-Setup beispielsweise die folgenden Links zurückgibt:

```
<a href="https://www.adobe.com/somepath/doc1.xml">doc 1</a> 
<a href="https://www.adobe.com/otherpath/doc2.xml">doc 2</a>
```

In der obigen Tabelle gilt Schritt 3 nicht und Schritt 4 wird zum Zeitpunkt des Crawling und der Indizierung abgeschlossen.

Alternativ können Sie Ihre XML-Dokumente mit anderen Dokumenten kombinieren, die durch den Crawl-Prozess auf natürliche Weise entdeckt wurden. In solchen Fällen können Sie Umschreibungsregeln ( **[!UICONTROL Settings]** > **[!UICONTROL Rewrite Rules]** > **[!UICONTROL Crawl List Retrieve URL Rules]**) verwenden, um die URLs der XML-Dokumente zu ändern und sie an den Index Connector weiterzuleiten.

Siehe [Über Crawl List Retrieve URL Rules](../c-about-settings-menu/c-about-rewrite-rules-menu.md#concept_EC8E2E48B99A458D8567B526C9827CBA).

Angenommen, Sie haben die folgende Neuschreibungsregel:

```
RewriteRule (^http.*[.]xml$) index:Adobe?key=$1
```

Diese Regel übersetzt alle URLs, die mit `.xml` enden, in einen Index-Connector-Link. Der Crawler erkennt und schreibt das URL-Schema `index:` neu. Der Download-Prozess wird über den Index Connector-Apache-Server auf der primären Instanz umgeleitet. Jedes heruntergeladene Dokument wird mit dem gleichen Muster für reguläre Ausdrücke geprüft, das für Feeds verwendet wird. In diesem Fall wird das erstellte HTML-Dokument jedoch nicht im Cache gespeichert. Stattdessen wird er direkt an den Crawler zur Indexverarbeitung übergeben.

## Konfigurieren mehrerer Index Connectors {#section_C2B14C0F06354A57AEF6238FF3814E5D}

Sie können für jedes Konto mehrere Index Connector-Konfigurationen definieren. Die Konfigurationen werden automatisch zur Dropdown-Liste in **[!UICONTROL Settings]** > **[!UICONTROL Crawl]** > **[!UICONTROL URL Entrypoints]** hinzugefügt, wie in der folgenden Abbildung dargestellt:

![](assets/url_entrypoints_index_connector.png)

Wenn Sie eine Konfiguration aus der Dropdown-Liste auswählen, wird der Wert am Ende der Liste der URL-Einstiegspunkte hinzugefügt.

>[!NOTE]
>
>Deaktivierte Index Connector-Konfigurationen werden zwar zur Dropdown-Liste hinzugefügt, Sie können sie jedoch nicht auswählen. Wenn Sie dieselbe Index Connector-Konfiguration ein zweites Mal auswählen, wird sie am Ende der Liste hinzugefügt und die vorherige Instanz wird gelöscht.

Um einen Index Connector-Einstiegspunkt für eine inkrementelle Suche anzugeben, können Sie Einträge im folgenden Format hinzufügen:

```
index:<indexconnector_configuration_name>
```

Der Crawler verarbeitet jeden hinzugefügten Eintrag, wenn er auf der Seite Index Connectors gefunden und aktiviert ist.

Hinweis: Da die URL eines jeden Dokuments mit dem Index Connector-Konfigurationsnamen und dem Primärschlüssel des Dokuments erstellt wird, müssen Sie bei der Durchführung inkrementeller Aktualisierungen denselben Index Connector-Konfigurationsnamen verwenden! Dadurch kann [!DNL Adobe Search&Promote] zuvor indizierte Dokumente korrekt aktualisieren.

Siehe auch [Über URL-Endpunkte](../c-about-settings-menu/c-about-crawling-menu.md#concept_5D857E3B5C124E85BC0B5AE77A509573).

**Verwendung von Setup-Maps beim Hinzufügen eines Index-Connectors**

Wenn Sie einen Index Connector hinzufügen, können Sie optional die Funktion **[!UICONTROL Setup Maps]** verwenden, um ein Beispiel Ihrer Datenquelle herunterzuladen. Die Daten werden auf Indizierungseignung geprüft.

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Wenn Sie den Index Connector-Typ auswählen... </p> </th> 
   <th colname="col2" class="entry"> <p>Die Funktion "Setup Maps".. </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Text </p> </td> 
   <td colname="col2"> <p>Bestimmt den Trennzeichenwert, indem zuerst Registerkarten und dann vertikale Balken ( <span class="codeph">) versucht werden | </span>) und schließlich Kommas ( <span class="codeph"> , </span>). Wenn Sie bereits einen Trennzeichenwert angegeben haben, bevor Sie auf <span class="uicontrol"> Einrichtungskarten </span> geklickt haben, wird dieser Wert stattdessen verwendet. </p> <p>Das am besten geeignete Schema führt dazu, dass die Zuordnungsfelder mit Schätzungen zu den entsprechenden Tag- und Feldwerten ausgefüllt werden. Zusätzlich wird eine Auswahl der analysierten Daten angezeigt. Wählen Sie <span class="uicontrol"> Kopfzeilen in der ersten Zeile </span> aus, wenn Sie wissen, dass die Datei eine Kopfzeile enthält. Die Setup-Funktion verwendet diese Informationen, um die resultierenden Zuordnungseinträge besser zu identifizieren. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Feed </p> </td> 
   <td colname="col2"> <p>Lädt die Datenquelle herunter und führt einfache XML-Parsing durch. </p> <p>Die resultierenden XPath-IDs werden in den Tag-Zeilen der Map-Tabelle und in den Feldern in ähnlichen Werten angezeigt. Diese Zeilen identifizieren nur die verfügbaren Daten und generieren nicht die komplizierteren XPath-Definitionen. Es ist jedoch weiterhin hilfreich, da es die XML-Daten beschreibt und ItemTag-Werte identifiziert. </p> <p> <p>Hinweis:  Die Funktion "Setup-Maps"lädt die gesamte XML-Quelle herunter, um die Analyse durchzuführen. Wenn die Datei groß ist, kann bei diesem Vorgang eine Zeitüberschreitung auftreten. </p> </p> <p>Nach erfolgreichem Abschluss identifiziert diese Funktion alle möglichen XPath-Elemente, von denen viele nicht verwendet werden sollten. Achten Sie darauf, die resultierenden Kartendefinitionen zu untersuchen und diejenigen zu entfernen, die Sie nicht benötigen oder möchten. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>XML </p> </td> 
   <td colname="col2"> <p>Lädt die URL eines repräsentativen individuellen Dokuments herunter, nicht die Liste der primären Links. Dieses einzelne Dokument wird mit demselben Mechanismus analysiert, der für Feeds verwendet wird, und die Ergebnisse werden angezeigt. </p> <p>Bevor Sie auf <span class="uicontrol"> </span> klicken, um die Konfiguration zu speichern, stellen Sie sicher, dass Sie die URL wieder in das Dokument mit der primären Link-Liste ändern. </p> </td> 
  </tr> 
 </tbody> 
</table>

**Wichtig**: Die Funktion &quot;Setup Maps&quot;funktioniert möglicherweise nicht für große XML-Datensätze, da der Dateiparser versucht, die gesamte Datei in den Speicher zu lesen. Daher kann es zu einer Speicherüberschreitung kommen. Wenn dasselbe Dokument jedoch zum Zeitpunkt der Indizierung verarbeitet wird, wird es nicht in den Speicher gelesen. Stattdessen werden große Dokumente &quot;unterwegs&quot;verarbeitet und zuerst nicht vollständig in den Speicher gelesen.

**Die Verwendung der Vorschau beim Hinzufügen eines Index-Connectors**

Zum Zeitpunkt des Hinzufügens eines Index-Connectors können Sie optional die Funktion **[!UICONTROL Preview]** verwenden, um die Daten zu validieren, als ob Sie sie gespeichert hätten. Er führt einen Test für die Konfiguration aus, ohne die Konfiguration im Konto zu speichern. Der Test greift auf die konfigurierte Datenquelle zu. Der Download-Cache wird jedoch an einen temporären Speicherort geschrieben. Es steht nicht im Konflikt mit dem Hauptcache-Ordner, den der Indizierungs-Crawler verwendet.

Die Vorschau verarbeitet nur einen Standardwert von fünf Dokumenten, wie von Acct:IndexConnector-Preview-Max-Documents gesteuert. Die in der Vorschau angezeigten Dokumente werden im Quellformular angezeigt, da sie dem Indizierungs-Crawler präsentiert werden. Die Anzeige ähnelt der Funktion &quot;Quelle anzeigen&quot;in einem Webbrowser. Sie können mithilfe von Standardnavigationslinks in den Dokumenten im Vorschauset navigieren.

Die Vorschau unterstützt keine XML-Konfigurationen, da diese Dokumente direkt verarbeitet und nicht in den Cache heruntergeladen werden.

## Hinzufügen einer Index Connector-Definition {#task_96779B651A654E1F871F55D6DBBC8886}

Jede Index Connector-Konfiguration definiert eine Datenquelle und Zuordnungen, um die für diese Quelle definierten Datenelemente mit den Metadatenfeldern im Index zu verknüpfen.

Bevor die Auswirkungen der neuen und aktivierten Definition für Kunden sichtbar sind, müssen Sie Ihren Site-Index neu erstellen.

**So fügen Sie eine Index Connector-Definition hinzu**

1. Klicken Sie im Produktmenü auf **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Index Connector]**.
1. Klicken Sie auf der Seite [!DNL Stage Index Connector Definitions] auf **[!UICONTROL Add New Index Connector]**.
1. Legen Sie auf der Seite [!DNL Index Connector Add] die gewünschten Connector-Optionen fest. Die verfügbaren Optionen hängen von der ausgewählten **[!UICONTROL Type]** ab.

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
      <td colname="col2"> <p>Der eindeutige Name der Index Connector-Konfiguration. Sie können alphanumerische Zeichen verwenden. Die Zeichen "_"und "-"sind ebenfalls zulässig. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Typ </p> </td> 
      <td colname="col2"> <p>Die Quelle Ihrer Daten. Der ausgewählte Datenquellentyp wirkt sich auf die resultierenden Optionen aus, die auf der Seite <span class="wintitle"> Index Connector Add </span> verfügbar sind. Sie können aus folgenden Optionen wählen: </p> <p> 
      <ul id="ul_1ADC3DFBC929467385F7465BE8E13635"> 
      <li id="li_64FCD749F55442BAB316BD474128D4F9"> <span class="uicontrol"> Text </span> <p>Einfache flache Textdateien, kommagetrennte, tabulatorgetrennte oder andere konsistent getrennte Formate. Jede durch Zeilenumbrüche getrennte Textzeile entspricht einem einzelnen Dokument und wird mithilfe des angegebenen Trennzeichens analysiert. </p> <p>Sie können jeden Wert bzw. jede Spalte einem Metadatenfeld zuordnen, das durch die Spaltennummer referenziert wird, beginnend bei 1 (eins). </p> </li> 
      <li id="li_2A4F16CE6DCE4114B7F8E4FE156252BB"> <span class="uicontrol"> Feed </span> <p>Lädt ein primäres XML-Dokument herunter, das mehrere "Zeilen"mit Informationen enthält. </p> </li> 
      <li id="li_5A61C53522D74D4C9A5F65989604BDEF"> <span class="uicontrol"> XML </span> <p>Laden Sie ein primäres XML-Dokument herunter, das Links enthält ( 
      <code>
        &lt;a&gt; 
      </code>) für einzelne XML-Dokumente. </p> </li> 
      </ul> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p> <b>Datenquellentyp: Text</b> </p> </td> 
      <td colname="col2"> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Aktiviert </p> </td> 
      <td colname="col2"> <p>Wandelt die Konfiguration "ein"in Crawl und Index um. Alternativ können Sie die Konfiguration "deaktivieren", um Crawling und Indizierung zu verhindern. </p> <p> <b>Hinweis</b>: Deaktivierte Index Connector-Konfigurationen werden ignoriert, wenn sie in einer Einstiegspunktliste gefunden werden. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Hostadresse </p> </td> 
      <td colname="col2"> <p>Gibt die Adresse des Serverhosts an, auf dem sich Ihre Daten befinden. </p> <p>Bei Bedarf können Sie einen vollständigen URI-Pfad (Uniform Resource Identifier) zum Datenquellendokument wie in den folgenden Beispielen angeben: </p> <p> <code> https://www.somewhere.com/some_path/some_file.xml </code> </p> <p>oder </p> <p> <code> ftp://user:password@ftpserver.somewhere.com/some_path/some_file.xml </code> </p> <p>Der URI ist in die entsprechenden Einträge für die Felder Host-Adresse, Dateipfad, Protokoll und optional Benutzername und Kennwort unterteilt. </p> <p>Gibt die IP-Adresse oder die URL-Adresse des Hostsystems an, in dem die Datenquellendatei gefunden wird. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Dateipfad </p> </td> 
      <td colname="col2"> <p>Gibt den Pfad zur einfachen Textdatei mit einfach strukturiertem, kommagetrennten, tabulatorgetrennten oder anderen konsistent getrennten Formatdateien an. </p> <p>Der Pfad ist relativ zum Stammverzeichnis der Hostadresse. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Inkrementeller Dateipfad </p> </td> 
      <td colname="col2"> <p>Gibt den Pfad zur einfachen Textdatei mit einfach strukturiertem, kommagetrennten, tabulatorgetrennten oder anderen konsistent getrennten Formatdateien an. </p> <p>Der Pfad ist relativ zum Stammverzeichnis der Hostadresse. </p> <p>Diese Datei wird, sofern angegeben, während der Vorgänge "Inkrementeller Index"heruntergeladen und verarbeitet. Wenn keine Datei angegeben ist, wird stattdessen die unter Dateipfad aufgelistete Datei verwendet. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Vertikaler Dateipfad </p> </td> 
      <td colname="col2"> <p>Gibt den Pfad zur einfachen, durch Kommas getrennten, tabulatorgetrennten oder anderen, konsistent getrennten Formatdatei an, die bei einer vertikalen Aktualisierung verwendet werden soll. </p> <p>Der Pfad ist relativ zum Stammverzeichnis der Hostadresse. </p> <p>Diese Datei wird, sofern angegeben, während des Vorgangs "Vertikale Aktualisierung"heruntergeladen und verarbeitet. </p> <p> <b>Hinweis</b>: Diese Funktion ist standardmäßig nicht aktiviert. Wenden Sie sich an den technischen Support , um die Funktion für Ihre Verwendung zu aktivieren. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Löschen des Dateipfads </p> </td> 
      <td colname="col2"> <p>Gibt den Pfad zur einfachen Textdatei mit einem einzelnen Dokumentkennungswert pro Zeile an. </p> <p>Der Pfad ist relativ zum Stammverzeichnis der Hostadresse. </p> <p>Diese Datei wird, sofern angegeben, während der Vorgänge "Inkrementeller Index"heruntergeladen und verarbeitet. Die in dieser Datei gefundenen Werte werden verwendet, um "Löschanfragen"zum Entfernen zuvor indizierter Dokumente zu erstellen. Die Werte in dieser Datei müssen den Werten in den Dateien Vollständiger oder Inkrementeller Dateipfad in der Spalte entsprechen, die als Primärer Schlüssel </span> bezeichnet wird.<span class="uicontrol"> </span></p> <p> <b>Hinweis</b>: Diese Funktion ist standardmäßig nicht aktiviert. Wenden Sie sich an den technischen Support , um die Funktion für Ihre Verwendung zu aktivieren. </p> </td> 
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
      <td colname="col1"> <p>Mindestanzahl von Dokumenten für die Indizierung </p> </td> 
      <td colname="col2"> <p>Wenn der Wert auf einen positiven Wert gesetzt wird, gibt dies die Mindestanzahl von Datensätzen an, die in der heruntergeladenen Datei erwartet werden. Wenn weniger Datensätze empfangen werden, wird der Indexvorgang abgebrochen. </p> <p> <b>Hinweis</b>: Diese Funktion ist standardmäßig nicht aktiviert. Wenden Sie sich an den technischen Support , um die Funktion für Ihre Verwendung zu aktivieren. </p> <p> <b>Hinweis</b>: Diese Funktion wird nur bei vollständigen Indexvorgängen verwendet. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Landkarte </p> </td> 
      <td colname="col2"> <p>Gibt Zuordnungen von Spalten zu Metadaten mithilfe von Spaltennummern an. </p> <p> 
      <ul id="ul_981AE2C6D30443BDBFC6575D413732A2"> 
      <li id="li_A42CB9DFFF8C45A7BAC2D471FE96CEBE"> <span class="uicontrol"> Spalte </span> <p> Gibt eine Spaltennummer an, wobei die erste Spalte 1 (1) ist. Um für jede Spalte neue Zuordnungszeilen hinzuzufügen, klicken Sie unter <span class="wintitle"> Aktion </span> auf <span class="uicontrol"> + </span>. </p> <p>Sie müssen nicht jede Spalte in der Datenquelle referenzieren. Stattdessen können Sie Werte überspringen. </p> </li> 
      <li id="li_26E8C9554A5D4BC5A5073D6385E3626F"> <span class="uicontrol"> Feld </span> <p>Definiert den Attribut name -Wert, der für jedes generierte &lt;meta&gt; -Tag verwendet wird. </p> </li> 
      <li id="li_5DFA514B7F9549B98D6CBC095A66033C"> <span class="uicontrol"> Metadaten? </span> <p>Verursacht, dass <span class="uicontrol"> Feld </span> zu einer Dropdown-Liste wird, aus der Sie definierte Metadatenfelder für das aktuelle Konto auswählen können. </p> <p>Der Wert <span class="uicontrol"> Feld </span> kann ein nicht definiertes Metadatenfeld sein, falls gewünscht. Manchmal ist ein nicht definiertes Metadatenfeld nützlich, um Inhalte zu erstellen, die von <span class="wintitle"> Filterskript </span> verwendet werden. </p> <p>Siehe <a href="../c-about-settings-menu/c-about-filtering-menu.md#concept_E56B73D625854AB2A899EF2D56CFCB47" type="concept" format="dita" scope="local"> Informationen zum Filtern von Skript </a>. </p> <p>Wenn Index Connector XML-Dokumente mit mehreren Treffern in einem Zuordnungsfeld verarbeitet, werden die verschiedenen Werte im resultierenden zwischengespeicherten Dokument zu einem einzigen Wert verkettet. Standardmäßig werden diese Werte mit einem Kommatrennzeichen kombiniert. Angenommen, der entsprechende Wert <span class="wintitle"> Feld </span> ist ein definiertes Metadatenfeld. Darüber hinaus ist für dieses Feld das Attribut <span class="wintitle"> Zulassungslisten </span> festgelegt. In diesem Fall wird der Wert "Listentrennzeichen"des Felds, das erste definierte Trennzeichen, in der Verkettung verwendet. </p> </li> 
      <li id="li_80DB205525094CE1AA6762BFC7892C95"> <span class="uicontrol"> Primärschlüssel? </span> <p>Nur eine Zuordnungsdefinition wird als Primärschlüssel identifiziert. Dieses Feld wird zum eindeutigen Verweis, der angezeigt wird, wenn dieses Dokument zum Index hinzugefügt wird. Dieser Wert wird in der URL des Dokuments im Index verwendet. </p> <p>Die <span class="uicontrol">-Werte für den Primären Schlüssel </span> müssen in allen Dokumenten eindeutig sein, die von der Index Connector-Konfiguration repräsentiert werden. Alle gefundenen Duplikate werden ignoriert. Wenn Ihre Quelldokumente keinen einzigen eindeutigen Wert enthalten, der als <span class="uicontrol"> Primärer Schlüssel </span> verwendet werden soll, aber zwei oder mehr Felder zusammen <i>einen eindeutigen Bezeichner bilden können, können Sie den Primären Schlüssel <span class="uicontrol"> definieren, indem Sie mehrere <span class="uicontrol"> Spaltenwerte </span> mit einem vertikalen Balken ("|") kombinieren, der die Werte trennt.</i></span> </p> </li> 
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
      <td colname="col2"> <p>Wandelt die Konfiguration "ein"in Crawl und Index um. Alternativ können Sie die Konfiguration "deaktivieren", um Crawling und Indizierung zu verhindern. </p> <p> <b>Hinweis</b>: Deaktivierte Index Connector-Konfigurationen werden ignoriert, wenn sie in einer Einstiegspunktliste gefunden werden. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Hostadresse </p> </td> 
      <td colname="col2"> <p>Gibt die IP-Adresse oder die URL-Adresse des Hostsystems an, in dem die Datenquellendatei gefunden wird. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Dateipfad </p> </td> 
      <td colname="col2"> <p>Gibt den Pfad zum primären XML-Dokument an, das mehrere "Zeilen"mit Informationen enthält. </p> <p>Der Pfad ist relativ zum Stammverzeichnis der Hostadresse. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Inkrementeller Dateipfad </p> </td> 
      <td colname="col2"> <p>Gibt den Pfad zum inkrementellen XML-Dokument an, das mehrere "Zeilen"mit Informationen enthält. </p> <p>Der Pfad ist relativ zum Stammverzeichnis der Hostadresse. </p> <p>Diese Datei wird, sofern angegeben, während der Vorgänge "Inkrementeller Index"heruntergeladen und verarbeitet. Wenn keine Datei angegeben ist, wird stattdessen die unter Dateipfad aufgelistete Datei verwendet. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Vertikaler Dateipfad </p> </td> 
      <td colname="col2"> <p>Gibt den Pfad zum XML-Dokument an, das mehrere wenige "Zeilen"mit Informationen enthält, die während einer vertikalen Aktualisierung verwendet werden sollen. </p> <p>Der Pfad ist relativ zum Stammverzeichnis der Hostadresse. </p> <p>Diese Datei wird, sofern angegeben, während des Vorgangs "Vertikale Aktualisierung"heruntergeladen und verarbeitet. </p> <p> <b>Hinweis</b>: Diese Funktion ist standardmäßig nicht aktiviert. Wenden Sie sich an den technischen Support , um die Funktion für Ihre Verwendung zu aktivieren. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Löschen des Dateipfads </p> </td> 
      <td colname="col2"> <p>Gibt den Pfad zur einfachen Textdatei mit einem einzelnen Dokumentkennungswert pro Zeile an. </p> <p>Der Pfad ist relativ zum Stammverzeichnis der Hostadresse. </p> <p>Diese Datei wird, sofern angegeben, während der Vorgänge "Inkrementeller Index"heruntergeladen und verarbeitet. Die in dieser Datei gefundenen Werte werden verwendet, um "Löschanfragen"zum Entfernen zuvor indizierter Dokumente zu erstellen. Die Werte in dieser Datei müssen den Werten in den Dateien Vollständiger oder Inkrementeller Dateipfad in der Spalte entsprechen, die als Primärer Schlüssel </span> bezeichnet wird.<span class="uicontrol"> </span></p> <p> <b>Hinweis</b>: Diese Funktion ist standardmäßig nicht aktiviert. Wenden Sie sich an den technischen Support , um die Funktion für Ihre Verwendung zu aktivieren. </p> </td> 
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
      <td colname="col2"> <p>Identifiziert das XML-Element, mit dem Sie einzelne XML-Zeilen in der angegebenen Datenquellendatei identifizieren können. </p> <p>Im folgenden Feed-Fragment eines Adobe XML-Dokuments lautet der ItemTag-Wert beispielsweise <span class="codeph"> record </span>: </p> <p> <code> &lt;?xml&nbsp;version="1.0"&nbsp;encoding="utf-8"?&gt; 
        &lt;!DOCTYPE&nbsp;gsafeed&nbsp;PUBLIC&nbsp;"-//Google//DTD&nbsp;GSA&nbsp;Feeds//EN"&nbsp;""&gt; &lt;gsafeed&gt; 
        &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;header&gt; 
        &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;datasource&gt;marketplace&lt;/datasource&gt; 
        &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;feedtype&gt;incremental&lt;/feedtype&gt; 
        &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/header&gt; 
        &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;group&nbsp;action="add"&gt; 
        &lt;record&nbsp;url=https://www.adobe.com/cfusion/marketplace_gsa
        index.cfm?event=marketplace.home&amp;amp;marketplaceid=1&nbsp;action="add"&nbsp;mimetype="text/html"displayurl="https://www.adobe.com/cfusion/marketplace/index.cfm?event=marketplace.home&amp;amp;marketplaceid=1"&gt;&lt;metadata&gt; 
        &lt;meta&nbsp;name="mp_mkt"&nbsp;content="1"/&gt; 
        &lt;meta&nbsp;name="mp_logo"&nbsp;content="/images/marketplace/ 
        dbreferenced/marketplaceicons/icn_air.png"/&gt; 
        &lt;meta&nbsp;name="title"&nbsp;content="Adobe&nbsp;AIR&nbsp;Marketplace"/&gt; 
        &lt;meta&nbsp;name="description"&nbsp;content="Discover&nbsp;new&nbsp;applications&nbsp;..."/&gt; &lt;/metadata&gt; 
        &lt;content&gt;&lt;![CDATA[&lt;html&gt;&lt;head&gt;&lt;title&gt;Adobe&nbsp;AIR&nbsp;Marketplace&lt;/title&gt;&lt;/head&gt;&lt;body&gt;Discover&nbsp;new&nbsp;applications&nbsp;...&lt;/body&gt;&lt;/html&gt;]]&gt;&lt;/cntent&gt; 
        &lt;/record&gt; 
        &lt;record&nbsp;url=https://www.adobe.com/cfusion/marketplace_gsa/
        index.cfm?event=marketplace.home&amp;amp;marketplaceid=2&nbsp;action="add"&nbsp;mimetype="text/html"&nbsp;displayurl="https://www.adobe.com/cfusion/ 
        marketplace/index.cfm?event=marketplace.home&amp;amp;marketplaceid=2"&gt; 
        &lt;metadata&gt; 
        &lt;meta&nbsp;name="mp_mkt"&nbsp;content="2"/&gt; 
        &lt;meta&nbsp;name="mp_logo"&nbsp;content="/images/marketplace/ 
        dbreferenced/marketplaceicons/icn_photoshop.png"/&gt;         &lt;meta&nbsp;name="title"&nbsp;content="Adobe&nbsp;Photoshop&nbsp;Marketplace"/&gt;         &lt;meta&nbsp;name="description"&nbsp;content="Extend&nbsp;your&nbsp;creative&nbsp;possibilities&nbsp;..."/&gt; 
        &lt;/metadata&gt;         &lt;content&gt;&lt;![CDATA[&lt;html&gt;&lt;head&gt;&lt;title&gt;Adobe&nbsp;Photoshop&nbsp;Marketplace&lt;/title&gt;&lt;/head&gt;&lt;body&gt;Extend&nbsp;your&nbsp;creative&nbsp;possibilities&nbsp;...&lt;/body&gt;&lt;/html&gt;]]&gt;/content&gt; 
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
      <td colname="col1"> <p>Mindestanzahl von Dokumenten für die Indizierung </p> </td> 
      <td colname="col2"> <p>Wenn der Wert auf einen positiven Wert gesetzt wird, gibt dies die Mindestanzahl von Datensätzen an, die in der heruntergeladenen Datei erwartet werden. Wenn weniger Datensätze empfangen werden, wird der Indexvorgang abgebrochen. </p> <p> <b>Hinweis</b>: Diese Funktion ist standardmäßig nicht aktiviert. Wenden Sie sich an den technischen Support , um die Funktion für Ihre Verwendung zu aktivieren. </p> <p> <b>Hinweis</b>: Diese Funktion wird nur bei vollständigen Indexvorgängen verwendet. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Landkarte </p> </td> 
      <td colname="col2"> <p>Ermöglicht die Angabe von XML-Element-zu-Metadaten-Zuordnungen mithilfe von XPath-Ausdrücken. </p> <p> 
      <ul id="ul_604108C0277C4892AE8A40CA39889ABD"> 
      <li id="li_0AF92270AE9F4BA8B2C7EE41FABC0F34"> <span class="uicontrol"> Tag </span> <p>Gibt eine XPath-Darstellung der analysierten XML-Daten an. Unter Verwendung des obigen Beispieldokuments für die Adobe XML unter der Option ItemTag kann es mit der folgenden Syntax zugeordnet werden: </p> <p> <code> /record/@displayurl&nbsp;-&gt;&nbsp;page-url 
      /record/metadata/meta[@name='title']/@content&nbsp;-&gt;&nbsp;title 
      /record/metadata/meta[@name='description']/@content&nbsp;-&gt;&nbsp;desc 
      /record/metadata/meta[@name='description']/@content&nbsp;-&gt;&nbsp;body </code> </p> <p>Die obige Syntax lautet wie folgt: </p> <p> 
      <ul id="ul_6400EBD08D424EADA1612FE4F7EFB640"> 
      <li id="li_9958F9B40D42434195597DBA9F2AF28F"> <code> /record/@displayurl&amp;nbsp;-&gt;&amp;nbsp;page-url </code> <p>Das Attribut <span class="codeph"> displayURL </span> des Elements <span class="codeph"> record </span> ist dem Metadatenfeld <span class="codeph"> page-url </span> zugeordnet. </p> </li> 
      <li id="li_759013EA02CD48BE971A55B0A6A11424"> <code> /record/metadata/meta[@name='title']/@content&amp;nbsp;-&gt;&amp;nbsp;title </code> <p>Das Attribut <span class="codeph"> content </span> jedes <span class="codeph"> meta </span> -Elements, das in einem <span class="codeph"> -Metadatenelement </span> enthalten ist, das in einem <span class="codeph"> -Datensatz </span>-Element enthalten ist, dessen Namensattribut <span class="codeph"> title </span> ist, wird dem Metadatenfeld <span class="codeph"> title &lt;a11 zugeordnet/&gt;.</span> </p> </li> 
      <li id="li_E741CA59197D462EB2946EDE874AFDC8"> <code> /record/metadata/meta[@name='description']/@content&amp;nbsp;-&gt;&amp;nbsp;desc </code> <p>Das Attribut <span class="codeph"> content </span> jedes <span class="codeph"> meta </span> -Elements, das in einem <span class="codeph"> -Metadatenelement </span> enthalten ist, das innerhalb des Elements <span class="codeph"> record </span> enthalten ist, dessen Namensattribut <span class="codeph"> description </span> ist, wird dem Metadatenfeld <span class="codeph"> desc &lt;a1 zugeordnet 1/&gt;.</span> </p> </li> 
      <li id="li_E35EAE3D284D46D485D9064D7BB6AB13"> <code> /record/metadata/meta[@name='description']/@content&amp;nbsp;-&gt;&amp;nbsp;body </code> <p>Das Attribut <span class="codeph"> content </span> jedes <span class="codeph"> meta </span> -Elements, das in einem <span class="codeph"> -Metadatenelement </span> enthalten ist, das im Element <span class="codeph"> Datensatz </span> enthalten ist, dessen Namensattribut <span class="codeph"> description </span> ist, wird dem Metadatenfeld <span class="codeph"> body &lt;a1 zugeordnet/&gt;.</span> </p> </li> 
      </ul> </p> <p>XPath ist eine relativ komplizierte Notation. Weitere Informationen finden Sie unter: </p> <p>Siehe <a href="https://www.w3schools.com/xml/xpath_intro.asp" scope="external" format="html"> https://www.w3schools.com/xpath/ </a> </p> </li> 
      <li id="li_8147075D7ACD4811A7ED335F23FE62A6"> <span class="uicontrol"> Feld </span> <p>Definiert den Attribut name -Wert, der für jedes generierte Tag <span class="codeph"> &lt;meta&gt; </span> verwendet wird. </p> </li> 
      <li id="li_2380199D63BF425A919606D8232FA6E2"> <span class="uicontrol"> Metadaten? </span> <p>Verursacht, dass <span class="uicontrol"> Feld </span> zu einer Dropdown-Liste wird, aus der Sie definierte Metadatenfelder für das aktuelle Konto auswählen können. </p> <p>Der Wert <span class="uicontrol"> Feld </span> kann ein nicht definiertes Metadatenfeld sein, falls gewünscht. Manchmal ist ein nicht definiertes Metadatenfeld nützlich, um Inhalte zu erstellen, die von <span class="wintitle"> Filterskript </span> verwendet werden. </p> <p>Siehe <a href="../c-about-settings-menu/c-about-filtering-menu.md#concept_E56B73D625854AB2A899EF2D56CFCB47" type="concept" format="dita" scope="local"> Informationen zum Filtern von Skript </a>. </p> <p>Wenn Index Connector XML-Dokumente mit mehreren Treffern in einem Zuordnungsfeld verarbeitet, werden die verschiedenen Werte im resultierenden zwischengespeicherten Dokument zu einem einzigen Wert verkettet. Standardmäßig werden diese Werte mit einem Kommatrennzeichen kombiniert. Angenommen, der entsprechende Wert <span class="wintitle"> Feld </span> ist ein definiertes Metadatenfeld. Darüber hinaus ist für dieses Feld das Attribut <span class="wintitle"> Zulassungslisten </span> festgelegt. In diesem Fall wird der Wert "Listentrennzeichen"des Felds, das erste definierte Trennzeichen, in der Verkettung verwendet. </p> </li> 
      <li id="li_DEA24003E97E406DA2510C43CCFDC70E"> <span class="uicontrol"> Primärschlüssel? </span> <p>Nur eine Zuordnungsdefinition wird als Primärschlüssel identifiziert. Dieses Feld wird zum eindeutigen Verweis, der angezeigt wird, wenn dieses Dokument zum Index hinzugefügt wird. Dieser Wert wird in der URL des Dokuments im Index verwendet. </p> <p>Die <span class="uicontrol">-Werte für den Primären Schlüssel </span> müssen in allen Dokumenten eindeutig sein, die von der Index Connector-Konfiguration repräsentiert werden. Alle gefundenen Duplikate werden ignoriert. Wenn Ihre Quelldokumente keinen einzigen eindeutigen Wert enthalten, der als <span class="uicontrol"> Primärer Schlüssel </span> verwendet werden soll, aber zwei oder mehr Felder zusammen <i>einen eindeutigen Bezeichner bilden können, können Sie den Primären Schlüssel <span class="uicontrol"> definieren, indem Sie mehrere <span class="uicontrol"> Tags </span> mit einer vertikalen Leiste ("|") kombinieren, die die Werte trennen.</i></span> </p> </li> 
      <li id="li_DEA24003E97E406DA2510C43CCFDC81F"> <span class="uicontrol"> HTML entfernen?  </span> <p>Wenn diese Option aktiviert ist, werden alle in den Daten dieses Felds gefundenen HTML-Tags entfernt. </p> </li> 
      <li id="li_5E829D1D0DBD4BB7AAB5DB983053D248"> <span class="uicontrol"> Verwenden Sie zum Löschen?  </span> <p>Wird nur bei Inkrementellen Indexvorgängen verwendet. Datensätze, die diesem XPath-Muster entsprechen, identifizieren Elemente zum Löschen. Der <span class="uicontrol">-Wert für den Primären Schlüssel </span> für jeden dieser Datensätze wird verwendet, um "Löschanfragen"zu erstellen, wie dies bei "Löschdateipfad"der Fall ist. </p> <p> <b>Hinweis</b>: Diese Funktion ist standardmäßig nicht aktiviert. Wenden Sie sich an den technischen Support , um die Funktion für Ihre Verwendung zu aktivieren. </p> </li> 
      <li id="li_D40E2F9AD8AD49FC9AC4B8C75BA31E28"> <span class="uicontrol"> Aktion </span> <p>Ermöglicht das Hinzufügen von Zeilen zur Zuordnung oder das Entfernen von Zeilen aus der Zuordnung. Die Reihenfolge der Zeilen ist nicht wichtig. </p> </li> 
      </ul> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p> <b>Datenquellentyp: XML</b> </p> </td> 
      <td colname="col2"> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Aktiviert </p> </td> 
      <td colname="col2"> <p>Wandelt die Konfiguration "ein"in Crawl und Index um. Alternativ können Sie die Konfiguration "deaktivieren", um Crawling und Indizierung zu verhindern. </p> <p> <b>Hinweis</b>: Deaktivierte Index Connector-Konfigurationen werden ignoriert, wenn sie in einer Einstiegspunktliste gefunden werden. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Hostadresse </p> </td> 
      <td colname="col2"> <p>Gibt die URL-Adresse des Hostsystems an, in dem die Datenquellendatei gefunden wird. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Dateipfad </p> </td> 
      <td colname="col2"> <p>Gibt den Pfad zum primären XML-Dokument an, das Links enthält ( 
      <code>
        &lt;a&gt; 
      </code>) für einzelne XML-Dokumente. </p> <p>Der Pfad ist relativ zum Stammverzeichnis der Hostadresse. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Protokoll </p> </td> 
      <td colname="col2"> <p>Gibt das Protokoll an, das für den Zugriff auf die Datei verwendet wird. Sie können aus folgenden Optionen wählen: </p> <p> 
      <ul id="ul_EA4EB7953D68483FAD75753B2EE70E74"> 
      <li id="li_537F24C6B2AB435CB7C14117663D7B3F"> HTTP <p>Bei Bedarf können Sie für den Zugriff auf den HTTP-Server die entsprechenden Authentifizierungsberechtigungen eingeben. </p> </li> 
      <li id="li_8C13C93C52364FFA8B9B18830CDB223C"> HTTPS <p>Bei Bedarf können Sie für den Zugriff auf den HTTPS-Server die entsprechenden Authentifizierungsberechtigungen eingeben. </p> </li> 
      <li id="li_2F967B5675254C949B31EAB19910751C"> FTP <p>Sie müssen die entsprechenden Authentifizierungsberechtigungen eingeben, um auf den FTP-Server zugreifen zu können. </p> </li> 
      <li id="li_C24BE4C1DE79488AA64C7133D78CD3A6"> SFTP <p>Sie müssen die entsprechenden Authentifizierungsberechtigungen eingeben, um auf den SFTP-Server zugreifen zu können. </p> </li> 
      <li id="li_7581C21CFC104986A361F62BD7A370C1"> Datei </li> 
      </ul> </p> <p> <b>Hinweis</b>: Die Einstellung Protokoll wird nur verwendet, wenn in den Feldern Host Address und/oder File Path Informationen angegeben sind. Einzelne XML-Dokumente werden gemäß ihren URL-Spezifikationen entweder mit HTTP oder HTTPS heruntergeladen. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>itemTag </p> </td> 
      <td colname="col2"> <p>Identifiziert das XML-Element, das eine "Zeile"in der von Ihnen angegebenen Datenquellendatei definiert. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Landkarte </p> </td> 
      <td colname="col2"> <p>Ermöglicht die Angabe von Zuordnungen zwischen Spalten und Metadaten mithilfe von Spaltennummern. </p> <p> 
      <ul id="ul_06F50CBA0AA64C7CB1AFAE076E629A64"> 
      <li id="li_0FA2502869BA40DC93D790B79E15A9D2"> <span class="uicontrol"> Tag  </span> <p>Gibt eine XPath-Darstellung der analysierten XML-Daten an. Mithilfe des obigen XML-Beispieldokuments für die Adobe können Sie es unter der Option "ItemTag"mit der folgenden Syntax zuordnen: </p> <p> <code> /record/@displayurl&nbsp;-&gt;&nbsp;page-url 
        /record/metadata/meta[@name='title']/@content&nbsp;-&gt;&nbsp;title 
        /record/metadata/meta[@name='description']/@content&nbsp;-&gt;&nbsp;desc 
        /record/metadata/meta[@name='description']/@content&nbsp;-&gt;&nbsp;body </code> </p> <p>Die obige Syntax lautet wie folgt: </p> <p> 
      <ul id="ul_F8C536E6E54546D9AA5B22B879C0AF39"> 
      <li id="li_78A35DFFF1B4496CAC6EDC7B1E991F29"> <code> /record/@displayurl&amp;nbsp;-&gt;&amp;nbsp;page-url </code> <p>Das Attribut <span class="codeph"> displayURL </span> des Elements <span class="codeph"> record </span> ist dem Metadatenfeld <span class="codeph"> page-url </span> zugeordnet. </p> </li> 
      <li id="li_FA7DF3D1942248B98660F3D0C82F4563"> <code> /record/metadata/meta[@name='title']/@content&amp;nbsp;-&gt;&amp;nbsp;title </code> <p>Das Attribut <span class="codeph"> content </span> jedes <span class="codeph"> meta </span> -Elements, das in einem <span class="codeph"> -Metadatenelement </span> enthalten ist, das in einem <span class="codeph"> -Datensatz </span>-Element enthalten ist, dessen Namensattribut <span class="codeph"> title </span> ist, wird dem Metadatenfeld <span class="codeph"> title &lt;a11 zugeordnet/&gt;.</span> </p> </li> 
      <li id="li_D8000A116FF84DE59ED19C656DDD3BC1"> <code> /record/metadata/meta[@name='description']/@content&amp;nbsp;-&gt;&amp;nbsp;desc </code> <p>Das Attribut <span class="codeph"> content </span> jedes <span class="codeph"> meta </span> -Elements, das in einem <span class="codeph"> -Metadatenelement </span> enthalten ist, das innerhalb des Elements <span class="codeph"> record </span> enthalten ist, dessen Namensattribut <span class="codeph"> description </span> ist, wird dem Metadatenfeld <span class="codeph"> desc &lt;a1 zugeordnet 1/&gt;.</span> </p> </li> 
      <li id="li_7FA6A53DFD3D42A98B7BA17CC29DDB81"> <code> /record/metadata/meta[@name='description']/@content&amp;nbsp;-&gt;&amp;nbsp;body </code> <p>Das Attribut <span class="codeph"> content </span> jedes <span class="codeph"> meta </span> -Elements, das in einem <span class="codeph"> -Metadatenelement </span> enthalten ist, das im Element <span class="codeph"> Datensatz </span> enthalten ist, dessen Namensattribut <span class="codeph"> description </span> ist, wird dem Metadatenfeld <span class="codeph"> body &lt;a1 zugeordnet/&gt;.</span> </p> </li> 
      </ul> </p> <p>XPath ist eine relativ komplizierte Notation. Weitere Informationen finden Sie unter: </p> <p>Siehe <a href="https://www.w3schools.com/xml/xpath_intro.asp" scope="external" format="html"> https://www.w3schools.com/xpath/ </a> </p> </li> 
      <li id="li_84999D07E0AE4265BC7928BBB49957B9"> <span class="uicontrol"> Feld </span> <p>Definiert den Attribut name -Wert, der für jedes generierte &lt;meta&gt; -Tag verwendet wird. </p> </li> 
      <li id="li_E125788D0F5242958BD790E26A675C20"> <span class="uicontrol"> Metadaten? </span> <p>Verursacht, dass <span class="uicontrol"> Feld </span> zu einer Dropdown-Liste wird, aus der Sie definierte Metadatenfelder für das aktuelle Konto auswählen können. </p> <p>Der Wert <span class="uicontrol"> Feld </span> kann ein nicht definiertes Metadatenfeld sein, falls gewünscht. Manchmal ist ein nicht definiertes Metadatenfeld nützlich, um Inhalte zu erstellen, die von <span class="wintitle"> Filterskript </span> verwendet werden. </p> <p>Siehe <a href="../c-about-settings-menu/c-about-filtering-menu.md#concept_E56B73D625854AB2A899EF2D56CFCB47" type="concept" format="dita" scope="local"> Informationen zum Filtern von Skript </a>. </p> <p>Wenn Index Connector XML-Dokumente mit mehreren Treffern in einem Zuordnungsfeld verarbeitet, werden die verschiedenen Werte im resultierenden zwischengespeicherten Dokument zu einem einzigen Wert verkettet. Standardmäßig werden diese Werte mit einem Kommatrennzeichen kombiniert. Angenommen, der entsprechende Wert <span class="wintitle"> Feld </span> ist ein definiertes Metadatenfeld. Darüber hinaus ist für dieses Feld das Attribut <span class="wintitle"> Zulassungslisten </span> festgelegt. In diesem Fall wird der Wert "Listentrennzeichen"des Felds, das erste definierte Trennzeichen, in der Verkettung verwendet. </p> </li> 
      <li id="li_9F435EFB3EC74B409EC82A851824609F"> <span class="uicontrol"> Primärschlüssel? </span> <p>Nur eine Zuordnungsdefinition wird als Primärschlüssel identifiziert. Dieses Feld wird zum eindeutigen Verweis, der angezeigt wird, wenn dieses Dokument zum Index hinzugefügt wird. Dieser Wert wird in der URL des Dokuments im Index verwendet. </p> <p>Die <span class="uicontrol">-Werte für den Primären Schlüssel </span> müssen in allen Dokumenten eindeutig sein, die von der Index Connector-Konfiguration repräsentiert werden. Alle gefundenen Duplikate werden ignoriert. Wenn Ihre Quelldokumente keinen einzigen eindeutigen Wert enthalten, der als <span class="uicontrol"> Primärer Schlüssel </span> verwendet werden soll, aber zwei oder mehr Felder zusammen <i>einen eindeutigen Bezeichner bilden können, können Sie den Primären Schlüssel <span class="uicontrol"> definieren, indem Sie mehrere <span class="uicontrol"> Tags </span> mit einer vertikalen Leiste ("|") kombinieren, die die Werte trennen.</i></span> </p> </li> 
      <li id="li_9F435EFB3EC74B409EC82A851824610G"> <span class="uicontrol"> HTML entfernen?  </span> <p>Wenn diese Option aktiviert ist, werden alle in den Daten dieses Felds gefundenen HTML-Tags entfernt. </p> </li> 
      <li id="li_6302D18971AD439FBECE27742649C56B"> <span class="uicontrol"> Aktion </span> <p>Ermöglicht das Hinzufügen von Zeilen zur Zuordnung oder das Entfernen von Zeilen aus der Zuordnung. Die Reihenfolge der Zeilen ist nicht wichtig. </p> </li> 
      </ul> </p> </td> 
      </tr> 
    </tbody> 
    </table>

1. (Optional) Klicken Sie auf **[!UICONTROL Setup Maps]** , um ein Beispiel Ihrer Datenquelle herunterzuladen. Die Daten werden auf Indizierungseignung geprüft. Diese Funktion ist nur für Text- und Feed-Typen verfügbar.
1. (Optional) Klicken Sie auf **[!UICONTROL Preview]** , um die tatsächliche Funktionsweise der Konfiguration zu testen. Diese Funktion ist nur für Text- und Feed-Typen verfügbar.
1. Klicken Sie auf **[!UICONTROL Add]** , um die Konfiguration zur Seite [!DNL Index Connector Definitions] und zur Dropdown-Liste [!DNL Index Connector Configurations] auf der Seite [!DNL URL Entrypoints] hinzuzufügen.

   Siehe [Über URL-Endpunkte](../c-about-settings-menu/c-about-crawling-menu.md#concept_5D857E3B5C124E85BC0B5AE77A509573).
1. Klicken Sie auf der Seite [!DNL Index Connector Definitions] auf **[!UICONTROL rebuild your staged site index]**.
1. (Optional) Führen Sie auf der Seite [!DNL Index Connector Definitions] einen der folgenden Schritte aus:

   * Klicken Sie auf **[!UICONTROL History]** , um alle Änderungen rückgängig zu machen, die Sie vorgenommen haben.

      Siehe [Verwendung der Option Verlauf](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Klicken **[!UICONTROL Live]**.

      Siehe [Anzeigen von Live-Einstellungen](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Klicken **[!UICONTROL Push Live]**.

      Siehe [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Bearbeiten einer Index Connector-Definition {#task_DCFC9C6A9964421DB5AB6C25DEE98DE9}

Sie können einen vorhandenen Index Connector bearbeiten, den Sie definiert haben.

>[!NOTE]
>
>Es stehen nicht alle Optionen zur Verfügung, die Sie ändern können, z. B. den Index-Connector-Namen oder den Typ aus der Dropdownliste [!DNL Type] .

**So bearbeiten Sie eine Index Connector-Definition**

1. Klicken Sie im Produktmenü auf **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Index Connector]**.
1. Klicken Sie auf der Seite [!DNL Index Connector] unter der Spaltenüberschrift [!DNL Actions] auf **[!UICONTROL Edit]** für einen Index Connector-Definitionsnamen, dessen Einstellungen Sie ändern möchten.
1. Legen Sie auf der Seite [!DNL Index Connector Edit] die gewünschten Optionen fest.

   Siehe Tabelle der Optionen unter [Definition des Index-Connectors](../c-about-settings-menu/c-about-crawling-menu.md#task_96779B651A654E1F871F55D6DBBC8886) hinzufügen.
1. Klicken **[!UICONTROL Save Changes]**.
1. (Optional) Klicken Sie auf der Seite [!DNL Index Connector Definitions] auf **[!UICONTROL rebuild your staged site index]**.
1. (Optional) Führen Sie auf der Seite [!DNL Index Connector Definitions] einen der folgenden Schritte aus:

   * Klicken Sie auf **[!UICONTROL History]** , um alle Änderungen rückgängig zu machen, die Sie vorgenommen haben.

      Siehe [Verwendung der Option Verlauf](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Klicken **[!UICONTROL Live]**.

      Siehe [Anzeigen von Live-Einstellungen](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Klicken **[!UICONTROL Push Live]**.

      Siehe [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Anzeigen der Einstellungen einer Index Connector-Definition {#task_D0B71A7426E54247BDB3468EC576D871}

Sie können die Konfigurationseinstellungen einer vorhandenen Index-Connector-Definition überprüfen.

Nachdem der Seite [!DNL Index Connector Definitions] eine Definition des Index-Connectors hinzugefügt wurde, können Sie die Einstellung Typ nicht ändern. Stattdessen müssen Sie die Definition löschen und dann eine neue hinzufügen.

**So zeigen Sie die Einstellungen einer Index Connector-Definition an**

1. Klicken Sie im Produktmenü auf **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Index Connector]**.
1. Klicken Sie auf der Seite [!DNL Index Connector] unter der Spaltenüberschrift [!DNL Actions] auf **[!UICONTROL Edit]** für einen Index Connector-Definitionsnamen, dessen Einstellungen Sie überprüfen oder bearbeiten möchten.

## Kopieren einer Index Connector-Definition {#task_3AD55DF07FC44A748D0EFDAB7B35699B}

Sie können eine vorhandene Index Connector-Definition kopieren, um sie als Grundlage für einen neuen Index Connector zu verwenden, den Sie erstellen möchten.

Beim Kopieren einer Index Connector-Definition ist die kopierte Definition standardmäßig deaktiviert. Um die Definition zu aktivieren oder zu aktivieren, müssen Sie sie auf der Seite [!DNL Index Connector Edit] bearbeiten und **[!UICONTROL Enable]** auswählen.

Siehe [Bearbeiten einer Index Connector-Definition](../c-about-settings-menu/c-about-crawling-menu.md#task_DCFC9C6A9964421DB5AB6C25DEE98DE9).

**So kopieren Sie eine Index-Connector-Definition**

1. Klicken Sie im Produktmenü auf **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Index Connector]**.
1. Klicken Sie auf der Seite [!DNL Index Connector] unter der Spaltenüberschrift [!DNL Actions] auf **[!UICONTROL Copy]** für einen Index Connector-Definitionsnamen, dessen Einstellungen Sie duplizieren möchten.
1. Geben Sie auf der Seite [!DNL Index Connector Copy] den neuen Namen der Definition ein.
1. Klicken **[!UICONTROL Copy]**.
1. (Optional) Führen Sie auf der Seite [!DNL Index Connector Definitions] einen der folgenden Schritte aus:

   * Klicken Sie auf **[!UICONTROL History]** , um alle Änderungen rückgängig zu machen, die Sie vorgenommen haben.

      Siehe [Verwendung der Option Verlauf](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Klicken **[!UICONTROL Live]**.

      Siehe [Anzeigen von Live-Einstellungen](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Klicken **[!UICONTROL Push Live]**.

      Siehe [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Umbenennen einer Index Connector-Definition {#task_5132118FC21B47D99881E0ED425225D7}

Sie können den Namen einer vorhandenen Index Connector-Definition ändern.

Nachdem Sie die Definition umbenannt haben, aktivieren Sie **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL URL Entrypoints]**. Sie möchten sicherstellen, dass der neue Definitionsname in der Dropdown-Liste auf der Seite [!DNL URL Entrypoints] angezeigt wird.

Siehe [Hinzufügen mehrerer URL-Einstiegspunkte, die indiziert werden sollen](../c-about-settings-menu/c-about-crawling-menu.md#task_2338A47387D74CFDAC4D4EF4A367ED45).

**So benennen Sie eine Index Connector-Definition um**

1. Klicken Sie im Produktmenü auf **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Index Connector]**.
1. Klicken Sie auf der Seite [!DNL Index Connector] unter der Spaltenüberschrift [!DNL Actions] unter Index Connector-Definitionsname auf **[!UICONTROL Rename]** , den Sie ändern möchten.
1. Geben Sie auf der Seite [!DNL Index Connector Rename] im Feld [!DNL Name] den neuen Namen der Definition ein.
1. Klicken **[!UICONTROL Rename]**.
1. Klicken Sie auf **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL URL Entrypoints]**. Wenn der Name des vorherigen Index-Connectors in der Liste vorhanden ist, entfernen Sie ihn und fügen Sie den neu umbenannten Eintrag hinzu.

   Siehe [Hinzufügen mehrerer URL-Einstiegspunkte, die indiziert werden sollen](../c-about-settings-menu/c-about-crawling-menu.md#task_2338A47387D74CFDAC4D4EF4A367ED45). 1. (Optional) Führen Sie auf der Seite [!DNL Index Connector Definitions] einen der folgenden Schritte aus:

   * Klicken Sie auf **[!UICONTROL History]** , um alle Änderungen rückgängig zu machen, die Sie vorgenommen haben.

      Siehe [Verwendung der Option Verlauf](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Klicken **[!UICONTROL Live]**.

      Siehe [Anzeigen von Live-Einstellungen](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Klicken **[!UICONTROL Push Live]**.

      Siehe [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Löschen einer Index Connector-Definition {#task_6B0BD5D0C09F4597A401B0F3AC7C7EA7}

Sie können eine vorhandene Index Connector-Definition löschen, die Sie nicht mehr benötigen oder verwenden.

**So löschen Sie eine Index Connector-Definition**

1. Klicken Sie im Produktmenü auf **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Index Connector]**.
1. Klicken Sie auf der Seite [!DNL Index Connector Definitions] unter der Spaltenüberschrift [!DNL Actions] für den Definitionsnamen des Index Connector, den Sie entfernen möchten, auf **[!UICONTROL Delete]** .
1. Klicken Sie auf der Seite [!DNL Index Connector Delete] auf **[!UICONTROL Delete]**.
