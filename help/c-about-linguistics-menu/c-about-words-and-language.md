---
description: Sie können mithilfe von Wörtern und Sprache bestimmen, wie Suchbegriffe mit dem Inhalt Ihrer Webseiten übereinstimmen.
seo-description: Sie können mithilfe von Wörtern und Sprache bestimmen, wie Suchbegriffe mit dem Inhalt Ihrer Webseiten übereinstimmen.
seo-title: Wörter und Sprache
solution: Target
title: Wörter und Sprache
topic: Linguistics,Site search and merchandising
uuid: 793d7a40-4609-44b8-a170-536eb1434537
translation-type: tm+mt
source-git-commit: ef818327e1cdaad79ac47575a8dfba1de3dc5c2e

---


# Wörter und Sprache{#about-words-language}

Sie können festlegen, [!DNL Words & Language] wie Suchbegriffe mit dem Inhalt Ihrer Webseiten übereinstimmen.

## Wörter und Sprache verwenden {#concept_CEB4B9576F3C4E2EB87B352EEC738D79}

Bevor die Auswirkungen der [!DNL Words & Language] Einstellungen für Site-Besucher verfügbar sind, einschließlich aller Änderungen, die Sie an diesen Einstellungen vornehmen, müssen Sie Ihren Site-Index neu generieren. Im Gegensatz zur Indexierung wird bei der Regenerierung keine Suche nach den Webseiten durchgeführt und dauert nur wenige Sekunden.

## Konfigurieren der Übereinstimmung von Suchbegriffen mit Ihrem Webinhalt {#task_351A9144A51F4B41923BDBACDEF3B616}

Mithilfe von Wörtern und Sprache können Sie bestimmen, wie die Site-Suche/das Merchandising mit den Suchbegriffen mit dem Inhalt Ihrer Webseiten übereinstimmt.

<!-- 

t_configuring_how_search_terms_matched_to_your_web_content.xml

 -->

**So konfigurieren Sie, wie Suchbegriffe mit Ihren Webinhalten übereinstimmen**

