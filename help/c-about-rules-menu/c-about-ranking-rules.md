---
description: Mithilfe von Ranking Rules können Sie die relative Positionierung oder Rangfolge der Suchergebnisse eines Kunden auf Basis von enthaltenen Meta-Tag-Inhalten und zugehörigen Adobe Analytics-Metriken steuern.
seo-description: Mithilfe von Ranking Rules können Sie die relative Positionierung oder Rangfolge der Suchergebnisse eines Kunden auf Basis von enthaltenen Meta-Tag-Inhalten und zugehörigen Adobe Analytics-Metriken steuern.
seo-title: Info zu Ranking Rules
solution: Target
subtopic: Ranking Rules
title: Info zu Ranking Rules
topic: Rules,Site search and merchandising
uuid: 21962f9a-1d9c-442f-a6c4-5f452436c640
translation-type: tm+mt
source-git-commit: 552f93f1f630c64bbe3d5c8a87c4f5895ae6868c
workflow-type: tm+mt
source-wordcount: '4647'
ht-degree: 0%

---


# Info zu Ranking Rules{#about-ranking-rules}

Mithilfe von Ranking Rules können Sie die relative Positionierung oder Rangfolge der Suchergebnisse eines Kunden auf Basis von enthaltenen Meta-Tag-Inhalten und zugehörigen Adobe Analytics-Metriken steuern.

## Verwenden von Ranking Rules {#concept_F555C076759B4E81B925441CFE707397}

Sie definieren Rangregeln, um die relative Platzierung der Dokumente in Ihren Suchergebnissen auf der Grundlage der Inhalte der einzelnen Dokument zu beeinflussen. Sie können Rangregeln entweder auf Meta-Tag-Inhalten, Adobe Analytics-Metriken (sofern Ihr Konto für die Verwendung mit Adobe Analytics konfiguriert ist) oder Adobe Analytics-HBX-Metriken (wenn Ihr Konto für die Verwendung mit Adobe Analytics HBX konfiguriert ist) aufbauen.

Sie können Webseiten mit Meta-Tags mit gewünschten Eigenschaften, wie z. B. einen bestimmten Markennamen oder Preis, oder Webseiten mit erwünschten Adobe Analytics-Leistungsindikatoren, wie z. B. Unique Viewers, so einrichten, dass sie eine höhere Rangfolge erhalten als Webseiten, die dies nicht tun. Die &quot;wünschenswerten&quot;Eigenschaften können einfach aktualisiert werden, indem Sie Rangregeln hinzufügen oder bearbeiten und dann Ihre Website neu indizieren.

Wenn Sie mehr als ein Meta-Tag des Typs &quot;Rang&quot;definiert haben, können Sie separate Regelsammlungen erstellen, die zur Berechnung der verschiedenen Rangfelder verwendet werden. Sie können eine Rangregelgruppe hinzufügen, die Sie dann einem Ihrer definierten Rangfelder zuweisen können. Regelgruppen enthalten in der Regel eine oder mehrere Regeldefinitionen, können aber auch auf andere Regelgruppen verweisen. So können Sie eine oder mehrere Gruppen häufig verwendeter Regeln erstellen, die bei der Berechnung Ihrer mehrstufigen Reihen gemeinsam verwendet werden.

