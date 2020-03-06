---
description: Mit einem skriptgesteuerten Index können Sie inkrementelle Indexierungsoptionen erstellen, aktualisieren und verwalten, ohne sich anmelden zu müssen. Der Suchroboter liest Anweisungen aus einer Textdatei, die auf Ihrem Server gehostet wird.
seo-description: Mit einem skriptgesteuerten Index können Sie inkrementelle Indexierungsoptionen erstellen, aktualisieren und verwalten, ohne sich anmelden zu müssen. Der Suchroboter liest Anweisungen aus einer Textdatei, die auf Ihrem Server gehostet wird.
seo-title: Über skriptgesteuerten Index
solution: Target
subtopic: Scripted Index
title: Über skriptgesteuerten Index
topic: Index,Site search and merchandising
uuid: 51e726ad-414b-4cbd-8a68-fefc3cf9b565
translation-type: tm+mt
source-git-commit: f21a3f7fe0aeaab517a5ca36da43594873b3e69a

---


# Über skriptgesteuerten Index{#about-scripted-index}

Mit einem skriptgesteuerten Index können Sie inkrementelle Indexierungsoptionen erstellen, aktualisieren und verwalten, ohne sich anmelden zu müssen. Der Suchroboter liest Anweisungen aus einer Textdatei, die auf Ihrem Server gehostet wird.

## Skriptbasierter Index {#concept_34F58D551BC04BFB8ADC294B9DA9199D}

## Grundlagen zum Konfigurieren der inkrementellen Skripterstellung {#section_161D254065E143F3A39F3FC09C400090}

Um skriptgesteuerten Index zu verwenden, geben Sie auf der Seite &quot;Konfiguration des inkrementellen Index&quot;die URL zu einer Skriptdatei (einer Textdatei) an, die sich auf Ihrem Server befindet. Zum Beispiel `https://www.mysite.com/indexlist.txt`. Wenn sich Ihre Site ändert, können Sie der Textdatei entweder manuell oder automatisch Befehlsblöcke hinzufügen (mit einem Skript, das durch die Eingabe von Informationen aus einem News-Feed, einem Stock-Ticker oder einer anderen geänderten Datei ausgelöst wird).

Wenn der skriptgesteuerte inkrementelle Index beginnt, liest der Suchroboter die Textdatei und führt die neuen Befehle aus, die in dieser Datei gefunden werden. Standardmäßig verarbeitet der Suchroboter nur die neuen Befehle, die vom Dateidatum bestimmt werden. Sofern Sie **[!UICONTROL Clear Date]** zum Zeitpunkt der Konfiguration des skriptgesteuerten Indexes keine Prüfung vornehmen, &quot;speichert&quot;der Suchroboter den Datumsbezeichner des zuletzt verarbeiteten Blocks.

## Grundlagen zur Skriptdatei {#section_B312E40539F44C6583B4F9637D428E19}

Die Skriptdatei, die Sie in der URL angeben, ist eine Textdatei, die sich auf Ihrem Server befindet. Sie können Wagenrückgaben, Zeilenvorschub oder beides für die Endsequenz verwenden. Eine leere Zeile enthält null oder mehr Leerzeichen, gefolgt von einer Zeilenende-Sequenz. Bei allen Befehlen wird nicht zwischen Groß- und Kleinschreibung unterschieden.

Die Textdatei ist in Blöcken angeordnet, die die Informationen beschreiben, die der Suchroboter bei der Durchführung eines skriptgesteuerten Inkrementalindex verwendet.

Blöcke werden nach Datum sortiert, wobei die ältesten Blöcke am Anfang der Textdatei und die letzten Blöcke am Ende angeordnet sind. Jeder Block beginnt mit einem einzeiligen Datums- und einem Datums-/Spezifizierer-Befehl und endet mit einem Leerzeilenzeichen, wie im folgenden Blockbeispiel dargestellt (dazwischen gibt es mehrere Befehle):

