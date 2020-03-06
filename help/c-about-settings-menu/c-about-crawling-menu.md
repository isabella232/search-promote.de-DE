---
description: Verwenden Sie das Menü "Crawling"(Crawling-Menü) mit Datums- und URL-Masken, Kennwörtern, Inhaltstypen, Verbindungen, Formulardefinitionen und URL-Einstiegspunkten.
seo-description: Verwenden Sie das Menü "Crawling"(Crawling-Menü) mit Datums- und URL-Masken, Kennwörtern, Inhaltstypen, Verbindungen, Formulardefinitionen und URL-Einstiegspunkten.
seo-title: Menü "Crawling"
solution: Target
subtopic: Crawling
title: Menü "Crawling"
topic: Settings,Site search and merchandising
uuid: a58c03bf-90f7-4b5b-91ff-988b95c246b0
translation-type: tm+mt
source-git-commit: 77a4e88c7bf47b637030e3935a39dfdf4f175e80

---


# Menü &quot;Crawling&quot;{#about-the-crawling-menu}

Verwenden Sie das Menü &quot;Crawling&quot;(Crawling-Menü) mit Datums- und URL-Masken, Kennwörtern, Inhaltstypen, Verbindungen, Formulardefinitionen und URL-Einstiegspunkten.

## Informationen zu URL-Einstiegspunkten {#concept_5D857E3B5C124E85BC0B5AE77A509573}

Die meisten Websites verfügen über einen primären Einstiegspunkt oder eine Homepage, die/die ein Kunde ursprünglich besucht. Dieser Haupteinstiegspunkt ist die URL-Adresse, von der aus der Suchroboter Indexcrawling beginnt. Wenn Ihre Website jedoch über mehrere Domänen oder Subdomänen verfügt oder Teile Ihrer Site nicht vom primären Einstiegspunkt aus verknüpft sind, können Sie mit URL-Einstiegspunkten weitere Einstiegspunkte hinzufügen.

Alle Webseiten unter jedem angegebenen URL-Einstiegspunkt werden indiziert. Sie können URL-Einstiegspunkte mit Masken kombinieren, um genau zu steuern, welche Teile einer Website Sie indizieren möchten. Sie müssen Ihren Website-Index neu erstellen, bevor die Auswirkungen der URL-Entrypoints-Einstellungen für Kunden sichtbar sind.

Der Haupteinstiegspunkt ist normalerweise die URL der Website, die Sie indizieren und suchen möchten. Sie konfigurieren diesen Haupteinstiegspunkt in den Kontoeinstellungen.

Siehe [Konfigurieren der Kontoeinstellungen](../c-about-settings-menu/c-about-account-options-menu.md#task_80A38D0C8E4F453395BD67B81E4B45D9).

Nachdem Sie den Einstiegspunkt der Haupt-URL angegeben haben, können Sie optional zusätzliche Einstiegspunkte angeben, die Sie in der richtigen Reihenfolge durchsuchen möchten. Meistens geben Sie zusätzliche Einstiegspunkte für Webseiten an, die nicht von Seiten unter dem Haupteinstiegspunkt verlinkt sind. Geben Sie zusätzliche Einstiegspunkte an, wenn Ihre Website mehr als eine Domäne umfasst (siehe folgendes Beispiel):

`https://www.domain.com/`

`https://www.domain.com/not_linked/but_search_me_too/`

`https://more.domain.com/`

Sie qualifizieren jeden Einstiegspunkt mit einem oder mehreren der folgenden durch Leerzeichen getrennten Suchbegriffe in der unten stehenden Tabelle. Diese Suchbegriffe beeinflussen, wie die Seite indiziert wird.

**Wichtig**: Achten Sie darauf, einen bestimmten Suchbegriff vom Einstiegspunkt und von einem Leerzeichen voneinander zu trennen. Komma ist kein gültiges Trennzeichen.

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
   <td colname="col2"> <p> Wenn Sie den Text nicht auf der Einstiegsseite indizieren möchten, aber den Links auf der Seite folgen möchten, fügen Sie 
     <userinput>
       noindex 
     </userinput> nach dem Einstiegspunkt. </p> <p>Trennen Sie den Suchbegriff vom Einstiegspunkt durch ein Leerzeichen, wie im folgenden Beispiel dargestellt: </p> <p> <code> https://www.my-additional-domain.com/more_pages/main.html&amp;nbsp;noindex </code> </p> <p>Dieser Suchbegriff entspricht einem Roboter-Meta-Tag mit 
     <userinput>
       content="noindex" 
     </userinput>) zwischen den 
     <userinput>
       &lt;head&gt; 
     </userinput>... 
     <userinput>
       &lt;/head&gt; 
     </userinput> -Tags der Einstiegsseite. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>nofollow </p> </td> 
   <td colname="col2"> <p> Wenn Sie den Text auf der Einstiegsseite indizieren möchten, aber keinem der Links auf der Seite folgen möchten, fügen Sie 
     <userinput>
       nofollow 
     </userinput> nach dem Einstiegspunkt. </p> <p>Trennen Sie den Suchbegriff vom Einstiegspunkt durch ein Leerzeichen, wie im folgenden Beispiel dargestellt: </p> <p> <code> https://www.domain.com/not_linked/directory_listing&amp;nbsp;nofollow </code> </p> <p>Dieser Suchbegriff entspricht einem Roboter-Meta-Tag mit 
     <userinput>
       content="nofollow" 
     </userinput> zwischen 
     <userinput>
       &lt;head&gt; 
     </userinput>... 
     <userinput>
       &lt;/head&gt; 
     </userinput> -Tag einer Einstiegsseite. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>form </p> </td> 
   <td colname="col2"> <p> Wenn der Einstiegspunkt eine Anmeldeseite ist, 
     <userinput>
       form 
     </userinput> wird normalerweise verwendet, damit der Suchroboter das Anmeldeformular senden und die entsprechenden Cookies empfangen kann, bevor er die Website durchsucht. Wenn das Schlüsselwort "form"verwendet wird, wird die Einstiegsseite nicht indiziert und der Suchroboter markiert die Einstiegsseite nicht als durchgekrackt. Verwenden Sie die   
     <userinput>
       nofollow 
     </userinput> wenn Sie nicht möchten, dass der Suchroboter den Links der Seite folgt. </p> </td> 
  </tr> 
 </tbody> 
</table>