Siehe [Hinzufügen einer Rangregelgruppe](../c-about-rules-menu/c-about-ranking-rules.md#task_B65081B3CC9E4330A7FEE77B7BCD36C8).

Ein positiver Rangwert fördert die Suchergebnisse nach oben; Ein negativer Rangwert zeigt Suchergebnisse am Ende der Suchergebnisse an. Der normale Bereich für die Rangwerte ist 1,0, was die maximale Promotion innerhalb der Suchergebnisse ist, während -1,0 die maximale Abbruchrate ist. Sie können diesen Bereich zwar anpassen, indem Sie das Feld &quot;Rang&quot;in den Metadatendefinitionen bearbeiten, diese Art der Anpassung ist jedoch in der Regel nicht erforderlich.

Siehe [Grundlagen zu Definitionen](../c-about-settings-menu/c-about-metadata-menu.md#concept_AE48035C210145169BE067D396975620).

Wenn Sie unter &quot;Einstellungen&quot;> &quot;Metadaten&quot;> &quot;Definitionen&quot;mehr als ein Rangfeld definiert haben, haben Sie die Möglichkeit, für jedes Rangfeld einen weiteren Satz von Rangregeln zu erstellen. Sie können zusätzliche Rangregeln definieren, ohne direkt mit einem Rangfeld verknüpft zu sein. Mit dieser Flexibilität können Sie allgemeine Regeln erstellen, die bei der Berechnung eines oder mehrerer Rangwerte freigegeben werden können.

**Wichtig**: Bevor Sie Ranking Rules verwenden können, müssen Sie mehrere Kontokonfigurationsschritte ausführen.

Siehe [Konfigurieren der Rangordnung](../c-about-rules-menu/c-about-ranking-rules.md#task_4CEBC13925B047FC95BDC217B48089C5)

## Konfigurieren der Rangordnung {#task_4CEBC13925B047FC95BDC217B48089C5}

Bevor Sie Rangregeln verwenden können, müssen Sie mehrere Kontokonfigurationsschritte ausführen.

**So konfigurieren Sie die Rangordnung**

1. Wählen Sie aus den folgenden Optionen:

   <table> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> <p>Aufgabe </p> </th> 
      <th colname="col2" class="entry"> <p>Konfiguration </p> </th> 
      </tr> 
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <p>So erstellen Sie Rangregeln, die auf Meta-Tags basieren </p> </td> 
      <td colname="col2"> <p> 
      <ol id="ol_28ABB980143948DFA79AC4360AAB7556"> 
      <li id="li_544075CFA0964C6F8FAF7941AAA9ECCC"> Klicken Sie im Produktmenü auf <span class="uicontrol"> Einstellungen </span> &gt; <span class="uicontrol"> Metadaten </span> &gt; <span class="uicontrol"> Definitionen </span>. </li> 
      <li id="li_F237F13B89E8425080C15D3BD697652C"> Klicken Sie auf der Seite Definitionen auf <span class="uicontrol"> Neues Feld Hinzufügen </span>. </li> 
      <li id="li_2A839874D71D45FEA661B3D3B8BE2A86"> Geben Sie auf der Seite "Hinzufügen"in das <span class="uicontrol"> Textfeld "Feldname" </span> ein <code>
        rank 
      </code>; Geben Sie im Textfeld <span class="uicontrol"> Meta-Tag-Name </span> den Wert <code>
        rank 
      </code>ein. Wählen Sie in der <span class="uicontrol"> Dropdown-Liste Datentyp </span> die Option <span class="uicontrol"> Rang </span>. Lassen Sie alle anderen Feldoptionen unverändert. <p>Siehe Abfrage Parameter <span class="codeph"> sp_sr </span> in <a href="../c-appendices/c-cgiparameters.md#reference_582E85C3886740C98FE88CA9DF7918E8" type="reference" format="dita" scope="local"> Backend-Suchparameter CGI </a>. </p> </li> 
      <li id="li_8E91AF4BE51A4A41ABBF9680DDE0B7CE">Klicken Sie auf <span class="uicontrol">Hinzufügen </span>. </li> 
      </ol> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>So erstellen Sie Rangregeln, die auf Adobe Analytics-Metriken basieren </p> </td> 
      <td colname="col2"> <p> 
      <ol id="ol_BE57CBC303D941778B10D855ADC93C68"> 
      <li id="li_8DF5D8F924B24ECBBD2D93C76C69D00C"> Vergewissern Sie sich, dass Sie die Adobe Analytics-Authentifizierung über die Site-Suche/Merchandising eingerichtet haben. <p>Siehe <a href="../c-about-settings-menu/c-about-adobe-analytics-menu.md#task_8AA93F6273B747F9B4DE9E8DFBCBDC42" type="task" format="dita" scope="local"> Einrichten der Adobe Analytics-Metriken-Authentifizierung </a>. </p> </li> 
      <li id="li_CF7DD073FC5A432DADBD282AA8BB9920"> Wählen Sie eine verfügbare Report Suite aus und fügen Sie sie hinzu. <p>Siehe <a href="../c-about-settings-menu/c-about-adobe-analytics-menu.md#task_6DE17305EA7146DA8C30FF8FDF68A3C0" type="task" format="dita" scope="local"> Hinzufügen einer Adobe Analytics Report Suite </a>. </p> </li> 
      <li id="li_9A63448577D04E028DF211D8715F943A"> Konfigurieren Sie die Liste der Adobe Analytics-Metriken, die für die Erstellung neuer Ranking Rules verfügbar sein sollen. <p>Siehe <a href="../c-about-settings-menu/c-about-adobe-analytics-menu.md#task_360904CCBBB140238ADA036C3CC07664" type="task" format="dita" scope="local"> Bearbeiten der Adobe Analytics-Metriken einer Report Suite </a>. </p> </li> 
      <li id="li_1ACA3611D9B44AC394604CD89209C966"> Laden Sie die ersten Adobe Analytics-Metriken für Ihre Webseiten. <p>Siehe <a href="../c-about-settings-menu/c-about-adobe-analytics-menu.md#task_2F3C55189B0A4049AB2113F2291CC181" type="task" format="dita" scope="local"> Laden von Adobe Analytics-Daten </a>. </p> </li> 
      </ol> </p> </td> 
      </tr> 
    </tbody> 
    </table>

1. hinzufügen einer oder mehreren Ranking Rules.

   Siehe [Hinzufügen einer Rangregel](../c-about-rules-menu/c-about-ranking-rules.md#task_A132789FD4E5423DAD090DCDA7311E8A).

1. Klicken Sie auf **[!UICONTROL regenerate your staged site index]** , um einen vollständigen Reindex Ihrer Website auszuführen (von **[!UICONTROL Index]** > **[!UICONTROL Full Index]**).

   Siehe [Ausführen eines vollständigen Indexes einer Live- oder Staged-Website...](../c-about-index-menu/c-about-full-index.md#task_F7FE04D8A1654A7787FCCA31B45EB42D).

   Siehe [Konfigurieren eines inkrementellen Indexes einer gestaffelten Website](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0).
1. Überprüfen Sie die Werte in der Spalte &quot;Rang&quot;unter **[!UICONTROL Settings]** > **[!UICONTROL Metadata]** > **[!UICONTROL Definitions]** , ob Ihre Ranking Rules korrekt angewendet wurden.

## Informationen zum Ranking von Dokumenten nach Alter {#topic_770815CF1B2A491F83FF765871B6F1B8}

Sie können ein HTML-Dokument mit einer exponentiellen Abklingfunktion nach Alter sortieren. Die Zerfallsrate wird mit einer gewählten Halbwertskonstante angegeben, d. h. der Zeit, die vergehen muss, bevor der Wert auf die Hälfte des Ausgangswerts fällt.

Die Altersbewertung basiert auf den folgenden beiden Gleichungen:

`K = -ln(2) / H`

`RANK = e^(K * T)`

Variablen `H` und `T` sind Eingaben in diese Funktion: `H` ist die gewünschte Halbwertszeit und `T` das Alter des Dokuments, ausgedrückt in Sekunden. `K` ist die berechnete Halbwertszeit und `RANK` der exponentielle Abfall des angegebenen Alterswerts. Der resultierende Wert liegt zwischen 0 und 1. Ein neueres Dokument hat einen Rangwert, der näher an 1 liegt als ein älteres Dokument. Theoretisch sollten Dokumente nie den Wert 0 erreichen, aber Rundungsfehler können dazu führen, dass das Ergebnis 0 ist.

## Anforderungen an die Verwendung der Altersklasse {#section_D716507D589442C6B7848892BD28F966}

* Ihr Konto sollte für die Rangordnung bereits korrekt konfiguriert sein. Wenn sie nicht konfiguriert ist, finden Sie weitere Informationen unter [Konfigurieren der Rangfolge](../c-about-rules-menu/c-about-ranking-rules.md#task_4CEBC13925B047FC95BDC217B48089C5).
* Das HTML-Dokument muss über ein HTML-Meta-Tag-Feld verfügen, das das Geburtsdatum oder die Anfangsphase als Zeitstempel oder einen anderen aussagekräftigen Datumswert darstellt.
* Die integrierte Sonderfunktion, `search_get_age_rank()`wie auf den Seiten Hinzufügen oder Edit Ranking Rule angegeben, wird zur Berechnung des Altersgrads eines Dokuments verwendet. Die folgenden Abschnitte beschreiben ausführlich die allgemeine Verwendung der Funktion der Altersklasse. Es wird auch ein Beispiel vorgestellt, das die Funktion der Altersklasse veranschaulicht.

## Verwenden von search_get_age_rank () auf der Seite &quot;Hinzufügen Ranking Rule&quot;oder der Seite &quot;Edit Ranking Rule&quot; {#section_34BC5276F2AB4419AD92872A397CA0AF}

Geben Sie `search_get_age_rank()` Folgendes an:

`search_get_age_rank(Birthdate#Half_Life#Default_Rank)`

* Geburtsdatum - Das Geburtsdatum oder das Anfangsdatum der Datei muss eine Datumszeichenfolge sein, die den Datumsformaten des Felds entspricht. Diese datumsformatierte Zeichenfolge muss wie in dargestellt als Feldverweis dienen `{field_name}`.
* Half_Life - Die Halbwertszeit ist die Zeitdauer, die vergehen muss, bevor der Wert auf die Hälfte des Ausgangswerts fällt. Dieser Wert wird in der Anzahl der Tage angegeben und ist eine Ganzzahl oder eine Gleitkommazahl.
* Default_Rank - Der Standardrang wird als Sicherheitsnetz verwendet, wenn das Geburtsdatum ungültig ist oder das Datum in der Zukunft liegt. Sie können diesen Standardwert nicht verwenden, wenn das zugehörige Metadatenfeld auch einen gültigen Standardwert hat. Der Wert hier ist eine Gleitkommazahl oder eine Ganzzahl. Vorschläge finden Sie unten, wenn Probleme mit dem Standardwert auftreten.

Siehe [Hinzufügen einer Rangregel](../c-about-rules-menu/c-about-ranking-rules.md#task_A132789FD4E5423DAD090DCDA7311E8A).

See [Editing a ranking rule](../c-about-rules-menu/c-about-ranking-rules.md#task_5EBF55A43D6545FEA46BAE5E586FA275).

**Beispiel**

Im folgenden Beispiel wird

`search_get_age_rank({birthdate}#28#0.20)`

das im `birthdate` Feld des Dokuments enthaltene Datum wird als Zeitstempel übergeben. Die Halbwertszeit beträgt 28 Tage. Der Standardwert für die Rangfolge ist 0,20, wenn das Datum ungültig ist.

Siehe die Tabelle &quot;Optionen&quot;unter [Hinzufügen einer Rangregel](../c-about-rules-menu/c-about-ranking-rules.md#task_A132789FD4E5423DAD090DCDA7311E8A).

Im Bereich &quot;Werte/Ränge&quot;auf der Seite &quot;Hinzufügen Ranking Rule&quot;oder &quot;Edit Ranking Rule&quot;können Sie nur `search_get_age_rank` mit benutzerspezifischen Regeln arbeiten. Wählen Sie daher in der Dropdown-Liste &quot;Werte/Ränge&quot;die Option &quot; **Benutzerdefiniert** &quot;aus. Wenn die Regel die Funktion &quot;Altersklasse&quot;verwendet, sind im Werteteil der Regel keine Leerzeichen zulässig. Stellen Sie sicher, dass keine Leerzeichen in den Funktionsargumenten oder dazwischen vorhanden sind. Und es gibt keine Leerzeichen zwischen mathematischen oder bedingten Operatoren.

Im Folgenden finden Sie ein Beispiel für eine Regel für Werte/Ränge, eine Regel, die mit einem Textfeld verknüpft ist:

`regexp .* search_get_age_rank({other_field}#365#0.20)`

Dieses Beispiel geht davon aus, dass es einen Datumswert `other_field` enthält. Wenn dieses Feld selbst kein Datumsfeld ist, wird dieser Wert mithilfe der Datumsformate interpretiert, die mit dem vordefinierten Datumsfeld verknüpft sind. Andernfalls werden die Datumsformate dieses Felds verwendet. Dieser Eintrag für Werte/Ränge wird immer dann verwendet, wenn das Feld des Dokuments, das die Datenquelle der Regel identifiziert, nicht leer ist und der Rückgabewert der Funktion (von 0 bis 1) der zugewiesene Rang ist.

Für eine Regel, die einem numerischen Feld zugeordnet ist, insbesondere für ein Datumsfeld:

`9999999999 search_get_age_rank({other_field}#365#0.20)`

Bei der Verarbeitung jedes Dokuments `other_field` wird der Wert in unter Verwendung der Datumsformatdefinitionen in das Unix-&quot;Epoche&quot;-Formular konvertiert. Dieser Wert wird im `search_get_age_rank()` Aufruf verwendet. Da jeder &quot;Epochenwert&quot;kleiner als 99999999999 (zumindest derzeit) ist, liefert die Regel lediglich den Rückgabewert der Funktion (von 0 bis 1) als Rang.

In beiden obigen Beispielen ist es typisch, dass die Datenquelle der Regel dasselbe Feld ist, das in der `search_get_age_rank()` Funktion verwendet wird - in diesem Fall `other_field` .

## Ein Beispiel für die Integration der Altersklasse in Rangregeln {#section_A86D909687CC45E19D4EA7A4A9283F28}

Im Folgenden sehen Sie ein Beispiel dafür, wie Sie Altersstufen in Rangregeln integrieren können. Das Beispiel zeigt Ihnen auch die unformatierten Ergebnisse der Funktion &quot;Altersklasse&quot;und die Ergebnisse der Ranking-Regeln. Das Beispiel geht von Folgendem aus:

* Die durchgekrackten Webseiten haben das HTML-Meta-Tag &quot;Geburtstag&quot;. Der Inhalt dieses Tags ist ein Zeitstempel, der sich auf das Dokument bezieht.
* Die Metadatendefinitionen verfügen über ein definiertes Metatag für das Geburtstag-Tag. Dieses Feld ist auf den Typ &quot;date&quot;eingestellt.

**Rangregeln**

Siehe [Hinzufügen eines neuen Meta-Tag-Felds](../c-about-settings-menu/c-about-metadata-menu.md#task_6DF188C0FC7F4831A4444CA9AFA615E5).

Jetzt fügen Sie eine neue Rangregel hinzu. Die Regel ist für die Verwendung des Felds &quot;Geburtstag&quot;im Dokument definiert. Es wird eine neue Rangregel mit den folgenden Eigenschaften hinzugefügt:

* Datenquellentyp: Meta-Tag
* Name der Datenquelle: Geburtstag
* Gewichtungen/Bedingungen: 10 - Höchste Wichtigkeit
* Werte/Ränge: 9999999999 search_get_age_rank({Geburtstag}#14#0.10)
* Standardrang: -1

Die Regel macht mehrere Dinge. Die Gewichtung der Regel ist auf 10 eingestellt. Der Rangwert ist einfach das Ergebnis der Funktion &quot;Altersklasse&quot;, ein Wert von 0 bis 1. Sie können keine Leerzeichen mit verwenden `search_get_age_rank()`. Beachten Sie auch, dass das Feld &quot;Geburtsdatum&quot;in Klammern steht. Wenn Sie diese Regel speichern, werden die Kommas in der Definition &quot;Werte/Ränge&quot;durch `#` Zeichen ersetzt. dieses Verhalten normal ist.

**Ansicht der Ergebnisse**

Verwenden Sie die Funktion Data Ansicht, um schnell die Ergebnisse der Funktion &quot;Altersklasse&quot;zu sehen. hinzufügen Sie die entsprechenden Metadatenfelder. In diesem Beispiel `age_val` und `myrank` sind die beiden Metadatenfelder, die der Data-Ansicht hinzugefügt werden sollten. Das `myrank` Feld zeigt an, wie die Altersklasse die Rangwerte beeinflusst. Das `age_val` Feld zeigt die Rohausgabe der exponentiellen Zerfallsfunktion für dieses Dokument an.

## Standardwerte {#section_CB109EF78F914E92955D512ACFC3310E}

Die folgende Funktion umfasst drei Standardwerte `search_get_age_rank()`:

* Der Standardwert, den Sie in die `search_get_age_rank()` Funktion selbst eingeben können.
* Der Standardwert für den Rang aus der Rangregel.
* Der Standardwert aus der Metadatendefinition.

Je nachdem, wo der Fehler auftritt, erhalten Sie möglicherweise andere Standardwerte.

Der Standardwert aus der Metadatendefinition sollte beispielsweise nie vorkommen, wenn Ranking und Filtern korrekt implementiert sind. Dieser Standardwert ist der letzte Ausweichwert, wenn für dieses Metadatenfeld kein gültiger oder bekannter Inhalt vorhanden ist. Der Standardwert aus den Ranking Rules kann angezeigt werden, wenn `search_get_age_rank()` auf ein eigenes verknüpftes Tag verwiesen wird und das Tag im Dokument fehlt. In diesem Fall geht diese Regel direkt zum Standardwert der Regel. Wenn die Funktion für die Altersklasse auf das Tag einer anderen Rangregel verweist, kann der Standardwert, der an diese Funktion für die Altersklasse übergeben wird, verwendet werden, wenn das referenzierte Tag fehlt oder ungültig ist.

## Hinzufügen einer Rangregel {#task_A132789FD4E5423DAD090DCDA7311E8A}

Sie können hinzufügen, [!DNL Ranking Rules] um die relative Platzierung der Webseiten in Ihren Suchergebnissen basierend auf dem Inhalt der einzelnen Webseiten zu beeinflussen.

Siehe [Konfigurieren der Rangordnung](../c-about-rules-menu/c-about-ranking-rules.md#task_4CEBC13925B047FC95BDC217B48089C5).

**So fügen Sie eine Rangregel hinzu**

1. Klicken Sie im Produktmenü auf **[!UICONTROL Rules]** > **[!UICONTROL Ranking Rules]** > **[!UICONTROL Edit Rules]**.
1. (Optional) Wenn Sie eine Regelgruppe erstellt und der Gruppe Regeln hinzugefügt haben, wählen Sie auf der [!DNL Define Ranking Rules] Seite in der **[!UICONTROL Select Rule Group]** Dropdown-Liste eine Regelgruppe aus, die die zu bearbeitenden Regeln enthält.

   Siehe [Hinzufügen einer Rangregelgruppe](../c-about-rules-menu/c-about-ranking-rules.md#task_B65081B3CC9E4330A7FEE77B7BCD36C8).
1. Klicken Sie auf der [!DNL Define Ranking Rules] Seite auf , **[!UICONTROL Add Rule]** um eine neue Rangregel hinzuzufügen oder um einen Verweis zu einem Regelsatz hinzuzufügen.
1. Legen Sie auf der [!DNL Add Ranking Rule] Seite die gewünschten Optionen fest. Felder, die mit einem Sternchen (*) gekennzeichnet sind, müssen ausgefüllt werden.

   Der ausgewählte Datenquellentyp wirkt sich auf die Optionen aus, die in der [!DNL Data Source Name] Dropdown-Liste verfügbar sind. Wenn Sie beispielsweise **[!UICONTROL Meta Tag]** als Datenquellentyp ausgewählt haben, bezieht sich der Datenquellenname auf den Namen eines Meta-Tags auf Ihren Webseiten. Wenn Sie **[!UICONTROL Adobe Analytics Metric (Number)]** diese Option ausgewählt haben, bezieht sich der Datenquellenname auf einen der von Ihnen in einer Report Suite ausgewählten Adobe Analytics-Metriknamen, wie auf der Seite in Site-Suche/Merchandising **[!UICONTROL Edit Adobe Analytics Metrics]** gefunden.

   Siehe [Bearbeiten der Adobe Analytics-Metriken einer Report Suite](../c-about-settings-menu/c-about-adobe-analytics-menu.md#task_360904CCBBB140238ADA036C3CC07664).

   <table> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> <p>Option </p> </th> 
      <th colname="col2" class="entry"> <p>Beschreibung </p> </th> 
      </tr> 
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <p>Datenquelle-Typ </p> </td> 
      <td colname="col2"> <p>Bestimmt die Eigenschaften der Datenquelle, die als Eingabe für diese Rangregel verwendet wird. </p> <p>Zu den Datenquellentypen, aus denen Sie Folgendes auswählen können: 
      <ul id="ul_B0A97BF0E314495985F44A642C86918D"> 
      <li id="li_4D8BDE32853540809AE78FF5FF5677A1"> <span class="uicontrol"> Meta-Tag </span> <p> Basiert diese Regel auf numerischen Daten oder Textdaten, die in einem benannten Meta-Tag auf Ihren Webseiten gespeichert werden. </p> </li> 
      <li id="li_4976C31D67254C7F81D554EC49DDBB40"> <span class="uicontrol"> Adobe Analytics-Metrik (Zahl) </span> <p>Basiert diese Regel auf einer numerischen Adobe Analytics-Metrik, die mit Ihren Siteseiten verknüpft ist. </p> </li> 
      </ul> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Datenquellenname </p> </td> 
      <td colname="col2"> <p>Wenn Sie <span class="uicontrol"> Meta-Tag </span> als Datenquelle-Typ auswählen, ist dies der Name eines Meta-Tags, das auf den Seiten Ihrer Website gefunden wird. Die Namen im Dropdown-Menü stammen aus der Liste der definierten Metadatenwerte, die unter "Einstellungen"&gt; "Metadaten"&gt; "Definitionen"konfiguriert wurden. </p> <p>Siehe <a scope="local" href="../c-about-settings-menu/c-about-metadata-menu.md#task_6DF188C0FC7F4831A4444CA9AFA615E5" type="task" format="dita"> Hinzufügen eines neuen Meta-Tag-Felds </a>. </p> <p>Wenn Sie als Datenquellentyp "Adobe Analytics-Metrik (Zahl)"auswählen, ist dies der Name einer Adobe Analytics-Metrik. Die Namen im Dropdown-Menü stammen aus der Liste, die unter "Einstellungen"&gt; "Adobe Analytics"&gt; "Metriken"&gt; "Bearbeiten"konfigurierte verfügbare Adobe Analytics-Metriken definiert hat. </p> <p>Siehe <a href="../c-about-settings-menu/c-about-adobe-analytics-menu.md#task_360904CCBBB140238ADA036C3CC07664" type="task" format="dita" scope="local"> Bearbeiten der Adobe Analytics-Metriken einer Report Suite </a>. </p> <p>Wenn der von Ihnen ausgewählte Adobe Analytics-Metrikname noch nicht unter <span class="uicontrol"> Einstellungen </span> &gt; <span class="uicontrol"> Metadaten </span> &gt; <span class="uicontrol"> </span>Definitionen definiert ist, werden ein Textfeld und eine Schaltfläche Hinzufügen angezeigt. Geben Sie den Namen des Metadatenfeldnamens ein (der Metadatenfeldname darf nicht länger als 20 Zeichen sein) und klicken Sie dann auf <span class="uicontrol"> Hinzufügen </span>. </p> <p>Wenn Seiten mit mehreren Adobe Analytics-Schlüsseln gefunden werden, wie bei einer Produktseite mit mehreren Produkten, gibt Composite Scheme an, wie mit den mehreren mit dieser Seite verbundenen Adobe Analytics-Metrikwerten umzugehen ist. Wählen Sie eine der folgenden Optionen: </p> <p> 
      <ul id="ul_D6E51748BB3949048A37C1895F2C0A58"> 
      <li id="li_04F00F382A264C96A519B0D975E25E94"> <span class="uicontrol"> Summe </span> <p>Gibt die Summe der Metrikwerte zurück. </p> </li> 
      <li id="li_FA44219B663F4CC197BD3A094EB84396"> <span class="uicontrol"> Durchschnitt </span> <p>Gibt den Durchschnitt der Werte zurück (die Summe geteilt durch die Anzahl der Werte). </p> </li> 
      <li id="li_F0EAAE1EA1754FFEB30F611E5550097B"> <span class="uicontrol"> Maximum </span> <p>Gibt den größten Wert zurück. </p> </li> 
      <li id="li_38E3E3F3D9AF4C57803B84B60223FB9D"> <span class="uicontrol"> Erste/r </span> <p>Gibt den Wert zurück, der dem ersten Schlüssel entspricht. </p> </li> 
      <li id="li_4AEE470CE6BB4D899E975915EC226624"> <span class="uicontrol"> Letztes </span> <p>Gibt den Wert zurück, der dem letzten Schlüssel entspricht. </p> </li> 
      </ul> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Gewichtungen/Bedingungen </p> </td> 
      <td colname="col2"> <p>Enthält entweder eine einfache Gewichtung mit einer einzelnen Regel oder eine paarweise Liste von Regeln, Gewichtungen und Testbedingungen. </p> <p>Eine Regelnummer ist ein Gewichtung von 1 bis 10, der angibt, wie wichtig diese Rangregel im Verhältnis zu den anderen Rangregeln für die Bestimmung des Gesamtrangs eines Dokuments ist. Eine höhere Gewichtung von Regeln weist auf eine höhere Wichtigkeit hin. Bei einer Gewichtung von null (0) wird die Regel ignoriert. </p> <p>Wählen Sie <span class="uicontrol"> Benutzerspezifisch </span> aus der Dropdown-Liste, um die Gewichtung der Regel für verschiedene Seiten anzupassen, indem Sie eine Liste der Paare für Gewichtungen-/Testbedingungen definieren. Testbedingungen sind Fragmente von Perl, die zum Testen von Datenquellenwerten verwendet werden, oder globale Ansichten, die in Ihrem benutzerdefinierten Filterskript definiert sind (z. B. Preis, Marke, Jahreszeit oder Seitenvariablen, wie im folgenden Beispiel). Wenn eine Testbedingung den Wert "true"ergibt, wird der zugehörige Regelwert auf die Gewichtung angewendet. Wenn eine Testbedingung "false"ergibt, wird die nächste Bedingung in der Liste ausgewertet. <code> 0&nbsp;({price}&nbsp;&gt;&nbsp;50.00)&nbsp;&amp;&amp;&nbsp;({brand}=~/Kuhl/)5&nbsp;{season}&nbsp;=~&nbsp;/Fall/10&nbsp;{pageviews}&nbsp;&gt;&nbsp;1000005 </code>Im oben gezeigten Beispiel für eine benutzerspezifische Gewichtung/Bedingung wird die Gewichtung 0 der Regel angewendet, wenn die erste Testbedingung "true"ergibt. Das heißt, der Preis enthält einen Wert über 50 und die Marke enthält "Kuhl"). Wenn die erste Testbedingung "false"ergibt, wird die nächste Bedingung ausgewertet. Wenn keine der vorherigen Bedingungen erfüllt ist, wird die Regel Gewichtung 5 zugewiesen. </p> <p>Sie sollten am Ende der Liste immer eine Gewichtung ohne Bedingung bereitstellen. Wenn Sie dies nicht tun, erhält die Regel die Gewichtung 0, wenn keiner der Bedingungstests "true"ergibt. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Werte/Ränge </p> </td> 
      <td colname="col2"> <p>Besteht aus einer der integrierten Rangfunktionen oder möglichen Datenquellen-Inhalten zusammen mit den gewünschten Rängen. </p> <p>Wenn Sie als Datenquellentyp <span class="uicontrol"> Adobe Analytics-Metrik (Zahl) </span> auswählen, erhalten Sie eine Dropdown-Liste mit den folgenden Optionen: 
      <ul id="ul_104906B6AA8547BAB6979AA37C4FAB90"> 
      <li id="li_7656A2855A054DB8B64E90FE501517AA"> <span class="uicontrol"> Autom. Rangfolge nach Reihenfolge (Standard) </span> <p>Berechnet einen Rang, der auf der relativen Position des Dokuments gemäß seiner Adobe Analytics-Metrik basiert. Je näher das Dokument beispielsweise dem obersten Dokument steht, desto höher ist sein Rang. </p> </li> 
      <li id="li_1A7D60EA6965434AA6D39B215C158306"> <span class="uicontrol"> Automatisch nach Wert sortieren </span> <p>Berechnet einen Rang anhand des relativen Werts des Dokuments gemäß seiner Adobe Analytics-Metrik. Je näher beispielsweise der Wert des Dokuments dem Wert des Dokuments mit der höchsten Rangstufe liegt, desto höher ist sein Rang. </p> </li> 
      <li id="li_457DE44D6ADA40619DC77220BF12318E"> <span class="uicontrol"> Benutzerspezifisch </span> <p>Gibt benutzerdefinierte Einstellungen an. Eine Datenquelle mit dem Namen "Marke"könnte beispielsweise den Markennamen für ein bestimmtes Produkt enthalten. Sie können die relative Bedeutung jeder Marke angeben, indem Sie sie zusammen mit ihrem Rang aufführen. </p> </li> 
      </ul> </p> <p>Die Rangwerte, die von den Berechnungen für den automatischen Rang zurückgegeben werden, liegen im Bereich von 0,0 (am niedrigsten) bis 1,0 (am höchsten). Sie werden nicht entsprechend den Bereichen angepasst, die für das Feld Rang unter Einstellungen &gt; Metadaten &gt; Definitionen definiert sind. </p> <p>Wenn im folgenden Beispiel die Markendatenquelle für ein bestimmtes Suchergebnis exakt mit "DKNY"übereinstimmt, wird für dieses Ergebnis der Rang 0,5 angewendet. Wenn die Marke "Levis"ist, beträgt der angewendete Rang andernfalls 0,1. Der Datenquelleninhalt muss mit dem eingestellten Wert übereinstimmen. Anders ausgedrückt, wenn der Datenquelleninhalt "Levis Corp."lautet, stimmt er nicht mit dem Wert "Levis"überein. Die Groß-/Kleinschreibung wird ignoriert, sodass "DKNY"mit "dkny"und "dkny"übereinstimmt. <code> DKNY&nbsp;0.5 Levis&nbsp;0.1 Lee&nbsp;0.2 </code> </p> <p>Als erweiterte Option können Sie Werte als reguläre Ausdruck angeben. Angenommen, einige Ihrer Siteseiten enthalten den Markenwert "Levis"und andere Siteseiten den Markenwert "Levis jeans". Sie können einen regulären Ausdruck verwenden, der mit dem Suchbegriff angegeben wird <code>
        regexp 
      </code>. </p> <p>Siehe <a href="../c-appendices/r-regular-expressions.md#reference_B5BA7D61D82E4109A01D2A2D964E3A6A" type="reference" format="dita" scope="local"> Reguläre Ausdrücke </a>. </p> <p>Im folgenden Beispiel wird einem Suchergebnis-Dokument mit Markeninhalt "Levis jeans"der Rang 0.1 zugewiesen. Wie bei einem Standardvergleich wird die Groß-/Kleinschreibung bei regulären Ausdrücken ignoriert. <code> DKNY&nbsp;0.5 regexp&nbsp;Levis.*&nbsp;0.1 Lee&nbsp;0.2 </code> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Standardrang </p> </td> 
      <td colname="col2"> <p> Gibt den Rang an, der für Suchergebnis-Dokumente gelten soll, die keinem der angegebenen Werte entsprechen. Im obigen Beispiel wird einem Dokument mit Suchergebnissen mit einer "Marke"-Datenquelle, die "die Lücke"enthält, der Standardwert zugewiesen, da "die Lücke"keinem der definierten Werte entspricht. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Hinweise </p> </td> 
      <td colname="col2"> <p>hinzufügen Informationen, die sich auf die Definition der Rangregel oder die von Ihnen erstellte Regelgruppendefinition beziehen. </p> </td> 
      </tr> 
    </tbody> 
    </table>

   Der Bereich gültiger Rangwerte liegt normalerweise zwischen -1,0 und 1,0 wie im Folgenden dargestellt:

   * `-1.0` ist &quot;Mindestrang (wird in den Suchergebnissen unten angezeigt)&quot;.
   * `0.0` ist &quot;Neutraler Rang (die Reihenfolge der Suchergebnisse nicht ändern)&quot;.
   * `1.0` ist &quot;Maximaler Rang (wird in den Suchergebnissen höher angezeigt)&quot;.

   Definierte Ränge sollten für jede Regel innerhalb desselben Bereichs liegen. Die Rangbereiche müssen auch mit den Bereichen übereinstimmen, die für das Feld Rang unter **[!UICONTROL Settings]** > **[!UICONTROL Metadata]** > **[!UICONTROL Definitions]** definiert sind.

   Siehe [Hinzufügen eines neuen Meta-Tag-Felds](../c-about-settings-menu/c-about-metadata-menu.md#task_6DF188C0FC7F4831A4444CA9AFA615E5).

   Siehe auch [Bearbeiten einer Rangregel](../c-about-rules-menu/c-about-ranking-rules.md#task_5EBF55A43D6545FEA46BAE5E586FA275).
1. Klicken **[!UICONTROL Add]**.
1. Klicken Sie zur Vorschau der Ergebnisse des Regelzusatzes auf **[!UICONTROL regenerate your staged site index]** , um den Index der gestaffelten Website neu zu erstellen.

   Siehe [Ausführen eines vollständigen Indexes einer Live- oder Staged-Website...](../c-about-index-menu/c-about-full-index.md#task_F7FE04D8A1654A7787FCCA31B45EB42D).

   Siehe [Ausführen eines inkrementellen Indexes einer Live- oder Staged-Website...](../c-about-index-menu/c-about-incremental-index.md#task_9BFB6157F3884B2FAECB7E0E9CA318CB).
1. (Optional) Führen Sie einen der folgenden Schritte aus:

   * Klicken Sie auf **[!UICONTROL History]** , um alle vorgenommenen Änderungen wiederherzustellen.

      Siehe [Verwenden der Option](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)Verlauf.

   * Klicken **[!UICONTROL Live]**.

      Siehe [Live-Einstellungen](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)anzeigen.

   * Klicken **[!UICONTROL Push Live]**.

      Siehe [Pushing-Einstellungen](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Bearbeiten einer Rangregel {#task_5EBF55A43D6545FEA46BAE5E586FA275}

Sie können eine vorhandene Rangregel bearbeiten, die Sie bereits hinzugefügt haben.

Siehe [Konfigurieren der Rangordnung](../c-about-rules-menu/c-about-ranking-rules.md#task_4CEBC13925B047FC95BDC217B48089C5).

**So bearbeiten Sie eine Rangregel**

1. Klicken Sie im Produktmenü auf **[!UICONTROL Rules]** > **[!UICONTROL Ranking Rules]** > **[!UICONTROL Edit Rules]**.
1. (Optional) Wenn Sie eine Regelgruppe erstellt und der Gruppe Regeln hinzugefügt haben, wählen Sie auf der **[!UICONTROL Define Ranking Rules]** Seite in der **[!UICONTROL Select Rule Group]** Dropdown-Liste eine Regelgruppe aus, die die zu bearbeitenden Regeln enthält.

   Siehe [Hinzufügen einer Rangregelgruppe](../c-about-rules-menu/c-about-ranking-rules.md#task_B65081B3CC9E4330A7FEE77B7BCD36C8).
1. Klicken Sie in der Tabelle unter der **[!UICONTROL Actions]** Spaltenüberschrift auf **[!UICONTROL Edit]** den Namen der Datenquelle, den Sie ändern möchten.
1. Legen Sie auf der [!DNL Edit Ranking Rule] Seite die gewünschten Optionen fest. Felder, die mit einem Sternchen (*) gekennzeichnet sind, müssen ausgefüllt werden.

   Siehe Tabelle der Optionen unter [Hinzufügen einer Rangregel](../c-about-rules-menu/c-about-ranking-rules.md#task_A132789FD4E5423DAD090DCDA7311E8A).
1. Klicken **[!UICONTROL Save Changes]**.
1. Erstellen Sie den Index Ihrer gestaffelten Website neu, um die Ergebnisse der Regelbearbeitung Vorschau.

   Siehe [Ausführen eines vollständigen Indexes einer Live- oder Staged-Website...](../c-about-index-menu/c-about-full-index.md#task_F7FE04D8A1654A7787FCCA31B45EB42D).

   Siehe [Ausführen eines inkrementellen Indexes einer Live- oder Staged-Website...](../c-about-index-menu/c-about-incremental-index.md#task_9BFB6157F3884B2FAECB7E0E9CA318CB).
1. (Optional) Führen Sie einen der folgenden Schritte aus:

   * Klicken Sie auf **[!UICONTROL History]** , um alle vorgenommenen Änderungen wiederherzustellen.

      Siehe [Verwenden der Option](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)Verlauf.

   * Klicken **[!UICONTROL Live]**.

      Siehe [Live-Einstellungen](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)anzeigen.

   * Klicken **[!UICONTROL Push Live]**.

      Siehe [Pushing-Einstellungen](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Löschen einer Rangregel {#task_742A3BCC2A6E4164BE84CC7408807EBB}

Sie können Rangregeln löschen, die Sie nicht mehr verwenden müssen.

Siehe [Konfigurieren der Rangordnung](../c-about-rules-menu/c-about-ranking-rules.md#task_4CEBC13925B047FC95BDC217B48089C5).

Siehe [Hinzufügen einer Rangregelgruppe](../c-about-rules-menu/c-about-ranking-rules.md#task_B65081B3CC9E4330A7FEE77B7BCD36C8).

**So löschen Sie eine Rangregel**

1. Klicken Sie im Produktmenü auf **[!UICONTROL Rules]** > **[!UICONTROL Ranking Rules]** > **[!UICONTROL Edit Rules]**.
1. (Optional) Wenn Sie eine Regelgruppe erstellt und der Gruppe Regeln hinzugefügt haben, wählen Sie auf der [!DNL Define Ranking Rules] Seite in der **[!UICONTROL Select Rule Group]** Dropdown-Liste eine Regelgruppe aus, die die zu löschenden Regeln enthält.
1. Klicken Sie in der Tabelle unter der **[!UICONTROL Actions]** Spaltenüberschrift auf **[!UICONTROL Delete]** den Namen der Datenquelle, den Sie ändern möchten.
1. Klicken Sie auf der [!DNL Delete Ranking Rule] Seite auf **[!UICONTROL Delete]**.

   Sie werden zur [!DNL Define Ranking Rules] Seite zurückgeleitet.
1. Erstellen Sie den Index Ihrer gestaffelten Website neu, um die Ergebnisse des Löschens der Regel Vorschau.

   Siehe [Ausführen eines vollständigen Indexes einer Live- oder Staged-Website...](../c-about-index-menu/c-about-full-index.md#task_F7FE04D8A1654A7787FCCA31B45EB42D).

   Siehe [Ausführen eines inkrementellen Indexes einer Live- oder Staged-Website...](../c-about-index-menu/c-about-incremental-index.md#task_9BFB6157F3884B2FAECB7E0E9CA318CB).
1. (Optional) Führen Sie einen der folgenden Schritte aus:

   * Klicken Sie auf **[!UICONTROL History]** , um alle vorgenommenen Änderungen wiederherzustellen.

      Siehe [Verwenden der Option](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)Verlauf.

   * Klicken **[!UICONTROL Live]**.

      Siehe [Live-Einstellungen](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)anzeigen.

   * Klicken **[!UICONTROL Push Live]**.

      Siehe [Pushing-Einstellungen](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Hinzufügen einer Rangregelgruppe {#task_B65081B3CC9E4330A7FEE77B7BCD36C8}

Wenn Sie mehr als ein Meta-Tag des Typs &quot;Rang&quot;definiert haben, können Sie separate Regelsammlungen erstellen, die zur Berechnung der verschiedenen Rangfelder verwendet werden. Sie können eine Rangregelgruppe hinzufügen, die Sie dann einem Ihrer definierten Rangfelder zuweisen können.

Regelgruppen enthalten in der Regel eine oder mehrere Regeln, die Sie hinzugefügt haben. Regelgruppen können jedoch auch auf andere Regelgruppen verweisen. Sie können beispielsweise eine oder mehrere Regelgruppen erstellen und dann häufig verwendete Regeln zu jeder Regelgruppe hinzufügen. Diese Regeln werden dann bei der Berechnung Ihrer Mehrfachranken freigegeben.

Siehe [Bearbeiten einer Rangregelgruppe](../c-about-rules-menu/c-about-ranking-rules.md#task_D3EC0437E47144BC9E754FEF99C725E5).

Siehe [Löschen einer Rangregelgruppe](../c-about-rules-menu/c-about-ranking-rules.md#task_BE5BE01F377843BEA9846E094A07F2EA).

Siehe [Überprüfen der Rangregelgruppen](../c-about-rules-menu/c-about-ranking-rules.md#task_5694459D050C4254A25186038CD66B6E).

**So fügen Sie eine Rangregelgruppe hinzu**

1. Klicken Sie im Produktmenü auf **[!UICONTROL Rules]** > **[!UICONTROL Ranking Rules]** > **[!UICONTROL Edit Rules]**.
1. Klicken Sie auf der [!DNL Define Ranking Rules] Seite rechts neben der **[!UICONTROL Select Rule Group]** Dropdown-Liste auf **[!UICONTROL Add]**.
1. Geben Sie auf der [!DNL Add Ranking Rule Group] Seite im **[!UICONTROL Rule Group Name]** Feld einen eindeutigen Namen für die neue Regelgruppe ein.
1. Wählen Sie in der **[!UICONTROL Rank Field Name]** Dropdown-Liste einen Rangmetadatenfeldnamen aus, den Sie der neuen Regelgruppe zuordnen möchten. Wählen Sie diese Option, **[!UICONTROL None]** wenn Sie keinen Rang zuweisen möchten.

   Die Liste von Rangfeldnamen stammt aus Metadatendefinitionen, die unter **[!UICONTROL Settings]** > **[!UICONTROL Metadata]** > **[!UICONTROL Definitions]** hinzugefügt wurden.

   Siehe die Tabelle der Optionen unter [Hinzufügen eines neuen Meta-Tag-Felds](../c-about-settings-menu/c-about-metadata-menu.md#task_6DF188C0FC7F4831A4444CA9AFA615E5).
1. Klicken **[!UICONTROL Add]**.
1. Erstellen Sie den Index Ihrer gestaffelten Website neu, um die Ergebnisse des Regelzusatzes Vorschau.

   Siehe [Ausführen eines vollständigen Indexes einer Live- oder Staged-Website...](../c-about-index-menu/c-about-full-index.md#task_F7FE04D8A1654A7787FCCA31B45EB42D).

   Siehe [Ausführen eines inkrementellen Indexes einer Live- oder Staged-Website...](../c-about-index-menu/c-about-incremental-index.md#task_9BFB6157F3884B2FAECB7E0E9CA318CB).
1. (Optional) Führen Sie einen der folgenden Schritte aus:

   * Klicken Sie auf **[!UICONTROL History]** , um alle vorgenommenen Änderungen wiederherzustellen.

      Siehe [Verwenden der Option](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)Verlauf.

   * Klicken **[!UICONTROL Live]**.

      Siehe [Live-Einstellungen](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)anzeigen.

   * Klicken **[!UICONTROL Push Live]**.

      Siehe [Pushing-Einstellungen](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Bearbeiten einer Rangregelgruppe {#task_D3EC0437E47144BC9E754FEF99C725E5}

Sie können die Einstellungen einer vorhandenen Rangregelgruppe bearbeiten.

Siehe [Hinzufügen einer Rangregelgruppe](../c-about-rules-menu/c-about-ranking-rules.md#task_B65081B3CC9E4330A7FEE77B7BCD36C8).

**So bearbeiten Sie eine Rangregelgruppe**

1. Klicken Sie im Produktmenü auf **[!UICONTROL Rules]** > **[!UICONTROL Ranking Rules]** > **[!UICONTROL Edit Rules]**.
1. Klicken Sie auf der [!DNL Define Ranking Rules] Seite rechts neben der **[!UICONTROL Select Rule Group]** Dropdown-Liste auf **[!UICONTROL Edit]**.
1. Geben Sie auf der [!DNL Edit Ranking Rule Group] Seite im **[!UICONTROL Rule Group Name]** Feld einen eindeutigen Namen für die Regelgruppe ein.
1. Wählen Sie in der **[!UICONTROL Rank Field Name]** Dropdown-Liste einen Rangmetadatenfeldnamen aus, den Sie der Regelgruppe zuordnen möchten. Wählen Sie diese Option, **[!UICONTROL None]** wenn Sie keinen Rang zuweisen möchten.

   Die Liste von Rangfeldnamen stammt aus Metadatendefinitionen, die unter **[!UICONTROL Settings]** > **[!UICONTROL Metadata]** > **[!UICONTROL Definitions]** hinzugefügt wurden.

   Siehe die Tabelle der Optionen unter [Hinzufügen eines neuen Meta-Tag-Felds](../c-about-settings-menu/c-about-metadata-menu.md#task_6DF188C0FC7F4831A4444CA9AFA615E5).
1. Klicken **[!UICONTROL Save Changes]**.
1. Erstellen Sie den Index Ihrer gestaffelten Website neu, um die Ergebnisse des Regelzusatzes Vorschau.

   Siehe [Ausführen eines vollständigen Indexes einer Live- oder Staged-Website...](../c-about-index-menu/c-about-full-index.md#task_F7FE04D8A1654A7787FCCA31B45EB42D).

   Siehe [Ausführen eines inkrementellen Indexes einer Live- oder Staged-Website...](../c-about-index-menu/c-about-incremental-index.md#task_9BFB6157F3884B2FAECB7E0E9CA318CB).
1. (Optional) Führen Sie einen der folgenden Schritte aus:

   * Klicken Sie auf **[!UICONTROL History]** , um alle vorgenommenen Änderungen wiederherzustellen.

      Siehe [Verwenden der Option](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)Verlauf.

   * Klicken **[!UICONTROL Live]**.

      Siehe [Live-Einstellungen](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)anzeigen.

   * Klicken **[!UICONTROL Push Live]**.

      Siehe [Pushing-Einstellungen](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Löschen einer Rangregelgruppe {#task_BE5BE01F377843BEA9846E094A07F2EA}

Sie können eine Rangregelgruppe löschen, die Sie nicht mehr benötigen oder verwenden. Wenn Sie eine Gruppe löschen, werden alle Regeln, die der Gruppe hinzugefügt wurden, ebenfalls gelöscht. Die Standardgruppe &quot;Ranking Rules&quot;kann nicht gelöscht werden.

Der Inhalt von Regelgruppen, die in der Gruppe zum Löschen enthalten sind, wird nicht gelöscht. Nur die Verweise auf diese Gruppen werden entfernt.

Stellen Sie sicher, dass Sie Ihre Website neu indizieren, damit die Änderung korrekt in den Suchergebnissen angezeigt wird.

Siehe [Hinzufügen einer Rangregelgruppe](../c-about-rules-menu/c-about-ranking-rules.md#task_B65081B3CC9E4330A7FEE77B7BCD36C8).

**So löschen Sie eine Rangregelgruppe**

1. Klicken Sie im Produktmenü auf **[!UICONTROL Rules]** > **[!UICONTROL Ranking Rules]** > **[!UICONTROL Edit Rules]**.
1. Wählen Sie auf der [!DNL Define Ranking Rules] Seite in der **[!UICONTROL Select Rule Group]** Dropdown-Liste eine zu löschende Gruppe aus.
1. Klicken Sie rechts neben der **[!UICONTROL Select Rule Group]** Dropdown-Liste auf **[!UICONTROL Delete]**.
1. Klicken Sie auf der [!DNL Delete Ranking Rule Group] Seite auf **[!UICONTROL Delete]**.
1. Erstellen Sie den Index Ihrer gestaffelten Website neu, um die Ergebnisse des Regelzusatzes Vorschau.

   Siehe [Ausführen eines vollständigen Indexes einer Live- oder Staged-Website...](../c-about-index-menu/c-about-full-index.md#task_F7FE04D8A1654A7787FCCA31B45EB42D).

   Siehe [Ausführen eines inkrementellen Indexes einer Live- oder Staged-Website...](../c-about-index-menu/c-about-incremental-index.md#task_9BFB6157F3884B2FAECB7E0E9CA318CB).
1. (Optional) Führen Sie einen der folgenden Schritte aus:

   * Klicken Sie auf **[!UICONTROL History]** , um alle vorgenommenen Änderungen wiederherzustellen.

      Siehe [Verwenden der Option](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)Verlauf.

   * Klicken **[!UICONTROL Live]**.

      Siehe [Live-Einstellungen](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)anzeigen.

   * Klicken **[!UICONTROL Push Live]**.

      Siehe [Pushing-Einstellungen](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Überprüfen von Gruppen von Ranking-Regeln {#task_5694459D050C4254A25186038CD66B6E}

Sie können die Übersicht über die Rangregelgruppen verwenden, um die einzelnen Gruppen den Namen der Rangfelder sowie die zugehörige Datenquelle und Gewichtung anzuzeigen.

Siehe [Hinzufügen einer Rangregelgruppe](../c-about-rules-menu/c-about-ranking-rules.md#task_B65081B3CC9E4330A7FEE77B7BCD36C8).

**So überprüfen Sie Rangregelgruppen**

1. Klicken Sie im Produktmenü auf **[!UICONTROL Rules]** > **[!UICONTROL Ranking Rules]** > **[!UICONTROL Edit Rules]**.
1. Klicken Sie auf der [!DNL Define Ranking Rules] Seite rechts neben der **[!UICONTROL Select Rule Group]** Dropdown-Liste auf **[!UICONTROL Overview]**.
1. Klicken Sie auf der [!DNL Ranking Rule Groups Overview] Seite auf **[!UICONTROL Close]** , um zur [!DNL Define Ranking Rules] Seite zurückzukehren.
1. (Optional) Führen Sie einen der folgenden Schritte aus:

   * Klicken Sie auf **[!UICONTROL History]** , um alle vorgenommenen Änderungen wiederherzustellen.

      Siehe [Verwenden der Option](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)Verlauf.

   * Klicken **[!UICONTROL Live]**.

      Siehe [Live-Einstellungen](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)anzeigen.

   * Klicken **[!UICONTROL Push Live]**.

      Siehe [Pushing-Einstellungen](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Testen von Ranking Rules {#task_56F64EE7ED5B42E481F0990A9DD98ADB}

Sie können einen geeigneten URL-Test für die von Ihnen eingerichteten Rangregeldefinitionen bereitstellen. Die in den Berechnungen verwendeten Metriken werden zusammen mit dem berechneten Rangwert angezeigt.

Siehe [Info zu Ranking Rules](../c-about-rules-menu/c-about-ranking-rules.md#concept_F555C076759B4E81B925441CFE707397).

**So testen Sie Rangregeln**

1. Klicken Sie im Produktmenü auf **[!UICONTROL Rules]** > **[!UICONTROL Ranking Rules]** > **[!UICONTROL Edit Rules]**.
1. Geben Sie auf der [!DNL Define Ranking Rules] Seite im **[!UICONTROL Test URL]** Bereich die URL zu einer Webseite ein, die sich auf Ihrer Website befindet.
1. Klicken **[!UICONTROL Test]**.
1. (Optional) Führen Sie einen der folgenden Schritte aus:

   * Klicken Sie auf **[!UICONTROL History]** , um alle vorgenommenen Änderungen wiederherzustellen.

      Siehe [Verwenden der Option](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)Verlauf.

   * Klicken **[!UICONTROL Live]**.

      Siehe [Live-Einstellungen](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)anzeigen.

   * Klicken **[!UICONTROL Push Live]**.

      Siehe [Pushing-Einstellungen](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Anpassen der mit Ranking-Regeln verbundenen Gewichtung {#task_3CB6FC92A66F4D99874A42D55825DB64}

Sie können die relativen Beiträge Ihrer individuellen Ranking Rules und den Beitrag der Ranking zu den endgültigen Suchergebnissen ändern.

Wenn Ranking nicht definiert ist, befinden sich die Suchergebnisse auf der **[!UICONTROL Natural Relevance]** Seite des Reglers Regeln und Relevanz auf der **[!UICONTROL Adjust Ranking Weights]** Seite zu 100 %. Diese Ausgewogenheit bedeutet einfach, dass die Suchergebnisse ausschließlich auf Suchbegriffen basieren.

Wenn Ranking definiert ist, wird dem zugehörigen Rang-Metadatenfeld ein Relevanzwert zwischen 1 und 10 zugewiesen. Ein Wert von 1 bedeutet, dass der berechnete Rang 10 % der Suchergebnisreihenfolge ausmacht und die restlichen 90 % &quot;Kostenlose Relevanz&quot;.

Wenn Sie mehr als eine Regel in einer Regelgruppe definiert haben, bestimmt der Wert der Gewichtung jeder Regel, wie viel das Ergebnis dieser Regel zum berechneten Rang insgesamt beiträgt. Angenommen, Sie haben eine natürliche Relevanz von 80 %, d. h., die Relevanz des zugehörigen Rangfelds ist 2. Sie haben außerdem zwei Regeln definiert: eine mit einer Gewichtung von 3 und die zweite mit einer Gewichtung von 7. In diesem Fall beträgt der Beitrag der ersten Regel zum Endergebnis 6% ((3 / (3+7)) * 20%). Der Beitrag des zweiten Artikels zum Endergebnis beträgt 14% ((7 / (3+7)) * 20%).

**So passen Sie die mit den Ranking-Regeln verknüpfte Gewichtung an**

1. Klicken Sie im Produktmenü auf **[!UICONTROL Rules]** > **[!UICONTROL Ranking Rules]** > **[!UICONTROL Adjust Weights]**.
1. Wählen Sie auf der [!DNL Adjust Ranking Weights] Seite in der **[!UICONTROL Select Rule Group]** Dropdown-Liste eine Gewichtung aus, deren Rangfolge Sie anpassen möchten.
1. Ziehen Sie die Schieberegler, um die entsprechenden Beitragswerte zu ändern.

   Das Kreisdiagramm spiegelt Ihre Änderungen grafisch wider.
1. Klicken **[!UICONTROL Save Changes]**.
1. Erstellen Sie den Index Ihrer gestaffelten Website neu, um die Ergebnisse des Regelzusatzes Vorschau.

   Siehe [Ausführen eines vollständigen Indexes einer Live- oder Staged-Website...](../c-about-index-menu/c-about-full-index.md#task_F7FE04D8A1654A7787FCCA31B45EB42D).

   Siehe [Ausführen eines inkrementellen Indexes einer Live- oder Staged-Website...](../c-about-index-menu/c-about-incremental-index.md#task_9BFB6157F3884B2FAECB7E0E9CA318CB).
1. (Optional) Führen Sie einen der folgenden Schritte aus:

   * Klicken **[!UICONTROL Live]**.

      Siehe [Live-Einstellungen](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)anzeigen.

   * Klicken **[!UICONTROL Push Live]**.

      Siehe [Pushing-Einstellungen](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).
