---
description: Sie können verschiedene Bereiche von "Automatisches Ausfüllen"konfigurieren, um die Erstellung des für die automatische Vervollständigung aktivierten Suchformulars und die Datei autocomplete_data.js zu steuern, die Teil des für die automatische Vervollständigung aktivierten Suchformulars ist.
solution: Target
subtopic: Auto-Complete
title: Über die automatische Vervollständigung
topic-legacy: Design,Site search and merchandising
uuid: 3dfdd14d-2044-4f01-a5bc-fcb2eb0d5068
exl-id: a1d08c0a-6c68-4da2-88d2-fe953d333536
source-git-commit: 95bf92df17d7832df72e8d883a22f9063e53a18d
workflow-type: tm+mt
source-wordcount: '1486'
ht-degree: 1%

---

# Über die automatische Vervollständigung{#about-auto-complete}

Sie können verschiedene Bereiche von &quot;Automatisches Ausfüllen&quot;konfigurieren, um die Erstellung des für die automatische Vervollständigung aktivierten Suchformulars und die Datei autocomplete_data.js zu steuern, die Teil des für die automatische Vervollständigung aktivierten Suchformulars ist.

## Über die automatische Vervollständigung {#concept_093A9CD754864BA79B456FE4BEB64578}

Die Datei [!DNL autocomplete_data.js] wird jedes Mal neu generiert und im Suchinhaltsnetzwerk veröffentlicht, wenn Änderungen vorgenommen werden, die auf der Seite für die automatische Vervollständigung gespeichert wurden.

## Konfigurieren des automatischen Abschlusses {#task_F491F2BFC4D24A61BBDC48B9059C11BB}

Sie können die Optionen zur Steuerung der Erstellung des für die automatische Vervollständigung aktivierten Suchformulars und der Datei konfigurieren und einrichten.

<!-- 

t_configuring_auto-complete.xml

 -->

Nachdem Sie die automatische Vervollständigung konfiguriert haben, können Sie die resultierende HTML-Quelle zur Überprüfung anzeigen. Die HTML-Quelle ist das, was Sie kopieren und in die Seiten Ihrer Website einfügen.