Bei Verwendung des HTTP 1.1-Stils ist für alle Datumsangaben mit einer Länge unter dem 10. eine vorangestellte Null erforderlich. Der 6. November ist beispielsweise 06. November, nicht der 6. November.

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Befehl </p> </th> 
   <th colname="col2" class="entry"> <p>Beschreibung </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>date-command </p> </td> 
   <td colname="col2"> <p>Die erste Zeile jedes Blocks beginnt mit einem von zwei Datumsbefehlen: </p> <p> 
     <ul id="ul_9C1B229B7F1846C490B853FC34989E77"> 
      <li id="li_31FEF1A7163842BDBB0ABE779D07045A"> <span class="codeph"> date </span> <p>Verwenden Sie den Befehl "Datum", um anzugeben, dass die Datums-/Zeitangabe aus einem Tag, einem Datum, einer Uhrzeit und einer Zeitzone besteht. </p> </li> 
      <li id="li_0918D5B090014C1A852CB80BB7C2867C"> <span class="codeph"> Sekunden </span> <p>Verwenden Sie <span class="codeph"> Sekunden, </span> um anzugeben, dass der Datumsbezeichner aus einer Zeit in Sekunden besteht (z. B. 784111777). Stellen Sie bei Verwendung von <span class="codeph"> Sekunden sicher, </span>dass die Anzahl der Sekunden zwischen den Blöcken zunimmt. </p> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>date-specifier </p> </td> 
   <td colname="col2"> <p>Der <span class="codeph"> Befehl "Date-Specifier" </span> zeichnet in der Regel entweder das normale Datum und die Uhrzeit (Befehl "Datum") oder die Zeit in Sekunden (Befehl "Sekunden") auf, zu der die Blockinformationen der Datei hinzugefügt wurden. Beispiel: </p> <p> <code> date&nbsp;Sun,&nbsp;06&nbsp;Nov&nbsp;1994&nbsp;08:49:37&nbsp;GMT&nbsp;(HTTP&nbsp;1.1&nbsp;style) 
      date&nbsp;Sunday,&nbsp;06-Nov-94&nbsp;08:49:37&nbsp;GMT&nbsp;(HTTP&nbsp;1.0&nbsp;style) 
      date&nbsp;Sun&nbsp;Nov&nbsp;6&nbsp;08:49:37&nbsp;1994&nbsp;(Unix&nbsp;asctime()&nbsp;date&nbsp;style) 
      seconds&nbsp;784111777&nbsp;(Unix&nbsp;epoch-seconds&nbsp;style) </code> </p> <p>Bei Verwendung des HTTP 1.1-Stils ist für alle Datumsangaben mit einer Länge unter dem 10. eine vorangestellte Null erforderlich. Der 6. November ist beispielsweise 06. November, nicht der 6. November. </p> <p>Der Suchroboter "erinnert"sich an den Datumsbezeichner des zuletzt verarbeiteten Blocks und indiziert nur Informationen, die er als "neuer"ansieht. (Echtzeit spielt für den Suchroboter keine Rolle. Stattdessen kommt es auf die Zeit im Verhältnis zu anderen zuvor verarbeiteten Zeiten an.) </p> <p>Nachdem der Suchroboter beispielsweise einen Block mit einer Datumsangabe von 22.00 Uhr gelesen hat, werden keine Blöcke gelesen, die vor 22.00 Uhr aufgezeichnet wurden, unabhängig davon, wann der Indexvorgang ausgeführt wird. Im schlimmsten Fall können Sie versehentlich das Jahr "2040"anstelle von "2004"in Ihrer Datumsangabe eingeben. In einem solchen Fall indiziert der Suchroboter den 2040-Block während des nächsten Indizierungsvorgangs und weigert sich dann, alle anderen Informationsblöcke zu lesen (es sei denn, dass ein solcher Zeitraum 2040 ist). Wenn dies der Fall sein sollte, entfernen Sie alle zuvor verarbeiteten Blöcke aus der Textdatei, klicken Sie auf "Datum <span class="uicontrol"> löschen" </span>, und veröffentlichen Sie es dann live. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Kommentarzeile </p> </td> 
   <td colname="col2"> <p>Beginnen Sie mit Kommentarzeilen mit dem Zeichen "#". </p> <p>Jede Kommentarzeile muss eine eigene Zeile sein. Sie können keine Kommentare zum Ende der Zeile eingeben. </p> <p>Eine Kommentarzeile wird nicht als Leerzeile betrachtet. Er kann auch an einer beliebigen Stelle in einem Block erscheinen, selbst vor einem Datums- oder Sekundenbefehl, wie im folgenden Beispiel: </p> <p> <code> &nbsp;&nbsp;&nbsp;&nbsp;#Added&nbsp;by&nbsp;Cathy&nbsp;Read&nbsp;after&nbsp;the&nbsp;Y2K&nbsp;seminar 
      &nbsp;&nbsp;&nbsp;&nbsp;date&nbsp;Mon,&nbsp;29&nbsp;Dec&nbsp;1999&nbsp;09:32:20&nbsp;GMT&nbsp; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>action-command </p> </td> 
   <td colname="col2"> <p>Jeder Textblock kann beliebig viele Aktionsbefehle enthalten. Die folgenden Optionen für Aktionsbefehle entsprechen denen für die standardmäßige inkrementelle Indexierung: </p> <p> 
     <ul id="ul_8E1435350A0F416BB8F7826CD3886E74"> 
      <li id="li_22181666628C48A28A6A0BA1F7CA8E77"> 
       <userinput>
         hinzufügen 
       </userinput> <p>Mit URL verwenden. Der Suchroboter indiziert nur die angegebenen URLs, die sich seit der letzten Indexierung geändert haben. Darüber hinaus folgt der Suchroboter Links, die in bestimmten Dokumenten und Indizes enthalten sind, nur den Dokumenten, die geändert wurden. </p> <p>Sie können der URL mit 
        <userinput>
          nofollow 
        </userinput> oder 
        <userinput>
          noindex 
        </userinput> Schlüsselwörter wie im folgenden Beispiel: </p> <p> <code> add&amp;nbsp;https://www.mydomain.com/&amp;nbsp;noindex </code> </p> </li> 
      <li id="li_8E47BF07DB24417083883F5BF40D6B9E"> 
       <userinput>
         update 
       </userinput> <p>Mit URL-Maske verwenden. Der Suchroboter findet und aktualisiert alle Dokumente, die der angegebenen URL-Maske entsprechen. </p> <p>Sie können der URL mit 
        <userinput>
          nofollow 
        </userinput> oder 
        <userinput>
          noindex 
        </userinput> Schlüsselwörter wie im folgenden Beispiel: </p> <p> <code> update&amp;nbsp;https://www.mydomain.com/products/ </code> </p> </li> 
      <li id="li_B3EC8B1670D54F66A1D8411A694EF7E4"> 
       <userinput>
         zählen 
       </userinput> oder 
       <userinput>
         exclude 
       </userinput> <p>Mit URL-Maske verwenden. Der Suchroboter findet und indiziert Dokumente ("einschließen") oder ignoriert ("ausschließen") je nach Art der angegebenen Maske. </p> <p>Beispiel: </p> <p> <code> include&amp;nbsp;https://www.mydomain.com/products/household/lightbulbs*.html </code> </p> <p>oder </p> <p> <code> exclude&amp;nbsp;https://www.mydomain.com/archive/ </code> </p> </li> 
      <li id="li_050B54B735F0475E93806455FA6DC6A5"> 
       <userinput>
         include-date 
       </userinput> oder 
       <userinput>
         exclude-date 
       </userinput> <p>Mit URL-Maske verwenden. Der Suchroboter findet und indiziert ("einschließen") oder ignoriert ("ausschließen") Dokumente, die auf der URL und dem Datum der Dokumente basieren. Die folgenden Masken stehen zur Verfügung: </p> <p> 
        <ul id="ul_23A15CB492214B86BE84D8E6EA1820AE"> 
         <li id="li_0C7051AC3B5A4C57A3E477F7B6246611"> 
          <userinput>
            include-days NNN 
          </userinput> <p>Der Suchroboter indiziert alle Dokumente, die mit der angegebenen URL-Maske übereinstimmen und mindestens NNN Tage alt sind. </p> <p>Sie können der URL-Maske mit den Suchbegriffen folgen 
           <userinput>
             nofollow 
           </userinput>, 
           <userinput>
             noindex 
           </userinput>und/oder 
           <userinput>
             server-date 
           </userinput>. </p> </li> 
         <li id="li_983A10E2ED5D434EA9031F32143F4EF4"> 
          <userinput>
            include-date YYYY-MM-DD 
          </userinput> <p> Der Suchroboter indiziert alle Dokumente, die mit der angegebenen URL-Maske übereinstimmen und älter sind als das Datum JJJJ-MM-TT, wobei "JJJ"das vierstellige Jahr, "MM"der ein- oder zweistellige Monat (1-12) und "TT"der ein- oder zweistellige Tag (1-31) ist. </p> <p>Sie können der URL-Maske mit den Suchbegriffen folgen 
           <userinput>
             nofollow 
           </userinput>, 
           <userinput>
             noindex 
           </userinput>und/oder 
           <userinput>
             server-date 
           </userinput>. </p> </li> 
         <li id="li_733CE1B748024CECA7FBE00D7BC7B88A"> 
          <userinput>
            exclude-days NNN 
          </userinput> <p> Deaktiviert die Indexierung aller Dokumente, die mit der angegebenen URL-Maske übereinstimmen und NN-Tage oder älter sind. </p> <p>Sie können der URL-Maske mit dem Suchbegriff folgen 
           <userinput>
             server-date 
           </userinput>. </p> </li> 
         <li id="li_90056A0B96CC4DA3854711860A15CE89"> 
          <userinput>
            exclude-date YYYY-MM-DD 
          </userinput> <p>Deaktiviert die Indexierung aller Dokumente, die der angegebenen URL-Maske entsprechen und älter als das Datum JJJ-MM-TT sind. </p> <p>Sie können der URL-Maske mit dem Suchbegriff folgen 
           <userinput>
             server-date 
           </userinput>. </p> </li> 
        </ul> </p> </li> 
      <li id="li_AA78F22B60FE4535BE73BA87A8992C08"> 
       <userinput>
         delete 
       </userinput> <p>Geben Sie URLs an. Der Suchroboter entfernt Dokumente aus dem Index, die durch die URL identifiziert werden. </p> </li> 
      <li id="li_9C63061568AA4D57A4FEBCF6DB9194EC"> 
       <userinput>
         deletemask 
       </userinput> <p>Der Suchroboter entfernt Dokumente aus dem Index, die der angegebenen URL-Maske entsprechen. </p> </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