1. Klicken Sie im Produktmenü auf **[!UICONTROL Linguistics]** > **[!UICONTROL Words & Language]**.
1. Legen Sie auf der [!DNL Words & Languages] Seite die gewünschten Optionen fest.

   <!-- 
   
   r_words_and_languages_options.xml
   
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
      <td colname="col1"> <p>Groß-/Kleinschreibung </p> </td> 
      <td colname="col2"> <p>Nicht standardmäßig ausgewählt. </p> <p>Legt fest, ob Groß- und Kleinbuchstaben unterschieden werden. Wenn diese Option aktiviert ist, wird z. B. "Erfolg"von "Erfolg"unterschieden und die Suchergebnisse können zwischen den beiden variieren. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Diakritische Empfindlichkeit </p> </td> 
      <td colname="col2"> <p>Standardmäßig ausgewählt. </p> <p> Bestimmt, ob Wörter mit diakritischen Zeichen von Wörtern, die dies nicht tun, unterschieden werden. Bei Auswahl dieser Option wird beispielsweise "pagina"von "página"unterschieden. Deaktivieren Sie diese Option, wenn Sie eine Website mit nicht-englischen Sprachen verwenden. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Zahlen </p> </td> 
      <td colname="col2"> <p>Standardmäßig ausgewählt. </p> <p>Legt fest, ob Wörter mit Ziffern indiziert werden. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Apostrophe ignorieren </p> </td> 
      <td colname="col2"> <p>Nicht standardmäßig ausgewählt. </p> <p>Apostrophe werden aus Abfragen entfernt. Beispielsweise würde eine Suche nach "Tree's"dieselben Ergebnisse wie eine Suche nach "Trees"zurückgeben. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Hyphen ignorieren </p> </td> 
      <td colname="col2"> <p>Nicht standardmäßig ausgewählt. </p> <p>Bindestriche werden aus Abfragen entfernt. Beispielsweise würde eine Suche nach "blue-bell"dieselben Ergebnisse wie eine Suche nach "bluebell"zurückgeben. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Teil-Alphanumerische Übereinstimmung </p> </td> 
      <td colname="col2"> <p>Nicht standardmäßig ausgewählt. </p> <p>Wenn diese Option aktiviert ist, können Sie Token auf alphabetisch-numerischen Übergängen aufteilen, um Freitextübereinstimmungen auf Teil- oder Produkttoken zuzulassen. </p> <p>Angenommen, Sie haben eine Produkt-ID von <span class="codeph"> 910XT </span> im Textinhalt einer oder mehrerer Seiten auf einer Website. Wenn diese Option <i>nicht</i> ausgewählt ist, <span class="keyword"> findet Adobe Search&amp;Promote bei der Suche nach </span> 910XT Übereinstimmungen für diese Produkt-ID <span class="codeph"> </span>. Und wenn <span class="uicontrol"> Search Concat-Div-Enable </span> aktiviert ist, <span class="keyword"> findet Adobe Search&amp;Promote auch </span> 910 XT <span class="codeph"> </span>. Es würden jedoch nicht ausschließlich Instanzen von <span class="codeph"> 910 </span> oder <span class="codeph"> XT </span> gefunden. </p> <p>Wenn Sie " <span class="uicontrol"> </span>Partielle alphanumerische Übereinstimmung"auswählen, unterteilt der Indexer diese gemischten alphanumerischen Token in mehrere Token. Eine Produkt-ID wie <span class="codeph"> XYZ123 </span> wird beispielsweise in drei Token indiziert: <span class="codeph"> XYZ123 </span>, <span class="codeph"> XYZ </span>und <span class="codeph"> 123 </span>. Diese Funktion ermöglicht die Suche nach einer beliebigen dieser Varianten mit freiem Text. </p> <p>Angenommen, Sie haben die Produkt-ID <span class="codeph"> AB910XT </span>. Wenn Sie " <span class="uicontrol"> Partielle Alphanumerische Übereinstimmung"auswählen </span> und <i>die Option "</i> Search Concat-Div-Aktivieren" <span class="uicontrol"> aktiviert haben, werden diese von </span> Adobe Search&amp;Promote <span class="keyword"> als </span> AB90XT <span class="codeph"> </span><span class="codeph"> </span><span class="codeph"> </span><span class="codeph"> </span>, AB, 1000, 10000, und XT angezeigt. Wenn ein Benutzer <span class="codeph"> z. B. nach </span>910XT sucht, wird die Suche erweitert, um auch Instanzen von <span class="codeph"> 910XT </span>, <span class="codeph"> 910 </span>oder <span class="codeph"> XT zu finden </span>. </p> <p> <p>Hinweis:  Die <span class="uicontrol"> Suche Concat-Div-Enable </span> ist standardmäßig nicht aktiviert. Wenden Sie sich an den technischen Support, um die Funktion für Ihre Verwendung zu aktivieren. </p> </p> <p> <p>Hinweis:  Die <span class="uicontrol"> teilweise alphanumerische Übereinstimmung </span> wird global auf alle indizierten Felder angewendet. Sie betrifft jedoch nur die Freitextabstimmung. es hat keine Auswirkungen auf die exakte Übereinstimmung oder Bereichsübereinstimmung. </p> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Sound-Alike Matching </p> </td> 
      <td colname="col2"> <p>Standardmäßig ausgewählt. </p> <p>Wörter, die sich ähnlich klingen, sind "Gesundheit"und "Gesundheit"zugeordnet. Diese Funktion ermöglicht es Ihrem Kunden, trotz falscher Schreibweise ein Wort einfach zu suchen. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Alternative Word-Formulare </p> </td> 
      <td colname="col2"> <p>Standard ist <b>Standardalternative Word-Formulare</b>. </p> <p>Sie können aus den folgenden Optionen in der Dropdownliste Alternative Word-Formulare auswählen: 
      <ul id="ul_CAC73FB4D1384312BB5DD327D3D66948"> 
      <li id="li_F4E76CD27EA34AC5BC81E648BC6CBA4C"><b>Keine</b> <p>Während der Indizierung werden keine Wortformulare mit einer Wortfolge oder einer anderen Wortform verwendet. </p> </li> 
      <li id="li_3186FD1F3BC94A5CB66FFF8EA6726D81"><b>Standardmäßige alternative Word-Formulare</b> <p>Die Stemmung erfolgt automatisch während der Indizierung. </p> </li> 
      <li id="li_5815DE0795E0423C9C84C62B96A3F841"><b>Domänenwörterbuch</b> <p>Jedes Domänenwörterbuch, das Sie als stemmendes Wörterbuch festlegen, wird als Quelle alternativer Wortformulare verwendet. </p> <p>Siehe <a href="../c-about-linguistics-menu/c-about-dictionaries.md#concept_B8028B71EC8144669614C64578EDB034" type="concept" format="dita" scope="local"> Info zu Wörterbüchern </a>. </p> <p>Siehe <a href="../c-about-linguistics-menu/c-about-dictionaries.md#task_541E8453A12F4A8E89CF6F595469F074" type="task" format="dita" scope="local"> Konfigurieren eines Wörterbuchs als stemmendes Wörterbuch </a>. </p> </li> 
      </ul> </p> <p>Wenn die Wortstammerkennung in <span class="keyword"> Adobe Search&amp;Promote aktiviert ist, beachten Sie, dass alternative Wortformulare auch innerhalb von Wortgruppen auftreten </span>können. </p> <p>Siehe <a href="../c-searchpromote-release-notes/c-rn-06-19-14-version-815.md#concept_E8CEBC65A28A4E61BDE69B4B4DA55E73" format="dita" scope="local"> Search&amp;Promote 8.15.0 - Versionshinweise (19.06.2014) </a>. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Sprache  </p> </td> 
      <td colname="col2"> <p>Der Standardwert ist <b>Englisch (USA)</b>. </p> <p>Die ausgewählte Sprache stellt sicher, dass Datums- und numerische Werte gemäß den Konventionen des ausgewählten Teils der Welt analysiert werden. </p> <p>Wenn für <span class="uicontrol"> alternative Word-Formulare " </span> Default Alternate Word Forms"oder " <span class="uicontrol"> Domain Dictionary"festgelegt </span> <span class="uicontrol"> </span>ist, ändern sich Wortformulare und Wortende entsprechend den Sprachregeln für die ausgewählte Sprache. </p> <p>Standardmäßig wird die Sprache der auf Ihrer Website gelesenen Seiten nicht mithilfe der Spracheinstellung bestimmt. Die Sprache für eine gelesene Seite wird anhand ihrer HTTP-Kopfzeilen oder von Metatags auf der Seite selbst bestimmt. Ihre Website kann Seiten in vielen verschiedenen Sprachen enthalten. Jede Seite wird korrekt gelesen und indiziert, unabhängig von der Sprache, die hier ausgewählt ist. </p> <p>Wenn Sie eine Unicode-Zeichensatzkodierung wie UTF-8 für einige Seiten auf Ihrer Website verwenden, stellen Sie sicher, dass die Sprache für jede dieser Seiten korrekt angegeben ist. Wenn die entsprechenden HTTP-Header oder -Metatags nicht für Ihre Unicode-Dokumente vorhanden sind, können Sie die entsprechende Sprache mit <span class="uicontrol"> Einstellungen </span> &gt; <span class="uicontrol"> Metadaten </span> &gt; <span class="uicontrol"> Injektionen </span> angeben. </p> <p>Markieren Sie Auf Dokumente ohne bestimmte Sprache <span class="uicontrol"> anwenden? </span> , um die Spracheinstellung für Seiten zu verwenden, die von Ihrer Website aus gelesen werden und keine explizite Einstellung haben. Verwenden Sie diese Einstellung, wenn nur <i>einige</i> Ihrer Dokumente keine Spracheinstellungen haben. Verwenden Sie <span class="uicontrol"> Einstellungen </span> &gt; <span class="uicontrol"> Metadaten </span> &gt; <span class="uicontrol"> Injektionen, </span> wenn entweder <i>keines</i> Ihrer Dokumente Spracheinstellungen hat oder die betroffenen Dokumente eine gut bekannte und überschaubar kleine Liste sind. </p> <p>Siehe <a href="../c-about-settings-menu/c-about-metadata-menu.md#concept_DA091920671948A0A893A26B3A2FAAE5" type="concept" format="dita" scope="local"> Informationen zu Injektionen </a>. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Decompounder verwenden? </p> </td> 
      <td colname="col2"> <p> <p>Hinweis:  Diese Funktion wird nur für Dänisch und Deutsch verwendet. Außerdem ist diese Funktion nicht standardmäßig aktiviert. Wenden Sie sich an den technischen Support, um die Funktion für Ihre Verwendung zu aktivieren. Nach der Aktivierung wird der Dekompounder <b>verwenden angezeigt?</b> wird nur angezeigt, wenn Sie in der oben in dieser Tabelle beschriebenen <span class="uicontrol"> Dropdownliste Sprache die Option Dänisch </span> oder <span class="uicontrol"> Deutsch auswählen </span> <span class="uicontrol"> </span> . </p> </p> <p>Wenn Sie "Dekompounder <span class="uicontrol"> verwenden"auswählen? </span>, unterteilt der Dienst dänische oder deutsche zusammengesetzte Wörter, die die Indizierung von Komponentenwörtern zusammen mit den ursprünglichen zusammengesetzten Wörtern ermöglichen. </p> <p>Um zu sehen, wie diese Funktion funktioniert, geben Sie Wörter in das Textfeld ein und klicken Sie dann auf <span class="uicontrol"> Testen </span>. </p> </td> 
      </tr> 
    </tbody> 
    </table>

1. Klicken **[!UICONTROL Save Settings]**.
1. Um die Ergebnisse Ihrer Änderungen in der Vorschau anzuzeigen, klicken Sie auf **[!UICONTROL regenerate your staged site index]** , um den Index der gestaffelten Website neu zu erstellen.
1. (Optional) Führen Sie einen der folgenden Schritte aus:

   * Klicken **[!UICONTROL Live]**.

      Siehe [Live-Einstellungen](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)anzeigen.

   * Klicken **[!UICONTROL Push Live]**.

      Siehe [Pushing-Einstellungen](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