Siehe auch [Informationen zu Inhaltstypen](../c-about-settings-menu/c-about-crawling-menu.md#concept_6FEA1355C0374500B4C53090C34A8A07).

Siehe auch [Info zu Index Connector](../c-about-settings-menu/c-about-crawling-menu.md#concept_CA6921E2FBF641F9B4F60C92B32AFA84).

## Hinzufügen mehrerer URL-Einstiegspunkte, die indiziert werden sollen {#task_2338A47387D74CFDAC4D4EF4A367ED45}

Wenn Ihre Website mehrere Domänen oder Subdomänen hat und Sie diese durchsuchen möchten, können Sie URL-Einstiegspunkte verwenden, um weitere URLs hinzuzufügen.

Um den Haupteinstiegspunkt für die URL Ihrer Website festzulegen, verwenden Sie die Kontoeinstellungen.

Siehe [Konfigurieren der Kontoeinstellungen](../c-about-settings-menu/c-about-account-options-menu.md#task_80A38D0C8E4F453395BD67B81E4B45D9).

**So fügen Sie mehrere URL-Einstiegspunkte hinzu, die Sie indizieren möchten**

1. Klicken Sie im Produktmenü auf **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL URL Entrypoints]**.
1. Geben Sie auf der [!DNL URL Entrypoints] Seite im [!DNL Entrypoints] Feld eine URL-Adresse pro Zeile ein.
1. (Optional) Wählen Sie in der **[!UICONTROL Add Index Connector Configurations]** Dropdownliste einen Indexanschluss aus, den Sie als Einstiegspunkt für die Indexierung hinzufügen möchten.

   Die Dropdownliste ist nur verfügbar, wenn Sie zuvor eine oder mehrere Indexschnittstellendefinitionen hinzugefügt haben.

   ![](assets/url_entrypoints_index_connector.png)

   Siehe [Hinzufügen einer Index-Connector-Definition](../c-about-settings-menu/c-about-crawling-menu.md#task_96779B651A654E1F871F55D6DBBC8886).
1. Klicken **[!UICONTROL Save Changes]**.
1. (Optional) Führen Sie einen der folgenden Schritte aus:

   * Klicken Sie auf **[!UICONTROL History]** , um alle vorgenommenen Änderungen wiederherzustellen.

      Siehe [Verwenden der Option](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)Verlauf.

   * Klicken **[!UICONTROL Live]**.

      Siehe [Live-Einstellungen](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)anzeigen.

   * Klicken **[!UICONTROL Push Live]**.

      Siehe [Pushing-Einstellungen](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## URL-Masken {#concept_8039DFC53FF3410AA494D602F71BA164}

URL-Masken sind Muster, die bestimmen, welche Ihrer Websites die Suchroboterindizes oder nicht Indizes dokumentieren.

Stellen Sie sicher, dass Sie Ihren Site-Index neu erstellen, damit die Ergebnisse Ihrer URL-Masken für Ihre Kunden sichtbar sind.

Siehe [Konfigurieren eines inkrementellen Indexes einer gestaffelten Website](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0).

Im Folgenden sind zwei Arten von URL-Masken aufgeführt, die Sie verwenden können:

* URL-Masken einschließen
* URL-Masken ausschließen

&quot;URL-Masken einschließen&quot;weist den Suchroboter an, alle Dokumente zu indizieren, die dem Muster der Maske entsprechen.

URL-Masken ausschließen weist den Suchroboter an, die passenden Dokumente zu indizieren.

Während der Suchroboter von einem Link zum Link durch Ihre Website reist, findet er URLs und sucht nach Masken, die mit diesen URLs übereinstimmen. Die erste Übereinstimmung bestimmt, ob diese URL in den Index aufgenommen oder ausgeschlossen werden soll. Entspricht keine Maske einer gefundenen URL, wird diese URL aus dem Index verworfen.

URL-Masken für Einstiegs-URLs einschließen werden automatisch generiert. Dadurch wird sichergestellt, dass alle auf Ihrer Website angetroffenen Dokumente indiziert sind. Es entfernt auch bequem mit Links, die Ihre Website &quot;verlassen&quot;. Wenn beispielsweise eine indizierte Seite mit https://www.yahoo.com verknüpft ist, wird diese URL nicht vom Suchroboter indiziert, da sie nicht mit der automatisch von der Einstiegs-URL generierten Einschlussmaske übereinstimmt.

Jede URL-Maske, die Sie angeben, muss sich in einer separaten Zeile befinden.

Die Maske kann Folgendes angeben:

* Ein vollständiger Pfad wie in `https://www.mydomain.com/products.html`.
* Ein teilweiser Pfad wie in `https://www.mydomain.com/products`.
* Eine URL, die Platzhalter wie in verwendet `https://www.mydomain.com/*.html`.
* Ein regulärer Ausdruck (für fortgeschrittene Benutzer).

   Um eine Maske zu einem regulären Ausdruck zu machen, fügen Sie das Schlüsselwort `regexp` zwischen dem Maskentyp ( `exclude` oder `include`) und der URL-Maske ein.

Im Folgenden sehen Sie ein einfaches Beispiel für eine URL-Maske zum Ausschließen:

```
exclude https://www.mydomain.com/photos
```

Da es sich bei diesem Beispiel um eine URL-Maske zum Ausschließen handelt, wird jedes Dokument, das dem Muster entspricht, nicht indiziert. Das Muster stimmt mit allen gefundenen Elementen überein, sowohl mit Dateien als auch mit Ordnern, sodass `https://www.mydomain.com/photos.html` und `https://www.mydomain.com/photos/index.html`beide mit der Ausschluss-URL übereinstimmen, nicht indiziert werden. Um nur Dateien im `/photos/` Ordner zuzuordnen, muss die URL-Maske einen nachfolgenden Schrägstrich enthalten (siehe folgendes Beispiel):

```
exclude https://www.mydomain.com/photos/
```

Im folgenden Beispiel für die Ausschlussmaske wird eine Platzhalterkarte verwendet. Er weist den Suchroboter an, Dateien mit der Erweiterung &quot;.pdf&quot;zu übersehen. Der Suchroboter fügt diese Dateien nicht zu Ihrem Index hinzu.

```
exclude *.pdf
```

Eine einfache URL-Maske zum Einschließen lautet wie folgt:

```
include https://www.mydomain.com/news/
```

Es werden nur Dokumente indiziert, die über eine Reihe von Links von einem URL-Einstiegspunkt aus verknüpft sind oder die selbst als URL-Einstiegspunkt verwendet werden. Wenn die URL eines Dokuments nur als URL-Maske zum Einschließen aufgelistet wird, wird kein nicht verknüpftes Dokument indiziert. Um Ihrem Index nicht verknüpfte Dokumente hinzuzufügen, können Sie die Funktion &quot;URL-Einstiegspunkte&quot;verwenden.

Siehe [Informationen zu URL-Einträgen](../c-about-settings-menu/c-about-crawling-menu.md#concept_5D857E3B5C124E85BC0B5AE77A509573).

Masken einschließen und Masken ausschließen können zusammen funktionieren. Sie können einen großen Teil Ihrer Website von der Indexierung ausschließen, indem Sie eine URL-Maske zum Ausschließen erstellen, aber eine oder mehrere der ausgeschlossenen Seiten mit einer URL-Maske zum Einschließen einschließen. Angenommen, Ihre Einstiegspunkt-URL lautet wie folgt:

```
https://www.mydomain.com/photos/
```

Der Suchroboter durchsucht und indiziert alle Seiten unter `/photos/summer/`und `/photos/spring/` (vorausgesetzt, dass es Links zu mindestens einer Seite in jedem Verzeichnis aus dem `/photos/fall/` `photos` Ordner gibt). Dieses Verhalten liegt daran, dass die Verknüpfungspfade es dem Suchroboter ermöglichen, die Dokumente in den Ordnern `/summer/`, `/spring/`und `/fall/`zu finden, und die Ordner-URLs mit der Include-Maske übereinstimmen, die automatisch von der Einstiegspunkt-URL generiert wird.

Sie können alle Seiten im `/fall/` Ordner mit einer URL-Maske ausschließen, wie im folgenden Beispiel dargestellt:

```
exclude https://www.mydomain.com/photos/fall/
```

Oder fügen Sie selektiv nur `/photos/fall/redleaves4.html` als Teil des Indexes mit der folgenden URL-Maske ein:

```
include https://www.mydomain.com/photos/fall/redleaves4.html
```

Damit die beiden oben genannten Maskenbeispiele wie gewünscht funktionieren, wird zuerst die Maske zum Einschließen aufgelistet, wie im Folgenden:

```
include https://www.mydomain.com/photos/fall/redleaves4.html 
exclude https://www.mydomain.com/photos/fall/
```

Da der Suchroboter den Anweisungen in der Reihenfolge folgt, in der sie aufgelistet sind, schließt der Suchroboter zunächst die übrigen Dateien im `/photos/fall/redleaves4.html`Ordner ein `/fall` und schließt sie dann aus.

Wenn die Anweisungen anders angegeben werden wie in der folgenden Tabelle:

```
exclude https://www.mydomain.com/photos/fall/ 
include https://www.mydomain.com/photos/fall/redleaves4.html
```

Dann `/photos/fall/redleaves4.html` wird nicht einbezogen, auch wenn die Maske angibt, dass sie eingeschlossen ist.

Eine zuerst angezeigte URL-Maske hat immer Vorrang vor einer URL-Maske, die später in den Maskeneinstellungen angezeigt wird. Wenn der Suchroboter außerdem auf eine Seite trifft, die mit einer URL-Maske zum Einschließen und einer URL-Maske zum Ausschließen übereinstimmt, hat die zuerst aufgeführte Maske immer Vorrang.

Siehe [Konfigurieren eines inkrementellen Indexes einer gestaffelten Website](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0).

## Grundlagen zur Verwendung von Suchbegriffen mit URL-Masken {#section_7609A7A6D79B482ABCA8900886541AAB}

Sie können jede Include-Maske mit einem oder mehreren durch Leerzeichen getrennten Suchbegriffen qualifizieren, was sich auf die Indexierung der entsprechenden Seiten auswirkt.

Ein Komma ist nicht als Trennzeichen zwischen der Maske und dem Schlüsselwort gültig. Sie können nur Leerzeichen verwenden.

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
   <td colname="col2"> <p> Wenn Sie den Text nicht auf den Seiten indizieren möchten, die mit der URL-Maske übereinstimmen, aber die Links zu den entsprechenden Seiten befolgen möchten, fügen Sie 
     <userinput>
       noindex 
     </userinput> nach der URL-Maske einschließen. Stellen Sie sicher, dass Sie den Suchbegriff von der Maske mit einem Leerzeichen trennen, wie im folgenden Beispiel gezeigt: </p> <p> <code> include&amp;nbsp;*.swf&amp;nbsp;noindex </code> </p> <p>Das obige Beispiel gibt an, dass der Suchroboter alle Links aus Dateien mit der Variablen 
     <userinput>
       .swf 
     </userinput> , deaktiviert jedoch die Indizierung des gesamten Textes, der in diesen Dateien enthalten ist. </p> <p>Die  
     <userinput>
       noindex 
     </userinput> Suchbegriff entspricht einem Roboter-Meta-Tag mit 
     <userinput>
       content="noindex" 
     </userinput> zwischen 
     <userinput>
       &lt;head&gt;...&lt;/head&gt; 
     </userinput> -Tags von übereinstimmenden Seiten. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>nofollow </p> </td> 
   <td colname="col2"> <p> Wenn Sie den Text auf den Seiten indizieren möchten, die mit der URL-Maske übereinstimmen, aber nicht den Links der entsprechenden Seite folgen möchten, fügen Sie 
     <userinput>
       nofollow 
     </userinput> nach der URL-Maske einschließen. Stellen Sie sicher, dass Sie den Suchbegriff von der Maske mit einem Leerzeichen trennen, wie im folgenden Beispiel gezeigt: </p> <p> <code> include&amp;nbsp;https://www.mydomain.com/photos&amp;nbsp;nofollow </code> </p> <p>Die  
     <userinput>
       nofollow 
     </userinput> Suchbegriff entspricht einem Roboter-Meta-Tag mit 
     <userinput>
       content="nofollow" 
     </userinput> zwischen 
     <userinput>
       &lt;head&gt;...&lt;/head&gt; 
     </userinput> -Tags von übereinstimmenden Seiten. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>regexp </p> </td> 
   <td colname="col2"> <p>Dient zum Einschließen und Ausschließen von Masken. </p> <p>Jede URL-Maske, der 
     <userinput>
       regexp 
     </userinput> wird als regulärer Ausdruck behandelt. Wenn der Suchroboter auf Dokumente trifft, die mit einer URL-Maske für reguläre Ausdrücke übereinstimmen, werden diese Dokumente nicht indiziert. Wenn der Suchroboter auf Dokumente trifft, die mit einer URL-Maske für reguläre Ausdrücke übereinstimmen, werden diese Dokumente indiziert. Angenommen, Sie haben die folgende URL-Maske: </p> <p> <code> exclude&amp;nbsp;regexp&amp;nbsp;^.*/products/.*\.html$ </code> </p> <p>Der Suchroboter schließt übereinstimmende Dateien wie 
     <userinput>
       https://www.mydomain.com/products/page1.html 
     </userinput> </p> <p>Wenn Sie die folgende URL-Maske für regulären Ausdruck ausschließen hatten: </p> <p> <code> exclude&amp;nbsp;regexp&amp;nbsp;^.*\?..*$ </code> </p> <p>Der Suchroboter enthält keine URL, die einen CGI-Parameter wie 
     <userinput>
       https://www.mydomain.com/cgi/prog/?arg1=val1&amp;arg2=val2 
     </userinput>. </p> <p>Wenn Sie die folgende URL-Maske für reguläre Ausdrücke haben: </p> <p> <code> include&amp;nbsp;regexp&amp;nbsp;^.*\.swf$&amp;nbsp;noindex </code> </p> <p>Der Suchroboter folgt allen Links von Dateien mit der Erweiterung ".swf". Die  
     <userinput>
       noindex 
     </userinput> gibt auch an, dass der Text der übereinstimmenden Dateien nicht indiziert ist. </p> <p>Siehe <a href="../c-appendices/r-regular-expressions.md#reference_B5BA7D61D82E4109A01D2A2D964E3A6A" type="reference" format="dita" scope="local"> Reguläre Ausdrücke </a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Hinzufügen von URL-Masken zum Indexieren von Teilen Ihrer Website {#task_E1AFC17C746048B8843013D979E082C1}

Sie können [!DNL URL Masks] festlegen, welche Teile Ihrer Website durchsucht und indiziert werden sollen.

Verwenden Sie das Feld &quot;URL-Masken testen&quot;, um zu testen, ob ein Dokument nach dem Index enthalten ist oder nicht.

Stellen Sie sicher, dass Sie Ihren Site-Index neu erstellen, damit die Ergebnisse Ihrer URL-Masken für Ihre Kunden sichtbar sind.

Siehe [Konfigurieren eines inkrementellen Indexes einer gestaffelten Website](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0).

**So fügen Sie URL-Masken hinzu, um Teile Ihrer Website zu indizieren oder nicht**

1. Klicken Sie im Produktmenü auf **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL URL Masks]**.
1. (Optional) Geben Sie auf der [!DNL URL Masks] Seite im **[!UICONTROL Test URL Masks]** Feld eine Test-URL-Maske von Ihrer Website ein und klicken Sie dann auf **[!UICONTROL Test]**.
1. Geben Sie in das [!DNL URL Masks] Feld `include` (um eine Website hinzuzufügen, die durchsucht und indexiert werden soll) oder geben Sie `exclude` (um zu verhindern, dass eine Website durchsucht und indiziert wird) gefolgt von der Adresse der URL-Maske ein.

   Geben Sie pro Zeile eine URL-Maske-Adresse ein. Beispiel:

   ```
   include https://www.mycompany.com/summer 
   include https://www.mycompany.com/spring 
   exclude regexp .*\.xml 
   exclude https://www.mycompany.com/fall
   ```

1. Klicken **[!UICONTROL Save Changes]**.
1. (Optional) Führen Sie einen der folgenden Schritte aus:

   * Klicken Sie auf **[!UICONTROL History]** , um alle vorgenommenen Änderungen wiederherzustellen.

      Siehe [Verwenden der Option](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)Verlauf.

   * Klicken **[!UICONTROL Live]**.

      Siehe [Live-Einstellungen](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)anzeigen.

   * Klicken **[!UICONTROL Push Live]**.

      Siehe [Pushing-Einstellungen](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Info zu Datumsmasken {#concept_F4F1F58A646F4A86B8650EC46FDCEF66}

Sie können Datumsmasken verwenden, um Dateien je nach Alter der Datei in die Suchergebnisse einzuschließen oder auszuschließen.

Stellen Sie sicher, dass Sie Ihren Site-Index neu erstellen, damit die Ergebnisse Ihrer URL-Masken für Ihre Kunden sichtbar sind.

Siehe [Konfigurieren eines inkrementellen Indexes einer gestaffelten Website](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0).

Im Folgenden sind zwei Arten von Datumsmasken aufgeführt, die Sie verwenden können:

* Datumsmasken einschließen (&quot;einschließlich Tage&quot;und &quot;Datum einschließen&quot;)

   Schließen Sie Datumsmasken-Indexdateien ein, die am oder vor dem angegebenen Datum datiert sind.
* Datumsmasken ausschließen (&quot;Ausschluss-Tage&quot;und &quot;Ausschlussdatum&quot;)

   Schließen Sie Datumsmasken-Indexdateien aus, die am oder vor dem angegebenen Datum datiert sind.

Standardmäßig wird das Dateidatum anhand der Meta-Tag-Informationen bestimmt. Wenn kein Meta-Tag gefunden wird, wird das Datum einer Datei anhand des HTTP-Headers ermittelt, der vom Server empfangen wird, wenn der Suchroboter eine Datei herunterlädt.

Jede angegebene Datumsmaske muss sich in einer separaten Zeile befinden.

Die Maske kann Folgendes angeben:

* Ein vollständiger Pfad wie in `https://www.mydomain.com/products.html`
* Ein partieller Pfad wie in `https://www.mydomain.com/products`
* Eine URL, die Platzhalter verwendet `https://www.mydomain.com/*.html`
* Ein regulärer Ausdruck. Um eine Maske zu einem regulären Ausdruck zu machen, fügen Sie den Suchbegriff `regexp` vor der URL ein.

Datumsmasken einschließen und ausschließen können auf eine der beiden folgenden Arten ein Datum angeben. Die Masken werden nur angewendet, wenn die entsprechenden Dateien am oder vor dem angegebenen Datum erstellt wurden:

1. Eine Anzahl von Tagen. Angenommen, Ihre Datumsmaske lautet wie folgt:

   ```
   exclude-days 30 https://www.mydomain.com/docs/archive/)
   ```

   Die Anzahl der angegebenen Tage wird zurückgezählt. Wenn die Datei am oder vor dem Datum der Ankunft am Tag datiert ist, wird die Maske angewendet.

1. Ein aktuelles Datum im Format JJJJ-MM-TT. Angenommen, Ihre Datumsmaske lautet wie folgt:

   ```
   include-date 2011-02-15 https://www.mydomain.com/docs/archive/)
   ```

   Wenn das übereinstimmende Dokument am oder vor dem angegebenen Datum datiert ist, wird die Datumsmaske angewendet.

Im Folgenden finden Sie ein einfaches Beispiel für eine Ausschluss-Datumsmaske:

```
exclude-days 90 https://www.mydomain.com/docs/archive
```

Da es sich hierbei um eine Ausschlussdatumsmaske handelt, wird jede Datei, die dem Muster entspricht, nicht indiziert und ist mindestens 90 Tage alt. Wenn Sie ein Dokument ausschließen, wird kein Text indiziert und aus dieser Datei werden keine Links gefolgt. Die Datei wird effektiv ignoriert. In diesem Beispiel stimmen Dateien und Ordner möglicherweise mit dem angegebenen URL-Muster überein. Beachten Sie, dass sowohl `https://www.mydomain.com/docs/archive.html` als auch `https://www.mydomain.com/docs/archive/index.html` dem Muster entsprechen und nicht indiziert sind, wenn sie 90 Tage alt oder älter sind. Um nur Dateien im `/docs/archive/` Ordner zuzuordnen, muss die Datumsmaske einen nachfolgenden Schrägstrich wie folgt enthalten:

```
exclude-days 90 https://www.mydomain.com/docs/archive/
```

Datumsmasken können auch mit Platzhaltern verwendet werden. Die folgende Ausschlussmaske weist den Suchroboter an, Dateien mit der Erweiterung &quot;.pdf&quot;zu übersehen, die am oder vor dem 15.02.2011 datiert sind. Der Suchroboter fügt Ihrem Index keine übereinstimmenden Dateien hinzu.

```
exclude-date 2011-02-15 *.pdf
```

Die Option &quot;Datumsmaske einschließen&quot;sieht ähnlich aus. Dem Index werden nur übereinstimmende Dateien hinzugefügt. Im folgenden Beispiel für die Datumsmaske einschließen wird der Suchroboter angewiesen, den Text aus Dateien zu indizieren, die im Bereich der Website `/docs/archive/manual/` null Tage oder älter sind.

```
include-days 0 https://www.mydomain.com/docs/archive/manual/
```

Masken einschließen und Masken ausschließen können zusammen funktionieren. Sie können beispielsweise einen Großteil Ihrer Website von der Indizierung ausschließen, indem Sie eine Ausschlussdatumsmaske erstellen und dabei mindestens eine der ausgeschlossenen Seiten mit einer Einschließen-URL-Maske einschließen. Wenn Ihre Einstiegspunkt-URL die folgende ist:

```
https://www.mydomain.com/archive/
```

Der Suchroboter durchsucht und indiziert alle Seiten unter `/archive/summer/`, `/archive/spring/`und `/archive/fall/` (vorausgesetzt, dass es Links zu mindestens einer Seite in jedem Ordner aus dem `archive` Ordner gibt). Dieses Verhalten liegt daran, dass die Link-Pfade es dem Suchroboter ermöglichen, die Dateien in den Ordnern `/summer/`, `/spring/`und `/fall/` zu finden, und die Ordner-URLs mit der Include-Maske übereinstimmen, die automatisch von der Einstiegspunkt-URL generiert wird.

Siehe [Informationen zu URL-Einträgen](../c-about-settings-menu/c-about-crawling-menu.md#concept_5D857E3B5C124E85BC0B5AE77A509573).

Siehe [Konfigurieren der Kontoeinstellungen](../c-about-settings-menu/c-about-account-options-menu.md#task_80A38D0C8E4F453395BD67B81E4B45D9).

Sie können alle über 90 Tage alten Seiten im `/fall/` Ordner mit einer Maske zum Ausschließen des Datums ausschließen, wie im Folgenden dargestellt:

```
exclude-days 90 https://www.mydomain.com/archive/fall/
```

Sie können nur `/archive/fall/index.html` (unabhängig davon, wie alt sie ist - eine Datei mit 0 Tagen oder älter wird zugeordnet) als Teil des Index mit der folgenden Datumsmaske einschließen:

```
include-days 0 https://www.mydomain.com/archive/fall/index.html
```

Damit die beiden oben genannten Maskenbeispiele wie gewünscht funktionieren, müssen Sie die Maske zum Einschließen wie folgt auflisten:

```
include-days 0 https://www.mydomain.com/archive/fall/index.html 
exclude-days 90 https://www.mydomain.com/archive/fall/
```

Da der Suchroboter den Anweisungen in der Reihenfolge folgt, in der sie angegeben sind, schließt der Suchroboter zunächst die übrigen Dateien im `/archive/fall/index.html`Ordner ein `/fall` und schließt sie dann aus.

Wenn die Anweisungen anders angegeben werden wie in der folgenden Tabelle:

```
exclude-days 90 https://www.mydomain.com/archive/fall/ 
include-days 0 https://www.mydomain.com/archive/fall/index.html 
```

Dann `/archive/fall/index.html` wird nicht einbezogen, auch wenn die Maske dies vorgibt. Eine zuerst angezeigte Datumsmaske hat immer Vorrang vor einer Datumsmaske, die später in den Maskeneinstellungen angezeigt wird. Wenn der Suchroboter außerdem auf eine Seite trifft, die sowohl mit einer einschließenden Datumsmaske als auch mit einer Datumsmaske zum Ausschließen übereinstimmt, hat die zuerst aufgeführte Maske immer Vorrang.

Siehe [Konfigurieren eines inkrementellen Indexes einer gestaffelten Website](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0).

## Grundlagen zur Verwendung von Suchbegriffen mit Datumsmasken {#section_CCBB3E3FDBDE4725B2B571FD6594470C}

Sie können jede Include-Maske mit einem oder mehreren durch Leerzeichen getrennten Suchbegriffen qualifizieren, was sich auf die Indexierung der entsprechenden Seiten auswirkt.

Ein Komma ist nicht als Trennzeichen zwischen der Maske und dem Schlüsselwort gültig. Sie können nur Leerzeichen verwenden.

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
   <td colname="col2"> <p> Wenn Sie den Text nicht auf den Seiten indizieren möchten, die am oder vor dem von der Include-Maske angegebenen Datum datiert sind, fügen Sie 
     <userinput>
       noindex 
     </userinput> nach der Datumsmaske zum Einschließen wie im Folgenden gezeigt: </p> <p> <code> include-days&amp;nbsp;10&amp;nbsp;*.swf&amp;nbsp;noindex </code> </p> <p>Achten Sie darauf, dass Sie den Suchbegriff von der Maske durch einen Leerzeichen trennen. </p> <p>Das obige Beispiel gibt an, dass der Suchroboter alle Links von Dateien mit der Erweiterung ".swf"befolgt, die mindestens 10 Tage alt sind. Sie deaktiviert jedoch die Indexierung des gesamten Textes, der in diesen Dateien enthalten ist. </p> <p>Sie sollten sicherstellen, dass der Text für ältere Dateien nicht indiziert ist, sondern trotzdem alle Links aus diesen Dateien befolgen. Verwenden Sie in solchen Fällen eine Datumsmaske zum Einschließen mit dem Schlüsselwort "noindex", anstatt eine Datumsmaske zum Ausschließen zu verwenden. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>nofollow </p> </td> 
   <td colname="col2"> <p> Wenn Sie den Text auf den Seiten indizieren möchten, die am oder vor dem Datum datiert sind, das durch die Include-Maske angegeben wird, Sie aber nicht den Links der entsprechenden Seite folgen möchten, fügen Sie 
     <userinput>
       nofollow 
     </userinput> nach der Datumsmaske zum Einschließen wie im Folgenden gezeigt: </p> <p> <code> include-days&amp;nbsp;8&amp;nbsp;https://www.mydomain.com/photos&amp;nbsp;nofollow </code> </p> <p>Achten Sie darauf, dass Sie den Suchbegriff von der Maske durch einen Leerzeichen trennen. </p> <p>Die  
     <userinput>
       nofollow 
     </userinput> Suchbegriff entspricht einem Roboter-Meta-Tag mit 
     <userinput>
       content="nofollow" 
     </userinput> zwischen 
     <userinput>
       &lt;head&gt;...&lt;/head&gt; 
     </userinput> Tag der übereinstimmenden Seiten. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>server-date </p> </td> 
   <td colname="col2"> <p>Dient zum Einschließen und Ausschließen von Masken. </p> <p>Der Suchroboter lädt im Allgemeinen jede Datei herunter und analysiert sie, bevor er die Datumsmasken überprüft. Dieses Verhalten tritt auf, da einige Dateitypen ein Datum in der Datei selbst angeben können. Ein HTML-Dokument kann beispielsweise Meta-Tags enthalten, mit denen das Datum der Datei festgelegt wird. </p> <p>Wenn Sie viele Dateien je nach Datum ausschließen und keine unnötige Belastung Ihrer Server verursachen möchten, können Sie 
     <userinput>
       server-date 
     </userinput> nach der URL in der Datumsmaske. </p> <p>Dieser Suchbegriff weist den Suchroboter an, dem Datum der Datei, die von Ihrem Server zurückgegeben wird, zu vertrauen, anstatt jede Datei zu analysieren. Bei der folgenden Datumsmaske zum Ausschließen werden beispielsweise Seiten ignoriert, die mit der URL übereinstimmen, wenn die Dokumente 90 Tage oder älter sind, und zwar entsprechend dem Datum, das vom Server in den HTTP-Kopfzeilen zurückgegeben wird: </p> <p> <code> exclude-days&amp;nbsp;90&amp;nbsp;https://www.mydomain.com/docs/archive&amp;nbsp;server-date </code> </p> <p> Wenn das vom Server zurückgegebene Datum 90 Tage oder länger zurückliegt, 
     <userinput>
       server-date 
     </userinput> gibt an, dass die ausgeschlossenen Dokumente nicht von Ihrem Server heruntergeladen werden. Dadurch wird die Indexierungszeit für Ihre Dokumente verkürzt und die Belastung Ihrer Server verringert. Wenn   
     <userinput>
       server-date 
     </userinput> nicht angegeben ist, ignoriert der Suchroboter das Datum, das vom Server in den HTTP-Headern zurückgegeben wird. Stattdessen wird jede Datei heruntergeladen und überprüft, um zu sehen, ob das Datum angegeben ist. Wenn in der Datei kein Datum angegeben ist, verwendet der Suchroboter das vom Server zurückgegebene Datum. </p> <p>Sie sollten 
     <userinput>
       server-date 
     </userinput> wenn Ihre Dateien Befehle enthalten, die das Serverdatum außer Kraft setzen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>regexp </p> </td> 
   <td colname="col2"> <p> Verwenden Sie diese sowohl für ein- als auch für ausgeschlossene Masken. </p> <p>Jede Datumsmaske, der 
     <userinput>
       regexp 
     </userinput> wird als regulärer Ausdruck behandelt. </p> <p>Wenn der Suchroboter auf Dateien trifft, die mit einer Datumsmaske für reguläre Ausdrücke übereinstimmen, werden diese Dateien nicht indiziert. </p> <p>Wenn der Suchroboter auf Dateien trifft, die mit einer Datumsmaske für reguläre Ausdrücke übereinstimmen, werden diese Dokumente indiziert. </p> <p>Angenommen, Sie haben die folgende Datumsmaske: </p> <p> <code> exclude-days&amp;nbsp;180&amp;nbsp;regexp&amp;nbsp;.*archive.* </code> </p> <p>Die Maske weist den Suchroboter an, passende Dateien, die 180 Tage oder älter sind, auszuschließen. Das heißt, Dateien, die das Wort "Archiv"in ihrer URL enthalten. </p> <p>Siehe <a href="../c-appendices/r-regular-expressions.md#reference_B5BA7D61D82E4109A01D2A2D964E3A6A" type="reference" format="dita" scope="local"> Reguläre Ausdrücke </a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Hinzufügen von Datumsmasken zum Indexieren oder Nicht-Indexieren von Teilen Ihrer Website {#task_0010543C55F648D2B5DEFEFAD60FAF04}

Sie können Datumsmasken verwenden, um Dateien je nach Alter der Dateien in die Suchergebnisse des Kunden einzuschließen oder auszuschließen.

Verwenden Sie die Felder **[!UICONTROL Test Date]** und **[!UICONTROL Test URL]** , um zu testen, ob eine Datei nach dem Index enthalten ist oder nicht.

Stellen Sie sicher, dass Sie Ihren Site-Index neu erstellen, damit die Ergebnisse Ihrer URL-Masken für Ihre Kunden sichtbar sind.

Siehe [Konfigurieren eines inkrementellen Indexes einer gestaffelten Website](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0).

**So fügen Sie Datumsmasken hinzu, um Teile Ihrer Website zu indizieren oder nicht**

1. Klicken Sie im Produktmenü auf **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Date Masks]**.
1. (Optional) Geben Sie auf der [!DNL Date Masks] Seite im **[!UICONTROL Test Date]** Feld ein Datum im Format JJJJ-MM-TT ein (z. B. `2011-07-25`). Geben Sie im **[!UICONTROL Test URL]** Feld eine URL-Maske von Ihrer Website ein und klicken Sie dann auf **[!UICONTROL Test]**.
1. Geben Sie in das [!DNL Date Masks] Feld eine Adresse für die Datumsmaske pro Zeile ein.
1. Klicken **[!UICONTROL Save Changes]**.
1. (Optional) Führen Sie einen der folgenden Schritte aus:

   * Klicken Sie auf **[!UICONTROL History]** , um alle vorgenommenen Änderungen wiederherzustellen.

      Siehe [Verwenden der Option](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)Verlauf.

   * Klicken **[!UICONTROL Live]**.

      Siehe [Live-Einstellungen](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)anzeigen.

   * Klicken **[!UICONTROL Push Live]**.

      Siehe [Pushing-Einstellungen](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Informationen zu Kennwörtern {#concept_3EDBD731725D46B891F834D4472774DC}

Um auf Teile Ihrer Website zuzugreifen, die mit der HTTP Basic-Authentifizierung geschützt sind, können Sie ein oder mehrere Kennwörter hinzufügen.

Bevor die Auswirkungen der Kennworteinstellungen für Kunden sichtbar sind, müssen Sie den Site-Index neu erstellen.

Siehe [Konfigurieren eines inkrementellen Indexes einer gestaffelten Website](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0).

Auf der [!DNL Passwords] Seite geben Sie jedes Kennwort in einer einzelnen Zeile ein. Das Kennwort besteht aus einer URL oder einem Realm, einem Benutzernamen und einem Kennwort, wie im folgenden Beispiel:

```
https://www.mydomain.com/ myname mypassword
```

Anstelle eines URL-Pfads wie oben können Sie auch einen Bereich angeben.

Um den richtigen Bereich zu bestimmen, öffnen Sie eine kennwortgeschützte Webseite mit einem Browser und sehen Sie sich das Dialogfeld &quot;Netzwerkkennwort eingeben&quot;an.

![](assets/realms.gif)

Der Realm-Name ist in diesem Fall &quot;Mein Site-Bereich&quot;.

Mithilfe des oben stehenden Bereichsnamens könnte Ihr Kennwort wie folgt aussehen:

```
My Site Realm myusername mypassword
```

Wenn Ihre Website über mehrere Realms verfügt, können Sie mehrere Passwörter erstellen, indem Sie für jeden Bereich einen Benutzernamen und ein Kennwort in einer separaten Zeile eingeben, wie im folgenden Beispiel dargestellt:

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

In der oben stehenden Liste wird das erste Kennwort verwendet, das einen Bereich oder eine URL enthält, der/die mit der Authentifizierungsanforderung des Servers übereinstimmt. Auch wenn die Datei unter `https://www.mysite.com/path1/path2/index.html` ist in `Realm3`, zum Beispiel `name2` `password2` und verwendet werden, weil das Kennwort, das mit der URL definiert ist, über dem mit dem Bereich definiert wird.

## Hinzufügen von Kennwörtern für den Zugriff auf Bereiche Ihrer Website, für die eine Authentifizierung erforderlich ist {#task_DED19D476FF04B48BB6456D5ECB8628A}

Sie können Passwords verwenden, um kennwortgeschützte Bereiche Ihrer Website für Crawling- und Indexierungszwecke aufzurufen.

Bevor die Auswirkungen Ihres Passworts für Kunden sichtbar sind, stellen Sie sicher, dass Sie Ihren Site-Index neu erstellen

Siehe [Konfigurieren eines inkrementellen Indexes einer gestaffelten Website](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0).

**So fügen Sie Kennwörter für den Zugriff auf Bereiche Ihrer Website hinzu, für die eine Authentifizierung erforderlich ist**

1. Klicken Sie im Produktmenü auf **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Passwords]**.
1. Geben Sie auf der [!DNL Passwords] Seite in das **[!UICONTROL Passwords]** Feld einen Bereich oder eine URL sowie den zugehörigen Benutzernamen und das Kennwort ein, jeweils durch ein Leerzeichen getrennt.

   Beispiel eines Realm-Kennworts und eines URL-Kennworts in separaten Zeilen:

   ```
   Realm1 name1 password1 
   https://www.mysite.com/path1/path2 name2 password2
   ```

   Fügen Sie nur ein Kennwort pro Zeile hinzu.
1. Klicken **[!UICONTROL Save Changes]**.
1. (Optional) Führen Sie einen der folgenden Schritte aus:

   * Klicken Sie auf **[!UICONTROL History]** , um alle vorgenommenen Änderungen wiederherzustellen.

      Siehe [Verwenden der Option](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)Verlauf.

   * Klicken **[!UICONTROL Live]**.

      Siehe [Live-Einstellungen](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)anzeigen.

   * Klicken **[!UICONTROL Push Live]**.

      Siehe [Pushing-Einstellungen](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Inhaltstypen {#concept_6FEA1355C0374500B4C53090C34A8A07}

Sie können festlegen, welche Dateitypen für dieses Konto durchsucht und indexiert werden [!DNL Content Types] sollen.

Zu den Inhaltstypen, die Sie durchsuchen und indizieren können, gehören PDF-Dokumente, Textdokumente, Adobe Flash-Filme, Dateien aus Microsoft Office-Anwendungen wie Word, Excel und Powerpoint sowie Text in MP3-Dateien. Der in den ausgewählten Inhaltstypen gefundene Text wird zusammen mit dem gesamten anderen Text auf Ihrer Website durchsucht.

Bevor die Auswirkungen der Einstellungen für Inhaltstypen für Kunden sichtbar sind, müssen Sie Ihren Site-Index neu erstellen.

Siehe [Konfigurieren eines inkrementellen Indexes einer gestaffelten Website](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0).

## Informationen zum Indexieren von MP3-Musikdateien {#section_AD2E28BEEE3E46629E2B05C34A963673}

Wenn Sie die Option **[!UICONTROL Text in MP3 Music Files]** auf der [!DNL Content Types] Seite auswählen, wird eine MP3-Datei auf zwei Arten durchsucht und indiziert. Der erste und häufigste Weg ist der von einem Anker-href-Tag in einer HTML-Datei, wie im Folgenden:

```
<a href="MP3-file-URL"></a>
```

Die zweite Möglichkeit ist, die URL der MP3-Datei als URL-Einstiegspunkt einzugeben.

Siehe [Informationen zu URL-Einträgen](../c-about-settings-menu/c-about-crawling-menu.md#concept_5D857E3B5C124E85BC0B5AE77A509573).

Eine MP3-Datei wird vom MIME-Typ &quot;audio/mpeg&quot;erkannt.

Beachten Sie, dass MP3-Musikdateien ziemlich groß sein können, obwohl sie normalerweise nur eine kleine Textmenge enthalten. Zum Beispiel können MP3-Dateien optional Elemente wie den Albumnamen, den Künstlernamen, den Titel des Liedes, das Musikgenre, das Jahr der Veröffentlichung und einen Kommentar speichern. Diese Informationen werden am Ende der Datei im so genannten TAG gespeichert. MP3-Dateien mit TAG-Informationen werden wie folgt indiziert:

* Der Titel des Liedes wird wie der Titel einer HTML-Seite behandelt.
* Der Kommentar wird wie eine Beschreibung behandelt, die für eine HTML-Seite definiert ist.
* Das Genre wird wie ein für eine HTML-Seite definierter Suchbegriff behandelt.
* Der Name des Künstlers, der Name des Albums und das Jahr der Veröffentlichung werden wie der Text einer HTML-Seite behandelt.

Beachten Sie, dass jede MP3-Datei, die auf Ihrer Website durchsucht und indiziert ist, als eine Seite gezählt wird.

Wenn Ihre Website viele große MP3-Dateien enthält, können Sie die Indexierungsbyte-Grenze für Ihr Konto überschreiten. In diesem Fall können Sie die Auswahl **[!UICONTROL Text in MP3 Music Files]** auf der [!DNL Content Types] Seite aufheben, um die Indizierung aller MP3-Dateien auf Ihrer Website zu verhindern.

Wenn Sie nur die Indizierung bestimmter MP3-Dateien auf Ihrer Website verhindern möchten, haben Sie folgende Möglichkeiten:

* Umschließen Sie die Anker-Tags, die mit den MP3-Dateien mit `<nofollow>` und `</nofollow>` -Tags verknüpft sind. Der Suchroboter folgt nicht den Verknüpfungen zwischen diesen Tags.

* Fügen Sie die URLs der MP3-Dateien als Ausschlussmasken hinzu.

   Siehe [URL-Masken](../c-about-settings-menu/c-about-crawling-menu.md#concept_8039DFC53FF3410AA494D602F71BA164).

## Auswählen von Inhaltstypen zum Durchsuchen und Indexieren {#task_CCAC5C67C8BF4AB7B79D34A1495D5EE8}

Sie können festlegen, welche Dateitypen für dieses Konto durchsucht und indexiert werden [!DNL Content Types] sollen.

Zu den Inhaltstypen, die Sie durchsuchen und indizieren können, gehören PDF-Dokumente, Textdokumente, Adobe Flash-Filme, Dateien aus Microsoft Office-Anwendungen wie Word, Excel und Powerpoint sowie Text in MP3-Dateien. Der in den ausgewählten Inhaltstypen gefundene Text wird zusammen mit dem gesamten anderen Text auf Ihrer Website durchsucht.

Bevor die Auswirkungen der Einstellungen für Inhaltstypen für Kunden sichtbar sind, müssen Sie Ihren Site-Index neu erstellen.

Siehe [Konfigurieren eines inkrementellen Indexes einer gestaffelten Website](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0).

Gehen Sie wie folgt vor, um chinesische, japanische oder koreanische MP3-Dateien zu crawlen und zu indizieren. Geben Sie dann unter **[!UICONTROL Settings]** > **[!UICONTROL Metadata]** **[!UICONTROL Injections]**> den Zeichensatz an, der zum Kodieren der MP3-Dateien verwendet wird.

Siehe [Info zu Injektionen](../c-about-settings-menu/c-about-metadata-menu.md#concept_DA091920671948A0A893A26B3A2FAAE5).

**So wählen Sie Inhaltstypen zum Durchsuchen und Indexieren aus**

1. Klicken Sie im Produktmenü auf **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Content Types]**.
1. Überprüfen Sie auf der [!DNL Content Types] Seite die Dateitypen, die Sie auf Ihrer Website durchsuchen und indizieren möchten.
1. Klicken **[!UICONTROL Save Changes]**.
1. (Optional) Führen Sie einen der folgenden Schritte aus:

   * Klicken Sie auf **[!UICONTROL History]** , um alle vorgenommenen Änderungen wiederherzustellen.

      Siehe [Verwenden der Option](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)Verlauf.

   * Klicken **[!UICONTROL Live]**.

      Siehe [Live-Einstellungen](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)anzeigen.

   * Klicken **[!UICONTROL Push Live]**.

      Siehe [Pushing-Einstellungen](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Verbindungen {#concept_E2F3B7E7521147479E5948A94BB3A40B}

Sie können Verbindungen verwenden, um bis zu zehn HTTP-Verbindungen hinzuzufügen, die der Suchroboter zur Indexierung Ihrer Website verwendet.

Eine Erhöhung der Anzahl der Verbindungen kann die Zeit, die zum Abschluss eines Crawls und eines Indexes benötigt wird, erheblich verkürzen. Beachten Sie jedoch, dass jede zusätzliche Verbindung die Belastung Ihres Servers erhöht.

## Hinzufügen von Verbindungen zur Erhöhung der Indexierungsgeschwindigkeit {#task_3E9B83E43C1842A19066355A15C4A6FB}

Sie können die Indexierung Ihrer Website verkürzen, indem Sie Connections verwenden, um die Anzahl der gleichzeitigen HTTP-Verbindungen zu erhöhen, die der Crawler verwendet. Sie können bis zu zehn Verbindungen hinzufügen.

Beachten Sie, dass jede zusätzliche Verbindung die auf Ihrem Server abgelegte Last erhöht.

**So fügen Sie Verbindungen hinzu, um die Indexgeschwindigkeit zu erhöhen**

1. Klicken Sie im Produktmenü auf **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Connections]**.
1. Geben Sie auf der [!DNL Parallel Indexing Connections] Seite im **[!UICONTROL Number of Connections]** Feld die Anzahl der Verbindungen (1-10) ein, die Sie hinzufügen möchten.
1. Klicken **[!UICONTROL Save Changes]**.
1. (Optional) Führen Sie einen der folgenden Schritte aus:

   * Klicken Sie auf **[!UICONTROL History]** , um alle vorgenommenen Änderungen wiederherzustellen.

      Siehe [Verwenden der Option](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)Verlauf.

   * Klicken **[!UICONTROL Live]**.

      Siehe [Live-Einstellungen](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)anzeigen.

   * Klicken **[!UICONTROL Push Live]**.

      Siehe [Pushing-Einstellungen](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Grundlagen zur Formularübermittlung {#concept_CADD5D7CF373497DAA6F8564D7BC8502}

Mit der Funktion &quot;Formularübermittlung&quot;können Sie Formulare auf Ihrer Website erkennen und verarbeiten.

Während des Crawling und der Indexierung Ihrer Website wird jedes gefundene Formular mit den von Ihnen hinzugefügten Formulardefinitionen verglichen. Entspricht ein Formular einer Formulardefinition, wird das Formular zur Indexierung gesendet. Entspricht ein Formular mehr als einer Definition, wird das Formular einmal für jede übereinstimmende Definition gesendet.

## Hinzufügen von Formulardefinitionen zum Indizieren von Formularen auf Ihrer Website {#task_62FBCE9E6DBE4BDA8D1249233ADFC00F}

Sie können Formulare, die auf Ihrer Website erkannt werden, [!DNL Form Submission] für Indizierungszwecke verarbeiten.

Stellen Sie sicher, dass Sie Ihren Site-Index neu erstellen, damit die Ergebnisse Ihrer Änderungen für Ihre Kunden sichtbar sind.

Siehe [Konfigurieren eines inkrementellen Indexes einer gestaffelten Website](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0).

**So fügen Sie Formulardefinitionen für die Indexierung von Formularen auf Ihrer Website hinzu**

1. Klicken Sie im Produktmenü auf **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Form Submission]**.
1. Klicken Sie auf der [!DNL Form Submission] Seite auf **[!UICONTROL Add New Form]**.
1. Legen Sie auf der [!DNL Add Form Definition] Seite die Optionen [!DNL Form Recognition] und [!DNL Form Submission] fest.

   Die fünf Optionen im [!DNL Form Recognition] Abschnitt auf der [!DNL Form Definition] Seite werden verwendet, um Formulare auf Ihren Webseiten zu identifizieren, die verarbeitet werden können.

   Die drei Optionen im [!DNL Form Submission] Abschnitt dienen zur Angabe der Parameter und Werte, die mit einem Formular an Ihren Webserver gesendet werden.

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
      <td colname="col1"> <p> <b>Formularerkennung</b> </p> </td> 
      <td colname="col2"> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Seiten-URL-Maske </p> </td> 
      <td colname="col2"> <p>Identifizieren Sie die Webseite oder Seiten, die das Formular enthalten. Um ein Formular zu identifizieren, das auf einer einzelnen Seite angezeigt wird, geben Sie die URL für diese Seite wie im folgenden Beispiel ein: </p> <p> <code> https://www.mydomain.com/login.html </code> </p> <p>Um Formulare zu identifizieren, die auf mehreren Seiten angezeigt werden, geben Sie eine URL-Maske an, die zur Beschreibung der Seiten Platzhalter verwendet. Zur Identifizierung von Formularen, die auf einer ASP-Seite gefunden werden, geben Sie <code> https://www.mydomain.com/register/ </code>beispielsweise Folgendes an: </p> <p> <code> https://www.mydomain.com/register/*.asp&amp;nbsp; </code> </p> <p>Sie können auch einen regulären Ausdruck verwenden, um mehrere Seiten zu identifizieren. Geben Sie einfach die 
      <userinput>
        regexp 
      </userinput> -Schlüsselwort vor der URL-Maske wie im folgenden Beispiel gezeigt: </p> <p> <code> regexp&amp;nbsp;^https://www\.mydomain\.com/.*/login\.html$ </code> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>URL-Maske der Aktion </p> </td> 
      <td colname="col2"> <p>Identifiziert das Aktionsattribut des 
      <userinput>
        &lt;form&gt; 
      </userinput> Tag Deklarationen folgen. </p> <p>Wie die Seiten-URL-Maske kann die Aktion-URL-Maske in Form einer einzelnen URL, einer URL mit Platzhaltern oder eines regulären Ausdrucks erfolgen. </p> <p>Bei der URL-Maske kann es sich um eine der folgenden Optionen handeln: 
      <ul id="ul_EDFE7688D3DD4C0BBACCE5D4648D8E44"> 
      <li id="li_77550A448D954EF29FF33EE5E8B5E0F5"> Ein vollständiger Pfad, wie im Folgenden gezeigt: <code> https://www.mydomain.com/products.html </code> </li> 
      <li id="li_F84E25553BBA41419BE153DC0709E011"> Ein partieller Pfad wie im Folgenden: <code> https://www.mydomain.com/products </code> </li> 
      <li id="li_8DADA1C8604740FCACBA30B4AAADB2A1"> Eine URL, die Platzhalter wie folgt verwendet: <code> https://www.mydomain.com/*.html </code> </li> 
      <li id="li_1EF637B450654B509AA4B618F7FD3C2B"> Ein regulärer Ausdruck wie im Folgenden: <code> regexp&amp;nbsp^https://www\.mydomain\.com/.*/login\.html$ </code> </li> 
      </ul> </p> <p>Wenn Sie den Text nicht auf Seiten indizieren möchten, die durch eine URL-Maske oder eine Action URL-Maske identifiziert werden, oder wenn auf diesen Seiten keine Links folgen sollen, können Sie die Variable 
      <userinput>
        noindex 
      </userinput> und 
      <userinput>
        nofollow 
      </userinput> Keywords. Sie können diese Suchbegriffe mithilfe von URL-Masken oder Einstiegspunkten zu Ihren Masken hinzufügen. </p> <p>Siehe <a href="../c-about-settings-menu/c-about-crawling-menu.md#concept_5D857E3B5C124E85BC0B5AE77A509573" type="concept" format="dita" scope="local"> Informationen zu URL-Einträgen </a>. </p> <p>Siehe <a href="../c-about-settings-menu/c-about-crawling-menu.md#concept_8039DFC53FF3410AA494D602F71BA164" type="concept" format="dita" scope="local"> Informationen zu URL-Masken </a>. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Formularnamenmaske </p> </td> 
      <td colname="col2"> <p>Identifiziert Formulare, wenn die Variable 
      <userinput>
        &lt;form&gt; 
      </userinput> -Tags in Ihren Webseiten enthalten ein Namensattribut. </p> <p>Sie können einen einfachen Namen ( 
      <userinput>
        login_form 
      </userinput>), einen Namen mit einem Platzhalter ( 
      <userinput>
        form* 
      </userinput>) oder einen regulären Ausdruck ( 
      <userinput>
        regexp ^.*autorisieren.*$ 
      </userinput>). </p> <p>Normalerweise können Sie dieses Feld leer lassen, da Formulare in der Regel kein Namensattribut aufweisen. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Formular-ID-Maske </p> </td> 
      <td colname="col2"> <p>Identifiziert Formulare, wenn die Variable 
      <userinput>
        &lt;form&gt; 
      </userinput> -Tags in Ihren Webseiten enthalten ein id-Attribut. </p> <p>Sie können einen einfachen Namen ( 
      <userinput>
        login_form 
      </userinput>), einen Namen mit einem Platzhalter ( 
      <userinput>
        form* 
      </userinput>) oder einen regulären Ausdruck ( 
      <userinput>
        regexp ^.*autorisieren.*$ 
      </userinput>). </p> <p>Normalerweise können Sie dieses Feld leer lassen, da Formulare in der Regel kein Namensattribut aufweisen. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Parameter </p> </td> 
      <td colname="col2"> <p>Identifizieren Sie Formulare, die einen benannten Parameter oder einen benannten Parameter mit einem bestimmten Wert enthalten oder nicht enthalten. </p> <p>Um beispielsweise ein Formular zu identifizieren, das einen E-Mail-Parameter enthält, der auf rick_brough@mydomain.com, einen Kennwortparameter, aber keinen Vorname-Parameter vorgegeben ist, geben Sie die folgenden Parametereinstellungen pro Zeile an: </p> <p> <code> email=rick_brough@mydomain.com password  not&nbsp;first-name </code> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p> <b>Formularübermittlung</b> </p> </td> 
      <td colname="col2"> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>URL der Aktion überschreiben </p> </td> 
      <td colname="col2"> <p>Geben Sie an, wann das Ziel der Formularübermittlung von dem im Aktionsattribut des Formulars angegebenen abweicht. </p> <p>Sie können diese Option beispielsweise verwenden, wenn das Formular über eine JavaScript-Funktion gesendet wird, die einen URL-Wert erstellt, der sich von dem im Formular enthaltenen Wert unterscheidet. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Methode überschreiben </p> </td> 
      <td colname="col2"> <p>Geben Sie an, wann das Ziel der Formularübermittlung von dem im Aktionsattribut des Formulars verwendeten abweicht und wann das sendende JavaScript die Methode geändert hat. </p> <p>Die Standardwerte für alle Formularparameter ( 
      <userinput>
        &lt;input&gt; 
      </userinput> Tags, einschließlich ausgeblendeter Felder), die Standardeinstellung 
      <userinput>
        &lt;option&gt; 
      </userinput> von 
      <userinput>
        &lt;Auswahl&gt; 
      </userinput> -Tag und der Standardtext zwischen 
      <userinput>
        &lt;textarea&gt;...&lt;/textarea&gt; 
      </userinput> -Tags) von der Webseite gelesen werden. Jeder Parameter, der im Abschnitt " <span class="wintitle"> Formularübermittlung" </span> im Feld " <span class="uicontrol"> </span> Parameter"aufgelistet ist, wird jedoch durch die Standardformulare ersetzt. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Parameter </p> </td> 
      <td colname="col2"> <p>Sie können den Formularsendeparametern mit dem Präfix 
      <userinput>
        nicht 
      </userinput> Suchbegriff. </p> <p>Beim Präfix eines Parameters mit 
      <userinput>
        nicht 
      </userinput>, wird es nicht als Teil der Formularübermittlung gesendet. Dieses Verhalten ist nützlich für Kontrollkästchen, die deaktiviert gesendet werden sollen. </p> <p>Angenommen, Sie möchten die folgenden Parameter senden: </p> <p> 
      <ul id="ul_962D12BACF464FF189DB12BFAFCC93A6"> 
      <li id="li_830C6C3EC8D2448388A453BB8EDE5940"> Der E-Mail-Parameter mit dem Wert 
      <userinput>
        nobody@mydomain.com 
      </userinput> </li> 
      <li id="li_905497E3FACE472DBDD49392D5B45E01"> Der Parameter password mit dem Wert 
      <userinput>
        tryme 
      </userinput> </li> 
      <li id="li_AAA411708ADC464793EADF0D821E282E"> Der Parameter "mycheckbox"ist deaktiviert. </li> 
      <li id="li_0D3DDE641E2B4BEF9F570C03FDB40ED2"> <p>Alle weiteren 
      <userinput>
        &lt;form&gt; 
      </userinput> Parameter als Standardwerte </p> </li> 
      </ul> </p> <p>Der Parameter für die Formularübermittlung würde wie folgt aussehen: </p> <p> <code> email=nobody@mydomain.com 
        password=tryme 
        not&nbsp;mycheckbox </code> </p> <p>Das method-Attribut der 
      <userinput>
        &lt;form&gt; 
      </userinput> -Tag auf der Webseite verwendet wird, um zu entscheiden, ob die Daten mit der GET-Methode oder der POST-Methode an Ihren Server gesendet werden. </p> <p>Wenn die Variable     
      <userinput>
        &lt;form&gt; 
      </userinput> -Tag kein Methodenattribut enthält, wird das Formular mit der GET-Methode gesendet. </p> </td> 
      </tr> 
    </tbody> 
    </table>

1. Klicken **[!UICONTROL Add]**.
1. (Optional) Führen Sie einen der folgenden Schritte aus:

   * Klicken **[!UICONTROL Live]**.

      Siehe [Live-Einstellungen](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)anzeigen.

   * Klicken **[!UICONTROL Push Live]**.

      Siehe [Pushing-Einstellungen](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Bearbeiten einer Formulardefinition {#task_9FB34E9C8A814DFE9BF7F8F8F69BF314}

Sie können eine vorhandene Formulardefinition bearbeiten, wenn sich ein Formular auf Ihrer Website geändert hat oder Sie lediglich die Definition ändern müssen.

Beachten Sie, dass es keine [!DNL History] Funktion auf der [!DNL Form Submission] Seite gibt, um Änderungen, die Sie an einer Formulardefinition vornehmen, wiederherzustellen.

Stellen Sie sicher, dass Sie Ihren Site-Index neu erstellen, damit die Ergebnisse Ihrer Änderungen für Ihre Kunden sichtbar sind.

Siehe [Konfigurieren eines inkrementellen Indexes einer gestaffelten Website](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0).

**So bearbeiten Sie eine Formulardefinition**

1. Klicken Sie im Produktmenü auf **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Form Submission]**.
1. Klicken Sie auf der [!DNL Form Submission] Seite rechts neben einer Formulardefinition, die Sie aktualisieren möchten, **[!UICONTROL Edit]** auf .
1. Legen Sie auf der [!DNL Edit Form Definition] Seite die Optionen [!DNL Form Recognition] und [!DNL Form Submission] fest.

   Siehe die Tabelle der Optionen unter [Hinzufügen von Formulardefinitionen zum Indizieren von Formularen auf Ihrer Website](../c-about-settings-menu/c-about-crawling-menu.md#task_62FBCE9E6DBE4BDA8D1249233ADFC00F).
1. Klicken **[!UICONTROL Save Changes]**.
1. (Optional) Führen Sie einen der folgenden Schritte aus:

   * Klicken **[!UICONTROL Live]**.

      Siehe [Live-Einstellungen](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)anzeigen.

   * Klicken **[!UICONTROL Push Live]**.

      Siehe [Pushing-Einstellungen](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Löschen einer Formulardefinition {#task_C350FC0CDE344F2786215D544C048B5E}

Sie können eine vorhandene Formulardefinition löschen, wenn das Formular nicht mehr auf Ihrer Website vorhanden ist oder wenn Sie ein bestimmtes Formular nicht mehr verarbeiten und indizieren möchten.

Beachten Sie, dass es keine [!DNL History] Funktion auf der [!DNL Form Submission] Seite gibt, um Änderungen, die Sie an einer Formulardefinition vornehmen, wiederherzustellen.

Stellen Sie sicher, dass Sie Ihren Site-Index neu erstellen, damit die Ergebnisse Ihrer Änderungen für Ihre Kunden sichtbar sind.

Siehe [Konfigurieren eines inkrementellen Indexes einer gestaffelten Website](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0).

**So löschen Sie eine Formulardefinition**

1. Klicken Sie im Produktmenü auf **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Form Submission]**.
1. Klicken Sie auf der [!DNL Form Submission] Seite rechts neben einer Formulardefinition, die Sie entfernen möchten, **[!UICONTROL Delete]** auf .

   Achten Sie darauf, die richtige Formulardefinition zum Löschen auszuwählen. Wenn Sie im nächsten Schritt auf **[!UICONTROL Delete]** die Schaltfläche klicken, gibt es kein Dialogfeld zum Löschen.
1. Klicken Sie auf der [!DNL Delete Form Definition] Seite auf **[!UICONTROL Delete]**.
1. (Optional) Führen Sie einen der folgenden Schritte aus:

   * Klicken **[!UICONTROL Live]**.

      Siehe [Live-Einstellungen](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)anzeigen.

   * Klicken **[!UICONTROL Push Live]**.

      Siehe [Pushing-Einstellungen](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Info zu Index Connector {#concept_CA6921E2FBF641F9B4F60C92B32AFA84}

Verwenden Sie [!DNL Index Connector] zum Definieren zusätzlicher Eingabequellen für die Indizierung von XML-Seiten oder beliebigen Feeds.

Sie können eine Data Feed-Eingabequelle verwenden, um auf Inhalte zuzugreifen, die in einem Formular gespeichert sind, das sich von dem unterscheidet, was normalerweise auf einer Website mithilfe einer der verfügbaren Crawl-Methoden entdeckt wird. Jedes Dokument, das durchsucht und indiziert wird, entspricht einer Inhaltsseite auf Ihrer Website. Ein Datenfeed stammt jedoch entweder aus einem XML-Dokument oder aus einer durch Kommas oder Tabulatoren getrennten Textdatei und enthält die zu indexierenden Inhaltsinformationen.

Eine XML-Datenquelle besteht aus XML-Stanza oder -Datensätzen, die Informationen enthalten, die einzelnen Dokumenten entsprechen. Diese einzelnen Dokumente werden dem Index hinzugefügt. Ein Textdaten-Feed enthält einzelne, durch Zeilenumbrüche getrennte Datensätze, die einzelnen Dokumenten entsprechen. Diese einzelnen Dokumente werden auch dem Index hinzugefügt. In beiden Fällen beschreibt eine Indexverbindungskonfiguration die Interpretation des Feeds. Jede Konfiguration beschreibt, wo sich die Datei befindet und wie die Server darauf zugreifen. Die Konfiguration beschreibt auch &quot;Zuordnungsinformationen&quot;. Das heißt, wie die Elemente der einzelnen Datensätze zum Füllen der Metadatenfelder im resultierenden Index verwendet werden.

Nachdem Sie der [!DNL Staged Index Connector Definitions] Seite eine Index-Connector-Definition hinzugefügt haben, können Sie alle Konfigurationseinstellungen ändern, *mit Ausnahme* der Werte für Name oder Typ.

Die [!DNL Index Connector] Seite enthält folgende Informationen:

* Der Name der definierten Index-Connectors, die Sie konfiguriert und hinzugefügt haben.
* Einer der folgenden Datenquellentypen für jeden Connector, den Sie hinzugefügt haben:

   * **Text** : Einfache &quot;flache&quot;Dateien, kommagetrennte, tabulatorgetrennte oder andere konsistent getrennte Formate.
   * **Feed** - XML-Feeds.
   * **XML** - Sammlungen von XML-Dokumenten.

* Ob der Connector für das nächste Crawl und Indizierung aktiviert ist oder nicht.
* Die Adresse der Datenquelle.

Siehe auch [Info zu Index Connector](../c-about-settings-menu/c-about-crawling-menu.md#concept_CA6921E2FBF641F9B4F60C92B32AFA84)

## Funktionsweise des Indexierungsvorgangs bei Text- und Feed-Konfigurationen in Index Connector {#section_E059A33D61EE4DB0972A37B8A35E9E16}

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
   <td colname="col2"> <p>Unterteilen Sie die heruntergeladene Datenquelle in einzelne Pseudo-Dokumente. </p> </td> 
   <td colname="col3"> <p>Bei <span class="uicontrol"> Text </span>entspricht jede durch Zeilenumbrüche getrennte Textzeile einem einzelnen Dokument und wird mit dem angegebenen Trennzeichen wie einem Komma oder einer Registerkarte analysiert. </p> <p>Für <span class="uicontrol"> Feed </span>werden die Daten jedes Dokuments mithilfe eines Musters für reguläre Ausdrücke in folgendem Formular extrahiert: </p> <p> <code> &lt;${Itemtag}&gt;(.*?)&lt;/${Itemtag}&gt; </code> </p> <p>Erstellen Sie mithilfe der <span class="uicontrol"> Zuordnung </span> auf der Seite " <span class="wintitle"> </span> Index-Connector-Hinzufügen"eine zwischengespeicherte Kopie der Daten und erstellen Sie dann eine Liste der Links für den Crawler. Die Daten werden in einem lokalen Cache gespeichert und mit den konfigurierten Feldern gefüllt. </p> <p>Die analysierten Daten werden in den lokalen Cache geschrieben. </p> <p>Dieser Cache wird später gelesen, um die einfachen HTML-Dokumente zu erstellen, die der Crawler benötigt. Beispiel: </p> <p> <code> &lt;html&gt;&lt;head&gt; 
      &lt;title&gt;{title}&lt;/title&gt; 
      &lt;meta&nbsp;name="{field}"&nbsp;content="{data}"&nbsp;/&gt; 
      ... 
      &lt;/head&gt;&lt;body&gt; 
      {body} 
      &lt;/body&gt;&lt;/html&gt; </code> </p> <p>Das <span class="codeph"> &lt;title&gt;- </span> Element wird nur generiert, wenn eine Zuordnung zum Metadatenfeld "Titel"vorhanden ist. Gleichermaßen wird das <span class="codeph"> &lt;body&gt;- </span> Element nur generiert, wenn eine Zuordnung zum Metadatenfeld "Textkörper"vorhanden ist. </p> <p> <b>Wichtig</b>: Die Zuweisung von Werten zum vordefinierten URL-Meta-Tag wird nicht unterstützt. </p> <p>Bei allen anderen Zuordnungen werden für jedes Feld, das Daten im Originaldokument enthält, <span class="codeph"> &lt;meta&gt;- </span> Tags generiert. </p> <p>Die Felder für jedes Dokument werden dem Cache hinzugefügt. Für jedes Dokument, das in den Cache geschrieben wird, wird auch ein Link wie in den folgenden Beispielen generiert: </p> <p> <code> &lt;a&nbsp;href="index:Adobe?key=&lt;primary&nbsp;key&nbsp;field&gt;\"&nbsp;/&gt; 
      &lt;a&nbsp;href="index:Adobe?key=&lt;primary&nbsp;key&nbsp;field&gt;\"&nbsp;/&gt; 
      .... </code> </p> <p>Bei der Zuordnung der Konfiguration muss ein Feld als Primärschlüssel identifiziert werden. Diese Zuordnung bildet den Schlüssel, der verwendet wird, wenn Daten aus dem Cache abgerufen werden. </p> <p>Der Crawler erkennt den URL- <span class="codeph"> Index: </span> Schemapräfix, das dann auf die lokal zwischengespeicherten Daten zugreifen kann. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>3 </p> </td> 
   <td colname="col2"> <p>Durchsuchen Sie den zwischengespeicherten Dokumentsatz. </p> </td> 
   <td colname="col3"> <p>Der <span class="codeph"> Index: Die </span> Links werden der Liste der ausstehenden Crawler hinzugefügt und in der normalen Crawl-Sequenz verarbeitet. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>4 </p> </td> 
   <td colname="col2"> <p>Verarbeiten Sie jedes Dokument. </p> </td> 
   <td colname="col3"> <p>Der Schlüsselwert jedes Links entspricht einem Eintrag im Cache, sodass beim Durchsuchen der einzelnen Links die Daten des Dokuments aus dem Cache abgerufen werden. Es wird dann zu einem HTML-Bild "zusammengestellt", das verarbeitet und dem Index hinzugefügt wird. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Funktionsweise des Indexierungsvorgangs bei XML-Konfigurationen in Index Connector {#section_7F1551EA51854C5C99F284CE260526EB}

Der Indexierungsprozess für die XML-Konfiguration ähnelt dem Prozess für Text- und Feed-Konfigurationen mit den folgenden geringfügigen Änderungen und Ausnahmen.

Da die Dokumente für XML-Crawls bereits in einzelne Dateien aufgeteilt sind, gelten die Schritte 1 und 2 in der obigen Tabelle nicht direkt. Wenn Sie eine URL in den Feldern **[!UICONTROL Host Address]** und **[!UICONTROL File Path]** auf der [!DNL Index Connector Add] Seite angeben, wird sie als normales HTML-Dokument heruntergeladen und verarbeitet. Es wird erwartet, dass das Download-Dokument eine Sammlung von `<a href="{url}"...` Links enthält, von denen jeder auf ein verarbeitetes XML-Dokument verweist. Solche Links werden in das folgende Formular konvertiert:

```
<a href="index:<ic_config_name>?url="{url}">
```

Wenn das Adobe-Setup beispielsweise die folgenden Links zurückgegeben hat:

```
<a href="https://www.adobe.com/somepath/doc1.xml">doc 1</a> 
<a href="https://www.adobe.com/otherpath/doc2.xml">doc 2</a>
```

In der obigen Tabelle gilt Schritt 3 nicht und Schritt 4 wird zum Zeitpunkt des Crawling und der Indexierung abgeschlossen.

Alternativ können Sie Ihre XML-Dokumente mit anderen Dokumenten kombinieren, die beim Crawl-Prozess auf natürliche Weise entdeckt wurden. In solchen Fällen können Sie die URLs der XML-Dokumente mit Umschreibungsregeln ( **[!UICONTROL Settings]** > **[!UICONTROL Rewrite Rules]** > **[!UICONTROL Crawl List Retrieve URL Rules]**) ändern, um sie an den Index Connector zu leiten.

Siehe [Grundlagen zu URL-Regeln](../c-about-settings-menu/c-about-rewrite-rules-menu.md#concept_EC8E2E48B99A458D8567B526C9827CBA)zum Abrufen der Crawl-Liste.

Angenommen, Sie haben die folgende Regel zum Umschreiben:

```
RewriteRule (^http.*[.]xml$) index:Adobe?key=$1
```

Diese Regel übersetzt alle URLs, die mit einem Index-Connector-Link enden, `.xml` in einen Index-Connector-Link. Der Crawler erkennt und schreibt das `index:` URL-Schema neu. Der Download-Prozess wird über den Index Connector Apache-Server auf dem Master umgeleitet. Jedes heruntergeladene Dokument wird mit demselben Muster für reguläre Ausdrücke wie Feeds geprüft. In diesem Fall wird das erstellte HTML-Dokument jedoch nicht im Cache gespeichert. Stattdessen wird sie direkt an den Crawler zur Indexverarbeitung übergeben.

## Konfigurieren mehrerer Index Connectors {#section_C2B14C0F06354A57AEF6238FF3814E5D}

Sie können mehrere Index Connector-Konfigurationen für ein beliebiges Konto definieren. Die Konfigurationen werden automatisch zur Dropdown-Liste unter **[!UICONTROL Settings]** > **[!UICONTROL Crawl]** > **[!UICONTROL URL Entrypoints]** , wie in der folgenden Abbildung gezeigt, hinzugefügt:

![](assets/url_entrypoints_index_connector.png)

Wenn Sie eine Konfiguration aus der Dropdownliste auswählen, wird der Wert am Ende der Liste der URL-Einstiegspunkte hinzugefügt.

>[!NOTE]
>
>Deaktivierte Index Connector-Konfigurationen werden der Dropdown-Liste hinzugefügt, Sie können sie jedoch nicht auswählen. Wenn Sie dieselbe Index Connector-Konfiguration ein zweites Mal auswählen, wird sie am Ende der Liste hinzugefügt und die vorherige Instanz wird gelöscht.

Um einen Index Connector-Einstiegspunkt für eine inkrementelle Crawl anzugeben, können Sie Einträge im folgenden Format hinzufügen:

```
index:<indexconnector_configuration_name>
```

Der Crawler verarbeitet jeden hinzugefügten Eintrag, wenn er auf der Seite Index Connectors gefunden und aktiviert ist.

Hinweis: Da die URL jedes Dokuments unter Verwendung des Index Connector-Konfigurationsnamens und des primären Schlüssels des Dokuments erstellt wird, sollten Sie beim Durchführen inkrementeller Aktualisierungen unbedingt denselben Index Connector-Konfigurationsnamen verwenden! Auf diese Weise können zuvor indizierte Dokumente korrekt aktualisiert [!DNL Adobe Search&Promote] werden.

Siehe auch URL- [Einstiegspunkte](../c-about-settings-menu/c-about-crawling-menu.md#concept_5D857E3B5C124E85BC0B5AE77A509573).

**Die Verwendung von Setup-Maps beim Hinzufügen eines Index Connector**

Wenn Sie einen Index Connector hinzufügen, können Sie optional mit dieser Funktion ein Beispiel Ihrer Datenquelle herunterladen **[!UICONTROL Setup Maps]** . Die Daten werden zur Indizierung der Eignung geprüft.

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Wenn Sie den Index Connector-Typ auswählen... </p> </th> 
   <th colname="col2" class="entry"> <p>Die Funktion "Imagemaps einrichten"... </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Text </p> </td> 
   <td colname="col2"> <p>Bestimmt den Wert des Trennzeichens, indem zuerst Registerkarten und dann vertikale Balken ( <span class="codeph"> | </span>) und schließlich Kommas ( <span class="codeph"> , </span>). Wenn Sie bereits vor dem Klicken auf <span class="uicontrol"> Setup Maps einen Trennzeichenwert angegeben haben </span>, wird dieser Wert verwendet. </p> <p>Das passende Schema führt dazu, dass die Kartenfelder mit Vermutungen bei den entsprechenden Tag- und Feldwerten ausgefüllt werden. Zusätzlich wird eine Stichprobe der analysierten Daten angezeigt. Wählen Sie <span class="uicontrol"> Kopfzeilen in erster Zeile aus, </span> wenn Sie wissen, dass die Datei eine Kopfzeile enthält. Die Setup-Funktion verwendet diese Informationen, um die resultierenden Zuordnungseinträge besser zu identifizieren. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Feed </p> </td> 
   <td colname="col2"> <p>Lädt die Datenquelle herunter und führt eine einfache XML-Analyse durch. </p> <p>Die resultierenden XPath-IDs werden in den Tag-Zeilen der Map-Tabelle und ähnliche Werte in den Feldern angezeigt. Diese Zeilen identifizieren nur die verfügbaren Daten und generieren keine komplizierteren XPath-Definitionen. Es ist jedoch weiterhin hilfreich, da es die XML-Daten beschreibt und die Werte von itemTag identifiziert. </p> <p> <p>Hinweis:  Die Funktion Setup-Karten lädt die gesamte XML-Quelle herunter, um die Analyse durchzuführen. Wenn die Datei groß ist, kann dieser Vorgang zu einem Timeout führen. </p> </p> <p>Wenn diese Funktion erfolgreich ist, identifiziert sie alle möglichen XPath-Elemente, von denen viele nicht verwendet werden sollten. Achten Sie darauf, die resultierenden Map-Definitionen zu prüfen und die nicht benötigten oder gewünschten zu entfernen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>XML </p> </td> 
   <td colname="col2"> <p>Lädt die URL eines repräsentativen Dokuments und nicht die Liste der Master-Links herunter. Dieses einzelne Dokument wird mit demselben Mechanismus analysiert, der mit Feeds verwendet wird, und die Ergebnisse werden angezeigt. </p> <p>Bevor Sie zum Speichern der Konfiguration auf <span class="uicontrol"> </span> Hinzufügen klicken, vergewissern Sie sich, dass Sie die URL wieder in das Dokument für die Master-Link-Liste ändern. </p> </td> 
  </tr> 
 </tbody> 
</table>

**Wichtig**: Die Funktion &quot;Einstellungskarten&quot;funktioniert möglicherweise nicht für große XML-Datensätze, da der Dateiparser versucht, die gesamte Datei in den Speicher zu lesen. Daher kann es zu einer Speicherüberschreitung kommen. Wird dasselbe Dokument jedoch zum Zeitpunkt der Indizierung verarbeitet, wird es nicht in den Speicher gelesen. Stattdessen werden große Dokumente &quot;unterwegs&quot;verarbeitet und erst nicht vollständig in den Speicher gelesen.

**Die Verwendung der Vorschau beim Hinzufügen eines Index Connector**

Beim Hinzufügen eines Index-Connectors können Sie optional die Funktion verwenden, **[!UICONTROL Preview]** um die Daten zu validieren, als ob Sie sie gespeichert hätten. Es führt einen Test für die Konfiguration aus, ohne die Konfiguration im Konto zu speichern. Der Test greift auf die konfigurierte Datenquelle zu. Der Download-Cache wird jedoch an einen temporären Speicherort geschrieben. Es steht nicht im Konflikt mit dem Hauptcache-Ordner, den der Indexcrawler verwendet.

&quot;Vorschau&quot;verarbeitet nur die Standardwerte von fünf Dokumenten, die von &quot;Acct:IndexConnector-Preview-Max-Documents&quot;gesteuert werden. Die in der Vorschau angezeigten Dokumente werden im Quellformular angezeigt, da sie dem Indexierungs-Crawler präsentiert werden. Die Anzeige ähnelt der Funktion &quot;Quelle anzeigen&quot;in einem Webbrowser. Sie können mithilfe von standardmäßigen Navigationslinks durch die Dokumente im Vorschausatz navigieren.

Die Vorschau unterstützt keine XML-Konfigurationen, da diese Dokumente direkt verarbeitet und nicht in den Cache heruntergeladen werden.

## Hinzufügen einer Index Connector-Definition {#task_96779B651A654E1F871F55D6DBBC8886}

Jede Index Connector-Konfiguration definiert eine Datenquelle und Zuordnungen, um die für diese Quelle definierten Datenelemente mit den Metadatenfeldern im Index zu verknüpfen.

Bevor die Auswirkungen der neuen und aktivierten Definition für Kunden sichtbar sind, erstellen Sie Ihren Site-Index neu.

**So fügen Sie eine Index Connector-Definition hinzu**

1. Klicken Sie im Produktmenü auf **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Index Connector]**.
1. Klicken Sie auf der [!DNL Stage Index Connector Definitions] Seite auf **[!UICONTROL Add New Index Connector]**.
1. Legen Sie auf der [!DNL Index Connector Add] Seite die gewünschten Anschlussoptionen fest. Die verfügbaren Optionen hängen von der ausgewählten **[!UICONTROL Type]** ab.

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
      <td colname="col1"> <p>Typ  </p> </td> 
      <td colname="col2"> <p>Die Quelle Ihrer Daten. Der ausgewählte Datenquellentyp wirkt sich auf die auf der Seite " <span class="wintitle"> Index-Connector-Hinzufügen"verfügbaren Optionen </span> aus. Sie können aus den folgenden Optionen wählen: </p> <p> 
      <ul id="ul_1ADC3DFBC929467385F7465BE8E13635"> 
      <li id="li_64FCD749F55442BAB316BD474128D4F9"> <span class="uicontrol"> Text </span> <p>Einfache Dateien mit flachem Text, kommagetrennte, tabulatorgetrennte oder andere konsistent getrennte Formate. Jede durch Zeilenumbrüche getrennte Textzeile entspricht einem einzelnen Dokument und wird mit dem angegebenen Trennzeichen analysiert. </p> <p>Sie können jeden Wert oder jede Spalte einem Metadatenfeld zuordnen, auf das die Spaltennummer verweist, beginnend mit 1 (1). </p> </li> 
      <li id="li_2A4F16CE6DCE4114B7F8E4FE156252BB"> <span class="uicontrol"> Feed </span> <p>Lädt ein XML-Masterdokument herunter, das mehrere "Zeilen"mit Informationen enthält. </p> </li> 
      <li id="li_5A61C53522D74D4C9A5F65989604BDEF"> <span class="uicontrol"> XML </span> <p>Lädt ein XML-Masterdokument herunter, das Links enthält ( 
      <userinput>
        &lt;a&gt; 
      </userinput>) in einzelne XML-Dokumente. </p> </li> 
      </ul> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p> <b>Datenquellentyp: Text</b> </p> </td> 
      <td colname="col2"> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Aktiviert </p> </td> 
      <td colname="col2"> <p>Aktiviert die Konfiguration zu Crawl und Index. Oder Sie können die Konfiguration deaktivieren, um Crawling und Indizierung zu verhindern. </p> <p> <b>Hinweis</b>: Deaktivierte Index Connector-Konfigurationen werden ignoriert, wenn sie in einer Einstiegsliste vorhanden sind. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Host-Adresse </p> </td> 
      <td colname="col2"> <p>Gibt die Adresse des Serverhosts an, auf dem sich Ihre Daten befinden. </p> <p>Bei Bedarf können Sie einen vollständigen URI (Uniform Resource Identifier)-Pfad zum Datenquellendokument angeben, wie in den folgenden Beispielen dargestellt: </p> <p> <code> https://www.somewhere.com/some_path/some_file.xml </code> </p> <p>oder </p> <p> <code> ftp://user:password@ftpserver.somewhere.com/some_path/some_file.xml </code> </p> <p>Der URI wird in die entsprechenden Einträge für die Felder Host-Adresse, Dateipfad, Protokoll und optional Benutzername und Kennwort unterteilt. </p> <p>Gibt die IP-Adresse oder die URL-Adresse des Hostsystems an, in dem die Datenquellendatei gefunden wird. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Dateipfad </p> </td> 
      <td colname="col2"> <p>Gibt den Pfad zur einfachen, mit Kommas getrennten, tabulatorgetrennten oder anderen konsistent getrennten Formatdatei für flachen Text an. </p> <p>Der Pfad ist relativ zum Stammverzeichnis der Hostadresse. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Inkrementeller Dateipfad </p> </td> 
      <td colname="col2"> <p>Gibt den Pfad zur einfachen, mit Kommas getrennten, tabulatorgetrennten oder anderen konsistent getrennten Formatdatei für flachen Text an. </p> <p>Der Pfad ist relativ zum Stammverzeichnis der Hostadresse. </p> <p>Diese Datei wird, sofern angegeben, während Inkrementeller Indexvorgänge heruntergeladen und verarbeitet. Wenn keine Datei angegeben ist, wird stattdessen die unter Dateipfad aufgelistete Datei verwendet. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Vertikaler Dateipfad </p> </td> 
      <td colname="col2"> <p>Gibt den Pfad zur einfachen, mit Kommas getrennten, tabulatorgetrennten oder anderen konsistent getrennten Formatdatei an, die bei einer vertikalen Aktualisierung verwendet werden soll. </p> <p>Der Pfad ist relativ zum Stammverzeichnis der Hostadresse. </p> <p>Diese Datei wird, sofern angegeben, während des Vorgangs Vertikale Aktualisierung heruntergeladen und verarbeitet. </p> <p> <b>Hinweis</b>: Diese Funktion ist standardmäßig nicht aktiviert. Wenden Sie sich an den technischen Support, um die Funktion für Ihre Verwendung zu aktivieren. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Löscht Dateipfad </p> </td> 
      <td colname="col2"> <p>Gibt den Pfad zur einfachen Textdatei mit einem einzelnen Dokumentkennungswert pro Zeile an. </p> <p>Der Pfad ist relativ zum Stammverzeichnis der Hostadresse. </p> <p>Diese Datei wird, sofern angegeben, während Inkrementeller Indexvorgänge heruntergeladen und verarbeitet. Die in dieser Datei gefundenen Werte werden verwendet, um Anforderungen zum Löschen von zuvor indizierten Dokumenten zu erstellen. Die Werte in dieser Datei müssen mit den Werten übereinstimmen, die in den Dateien "Vollständiger oder inkrementeller Dateipfad"in der Spalte " <span class="uicontrol"> Primärschlüssel"gefunden wurden </span>. </p> <p> <b>Hinweis</b>: Diese Funktion ist standardmäßig nicht aktiviert. Wenden Sie sich an den technischen Support, um die Funktion für Ihre Verwendung zu aktivieren. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Protokoll </p> </td> 
      <td colname="col2"> <p>Gibt das Protokoll an, das für den Zugriff auf die Datei verwendet wird. Sie können aus den folgenden Optionen wählen: </p> <p> 
      <ul id="ul_F6BC10FD51CA4A1D855B2B3212838A9C"> 
      <li id="li_79FB7DC65E774ABBB23E57BF98AD9738"> HTTP <p>Bei Bedarf können Sie für den Zugriff auf den HTTP-Server die entsprechenden Authentifizierungsdaten eingeben. </p> </li> 
      <li id="li_BAA9AD5E4B014E09B3A66C94022B7225"> HTTPS <p>Bei Bedarf können Sie für den Zugriff auf den HTTPS-Server die entsprechenden Authentifizierungsdaten eingeben. </p> </li> 
      <li id="li_E716ABB169DD408BA91F1CA27F445A16"> FTP <p>Für den Zugriff auf den FTP-Server müssen Sie entsprechende Authentifizierungsberechtigungen eingeben. </p> </li> 
      <li id="li_FD7143019C5244C3B8A5B1B5AA84859A"> SFTP <p>Für den Zugriff auf den SFTP-Server müssen Sie entsprechende Authentifizierungsberechtigungen eingeben. </p> </li> 
      <li id="li_38E0036C1365419F9D00083CACA34AFB"> Datei </li> 
      </ul> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Zeitüberschreitung </p> </td> 
      <td colname="col2"> <p>Gibt den Timeout in Sekunden für FTP-, SFTP-, HTTP- oder HTTPS-Verbindungen an. Dieser Wert muss zwischen 30 und 300 liegen. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Weitere Zustellversuche </p> </td> 
      <td colname="col2"> <p>Gibt die maximale Anzahl von Wiederholungen für fehlgeschlagene FTP-, SFTP-, HTTP- oder HTTPS-Verbindungen an. Dieser Wert muss zwischen 0 und 10 liegen. </p> <p>Der Wert Null (0) verhindert Wiederholungsversuche. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Kodierung </p> </td> 
      <td colname="col2"> <p>Gibt das Zeichencodierungssystem an, das in der angegebenen Datenquellendatei verwendet wird. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Trennzeichen </p> </td> 
      <td colname="col2"> <p>Gibt das Zeichen an, mit dem die einzelnen Felder in der angegebenen Datenquellendatei getrennt werden sollen. </p> <p>Das Komma ( <span class="codeph"> , </span>) ist ein Beispiel für ein Trennzeichen. Das Komma dient als Feldtrennzeichen, mit dem Datenfelder in der angegebenen Datenquellendatei voneinander getrennt werden können. </p> <p>Wählen Sie <span class="uicontrol"> Registerkarte? </span> , um das Zeichen für die horizontale Registerkarte als Trennzeichen zu verwenden. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Kopfzeilen in erster Zeile </p> </td> 
      <td colname="col2"> <p>Gibt an, dass die erste Zeile in der Datenquellendatei nur Kopfzeileninformationen enthält, nicht Daten. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Mindestanzahl von Dokumenten für die Indexierung </p> </td> 
      <td colname="col2"> <p>Bei Festlegung auf einen positiven Wert gibt dies die Mindestanzahl der Datensätze an, die in der heruntergeladenen Datei erwartet werden. Wenn weniger Datensätze empfangen werden, wird der Indexvorgang abgebrochen. </p> <p> <b>Hinweis</b>: Diese Funktion ist standardmäßig nicht aktiviert. Wenden Sie sich an den technischen Support, um die Funktion für Ihre Verwendung zu aktivieren. </p> <p> <b>Hinweis</b>: Diese Funktion wird nur bei vollständigen Indexvorgängen verwendet. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Landkarte </p> </td> 
      <td colname="col2"> <p>Gibt Zuordnungen von Spalten zu Metadaten mithilfe von Spaltennummern an. </p> <p> 
      <ul id="ul_981AE2C6D30443BDBFC6575D413732A2"> 
      <li id="li_A42CB9DFFF8C45A7BAC2D471FE96CEBE"> <span class="uicontrol"> Spalte </span> <p> Gibt eine Spaltennummer an, wobei die erste Spalte 1 (1) ist. Um neue Zuordnungszeilen für jede Spalte hinzuzufügen, klicken Sie unter <span class="wintitle"> Aktion </span>auf <span class="uicontrol"> + </span>. </p> <p>Sie müssen nicht auf jede Spalte in der Datenquelle verweisen. Stattdessen können Sie Werte überspringen. </p> </li> 
      <li id="li_26E8C9554A5D4BC5A5073D6385E3626F"> <span class="uicontrol"> Feld </span> <p>Definiert den Wert des Namensattributs, der für jedes generierte &lt;meta&gt;-Tag verwendet wird. </p> </li> 
      <li id="li_5DFA514B7F9549B98D6CBC095A66033C"> <span class="uicontrol"> Metadaten? </span> <p>Das <span class="uicontrol"> Feld wird </span> zu einer Dropdownliste, aus der Sie definierte Metadatenfelder für das aktuelle Konto auswählen können. </p> <p>Der <span class="uicontrol"> Feldwert </span> kann ein nicht definiertes Metadatenfeld sein, falls gewünscht. Ein nicht definiertes Metadatenfeld ist manchmal hilfreich, um Inhalte zu erstellen, die vom <span class="wintitle"> Filtern des Skripts verwendet werden </span>. </p> <p>Siehe <a href="../c-about-settings-menu/c-about-filtering-menu.md#concept_E56B73D625854AB2A899EF2D56CFCB47" type="concept" format="dita" scope="local"> Grundlagen zum Filtern von Skripten </a>. </p> <p>Wenn Index Connector XML-Dokumente mit mehreren Treffern in einem beliebigen Zuordnungsfeld verarbeitet, werden die Werte in einem Dokument, das im Cache gespeichert wird, zu einem einzigen Wert verkettet. Standardmäßig werden diese Werte mit einem Komma-Trennzeichen kombiniert. Angenommen, der entsprechende <span class="wintitle"> Feldwert </span> ist ein definiertes Metadatenfeld. Darüber hinaus ist für dieses Feld das <span class="wintitle"> Attribut Listen zulassen </span> festgelegt. In diesem Fall wird der Wert "Listentrennzeichen"des Felds, das erste definierte Trennzeichen, in der Verkettung verwendet. </p> </li> 
      <li id="li_80DB205525094CE1AA6762BFC7892C95"> <span class="uicontrol"> Primärschlüssel? </span> <p>Nur eine Kartendefinition wird als Primärschlüssel identifiziert. Dieses Feld wird zur eindeutigen Referenz, die angezeigt wird, wenn dieses Dokument zum Index hinzugefügt wird. Dieser Wert wird in der URL des Dokuments im Index verwendet. </p> <p>Die <span class="uicontrol"> primären </span> Schlüsselwerte müssen in allen Dokumenten, die von der Index Connector-Konfiguration dargestellt werden, eindeutig sein. Alle angefallenen Duplikate werden ignoriert. Wenn Ihre Quelldokumente keinen eindeutigen Wert für die Verwendung als <span class="uicontrol"> Primärschlüssel enthalten </span>, aber zwei oder mehr Felder zusammen einen eindeutigen Bezeichner bilden <i>können</i> , können Sie den <span class="uicontrol"> Primärschlüssel definieren, </span> indem Sie mehrere <span class="uicontrol"> </span> Spaltenwerte mit einem vertikalen Balken ("|"), der die Werte trennt, kombinieren. </p> </li> 
      <li id="li_80DB205525094CE1AA6762BFC7892D96"> <span class="uicontrol"> HTML entfernen? </span> <p>Wenn diese Option aktiviert ist, werden alle in den Daten dieses Felds gefundenen HTML-Tags entfernt. </p> </li> 
      <li id="li_359D2902859B4C5BADB0BA26F0BA4DC0"> <span class="uicontrol"> Aktion </span> <p>Hiermit können Sie Zeilen zur Map hinzufügen oder Zeilen aus der Map entfernen. Die Reihenfolge der Zeilen ist nicht wichtig. </p> </li> 
      </ul> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p> <b>Datenquellentyp: Feed</b> </p> </td> 
      <td colname="col2"> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Aktiviert </p> </td> 
      <td colname="col2"> <p>Aktiviert die Konfiguration zu Crawl und Index. Oder Sie können die Konfiguration deaktivieren, um Crawling und Indizierung zu verhindern. </p> <p> <b>Hinweis</b>: Deaktivierte Index Connector-Konfigurationen werden ignoriert, wenn sie in einer Einstiegsliste vorhanden sind. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Host-Adresse </p> </td> 
      <td colname="col2"> <p>Gibt die IP-Adresse oder die URL-Adresse des Hostsystems an, in dem die Datenquellendatei gefunden wird. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Dateipfad </p> </td> 
      <td colname="col2"> <p>Gibt den Pfad zum Master-XML-Dokument an, das mehrere "Zeilen"mit Informationen enthält. </p> <p>Der Pfad ist relativ zum Stammverzeichnis der Hostadresse. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Inkrementeller Dateipfad </p> </td> 
      <td colname="col2"> <p>Gibt den Pfad zum inkrementellen XML-Dokument an, das mehrere "Zeilen"mit Informationen enthält. </p> <p>Der Pfad ist relativ zum Stammverzeichnis der Hostadresse. </p> <p>Diese Datei wird, sofern angegeben, während Inkrementeller Indexvorgänge heruntergeladen und verarbeitet. Wenn keine Datei angegeben ist, wird stattdessen die unter Dateipfad aufgelistete Datei verwendet. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Vertikaler Dateipfad </p> </td> 
      <td colname="col2"> <p>Gibt den Pfad zum XML-Dokument an, der mehrere wenige "Zeilen"mit Informationen enthält, die bei einer vertikalen Aktualisierung verwendet werden sollen. </p> <p>Der Pfad ist relativ zum Stammverzeichnis der Hostadresse. </p> <p>Diese Datei wird, sofern angegeben, während des Vorgangs Vertikale Aktualisierung heruntergeladen und verarbeitet. </p> <p> <b>Hinweis</b>: Diese Funktion ist standardmäßig nicht aktiviert. Wenden Sie sich an den technischen Support, um die Funktion für Ihre Verwendung zu aktivieren. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Löscht Dateipfad </p> </td> 
      <td colname="col2"> <p>Gibt den Pfad zur einfachen Textdatei mit einem einzelnen Dokumentkennungswert pro Zeile an. </p> <p>Der Pfad ist relativ zum Stammverzeichnis der Hostadresse. </p> <p>Diese Datei wird, sofern angegeben, während Inkrementeller Indexvorgänge heruntergeladen und verarbeitet. Die in dieser Datei gefundenen Werte werden verwendet, um Anforderungen zum Löschen von zuvor indizierten Dokumenten zu erstellen. Die Werte in dieser Datei müssen mit den Werten übereinstimmen, die in den Dateien "Vollständiger oder inkrementeller Dateipfad"in der Spalte " <span class="uicontrol"> Primärschlüssel"gefunden wurden </span>. </p> <p> <b>Hinweis</b>: Diese Funktion ist standardmäßig nicht aktiviert. Wenden Sie sich an den technischen Support, um die Funktion für Ihre Verwendung zu aktivieren. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Protokoll </p> </td> 
      <td colname="col2"> <p>Gibt das Protokoll an, das für den Zugriff auf die Datei verwendet wird. Sie können aus den folgenden Optionen wählen: </p> <p> 
      <ul id="ul_976A34FD14A841F2B610C1C0CCBB82B9"> 
      <li id="li_05BBA0F670F14431A89AE4178F1A6F94"> HTTP <p>Bei Bedarf können Sie für den Zugriff auf den HTTP-Server die entsprechenden Authentifizierungsdaten eingeben. </p> </li> 
      <li id="li_100446691F304572B8FC3F083F86A2CB"> HTTPS <p>Bei Bedarf können Sie für den Zugriff auf den HTTPS-Server die entsprechenden Authentifizierungsdaten eingeben. </p> </li> 
      <li id="li_027088A8E30444DAA8CCCC5B0BAA74C1"> FTP <p>Für den Zugriff auf den FTP-Server müssen Sie entsprechende Authentifizierungsberechtigungen eingeben. </p> </li> 
      <li id="li_DCEF9D5C99354990B03E29083C2ED8DC"> SFTP <p>Für den Zugriff auf den SFTP-Server müssen Sie entsprechende Authentifizierungsberechtigungen eingeben. </p> </li> 
      <li id="li_44E34FF2AB0D429EB3408106E6FCF780"> Datei </li> 
      </ul> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>itemTag </p> </td> 
      <td colname="col2"> <p>Identifiziert das XML-Element, mit dem Sie einzelne XML-Zeilen in der angegebenen Datenquellendatei identifizieren können. </p> <p>Im folgenden Feed-Fragment eines Adobe XML-Dokuments lautet der itemTag-Wert beispielsweise <span class="codeph"> record </span>: </p> <p> <code> &lt;?xml&nbsp;version="1.0"&nbsp;encoding="utf-8"?&gt; 
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
      <td colname="col1"> <p>Mindestanzahl von Dokumenten für die Indexierung </p> </td> 
      <td colname="col2"> <p>Bei Festlegung auf einen positiven Wert gibt dies die Mindestanzahl der Datensätze an, die in der heruntergeladenen Datei erwartet werden. Wenn weniger Datensätze empfangen werden, wird der Indexvorgang abgebrochen. </p> <p> <b>Hinweis</b>: Diese Funktion ist standardmäßig nicht aktiviert. Wenden Sie sich an den technischen Support, um die Funktion für Ihre Verwendung zu aktivieren. </p> <p> <b>Hinweis</b>: Diese Funktion wird nur bei vollständigen Indexvorgängen verwendet. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Landkarte </p> </td> 
      <td colname="col2"> <p>Ermöglicht die Angabe von Zuordnungen von XML-Elementen zu Metadaten mithilfe von XPath-Ausdrücken. </p> <p> 
      <ul id="ul_604108C0277C4892AE8A40CA39889ABD"> 
      <li id="li_0AF92270AE9F4BA8B2C7EE41FABC0F34"> <span class="uicontrol"> Tag </span> <p>Gibt eine XPath-Darstellung der analysierten XML-Daten an. Anhand des obigen Adobe XML-Beispieldokuments unter der Option "item-Tag"könnte es mit der folgenden Syntax zugeordnet werden: </p> <p> <code> /record/@displayurl&nbsp;-&gt;&nbsp;page-url 
      /record/metadata/meta[@name='title']/@content&nbsp;-&gt;&nbsp;title 
      /record/metadata/meta[@name='description']/@content&nbsp;-&gt;&nbsp;desc 
      /record/metadata/meta[@name='description']/@content&nbsp;-&gt;&nbsp;body </code> </p> <p>Die obige Syntax übersetzt sich wie folgt: </p> <p> 
      <ul id="ul_6400EBD08D424EADA1612FE4F7EFB640"> 
      <li id="li_9958F9B40D42434195597DBA9F2AF28F"> <code> /record/@displayurl&amp;nbsp;-&gt;&amp;nbsp;page-url </code> <p>Das <span class="codeph"> displayURL- </span> Attribut des <span class="codeph"> record- </span> Elements wird dem Metadatenfeld <span class="codeph"> "page-url"zugeordnet </span>. </p> </li> 
      <li id="li_759013EA02CD48BE971A55B0A6A11424"> <code> /record/metadata/meta[@name='title']/@content&amp;nbsp;-&gt;&amp;nbsp;title </code> <p>Das <span class="codeph"> content- </span> Attribut eines <span class="codeph"> Metaelements, das in einem </span> Metadatenelement enthalten ist, das in einem <span class="codeph"> record- </span> Element enthalten ist, dessen Namensattribut <span class="codeph"> title ist, </span> <span class="codeph"> </span><span class="codeph"> </span>wird dem Metadatenfeld-Titel zugeordnet. </p> </li> 
      <li id="li_E741CA59197D462EB2946EDE874AFDC8"> <code> /record/metadata/meta[@name='description']/@content&amp;nbsp;-&gt;&amp;nbsp;desc </code> <p>Das <span class="codeph"> content- </span> Attribut eines <span class="codeph"> Metaelements, das in einem </span> Metadatenelement enthalten ist, das im <span class="codeph"> record- </span> Element enthalten ist, dessen Namensattribut <span class="codeph"> description lautet, </span> <span class="codeph"> </span><span class="codeph"> </span>ordnet das Metadatenfeld dem desc-zu. </p> </li> 
      <li id="li_E35EAE3D284D46D485D9064D7BB6AB13"> <code> /record/metadata/meta[@name='description']/@content&amp;nbsp;-&gt;&amp;nbsp;body </code> <p>Das <span class="codeph"> content- </span> Attribut eines <span class="codeph"> meta- </span> Elements, das in einem <span class="codeph"> metadata- </span> Element enthalten ist, das im record- <span class="codeph"> Element enthalten ist, dessen name-Attribut </span> <span class="codeph"> </span><span class="codeph"> </span>description ist, wird dem MetadatenfeldTextkörper zugeordnet. </p> </li> 
      </ul> </p> <p>XPath ist eine relativ komplizierte Notation. Weitere Informationen finden Sie unter: </p> <p>Siehe <a href="https://www.w3schools.com/xpath/" scope="external" format="html"> https://www.w3schools.com/xpath/ </a> </p> </li> 
      <li id="li_8147075D7ACD4811A7ED335F23FE62A6"> <span class="uicontrol"> Feld </span> <p>Definiert den Wert des Namensattributs, der für jedes generierte <span class="codeph"> &lt;meta&gt;- </span> Tag verwendet wird. </p> </li> 
      <li id="li_2380199D63BF425A919606D8232FA6E2"> <span class="uicontrol"> Metadaten? </span> <p>Das <span class="uicontrol"> Feld wird </span> zu einer Dropdownliste, aus der Sie definierte Metadatenfelder für das aktuelle Konto auswählen können. </p> <p>Der <span class="uicontrol"> Feldwert </span> kann ein nicht definiertes Metadatenfeld sein, falls gewünscht. Ein nicht definiertes Metadatenfeld ist manchmal hilfreich, um Inhalte zu erstellen, die vom <span class="wintitle"> Filtern des Skripts verwendet werden </span>. </p> <p>Siehe <a href="../c-about-settings-menu/c-about-filtering-menu.md#concept_E56B73D625854AB2A899EF2D56CFCB47" type="concept" format="dita" scope="local"> Grundlagen zum Filtern von Skripten </a>. </p> <p>Wenn Index Connector XML-Dokumente mit mehreren Treffern in einem beliebigen Zuordnungsfeld verarbeitet, werden die Werte in einem Dokument, das im Cache gespeichert wird, zu einem einzigen Wert verkettet. Standardmäßig werden diese Werte mit einem Komma-Trennzeichen kombiniert. Angenommen, der entsprechende <span class="wintitle"> Feldwert </span> ist ein definiertes Metadatenfeld. Darüber hinaus ist für dieses Feld das <span class="wintitle"> Attribut Listen zulassen </span> festgelegt. In diesem Fall wird der Wert "Listentrennzeichen"des Felds, das erste definierte Trennzeichen, in der Verkettung verwendet. </p> </li> 
      <li id="li_DEA24003E97E406DA2510C43CCFDC70E"> <span class="uicontrol"> Primärschlüssel? </span> <p>Nur eine Kartendefinition wird als Primärschlüssel identifiziert. Dieses Feld wird zur eindeutigen Referenz, die angezeigt wird, wenn dieses Dokument zum Index hinzugefügt wird. Dieser Wert wird in der URL des Dokuments im Index verwendet. </p> <p>Die <span class="uicontrol"> primären </span> Schlüsselwerte müssen in allen Dokumenten, die von der Index Connector-Konfiguration dargestellt werden, eindeutig sein. Alle angefallenen Duplikate werden ignoriert. Wenn Ihre Quelldokumente keinen eindeutigen Wert für die Verwendung als <span class="uicontrol"> Primärschlüssel enthalten </span>, aber zwei oder mehr Felder zusammen einen eindeutigen Bezeichner bilden <i>können</i> , können Sie den <span class="uicontrol"> Primärschlüssel definieren, </span> indem Sie mehrere <span class="uicontrol"> Tag- </span> Definitionen mit einem vertikalen Balken ("|"), der die Werte trennt, kombinieren. </p> </li> 
      <li id="li_DEA24003E97E406DA2510C43CCFDC81F"> <span class="uicontrol"> HTML entfernen? </span> <p>Wenn diese Option aktiviert ist, werden alle in den Daten dieses Felds gefundenen HTML-Tags entfernt. </p> </li> 
      <li id="li_5E829D1D0DBD4BB7AAB5DB983053D248"> <span class="uicontrol"> Für Löschen verwenden? </span> <p>Wird nur bei Inkrementellen Indexvorgängen verwendet. Datensätze, die diesem XPath-Muster entsprechen, identifizieren Elemente zum Löschen. Der <span class="uicontrol"> Primärschlüssel- </span> Wert für jeden dieser Datensätze wird verwendet, um "Löschanforderungen"zu erstellen, wie bei "Dateipfad löschen". </p> <p> <b>Hinweis</b>: Diese Funktion ist standardmäßig nicht aktiviert. Wenden Sie sich an den technischen Support, um die Funktion für Ihre Verwendung zu aktivieren. </p> </li> 
      <li id="li_D40E2F9AD8AD49FC9AC4B8C75BA31E28"> <span class="uicontrol"> Aktion </span> <p>Hiermit können Sie Zeilen zur Map hinzufügen oder Zeilen aus der Map entfernen. Die Reihenfolge der Zeilen ist nicht wichtig. </p> </li> 
      </ul> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p> <b>Datenquellentyp: XML</b> </p> </td> 
      <td colname="col2"> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Aktiviert </p> </td> 
      <td colname="col2"> <p>Aktiviert die Konfiguration zu Crawl und Index. Oder Sie können die Konfiguration deaktivieren, um Crawling und Indizierung zu verhindern. </p> <p> <b>Hinweis</b>: Deaktivierte Index Connector-Konfigurationen werden ignoriert, wenn sie in einer Einstiegsliste vorhanden sind. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Host-Adresse </p> </td> 
      <td colname="col2"> <p>Gibt die URL-Adresse des Hostsystems an, in dem die Datenquellendatei gefunden wird. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Dateipfad </p> </td> 
      <td colname="col2"> <p>Gibt den Pfad zum Master-XML-Dokument an, das Links enthält ( 
      <userinput>
        &lt;a&gt; 
      </userinput>) in einzelne XML-Dokumente. </p> <p>Der Pfad ist relativ zum Stammverzeichnis der Hostadresse. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Protokoll </p> </td> 
      <td colname="col2"> <p>Gibt das Protokoll an, das für den Zugriff auf die Datei verwendet wird. Sie können aus den folgenden Optionen wählen: </p> <p> 
      <ul id="ul_EA4EB7953D68483FAD75753B2EE70E74"> 
      <li id="li_537F24C6B2AB435CB7C14117663D7B3F"> HTTP <p>Bei Bedarf können Sie für den Zugriff auf den HTTP-Server die entsprechenden Authentifizierungsdaten eingeben. </p> </li> 
      <li id="li_8C13C93C52364FFA8B9B18830CDB223C"> HTTPS <p>Bei Bedarf können Sie für den Zugriff auf den HTTPS-Server die entsprechenden Authentifizierungsdaten eingeben. </p> </li> 
      <li id="li_2F967B5675254C949B31EAB19910751C"> FTP <p>Für den Zugriff auf den FTP-Server müssen Sie entsprechende Authentifizierungsberechtigungen eingeben. </p> </li> 
      <li id="li_C24BE4C1DE79488AA64C7133D78CD3A6"> SFTP <p>Für den Zugriff auf den SFTP-Server müssen Sie entsprechende Authentifizierungsberechtigungen eingeben. </p> </li> 
      <li id="li_7581C21CFC104986A361F62BD7A370C1"> Datei </li> 
      </ul> </p> <p> <b>Hinweis</b>: Die Einstellung "Protokoll"wird nur verwendet, wenn in den Feldern "Host-Adresse"und/oder "Dateipfad"Informationen angegeben sind. Einzelne XML-Dokumente werden gemäß den jeweiligen URL-Spezifikationen entweder über HTTP oder HTTPS heruntergeladen. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>itemTag </p> </td> 
      <td colname="col2"> <p>Identifiziert das XML-Element, das eine "Zeile"in der von Ihnen angegebenen Datenquellendatei definiert. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Landkarte </p> </td> 
      <td colname="col2"> <p>Hiermit können Sie Zuordnungen von Spalten zu Metadaten mithilfe von Spaltennummern festlegen. </p> <p> 
      <ul id="ul_06F50CBA0AA64C7CB1AFAE076E629A64"> 
      <li id="li_0FA2502869BA40DC93D790B79E15A9D2"> <span class="uicontrol"> Tag </span> <p>Gibt eine XPath-Darstellung der analysierten XML-Daten an. Mithilfe des obigen Beispieldokuments für Adobe XML können Sie es unter der Option ItemTag mit der folgenden Syntax zuordnen: </p> <p> <code> /record/@displayurl&nbsp;-&gt;&nbsp;page-url 
        /record/metadata/meta[@name='title']/@content&nbsp;-&gt;&nbsp;title 
        /record/metadata/meta[@name='description']/@content&nbsp;-&gt;&nbsp;desc 
        /record/metadata/meta[@name='description']/@content&nbsp;-&gt;&nbsp;body </code> </p> <p>Die obige Syntax übersetzt sich wie folgt: </p> <p> 
      <ul id="ul_F8C536E6E54546D9AA5B22B879C0AF39"> 
      <li id="li_78A35DFFF1B4496CAC6EDC7B1E991F29"> <code> /record/@displayurl&amp;nbsp;-&gt;&amp;nbsp;page-url </code> <p>Das <span class="codeph"> displayURL- </span> Attribut des <span class="codeph"> record- </span> Elements wird dem Metadatenfeld <span class="codeph"> "page-url"zugeordnet </span>. </p> </li> 
      <li id="li_FA7DF3D1942248B98660F3D0C82F4563"> <code> /record/metadata/meta[@name='title']/@content&amp;nbsp;-&gt;&amp;nbsp;title </code> <p>Das <span class="codeph"> content- </span> Attribut eines <span class="codeph"> Metaelements, das in einem </span> Metadatenelement enthalten ist, das in einem <span class="codeph"> record- </span> Element enthalten ist, dessen Namensattribut <span class="codeph"> title ist, </span> <span class="codeph"> </span><span class="codeph"> </span>wird dem Metadatenfeld-Titel zugeordnet. </p> </li> 
      <li id="li_D8000A116FF84DE59ED19C656DDD3BC1"> <code> /record/metadata/meta[@name='description']/@content&amp;nbsp;-&gt;&amp;nbsp;desc </code> <p>Das <span class="codeph"> content- </span> Attribut eines <span class="codeph"> Metaelements, das in einem </span> Metadatenelement enthalten ist, das im <span class="codeph"> record- </span> Element enthalten ist, dessen Namensattribut <span class="codeph"> description lautet, </span> <span class="codeph"> </span><span class="codeph"> </span>ordnet das Metadatenfeld dem desc-zu. </p> </li> 
      <li id="li_7FA6A53DFD3D42A98B7BA17CC29DDB81"> <code> /record/metadata/meta[@name='description']/@content&amp;nbsp;-&gt;&amp;nbsp;body </code> <p>Das <span class="codeph"> content- </span> Attribut eines <span class="codeph"> meta- </span> Elements, das in einem <span class="codeph"> metadata- </span> Element enthalten ist, das im record- <span class="codeph"> Element enthalten ist, dessen name-Attribut </span> <span class="codeph"> </span><span class="codeph"> </span>description ist, wird dem MetadatenfeldTextkörper zugeordnet. </p> </li> 
      </ul> </p> <p>XPath ist eine relativ komplizierte Notation. Weitere Informationen finden Sie unter: </p> <p>Siehe <a href="https://www.w3schools.com/xpath/" scope="external" format="html"> https://www.w3schools.com/xpath/ </a> </p> </li> 
      <li id="li_84999D07E0AE4265BC7928BBB49957B9"> <span class="uicontrol"> Feld </span> <p>Definiert den Wert des Namensattributs, der für jedes generierte &lt;meta&gt;-Tag verwendet wird. </p> </li> 
      <li id="li_E125788D0F5242958BD790E26A675C20"> <span class="uicontrol"> Metadaten? </span> <p>Das <span class="uicontrol"> Feld wird </span> zu einer Dropdownliste, aus der Sie definierte Metadatenfelder für das aktuelle Konto auswählen können. </p> <p>Der <span class="uicontrol"> Feldwert </span> kann ein nicht definiertes Metadatenfeld sein, falls gewünscht. Ein nicht definiertes Metadatenfeld ist manchmal hilfreich, um Inhalte zu erstellen, die vom <span class="wintitle"> Filtern des Skripts verwendet werden </span>. </p> <p>Siehe <a href="../c-about-settings-menu/c-about-filtering-menu.md#concept_E56B73D625854AB2A899EF2D56CFCB47" type="concept" format="dita" scope="local"> Grundlagen zum Filtern von Skripten </a>. </p> <p>Wenn Index Connector XML-Dokumente mit mehreren Treffern in einem beliebigen Zuordnungsfeld verarbeitet, werden die Werte in einem Dokument, das im Cache gespeichert wird, zu einem einzigen Wert verkettet. Standardmäßig werden diese Werte mit einem Komma-Trennzeichen kombiniert. Angenommen, der entsprechende <span class="wintitle"> Feldwert </span> ist ein definiertes Metadatenfeld. Darüber hinaus ist für dieses Feld das <span class="wintitle"> Attribut Listen zulassen </span> festgelegt. In diesem Fall wird der Wert "Listentrennzeichen"des Felds, das erste definierte Trennzeichen, in der Verkettung verwendet. </p> </li> 
      <li id="li_9F435EFB3EC74B409EC82A851824609F"> <span class="uicontrol"> Primärschlüssel? </span> <p>Nur eine Kartendefinition wird als Primärschlüssel identifiziert. Dieses Feld wird zur eindeutigen Referenz, die angezeigt wird, wenn dieses Dokument zum Index hinzugefügt wird. Dieser Wert wird in der URL des Dokuments im Index verwendet. </p> <p>Die <span class="uicontrol"> primären </span> Schlüsselwerte müssen in allen Dokumenten, die von der Index Connector-Konfiguration dargestellt werden, eindeutig sein. Alle angefallenen Duplikate werden ignoriert. Wenn Ihre Quelldokumente keinen eindeutigen Wert für die Verwendung als <span class="uicontrol"> Primärschlüssel enthalten </span>, aber zwei oder mehr Felder zusammen einen eindeutigen Bezeichner bilden <i>können</i> , können Sie den <span class="uicontrol"> Primärschlüssel definieren, </span> indem Sie mehrere <span class="uicontrol"> Tag- </span> Definitionen mit einem vertikalen Balken ("|"), der die Werte trennt, kombinieren. </p> </li> 
      <li id="li_9F435EFB3EC74B409EC82A851824610G"> <span class="uicontrol"> HTML entfernen? </span> <p>Wenn diese Option aktiviert ist, werden alle in den Daten dieses Felds gefundenen HTML-Tags entfernt. </p> </li> 
      <li id="li_6302D18971AD439FBECE27742649C56B"> <span class="uicontrol"> Aktion </span> <p>Hiermit können Sie Zeilen zur Map hinzufügen oder Zeilen aus der Map entfernen. Die Reihenfolge der Zeilen ist nicht wichtig. </p> </li> 
      </ul> </p> </td> 
      </tr> 
    </tbody> 
    </table>

1. (Optional) Klicken Sie auf **[!UICONTROL Setup Maps]** , um ein Beispiel Ihrer Datenquelle herunterzuladen. Die Daten werden zur Indizierung der Eignung geprüft. Diese Funktion ist nur für Text- und Feed-Typen verfügbar.
1. (Optional) Klicken Sie **[!UICONTROL Preview]** auf , um die eigentliche Funktionsweise der Konfiguration zu testen. Diese Funktion ist nur für Text- und Feed-Typen verfügbar.
1. Klicken Sie auf **[!UICONTROL Add]** , um die Konfiguration der [!DNL Index Connector Definitions] Seite und der [!DNL Index Connector Configurations] Dropdownliste auf der [!DNL URL Entrypoints] Seite hinzuzufügen.

   Siehe [Informationen zu URL-Einträgen](../c-about-settings-menu/c-about-crawling-menu.md#concept_5D857E3B5C124E85BC0B5AE77A509573).
1. Klicken Sie auf der [!DNL Index Connector Definitions] Seite auf **[!UICONTROL rebuild your staged site index]**.
1. (Optional) Führen Sie auf der [!DNL Index Connector Definitions] Seite einen der folgenden Schritte aus:

   * Klicken Sie auf **[!UICONTROL History]** , um alle vorgenommenen Änderungen wiederherzustellen.

      Siehe [Verwenden der Option](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)Verlauf.

   * Klicken **[!UICONTROL Live]**.

      Siehe [Live-Einstellungen](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)anzeigen.

   * Klicken **[!UICONTROL Push Live]**.

      Siehe [Pushing-Einstellungen](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Bearbeiten einer Index Connector-Definition {#task_DCFC9C6A9964421DB5AB6C25DEE98DE9}

Sie können einen von Ihnen definierten Index Connector bearbeiten.

>[!NOTE]
>
>Es stehen nicht alle Optionen zur Verfügung, die Sie ändern können, z. B. den Index-Connector-Namen oder den Typ aus der [!DNL Type] Dropdownliste.

**So bearbeiten Sie eine Index Connector-Definition**

1. Klicken Sie im Produktmenü auf **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Index Connector]**.
1. Klicken Sie auf der [!DNL Index Connector] Seite unter der [!DNL Actions] Spaltenüberschrift auf **[!UICONTROL Edit]** einen Index Connector-Definitionsnamen, dessen Einstellungen Sie ändern möchten.
1. Legen Sie auf der [!DNL Index Connector Edit] Seite die gewünschten Optionen fest.

   Siehe Tabelle der Optionen unter [Hinzufügen einer Index-Connector-Definition](../c-about-settings-menu/c-about-crawling-menu.md#task_96779B651A654E1F871F55D6DBBC8886).
1. Klicken **[!UICONTROL Save Changes]**.
1. (Optional) Klicken Sie auf der [!DNL Index Connector Definitions] Seite auf **[!UICONTROL rebuild your staged site index]**.
1. (Optional) Führen Sie auf der [!DNL Index Connector Definitions] Seite einen der folgenden Schritte aus:

   * Klicken Sie auf **[!UICONTROL History]** , um alle vorgenommenen Änderungen wiederherzustellen.

      Siehe [Verwenden der Option](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)Verlauf.

   * Klicken **[!UICONTROL Live]**.

      Siehe [Live-Einstellungen](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)anzeigen.

   * Klicken **[!UICONTROL Push Live]**.

      Siehe [Pushing-Einstellungen](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Anzeigen der Einstellungen einer Index Connector-Definition {#task_D0B71A7426E54247BDB3468EC576D871}

Sie können die Konfigurationseinstellungen einer vorhandenen Indexverbindungsdefinition überprüfen.

Nachdem der Seite eine Index-Connector-Definition hinzugefügt wurde, können Sie deren Typeinstellung nicht mehr ändern. [!DNL Index Connector Definitions] Stattdessen müssen Sie die Definition löschen und dann eine neue hinzufügen.

**So zeigen Sie die Einstellungen einer Index Connector-Definition an**

1. Klicken Sie im Produktmenü auf **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Index Connector]**.
1. Klicken Sie auf der [!DNL Index Connector] Seite unter der [!DNL Actions] Spaltenüberschrift auf **[!UICONTROL Edit]** einen Index Connector-Definitionsnamen, dessen Einstellungen Sie überprüfen oder bearbeiten möchten.

## Kopieren einer Index Connector-Definition {#task_3AD55DF07FC44A748D0EFDAB7B35699B}

Sie können eine vorhandene Index Connector-Definition kopieren, um sie als Grundlage für einen neuen Index Connector zu verwenden, den Sie erstellen möchten.

Beim Kopieren einer Index Connector-Definition ist die kopierte Definition standardmäßig deaktiviert. Um die Definition zu aktivieren oder zu aktivieren, müssen Sie sie auf der [!DNL Index Connector Edit] Seite bearbeiten und dann auswählen **[!UICONTROL Enable]**.

Siehe [Bearbeiten einer Index Connector-Definition](../c-about-settings-menu/c-about-crawling-menu.md#task_DCFC9C6A9964421DB5AB6C25DEE98DE9).

**So kopieren Sie eine Index Connector-Definition**

1. Klicken Sie im Produktmenü auf **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Index Connector]**.
1. Klicken Sie auf der [!DNL Index Connector] Seite unter der [!DNL Actions] Spaltenüberschrift auf **[!UICONTROL Copy]** einen Index Connector-Definitionsnamen, dessen Einstellungen Sie duplizieren möchten.
1. Geben Sie auf der [!DNL Index Connector Copy] Seite den neuen Namen der Definition ein.
1. Klicken **[!UICONTROL Copy]**.
1. (Optional) Führen Sie auf der [!DNL Index Connector Definitions] Seite einen der folgenden Schritte aus:

   * Klicken Sie auf **[!UICONTROL History]** , um alle vorgenommenen Änderungen wiederherzustellen.

      Siehe [Verwenden der Option](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)Verlauf.

   * Klicken **[!UICONTROL Live]**.

      Siehe [Live-Einstellungen](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)anzeigen.

   * Klicken **[!UICONTROL Push Live]**.

      Siehe [Pushing-Einstellungen](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Umbenennen einer Index Connector-Definition {#task_5132118FC21B47D99881E0ED425225D7}

Sie können den Namen einer vorhandenen Index Connector-Definition ändern.

Nachdem Sie die Definition umbenannt haben, wählen Sie **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL URL Entrypoints]**. Sie möchten sicherstellen, dass der neue Definitionsname in der Dropdown-Liste auf der [!DNL URL Entrypoints] Seite angezeigt wird.

Siehe [Hinzufügen mehrerer URL-Einstiegspunkte, die indiziert](../c-about-settings-menu/c-about-crawling-menu.md#task_2338A47387D74CFDAC4D4EF4A367ED45)werden sollen.

**So benennen Sie eine Index Connector-Definition um**

1. Klicken Sie im Produktmenü auf **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Index Connector]**.
1. Klicken Sie auf der [!DNL Index Connector] Seite unter der [!DNL Actions] Spaltenüberschrift auf **[!UICONTROL Rename]** den Namen der Index Connector-Definition, den Sie ändern möchten.
1. Geben Sie auf der [!DNL Index Connector Rename] Seite den neuen Namen der Definition in das [!DNL Name] Feld ein.
1. Klicken **[!UICONTROL Rename]**.
1. Klicken Sie auf **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL URL Entrypoints]**. Wenn der Name des vorherigen Index-Connectors in der Liste vorhanden ist, entfernen Sie ihn und fügen Sie den neu umbenannten Eintrag hinzu.

   Siehe [Hinzufügen mehrerer URL-Einstiegspunkte, die indiziert](../c-about-settings-menu/c-about-crawling-menu.md#task_2338A47387D74CFDAC4D4EF4A367ED45)werden sollen. 1. (Optional) Führen Sie auf der [!DNL Index Connector Definitions] Seite einen der folgenden Schritte aus:

   * Klicken Sie auf **[!UICONTROL History]** , um alle vorgenommenen Änderungen wiederherzustellen.

      Siehe [Verwenden der Option](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)Verlauf.

   * Klicken **[!UICONTROL Live]**.

      Siehe [Live-Einstellungen](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)anzeigen.

   * Klicken **[!UICONTROL Push Live]**.

      Siehe [Pushing-Einstellungen](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Löschen einer Index Connector-Definition {#task_6B0BD5D0C09F4597A401B0F3AC7C7EA7}

Sie können eine vorhandene Index Connector-Definition löschen, die Sie nicht mehr benötigen oder verwenden.

**So löschen Sie eine Index Connector-Definition**

1. Klicken Sie im Produktmenü auf **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Index Connector]**.
1. Klicken Sie auf der [!DNL Index Connector Definitions] Seite unter der [!DNL Actions] Spaltenüberschrift auf **[!UICONTROL Delete]** den Namen der Index Connector-Definition, den Sie entfernen möchten.
1. Klicken Sie auf der [!DNL Index Connector Delete] Seite auf **[!UICONTROL Delete]**.