Siehe auch [URL-Masken](../c-about-settings-menu/c-about-crawling-menu.md#concept_8039DFC53FF3410AA494D602F71BA164).

## Beispieldatei {#section_9F580F20E7214751B157A28B392BD64E}

Im folgenden Beispielskript-Dateibeispiel verarbeitet der Suchroboter die Blöcke, sofern die Datumsangabe nach dem Datum der Datumsangabe des zuletzt verarbeiteten Blocks erfolgt. Ist dies der Fall, werden die folgenden Indexierungsvorgänge ausgeführt:

* Löscht `y2k-problems.html` aus dem Index.
* Fügt `no-y2k-problems.html` zum Suchindex hinzu und folgt keinem der Links für `no-y2k-problems.html`.

* Schließen Sie beim Crawling URLs, die mit `housewares.htm` und `lightfixtures.htm`l übereinstimmen, aus dem Suchindex aus.

* Schließen Sie alle anderen Ordner und Dokumente unter ein `www.mydomain.com`.
* Aktualisieren Sie alle Dokumente innerhalb der Ordner `products` und `information` Ordner, indem Sie alle Links, die sich seit der letzten Indexierung geändert haben, durchsuchen und indizieren.

* Schließen Sie beim Crawling URLs im `archive` Abschnitt der Website aus, wenn sie am oder vor dem 1. Januar 1999 datiert sind.
* Schließen Sie URLs aus, die mit dem Suchindex übereinstimmen `housewares.html` und `lightfixtures.html` diese enthalten.

* Indexdateien im `help` Verzeichnis, jedoch keine Links aus diesen Dateien durchsuchen oder indizieren.
* Suchen und indizieren Sie alle anderen Dateien, die für `www.mydomain.com`gefunden wurden.

```
# Start of file. 
# Added by John Smith 
date Sat, 01 Jan 2004 16:05:53 PST 
exclude https://www.mydomain.com/housewares.html 
exclude https://www.mydomain.com/lightfixtures.html 
include https://www.mydomain.com/ 
delete https://www.mydomain.com/y2k-problems.html 
add https://www.mydomain.com/no-y2k-problems.html nofollow 
 
date Sun, 02 Jan 2004 20:19:08 PST 
# Added by the wire service updater 
exclude-date 1999-01-01 https://www.mydomain.com/archive server-date 
exclude https://www.mydomain.com/housewares.html 
exclude https://www.mydomain.com/lightfixtures.html 
include https://www.mydomain.com/help/ nofollow 
include https://www.mydomain.com/ 
# no add files, just update existing files 
# update all files in the "products" directory 
update https://www.mydomain.com/products/ 
# update all files in the "information" directory 
update regexp ^https://www\.mydomain\.com/information/.*$ 
# End of file.
```

## Konfigurieren eines skriptgesteuerten inkrementellen Indexes {#task_05AE040FE75E40FFAA5E10B6B6D4D255}

Sie können ein von Ihnen erstelltes Skript angeben, das einen inkrementellen Index schreibt, aktualisiert und verwaltet, ohne sich anmelden zu müssen. Der Suchroboter liest Anweisungen aus der Textdatei, die auf Ihrem Server gehostet wird, um den inkrementellen Index auszuführen.

**So konfigurieren Sie einen skriptbasierten inkrementellen Index**

1. Klicken Sie im Produktmenü auf **[!UICONTROL Index]** > **[!UICONTROL Scripted Index]** > **[!UICONTROL Configuration]**.
1. Geben Sie auf der **[!UICONTROL Scripted Incremental Index Configuration]** Seite im Feld **[!UICONTROL Script File URL]** die URL zum Skript für die Textdatei ein, das sich auf Ihrem Server befindet.

   Siehe [Grundlagen zu skriptgesteuerten Index](../c-about-index-menu/c-about-scripted-index.md#concept_34F58D551BC04BFB8ADC294B9DA9199D).
1. (Optional) Überprüfen Sie, **[!UICONTROL Clear Date]** ob der Suchroboter nicht die Datumsangabe des zuletzt verarbeiteten Blocks &quot;merken&quot;soll.

   Standardmäßig verarbeitet der Suchroboter nur neue Befehlsblöcke, die in der Textdatei enthalten sind, die vom Datum der Datei bestimmt wird. Wenn Sie die Standardeinstellung nicht wünschen, aktivieren Sie **[!UICONTROL Clear Date]**.
1. Klicken **[!UICONTROL Save Changes]**.
1. (Optional) Führen Sie einen der folgenden Schritte aus:

   * Klicken Sie auf **[!UICONTROL History]** , um alle vorgenommenen Änderungen wiederherzustellen.

      Siehe [Verwenden der Option](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)Verlauf.

   * Klicken **[!UICONTROL Live]**.

      Siehe [Live-Einstellungen](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)anzeigen.

   * Klicken **[!UICONTROL Push Live]**.

      Siehe [Pushing-Einstellungen](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Einstellen des inkrementellen Index-Zeitplans für eine Live-Website {#task_B3A87AC4AC784507859C23B9062BA11C}

Sie können die skriptgesteuerte inkrementelle Indexierung planen, die in regelmäßigen Abständen am Tag erfolgt.

Die gewählte Basiszeit ist lokal gemäß der Zeitzone, die in den Kontoeinstellungen konfiguriert ist.

Siehe [Konfigurieren der Kontoeinstellungen](../c-about-settings-menu/c-about-account-options-menu.md#task_80A38D0C8E4F453395BD67B81E4B45D9).

Webserver sollen oft mitten in der Nacht zur Wartung aussteigen. Wenn Ihr Server während einer geplanten Indexzeit ausfällt, schlägt der Indexierungsvorgang fehl. Stellen Sie sicher, dass Sie eine Tageszeit auswählen, zu der der Webserver verfügbar ist.

Der Index-Plan gilt nur für Ihren Live-Index. Sie können keine gestaffelten inkrementellen Indizes planen.

**So legen Sie den Zeitplan für den inkrementellen Index für eine Live-Website fest**

1. Klicken Sie im Produktmenü auf **[!UICONTROL Index]** > **[!UICONTROL Scripted Index]** > **[!UICONTROL Live Schedule]**.
1. Wählen Sie auf der **[!UICONTROL Scripted Incremental Index Schedule]** Seite in der **[!UICONTROL Read the Scripted Incrementally Indexing File]** Dropdownliste die Häufigkeit, mit der die skriptbasierte inkrementelle Textdatei in Stunden oder Minuten ausgeführt werden soll.
1. Wählen Sie in der **[!UICONTROL Base Time]** Dropdownliste die Startzeit aus, zu der Sie einen neuen skriptgesteuerten Inkrementalindex neu generieren möchten.
1. Klicken **[!UICONTROL Save Changes]**.

## Ausführen eines skriptbasierten inkrementellen Indexes einer Live- oder Staged-Website {#task_6E6FC76EE1E84A5FADB3B67AD7B1DACB}

Sie können Scripted Incremental Index verwenden, um &quot;Teile&quot;Ihrer Live- oder Stage-Website zu indizieren, z. B. eine Sammlung häufig geänderter Seiten, ohne sich anmelden zu müssen.

Um diese Funktion zu verwenden, müssen Sie eine skriptgesteuerte inkrementelle Indextextdatei konfigurieren.

Siehe [Konfigurieren eines skriptgesteuerten Inkrementalindex](../c-about-index-menu/c-about-scripted-index.md#task_05AE040FE75E40FFAA5E10B6B6D4D255).

**So führen Sie einen skriptgesteuerten inkrementellen Index einer Live- oder Staged-Website aus**

1. Führen Sie im Produktmenü einen der folgenden Schritte aus:

   * Klicken Sie auf **[!UICONTROL Index]** > **[!UICONTROL Scripted Index]** > **[!UICONTROL Live Index]**.
   * Klicken Sie auf **[!UICONTROL Index]** > **[!UICONTROL Scripted Index]** > **[!UICONTROL Staged Index]**.

1. Klicken **[!UICONTROL Scripted Index Now]**.
1. (Optional) Wenn Indexierungsfehler aufgetreten sind, klicken Sie auf **[!UICONTROL View Errors]** , um das zugehörige Protokoll anzuzeigen.

## Ansicht des skriptgesteuerten inkrementellen Indexprotokolls einer Live- oder Staged-Website {#task_CBFCE9B9A87B4DF7A2A35A6E83DE93D7}

Wenn ein vollständiger, skriptfähiger Index oder ein gestaffelter vollständiger, skriptgebundener Index abgeschlossen ist, können Sie das zugehörige Protokoll anzeigen, um Fehler zu beheben, die aufgetreten sind.

Protokolle können weder exportiert noch gespeichert werden. Das Protokoll bleibt jedoch bis zum Auftreten des neuen Indexes zur Ansicht verfügbar.

**So zeigen Sie das inkrementelle Indexprotokoll einer Live- oder Stage-Website an**

1. Führen Sie im Produktmenü einen der folgenden Schritte aus:

   * Klicken Sie auf **[!UICONTROL Index]** > **[!UICONTROL Scripted Index]** > **[!UICONTROL Live Log]**.

   * Klicken Sie auf **[!UICONTROL Index]** > **[!UICONTROL Scripted Index]** > **[!UICONTROL Staged Log]**.

1. Führen Sie auf der Protokollseite oben oder unten einen der folgenden Schritte aus:

   * Verwenden Sie die Navigationsoptionen **[!UICONTROL First]**, **[!UICONTROL Prev]**, **[!UICONTROL Next]**, **[!UICONTROL Last]** oder **[!UICONTROL Go to line]** , um durch das Protokoll zu navigieren.

   * Verwenden Sie die Anzeigeoptionen **[!UICONTROL Errors only]**, **[!UICONTROL Wrap line]** oder **[!UICONTROL Show]** , um Ihre Anzeige zu verfeinern.