Siehe [Anzeigen einer Vorschau des Suchformulars, wie es auf Ihrem..](c-about-auto-complete.md#task_437B35EFA5424603A08AF8E79E6B4714).

Siehe [Konfigurieren der automatischen Vervollständigung von Word-Liste](c-about-auto-complete.md#task_1F8E0F346263443383F8CFD2C7AB35D4).

Siehe [Konfigurieren des automatischen Ausfüllens von CSS](c-about-auto-complete.md#task_EECE35DEB6C94F4A8A5B42B4DED76D96).

**So konfigurieren Sie die automatische Vervollständigung**

1. Klicken Sie im Produktmenü auf **[!UICONTROL Design]** > **[!UICONTROL Auto-Complete]** > **[!UICONTROL Auto-Complete Setup]**.
1. Legen Sie auf der Seite [!DNL Auto-Complete Setup] die gewünschten Optionen fest.

   Siehe auch [Anzeigen einer Vorschau des Suchformulars, wie es auf Ihrem...](c-about-auto-complete.md#task_437B35EFA5424603A08AF8E79E6B4714).

   <table> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> <p>Option </p> </th> 
      <th colname="col2" class="entry"> <p>Beschreibung </p> </th> 
      </tr> 
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <p>Maximale Vorschläge </p> </td> 
      <td colname="col2"> <p>Gibt die maximale Anzahl von Elementen an, die in der Liste mit Vorschlägen zur automatischen Vervollständigung angezeigt werden. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Mindesteingabezeichen </p> </td> 
      <td colname="col2"> <p>Gibt die Anzahl der Zeichen an, die ein Kunde in das Suchformular für die automatische Vervollständigung eingeben muss, bevor Vorschläge angezeigt werden. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Maximale Cache-Einträge </p> </td> 
      <td colname="col2"> <p>Gibt die maximale Anzahl der zuvor angeforderten Vorschläge zur automatischen Vervollständigung an, die im Browser des Kunden zwischengespeichert werden sollen. Im Allgemeinen sollten Sie diese Einstellung auf den Standardwert 1000 setzen. </p> <p>Sie können die Browserzwischenspeicherung zwar vollständig deaktivieren, indem Sie diese Option auf 0 setzen, jedoch wird dies nicht empfohlen. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Name des Formulars </p> </td> 
      <td colname="col2"> <p>Gibt das Attribut "name"des "form"-Tags des automatisch ausgefüllten aktivierten Suchformulars an. Beispiel: </p> <p> <span class="filepath"> &lt;form name="SiteSearch" method="get" action="https://sp1004337c.guided.t1.atomz.com" target="_blank"&gt; </span> </p> <p>wobei <span class="filepath"> SiteSearch </span> das Attribut name des Formular-Tags ist. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Div-Tag-ID </p> </td> 
      <td colname="col2"> <p>Gibt das ID-Attribut des "div"-Tags des automatisch ausgefüllten aktivierten Suchformulars an. Beispiel: </p> <p> <span class="filepath"> &lt;div id="autocomplete"&gt; </span> </p> <p>wobei <span class="filepath"> autocomplete </span> das Attribut des div-Tags ist. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Eingabe-Tag-ID </p> </td> 
      <td colname="col2"> <p>Gibt das ID-Attribut des "input"-Tags des automatisch ausgefüllten aktivierten Suchformulars an. Beispiel: </p> <p> <span class="filepath"> &lt;input type="text" id="q" name="q" /&gt; </span> </p> <p>wobei <span class="filepath"> q </span> das id-Attribut des Eingabe-Tags ist. </p> </td> 
      </tr> 
      <tr>
      <td colname="col1"> <p>Schatten anzeigen </p> </td>
      <td colname="col2"> <p>Fügt der Liste mit Vorschlägen für die automatische Vervollständigung einen kosmetischen Schlagschatten hinzu. </p> </td>
      </tr>
      <tr>
      <td colname="col1"> <p>Übereinstimmung nur am Anfang der Wortgruppe </p> </td>
      <td colname="col2"> <p>Nur Ergebnisse vorschlagen, die mit dem Anfang des Eingabetexts übereinstimmen. </p> </td>
      </tr>
      <tr>
      <td colname="col1"> <p>UTF-8-Zeichensatz unterstützen </p> </td>
      <td colname="col2"> <p>Ordnungsgemäße Handhabung von Nicht-ASCII-Zeichen in Begriffen. </p> </td>
      </tr>
    </tbody> 
   </table>

1. Klicken **[!UICONTROL Save Changes]**.
1. (Optional) Führen Sie einen der folgenden Schritte aus:

   * Klicken Sie auf **[!UICONTROL History]** , wenn Sie Ihre Änderungen rückgängig machen möchten.

      Siehe [Verwendung der Option Verlauf](t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Klicken **[!UICONTROL Live]**.

      Siehe [Anzeigen von Live-Einstellungen](c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Klicken **[!UICONTROL Push Live]**.

      Siehe [Pushing stage settings live](c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Konfigurieren der automatischen Vervollständigung von Wortlisten {#task_1F8E0F346263443383F8CFD2C7AB35D4}

Konfigurieren Sie die Liste der Wörter und Ausdrücke, die ein Kunde durch automatisches Ausfüllen als Vorschläge anzeigt.

<!-- 

t_configuring_auto-complete_word_list.xml

 -->

Siehe [Konfigurieren des automatischen Ausfüllens](c-about-auto-complete.md#task_F491F2BFC4D24A61BBDC48B9059C11BB).

Siehe [Konfigurieren des automatischen Ausfüllens von CSS](c-about-auto-complete.md#task_EECE35DEB6C94F4A8A5B42B4DED76D96).

**So konfigurieren Sie die automatische Wortliste**

1. Klicken Sie im Produktmenü auf **[!UICONTROL Design]** > **[!UICONTROL Auto-Complete]** > **[!UICONTROL Auto-Complete Word List]**.
1. Legen Sie auf der Seite [!DNL Auto-Complete Word List] die gewünschten Optionen fest.

   Siehe [Anzeigen einer Vorschau des Suchformulars, wie es auf Ihrem..](c-about-auto-complete.md#task_437B35EFA5424603A08AF8E79E6B4714).

   <table> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> <p>Option </p> </th> 
      <th colname="col2" class="entry"> <p>Beschreibung </p> </th> 
      </tr> 
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <p>Zeitraum der beliebten Suchen </p> </td> 
      <td colname="col2"> <p> Steuert den Zeitraum für die Einbeziehung von Wörtern und Ausdrücken aus den jüngsten Suchvorgängen eines Kunden. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p> Maximale Suchanzahl </p> </td> 
      <td colname="col2"> <p>Steuert die maximale Anzahl von gesuchten Wörtern und Ausdrücken, die in die Liste der automatisch ausgefüllten Wörter aufgenommen werden sollen. Die wichtigsten Wörter und Ausdrücke, die auch am beliebtesten sind, sind enthalten. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Feldname </p> </td> 
      <td colname="col2"> <p>Jeder Feldname definiert den Namen eines Felds, für das indizierte Werte eingefügt werden sollen. Verwenden Sie + und - , um Feldnamen hinzuzufügen oder zu entfernen. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Maximale Wertanzahl </p> </td> 
      <td colname="col2"> <p>Definiert die maximale Anzahl von Feldwerten, die für den ausgewählten Feldnamen zulässig sind. Die Top-Werte, die auch am häufigsten referenziert werden, sind enthalten. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Fügen Sie diese Wörter und Ausdrücke hinzu </p> </td> 
      <td colname="col2"> <p> Die Wortliste für die automatische Vervollständigung enthält die Wörter und Ausdrücke, die in diesem Bereich aufgeführt sind. </p> <p> Klicken Sie auf <span class="uicontrol"> </span> bearbeiten , um die Liste anzuzeigen oder Wort und Wortgruppen zur Liste hinzuzufügen. Wenn Sie fertig sind, klicken Sie auf <span class="uicontrol"> Änderungen speichern </span>. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Entfernen Sie diese Wörter und Ausdrücke </p> </td> 
      <td colname="col2"> <p> Einträge in diesem Bereich werden nicht in der Wortliste der automatischen Vervollständigung angezeigt. </p> <p> Klicken Sie auf <span class="uicontrol"> </span> bearbeiten , um die Liste anzuzeigen oder Wort und Wortgruppen zur Liste hinzuzufügen. Wenn Sie fertig sind, klicken Sie auf <span class="uicontrol"> Änderungen speichern </span>. </p> <p> Reguläre Ausdrücke sind in dieser Liste zulässig. Um einen regulären Ausdruck in dieser Liste anzugeben, beginnen Sie die Zeile mit <code>regexp</code> , gefolgt von einem Leerzeichen, gefolgt vom regulären Ausdruck. Alle Zeilen in der Wortliste, die mit dem regulären Ausdruck übereinstimmen, werden entfernt. </p> <p> <b>Wichtig</b>: Sie sollten reguläre Ausdrücke nur verwenden, wenn Sie zuvor in anderen Anwendungen mit ihnen gearbeitet haben. </p> <p>Siehe <a href="c-appendices/r-regular-expressions.md#reference_B5BA7D61D82E4109A01D2A2D964E3A6A" type="reference" format="dita" scope="local"> Reguläre Ausdrücke </a>. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Groß-/Kleinschreibung ignorieren </p> </td> 
      <td colname="col2"> <p>Doppelte Einträge in der Wörterliste für die automatische Vervollständigung, die sich nur durch alphabetische Groß-/Kleinschreibung unterscheiden, werden entfernt. alle Einträge der Wortliste werden in Kleinbuchstaben umgewandelt. </p> <p>Wenn die Vorschläge zum automatischen Ausfüllen "erster Buchstabe großgeschrieben"oder "Großbuchstaben"angezeigt werden sollen, fügen Sie die 
        <code>
          text-transform : capitalize; 
        </code> oder 
        <code>
          text-transform : uppercase; 
        </code> CSS-Texteigenschaften zum automatisch ausgefüllten CSS-Inhalt unter "/* Stile für Ergebniselement */". </p> <p>Siehe <a href="c-about-auto-complete.md#task_EECE35DEB6C94F4A8A5B42B4DED76D96" type="task" format="dita" scope="local"> Konfigurieren des automatischen Ausfüllens von CSS </a>. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Aktualisierung auf Neuindizierung </p> </td> 
      <td colname="col2"> <p>Die automatische Vervollständigung der Wortliste wird nach jeder erfolgreichen Kontoneuindizierung automatisch neu generiert. </p> </td> 
      </tr> 
    </tbody> 
   </table>

1. Klicken **[!UICONTROL Save Changes]**.
1. (Optional) Führen Sie einen der folgenden Schritte aus:

   * Klicken Sie auf **[!UICONTROL History]** , wenn Sie Ihre Änderungen rückgängig machen möchten.
   * Klicken Sie auf **[!UICONTROL Preview Word List]**, um alle von Ihnen vorgenommenen Änderungen zu speichern, und öffnen Sie dann die Seite [!DNL Auto-Complete Word List Preview], auf der Sie die Liste mit Vorschlägen zur automatischen Vervollständigung überprüfen können. Verwenden Sie die Navigationsoptionen oben auf der Seite, um die angezeigte Liste zu überprüfen und zu verfeinern. Wenn Sie fertig sind, klicken Sie auf **[!UICONTROL Close]** , um zur Seite [!DNL Auto-Complete Word List] zurückzukehren.

      Siehe [Verwendung der Option Verlauf](t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Klicken **[!UICONTROL Live]**.

      Siehe [Anzeigen von Live-Einstellungen](c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Klicken **[!UICONTROL Push Live]**.

      Siehe [Pushing stage settings live](c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Konfigurieren der automatischen Vervollständigung von CSS {#task_EECE35DEB6C94F4A8A5B42B4DED76D96}

Verwenden Sie das automatische Ausfüllen von CSS, um das zu verwendende Cascading Style Sheet zu konfigurieren.

<!-- 

t_configuring_auto-complete_css.xml

 -->

Automatische Vervollständigung CSS steuert den Inhalt von [!DNL autocomplete_styles.css], der als Teil des für die automatische Vervollständigung aktivierten Suchformulars enthalten ist. Das hier angegebene CSS steuert die visuelle Darstellung der Vorschlagsliste für die automatische Vervollständigung. Ein Beispiel für die möglichen Ideen zur visuellen Präsentation finden Sie unter:

<!-- 404 DEAD LINK [https://developer.yahoo.com/yui/examples/autocomplete/ac_skinning.html](https://developer.yahoo.com/yui/examples/autocomplete/ac_skinning.html). -->

[Konfigurieren der automatischen Vervollständigung von Wortlisten](c-about-auto-complete.md#task_1F8E0F346263443383F8CFD2C7AB35D4).

[Konfigurieren der automatischen Vervollständigung](c-about-auto-complete.md#task_F491F2BFC4D24A61BBDC48B9059C11BB).

Wenn Sie mit der Konfiguration von CSS zum automatischen Ausfüllen fertig sind, können Sie eine Vorschau des Suchformulars anzeigen, um zu sehen, ob das von Ihnen angegebene CSS für das Erscheinungsbild und Layout akzeptabel ist.

Siehe [Anzeigen einer Vorschau des Suchformulars, wie es auf Ihrem..](c-about-auto-complete.md#task_437B35EFA5424603A08AF8E79E6B4714).

**Wichtig**: Um Ihre benutzerdefinierte CSS für die automatische Vervollständigung anzuwenden, müssen Sie die Kommentar-Tags aus der zweiten Zeile entfernen, die im HTML-Code angezeigt wird. Verschieben Sie dann dieselbe Zeile in den Kopfabschnitt der Seite, die das Suchformular enthält.

Siehe [Kopieren des HTML-Codes des Suchformulars in den ...](c-about-auto-complete.md#task_A3A01EA800F24C0AA33902387E0362C7).

**So konfigurieren Sie automatisch vervollständigte CSS**

1. Klicken Sie im Produktmenü auf **[!UICONTROL Design]** > **[!UICONTROL Auto-Complete]** > **[!UICONTROL Auto-Complete CSS]**.
1. Fügen Sie im Textfeld [!DNL Auto-Complete CSS] die kaskadierenden Stylesheet-Informationen ein oder geben Sie sie ein, die Sie mit der Liste für die automatische Vervollständigung verknüpfen möchten.
1. Klicken **[!UICONTROL Save Changes]**.
1. (Optional) Führen Sie einen der folgenden Schritte aus:

   * Klicken Sie auf **[!UICONTROL History]** , um alle Änderungen rückgängig zu machen, die Sie vorgenommen haben.

      Siehe [Verwendung der Option Verlauf](t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Klicken **[!UICONTROL Live]**.

      Siehe [Anzeigen von Live-Einstellungen](c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Klicken **[!UICONTROL Push Live]**.

      Siehe [Pushing stage settings live](c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Anzeigen einer Vorschau des Suchformulars, wie es auf Ihrer Website angezeigt wird {#task_437B35EFA5424603A08AF8E79E6B4714}

Basierend auf Ihrer Konfiguration von CSS für automatisches Ausfüllen und automatisches Ausfüllen können Sie eine Vorschau des Suchformulars anzeigen, wenn Sie den HTML-Code zu Ihrer Website hinzufügen möchten.

<!-- 

t_previewing_the_search_form_as_it_would_appear_on_your_website.xml

 -->

Siehe [Konfigurieren des automatischen Ausfüllens](c-about-auto-complete.md#task_F491F2BFC4D24A61BBDC48B9059C11BB).

Siehe [Konfigurieren des automatischen Ausfüllens von CSS](c-about-auto-complete.md#task_EECE35DEB6C94F4A8A5B42B4DED76D96).

Siehe [Kopieren des HTML-Codes des Suchformulars in den ...](c-about-auto-complete.md#task_A3A01EA800F24C0AA33902387E0362C7).

Siehe [Verwenden von Sammlungen in Suchformularen](c-appendices/c-searchforms.md#reference_5A079AEEEFB84457892EF0870D0605C3).

Siehe [Verwenden von Frames mit Formularen](c-appendices/c-searchforms.md#reference_82CDDDA1E37042E4849EBF7EA05407C5).

Siehe [Beispiel für ein erweitertes Suchformular](c-appendices/c-searchforms.md#reference_82E1051918744EBA88A01E9E6AE42C4A).

Siehe [Erweiterter HTML-Code für Suchformulare](c-appendices/c-searchforms.md#reference_9AAD4A46B68D4D48865508982CB86DB9).

Siehe [Vordefinierter Code für erweiterte Suchformulare](c-appendices/c-searchforms.md#reference_D762C22E754E462DBEECD88D2C3FA579).

**So zeigen Sie eine Vorschau des Suchformulars an, wie es auf Ihrer Website angezeigt wird**

1. Klicken Sie im Produktmenü auf **[!UICONTROL Design]** > **[!UICONTROL Auto-Complete]** > **[!UICONTROL Search Form]**.
1. (Optional) Klicken Sie auf **[!UICONTROL HTML code]** , um den HTML-Code anzuzeigen, den Sie kopieren und in die Seiten Ihrer Website einfügen.

## Kopieren des HTML-Codes des Suchformulars in die Seiten Ihrer Website {#task_A3A01EA800F24C0AA33902387E0362C7}

Basierend auf Ihrer Konfiguration von CSS für automatisches Ausfüllen und automatisches Ausfüllen können Sie eine Vorschau des Suchformulars anzeigen, wenn Sie den HTML-Code zu Ihrer Website hinzufügen möchten.

<!-- 

t_copying_the_html_code_of_the_search_form_into_the_pages_of_your_website.xml

 -->

Siehe [Konfigurieren des automatischen Ausfüllens](c-about-auto-complete.md#task_F491F2BFC4D24A61BBDC48B9059C11BB).

Siehe [Konfigurieren des automatischen Ausfüllens von CSS](c-about-auto-complete.md#task_EECE35DEB6C94F4A8A5B42B4DED76D96).

Siehe [Kopieren des HTML-Codes des Suchformulars in den ...](c-about-auto-complete.md#task_A3A01EA800F24C0AA33902387E0362C7).

Siehe [Verwenden von Sammlungen in Suchformularen](c-appendices/c-searchforms.md#reference_5A079AEEEFB84457892EF0870D0605C3).

Siehe [Verwenden von Frames mit Formularen](c-appendices/c-searchforms.md#reference_82CDDDA1E37042E4849EBF7EA05407C5).

Siehe [Beispiel für ein erweitertes Suchformular](c-appendices/c-searchforms.md#reference_82E1051918744EBA88A01E9E6AE42C4A).

Siehe [Erweiterter HTML-Code für Suchformulare](c-appendices/c-searchforms.md#reference_9AAD4A46B68D4D48865508982CB86DB9).

Siehe [Vordefinierter Code für erweiterte Suchformulare](c-appendices/c-searchforms.md#reference_D762C22E754E462DBEECD88D2C3FA579).

**So kopieren Sie den HTML-Code des Suchformulars in die Seiten Ihrer Website**

1. Klicken Sie im Produktmenü auf **[!UICONTROL Design]** > **[!UICONTROL Auto-Complete]** > **[!UICONTROL Form Source]**.

   >[!NOTE]
   >
   >Ändern Sie den Wert `form name=` in der Formularquelle nicht.

1. (Optional) Führen Sie einen der folgenden Schritte aus:

   * Wenn Sie das automatische Ausfüllen von CSS konfiguriert haben und die Stile auf das Suchformular angewendet werden sollen, entfernen Sie die Kommentar-Tags aus der zweiten Zeile, die im HTML-Code angezeigt wird. Verschieben Sie dann dieselbe Zeile in den Kopfabschnitt der Seite, die das Suchformular enthält.
   * Um eine maximale Leistung zu erzielen, verschieben Sie die Tags, die unten im HTML-Code aufgelistet sind, und platzieren Sie sie am unteren Rand des Textabschnitts jeder Seite, die das Suchformular enthält.

1. Kopieren Sie den Code und fügen Sie ihn auf den Webseiten Ihrer Website ein, auf denen das Suchformular erscheinen soll.
