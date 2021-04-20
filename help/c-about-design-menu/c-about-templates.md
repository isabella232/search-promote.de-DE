---
description: Sie können Vorlagen verwenden, um Ihre Präsentationsvorlagen und Transportvorlagen zu verwalten.
solution: Target
title: Vorlagen
topic: Design,Site search and merchandising
uuid: f5805d3e-43bf-4e13-95df-b6bd6b762d11
translation-type: tm+mt
source-git-commit: d015154efdccbb4c6a39a56907c0c337ec065c9f
workflow-type: tm+mt
source-wordcount: '2652'
ht-degree: 1%

---


# Grundlagen zu Vorlagen{#about-templates}

Sie können **[!UICONTROL Templates]** verwenden, um Ihre Präsentationsvorlagen und Transportvorlagen zu verwalten.

## Vorlagen {#concept_06EB481B14864E18A8AE2BCD1D6EF0B5}

<!-- 

c_about_templates.xml

 -->

Sie können Präsentationsvorlagen und Transportvorlagen hinzufügen, bearbeiten, kopieren, umbenennen oder löschen. Wenn Sie in der Tabelle &quot;Vorlagen&quot;auf einen vorhandenen Vorlagennamen klicken, wird dieser in einem Editor- oder Viewer-Fenster geöffnet, in dem Sie Ihre Änderungen vornehmen können.

Sie können Änderungen, die Sie an Vorlagen vornehmen, mithilfe der Verlaufsfunktion aus der Dropdown-Liste des Vorlagennamen in der Tabelle &quot;Vorlagen&quot;wiederherstellen.

Sie können die Gewichtung einer Präsentationsvorlage verringern, indem Sie das entsprechende Kontrollkästchen **[!UICONTROL Minimize]** der Vorlage in der Vorlagentabelle markieren. Durch die Reduzierung der Seitenlänge der Vorlage können Sie die Inline-JavaScript- und CSS-Gewichtung dynamisch minimieren. Sie entfernen auch redundante Leerzeichen im HTML-Code. Die Minimierung der Gewichtung der Seite in Ihrer Präsentationsvorlage kann dazu beitragen, die Suchergebnisse schneller zu liefern.

Sie können das Erscheinungsbild der minimierten Vorlage durch Klicken auf die Dropdown-Liste neben dem Dateinamen und dann auf **[!UICONTROL Preview minimized]** Vorschau. Wenn Sie die Vorlage der Hauptpräsentation minimieren, stellen Sie sicher, dass Sie die Minimierung für eingeschlossene Vorlagen (mit `guided-include`-Tag) aktivieren, da diese Option nicht vererbbar ist.

Auch wenn Sie eine Präsentationsvorlage minimieren, können Sie trotzdem die &quot;nicht minimierte&quot;Version derselben Vorlage bearbeiten.

Sie können die Regeln vor der Suche, die Regeln nach der Suche und die Geschäftsregeln verwenden, um zu bestimmen, wann eine Ihrer anderen Präsentationsvorlagen verwendet werden soll. Es ist üblich, dass eine Regel wie &quot;Für jede Suche, setzen Sie die zielgerichtete Vorlage auf xxxx&quot;. Wenn eine solche Regel angewendet wird und Sie die Vorlage &quot;Standard&quot;in der Tabelle &quot;Vorlagen&quot;ändern, scheint sie keine Auswirkungen zu haben.

Siehe [Info zu Vorsuchregeln](../c-about-rules-menu/c-about-pre-search-rules.md#concept_5BF84BB6FACB4645BA9CB7496A01CD1F).

Siehe [Über Regeln nach der Suche](../c-about-rules-menu/c-about-post-search-rules.md#concept_AF6ADFCC0ADF4A788003964939917FDE).

Siehe [Geschäftsregeln](../c-about-rules-menu/c-about-business-rules.md#concept_2A93D76216754D3D8412CDEA00BD26BD).

## Informationen zu Präsentationsvorlagen {#section_ACDDEA5C499E481C828A517C230D4596}

Präsentationsvorlagen sind HTML-Vorlagen, die Kunden sehen, wenn sie die Ergebnisse ihrer Suche auf Ihrer Website anzeigen.

In Ihrer Präsentationsebene können Sie über eine einzelne Präsentationsvorlage verfügen, die die Ergebnisse mehrerer Suchen aus verschiedenen Quellen darstellt. Sie können beliebig viele Präsentationsvorlagen definieren und sogar Präsentationsvorlagen definieren, die andere Vorlagen mit `include`-Befehlen gemeinsam verwenden. In der Präsentationsvorlage werden alle Designkomponenten wie Facetten, Menüs und Breadcrumbs zusammengeführt. Um die verschiedenen Designkomponenten anzuzeigen, müssen Sie die Tags der Präsentationsvorlage verwenden.

Siehe [Tags der Präsentationsvorlage](../c-appendices/c-templates.md#reference_F1BBF616BCEC4AD7B2548ECD3CA74C64)

Wenn Sie über mehr als eine Präsentationsvorlage verfügen, legen Sie fest, unter welchen Bedingungen die verschiedenen Präsentationsvorlagen verwendet werden. Sie können festlegen, welche Präsentationsvorlage basierend auf den eingehenden CGI-Parametern und Cookies verwendet werden soll. Oder Sie können je nach Ergebnis einer vorherigen Suche die von Ihnen verwendete Präsentationsvorlage ändern.

Wenn Sie mehrere Präsentationsvorlagen verwenden, stellen Sie sicher, dass Sie die Vorlage angeben, in der die Suchergebnisse zuerst angezeigt werden sollen. Dazu verwenden Sie die Spalte **[!UICONTROL Default]** der Tabelle &quot;Vorlagen&quot;.

## Grundlagen zu Transportvorlagen {#section_35FD3E8AAA4E4695A737DB7E00C3258B}

Transportvorlagen können entweder XML- oder JSON-Vorlagen sein, die Daten aus der Backend-Suche an die Präsentationsebene der geführten Suche weiterleiten.

Standardmäßig ist Ihr Konto für die Verwendung von XML-Transportvorlagen konfiguriert. Wenn Sie Ihre Daten jedoch lieber mit JSON an die geführte Suche weiterleiten möchten, wenden Sie sich an Adobe Consulting, der Sie unterstützen kann.

In Ihrer Präsentationsebene können Sie über eine einzelne Präsentationsvorlage verfügen, die die Ergebnisse mehrerer Suchen darstellt. Jede Suche kann dieselbe Transportvorlage oder eine benutzerdefinierte Transportvorlage verwenden, um die Daten an die Präsentationsebene zu übergeben. Da die Transportvorlage nur zum Übermitteln von Daten an die Präsentationsebene verwendet wird, darf sie keinen HTML-Code enthalten, mit dem die Suchergebnisse angezeigt werden. Die Vorlage verwendet Transportvorlage-Tags, um die Ergebnisse der Suche und die Ergebnisse zum Füllen der Facetten zu übermitteln. Innerhalb dieser Tags werden die tatsächlichen Werte mit den Standard-Tags der Suchvorlage angezeigt.

Siehe [Suchvorlagen-Tags](../c-appendices/c-templates.md#reference_F7AA3FF602314E42842BBC740D2CA1A4).

**XML-Transport-Vorlagen-spezifische Tags**

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>XML-Transportvorlage-Tag </p> </th> 
   <th colname="col2" class="entry"> <p>Beschreibung </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-xml&gt;&lt;/guided-xml&gt; </span> </p> </td> 
   <td colname="col2"> <p>Dies sind die XML-Stamm-Tags, die die Präsentationsebene verwendet, um zu erkennen, was aus der Transportvorlage analysiert werden muss. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;general&gt;&lt;/general&gt; </span> </p> </td> 
   <td colname="col2"> <p>Dieser Tag-Satz umschließt Suchvorlagen-Tags, die Zusammenfassungsdaten basierend auf der Ergebnismenge bereitstellen. Normalerweise enthalten diese Tags Suchtags für die Gesamtanzahl der Ergebnisse, das niedrigste Ergebnis und das höchste Ergebnis. Sie können eine beliebige Anzahl zusätzlicher globaler Felder definieren, die Sie mit dem Tag <span class="codeph"> general-field </span> verwenden möchten. </p> <p> <b>Beispiel</b> </p> <p> <code> &nbsp;&nbsp;&nbsp;&nbsp;&lt;general&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;total&gt;&lt;search-total&nbsp;/&gt;&lt;/total&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;lower&gt;&lt;search-lower&nbsp;/&gt;&lt;/lower&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;upper&gt;&lt;search-upper&nbsp;/&gt;&lt;/upper&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;general-field&nbsp;name="my_custom_field"&gt;Some&nbsp;global&nbsp;content&lt;/general-field&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&lt;/general&gt; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;results&gt;&lt;/results&gt; </span> </p> </td> 
   <td colname="col2"> <p>Dieser Satz von Tags wird um die Suchergebnisse herum umschlossen, sodass die geführte Suche weiß, wo sie gesucht werden soll. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;result&gt;&lt;/result&gt; </span> </p> </td> 
   <td colname="col2"> <p>Dieser Satz von Tags wird um jedes Suchergebnis herum umschlossen, sodass die geführte Suche erkennt, wo der Inhalt für ein einzelnes Suchergebnis Beginn und endet. </p> <p> <b>Beispiel</b> </p> <p> <code> &nbsp;&nbsp;&nbsp;&nbsp;&lt;results&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;search-results&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;result&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;index&gt;&lt;search-index&nbsp;/&gt;&lt;/index&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;loc&gt;&lt;search-cdata&gt;&lt;search-url&nbsp;length="500"&nbsp;/&gt;&lt;/search-cdata&gt;&lt;/loc&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/result&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/search-results&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&lt;/results&gt; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;attribute-table name="tablename"&gt; </span> </p> </td> 
   <td colname="col2"> <p>Mit diesem Tag können Sie jedes Element in einer Liste mit mehreren Werten für ein einzelnes Ergebnis durchlaufen. Verwenden Sie das Tag nur in einem Ergebnis. Sein Hauptzweck besteht darin, dass Sie Attribute durchlaufen können, die zu einem Ergebnisfeld gehören. </p> <p> <b>Beispiel</b> </p> <p> <code> &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;results&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;search-results&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;result&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;index&gt;&lt;search-index&nbsp;/&gt;&lt;/index&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;loc&gt;&lt;search-url&nbsp;/&gt;&lt;/loc&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;title&gt;&lt;search-title&nbsp;/&gt;&lt;/title&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;attribute-table&nbsp;name="downloads"&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;field&nbsp;name="download_title"&gt;&lt;search-display-field&nbsp;name="download_title"&nbsp;/&gt;&lt;/field&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;field&nbsp;name="download_link"&nbsp;delimiter="|"&gt;&lt;search-display-field&nbsp;name="download_link"&nbsp;/&gt;&lt;/field&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/attribute-table&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/result&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/search-results&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/results&gt; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;facets&gt;&lt;/facets&gt; </span> </p> </td> 
   <td colname="col2"> <p>Dieser Tag-Satz übergibt die Ergebnisse, die die Facetten füllen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;facet name="name"&gt;&lt;/facet&gt; </span> </p> </td> 
   <td colname="col2"> <p>Jede Facette muss über eigene Facetten-Tags verfügen, bei denen der Parameter name mit dem Facettennamen übereinstimmt. Suchtags werden innerhalb der facet-Tags für die Facettenwerte verwendet. </p> <p>Siehe <a href="../c-about-design-menu/c-about-facets.md#concept_FA912B3B41EE493DB2F492D188457FF5" type="concept" format="dita" scope="local"> Facets </a>. </p> <p> <b>Beispiel</b> </p> <p> <code> &nbsp;&nbsp;&nbsp;&nbsp;&lt;facets&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;facet&nbsp;name="brand"&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;values&gt;&lt;search-field-value-list&nbsp;name="brand"&nbsp;quotes="no"&nbsp;commas="yes"&nbsp;data="values"&nbsp;sortby="values"&nbsp;/&gt;&lt;/values&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;counts&gt;&lt;search-field-value-list&nbsp;name="brand"&nbsp;quotes="no"&nbsp;commas="yes"&nbsp;data="counts"&nbsp;sortby="values"&nbsp;/&gt;&lt;/counts&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/facet&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;facet&nbsp;name="category"&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;values&gt;&lt;search-field-value-list&nbsp;name="category"&nbsp;quotes="no"&nbsp;commas="yes"&nbsp;data="values"&nbsp;sortby="values"&nbsp;/&gt;&lt;/values&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;counts&gt;&lt;search-field-value-list&nbsp;name="category"&nbsp;quotes="no"&nbsp;commas="yes"&nbsp;data="counts"&nbsp;sortby="values"&nbsp;/&gt;&lt;/counts&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/facet&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&lt;/facets&gt; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;suggestions&gt;&lt;/suggestions&gt; </span> </p> </td> 
   <td colname="col2"> <p>Diese Gruppe von Tags umschließt Ihre "Meinten Sie"-Vorschläge, sodass die geführte Suche erkennt, welche XML-Knoten Vorschläge enthalten. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;suggestion&gt;&lt;/suggestion&gt; </span> </p> </td> 
   <td colname="col2"> <p>Diese Gruppe von Tags umschließt jede "Meinten Sie"-Empfehlung. </p> <p> <b>Beispiel</b> </p> <p> <code> &nbsp;&nbsp;&nbsp;&nbsp;&lt;search-if-suggestions&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;suggestions&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;search-suggestions&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;suggestion&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;value&gt;&lt;search-suggestion-text&nbsp;/&gt;&lt;/value&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;count&gt;&lt;search-suggestion-result-count&nbsp;/&gt;&lt;/count&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/suggestion&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/search-suggestions&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/suggestions&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&lt;/search-if-suggestions&gt; </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

**JSON-Tags für Transportvorlagen**

Die Weitergabe von JSON im Vergleich zu XML von der Suchmaschine ist bekanntermaßen schneller, da es sich um eine geringere Nutzlast und einen schnelleren Parser handelt. Seien Sie jedoch vorsichtig, wenn Sie JSON verwenden, um sicherzustellen, dass die Ausgabe striktes JSON ist, da der Parser nicht vergeben wird.

Wenn Sie neu bei JSON sind, können Sie mithilfe der folgenden Links und Beispiele die ersten Schritte durchführen:

* Eine Einführung in JSON. Siehe [https://www.json.org/](https://www.json.org/).
* Testen Sie JSON, um sicherzustellen, dass es gültig ist. Siehe [https://jsonlint.com/](https://jsonlint.com/).

**Beispiel für eine JSON-Vorlage**

```
{ 
 "general": 
 { 
  "total" : "<search-total />", 
  "lower" : "<search-lower />", 
  "upper" : "<search-upper />", 
  "rbt-trigger-list" : "<search-rbta-trigger-id-list>", 
  "fields" :  
  [ 
   { 
    "name" : "seo_search_title", 
    "value" : "<search-include file="seo/seo_search_title.tpl" />" 
   }, 
   { 
    "name" : "seo_search_keywords", 
    "value" : "<search-include file="seo/seo_search_keywords.tpl" />" 
   } 
  ] 
 }, 
 
 <search-if-suggestions> 
 "suggestions": 
  [ 
  <search-suggestions> 
  { 
   "suggestion":"<search-suggestion-text />", 
   "count": "<search-suggestion-result-count>" 
  }<search-if-not-last-suggestion>,</search-if-not-last-suggestion> 
  </search-suggestions> 
 ], 
 </search-if-suggestions> 
 
 "facets" : 
 [ 
  { 
   "name" : "leveli", 
   "values" : [ <search-field-value-list name="leveli" quotes="yes" sortby="values" data="values" encoding="json"/>], 
   "counts" : [<search-field-value-list name="leveli" quotes="no" sortby="values" data="results" />] 
  }, 
  { 
   "name" :"levelii", 
   "values" : [<search-field-value-list name="levelii" quotes="yes" sortby="values" data="values" encoding="json"/>], 
   "counts" : [<search-field-value-list name="levelii" quotes="no" sortby="values" data="results" />] 
  }, 
  { 
   "name" : "brand", 
   "values" : [<search-field-value-list name="brand" quotes="yes" sortby="values" data="values" encoding="json"/>], 
   "counts" : [<search-field-value-list name="brand" quotes="no" sortby="values" data="results" />] 
  }, 
 ], 
 "results" : 
 [ 
  <search-results> 
  { 
   "fields" : 
   [ 
    { 
     "name" : "index", 
     "value" : "<search-index />" 
    }, 
    { 
     "name" : "loc", 
     "value" : "<search-display-field name="url" length="500" encoding="json"/>" 
    }, 
    { 
     "name" : "title", 
     "value" : "<search-display-field name="title" encoding="json"/>" 
    }, 
    { 
     "name" : "img_url_thumbnail", 
     "value" : "<search-display-field name="img_url_thumbnail" encoding="json"/>" 
    }, 
    { 
     "name" : "description", 
     "value" : "<search-display-field name="description" encoding="json"/>" 
    }, 
    { 
     "name" : "mdi", 
     "value" : "<SEARCH-RBTA-DISPLAY-MDI-FIELD>" 
    } 
   ] 
  }<search-if-not-last>,</search-if-not-last>  
  </search-results> 
 ] 
}
```

**Beispiel für einen JSON-Ergebnisabschnitt mit einer Ergebnisattributtabelle**

```
{ 
 "results" : 
 [ 
  <search-results> 
  { 
   "fields" : 
   [ 
    { 
     "name" : "index", 
     "value" : "<search-index />" 
    }, 
    { 
     "name" : "loc", 
     "value" : "<search-display-field name="url" length="500" encoding="json"/>" 
    } 
   ], 
   "tables" : 
   [ 
    { 
     "name" : "downloads", 
     "fields" : 
     [ 
      { 
       "name" : "download_title", 
       "value" : <search-display-field name="download_title" encoding="json"/> 
      }, 
      { 
       "name" : "download_link", 
       "value" : <search-display-field name="download_link" encoding="json"/> 
      } 
     ] 
    } 
   ] 
  }<search-if-not-last>,</search-if-not-last>  
  </search-results> 
 ] 
}
```

**Beispiel für einen JSON Facet-Abschnitt für eine Facette mit zugehörigen Feldern**

```
{ 
 facets" : 
 [ 
  { 
   "name" : "t1", 
   "values" : [<search-field-value-list name="t1" quotes="yes" commas="yes" data="values" sortby="values" encoding="json" />], 
   "counts" : [<search-field-value-list name="t1" quotes="yes" commas="yes" data="results" sortby="values" />], 
   "custom-fields" : 
   [ 
    { 
     "name" : "taxonmyId", 
     "value" : [<search-field-value-list name="tax1" quotes="yes" commas="yes" data="values" sortby="values" encoding="json" />] 
    } 
   ] 
  } 
 ] 
}
```

**Beispiel für einen JSON-Facet-Abschnitt für formatierte Facetten**

```
{ 
  "facets" : 
  [  
   { 
    "name" : "fvalue0", 
                  "dynamic" : 1, 
                  "display-names" : [<search-field-value-list name="fname0" quotes="yes" commas="yes" data="values" sortby="values" encoding="json" />], 
    "values" : [<search-field-value-list name="fvalue0" quotes="yes" commas="yes" data="values" sortby="values" encoding="json" />], 
    "counts" : [<search-field-value-list name="fvalue0" quotes="no" commas="yes" data="results" sortby="values" />] 
   } 
  ] 
} 
```

## Hinzufügen einer neuen Präsentations- oder Transportvorlagendatei {#task_73199757B6E748CAA604902FF913F012}

Sie können **[!UICONTROL Add Template]** verwenden, um der [!DNL Templates]-Seite Präsentationsvorlagen (.tmpl) oder Transportvorlagen (.tpl) hinzuzufügen.

<!-- 

t_adding_a_new_presentation_or_transport_template_file.xml

 -->

**So fügen Sie eine neue Präsentations- oder Transportvorlagendatei hinzu**

1. Klicken Sie im Produktmenü auf **[!UICONTROL Design]** > **[!UICONTROL Templates]**.
1. Klicken Sie auf der Seite [!DNL Templates] auf **[!UICONTROL Add New Template]**.
1. Legen Sie im Dialogfeld [!DNL Add Template] die gewünschten Optionen fest.

   <!-- 
   
   r_add_template_options.xml
   
   -->

   | Option | Beschreibung |
   |--- |--- |
   | Neuer Dateiname | Gibt den Namen der Vorlage an, die Sie hinzufügen möchten. Die richtige Dateierweiterung wird dem Dateinamen automatisch entsprechend dem ausgewählten Vorlagentyp hinzugefügt.  Präsentationsvorlagen haben die Dateierweiterung &quot;.tmpl&quot;. Transportvorlagen haben die Dateierweiterung .tpl. |
   | Neuer Vorlagentyp | Hier können Sie eine Präsentation oder eine Transportvorlage auswählen, die Sie hinzufügen möchten.  Siehe [Vorlagen](../c-about-design-menu/c-about-templates.md). |

   Siehe auch [Bearbeiten einer Präsentation oder einer Transportvorlage](../c-about-design-menu/c-about-templates.md#task_800E0E2265C34C028C92FEB5A1243EC3).
1. Klicken **[!UICONTROL Add]**.
1. (Optional) Führen Sie auf der Seite [!DNL Templates] einen der folgenden Schritte aus:

   * Klicken Sie auf **[!UICONTROL History]**, um alle vorgenommenen Änderungen wiederherzustellen.

      Siehe [Verwenden der Option Verlauf](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Klicken **[!UICONTROL Live]**.

      Siehe [Live-Einstellungen anzeigen](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Klicken **[!UICONTROL Push Live]**.

      Siehe [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Bearbeiten einer Präsentation oder einer Transportvorlage {#task_800E0E2265C34C028C92FEB5A1243EC3}

Sie können den Vorlageneditor verwenden, um den Inhalt Ihrer Präsentations- und Transportvorlagendateien Ansicht und zu bearbeiten.

<!-- 

t_editing_a_template.xml

 -->

Sie können Ihre Vorlagen für gestaffelte Präsentationen und Transporte bearbeiten und testen, während Ihre Website-Besucher weiterhin die Live-Version Ihrer Vorlagen verwenden. Sie testen Ihre gestaffelte Vorlage mit der gestaffelten Version der URL Ihrer Suchdomäne. Sie können beispielsweise Ihre gestaffelte Transportvorlage testen, indem Sie eine gestaffelte Abfrage ( `sp_staged=1`) mit `sp_t` ausführen, die auf den Namen Ihrer Transportvorlage eingestellt ist. Wenn Sie mit dem Erscheinungsbild des Layouts zufrieden sind, können Sie **[!UICONTROL Push Live]** aus dem Vorlageneditor verwenden, um die Vorlage zu aktivieren. Nachdem die Vorlage live geschaltet wurde, beginnen die Site-Besucher damit, sie zu verwenden.

Verwenden Sie den Tag-Verweis auf die Präsentationsvorlage, um zu erfahren, wie Sie Ihre Präsentationsvorlage mit Komponenten der geführten Suche wie Facets, Breadcrumbs und Menüs verknüpfen können.

Siehe [Tags der Präsentationsvorlage](../c-appendices/c-templates.md#reference_F1BBF616BCEC4AD7B2548ECD3CA74C64)

Verwenden Sie den Tag-Verweis auf die Transportvorlage, um mehr über die Tags zu erfahren, die in Transportvorlagen verwendet werden sollen.

Siehe [Tags der Transportvorlage](../c-appendices/c-templates.md#reference_227D199F5A7248049BE1D405C0584751)

**[!UICONTROL To edit a presentation or a transport template]**

1. Klicken Sie im Produktmenü auf **[!UICONTROL Design]** > **[!UICONTROL Templates]**.
1. Klicken Sie auf der Seite [!DNL Templates] auf eine Präsentation oder einen Transportvorlagennamen.
1. Nehmen Sie auf der Seite [!DNL Template Editor] die gewünschten Änderungen an den Tags und Kodierungen vor.

   Achten Sie auf die Änderungen, die Sie in [!DNL Template Editor] vornehmen. Es gibt keine Rückgängig-Funktion. Wenn Sie eine unerwünschte Änderung vornehmen und zur vorherigen Version der Datei zurückkehren möchten, können Sie auf **[!UICONTROL Cancel]** klicken, um zur Tabelle der Vorlagen zurückzukehren (vorausgesetzt, Sie haben bis zu diesem Zeitpunkt keine Änderungen gespeichert). Wenn Sie Ihre Änderungen bereits gespeichert haben, können Sie **[!UICONTROL History]** im Editor verwenden, um diese Änderungen wiederherzustellen.
1. (Optional) Klicken Sie auf **[!UICONTROL Insert Symbol]**, um Sonderzeichen und Symbole einzugeben, die keine entsprechenden Schlüssel auf US-amerikanischen Tastaturen enthalten.
1. Klicken **[!UICONTROL Save Changes]**.
1. (Optional) Führen Sie einen der folgenden Schritte aus:

   * Klicken Sie auf **[!UICONTROL History]**, um alle vorgenommenen Änderungen wiederherzustellen.

      Siehe [Verwenden der Option Verlauf](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Klicken **[!UICONTROL Live]**.

      Siehe [Live-Einstellungen anzeigen](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Klicken **[!UICONTROL Push Live]**.

      Siehe [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

1. Schließen Sie die Seite &quot;Vorlagen-Editor&quot;, wenn Sie fertig sind. zurück zur Seite &quot;Vorlagen&quot;.

## Kopieren einer Präsentation oder einer Transportvorlagendatei {#task_B744AB3384C84DD59C33CD25E18C2C90}

Sie können **[!UICONTROL Copy Template]** verwenden, um Zeit zu sparen, indem Sie eine vorhandene Präsentationsvorlage (.tmpl) oder eine Transportvorlage (.tpl) duplizieren und sie der Seite &quot;Vorlagen&quot;hinzufügen.

<!-- 

t_copying_a_presentation_or_a_transport_template.xml

 -->

Sie müssen den Vorlagennamen, den Vorlagentyp oder beides ändern. Wenn Sie keine Änderungen vornehmen, wird die Vorlage nicht kopiert.

Sie benötigen bereits eine Vorlage, um eine Vorlage kopieren zu können.

Siehe [Hinzufügen einer neuen Präsentations- oder Transportvorlagendatei](../c-about-design-menu/c-about-templates.md#task_73199757B6E748CAA604902FF913F012).

**So kopieren Sie eine Präsentation oder eine Transportvorlagendatei**

1. Klicken Sie im Produktmenü auf **[!UICONTROL Design]** > **[!UICONTROL Templates]**.
1. Klicken Sie auf der Seite [!DNL Templates] in der Dropdown-Liste neben dem Vorlagennamen, den Sie kopieren möchten, auf **[!UICONTROL Copy]**.
1. Legen Sie im Dialogfeld [!DNL Copy Template] eine oder mehrere der gewünschten Optionen fest.
1. Klicken **[!UICONTROL Copy]**.
1. (Optional) Führen Sie einen der folgenden Schritte aus:

   * Klicken Sie auf **[!UICONTROL History]**, um alle vorgenommenen Änderungen wiederherzustellen.

      Siehe [Verwenden der Option Verlauf](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Klicken **[!UICONTROL Live]**.

      Siehe [Live-Einstellungen anzeigen](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Klicken **[!UICONTROL Push Live]**.

      Siehe [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Umbenennen einer Präsentation oder einer Transportvorlagendatei {#task_CC30050FC2DE4898BF44379D8378EB31}

Sie können [!DNL Rename Template] verwenden, um den Namen einer vorhandenen Präsentationsvorlage (.tmpl) oder einer Transportvorlage (.tpl) zu ändern.

<!-- 

t_renaming_a_presentation_or_a_transport_template_file.xml

 -->

Sie können bei Bedarf auch den Vorlagentyp ändern.

Zum Umbenennen einer Vorlage muss bereits eine Vorlage hinzugefügt worden sein.

Siehe [Hinzufügen einer neuen Präsentations- oder Transportvorlagendatei](../c-about-design-menu/c-about-templates.md#task_73199757B6E748CAA604902FF913F012).

**So benennen Sie eine Präsentation oder eine Transportvorlagendatei um**

1. Klicken Sie im Produktmenü auf **[!UICONTROL Design]** > **[!UICONTROL Templates]**.
1. Klicken Sie auf der Seite [!DNL Templates] in der Dropdown-Liste neben dem Vorlagennamen, den Sie umbenennen möchten, auf **[!UICONTROL Rename]**.
1. Legen Sie im Dialogfeld [!DNL Rename Template] eine oder mehrere der gewünschten Optionen fest.
1. Klicken **[!UICONTROL Rename]**.
1. (Optional) Führen Sie einen der folgenden Schritte aus:

   * Klicken Sie auf **[!UICONTROL History]**, um alle vorgenommenen Änderungen wiederherzustellen.

      Siehe [Verwenden der Option Verlauf](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Klicken **[!UICONTROL Live]**.

      Siehe [Live-Einstellungen anzeigen](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Klicken **[!UICONTROL Push Live]**.

      Siehe [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Löschen einer Präsentation oder einer Transportvorlagendatei {#task_67E532C2B83A449687737E3B06C5AA58}

Sie können **[!UICONTROL Delete Template]** verwenden, um eine vorhandene Präsentationsvorlage (.tmpl) oder eine Transportvorlage (.tpl) zu entfernen.

<!-- 

t_deleting_a_presentation_or_a_transport_template_file.xml

 -->

Möglicherweise haben Sie bereits eine entsprechende Version der gestaffelten Vorlage, die live geschaltet wird. Ist dies der Fall, stellen Sie sicher, dass Sie die gelöschte Vorlage mit **[!UICONTROL Staging]** live schalten, damit sie auch aus der Live-Umgebung gelöscht wird. Sie können auch **[!UICONTROL Push Live]** auf der Seite &quot;Vorlagen&quot;verwenden.

Siehe [Über Staging](../c-about-staging.md#concept_08B8F3CA1F4241108F14BA7FC7806CA7)

Siehe [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)

Sie benötigen bereits eine Vorlage, um eine Vorlage löschen zu können.

Siehe [Hinzufügen einer neuen Präsentations- oder Transportvorlagendatei](../c-about-design-menu/c-about-templates.md#task_73199757B6E748CAA604902FF913F012)

**So löschen Sie eine Präsentation oder eine Transportvorlagendatei**

1. Klicken Sie im Produktmenü auf **[!UICONTROL Design]** > **[!UICONTROL Templates]**.
1. Klicken Sie auf der Seite [!DNL Templates] in der Dropdown-Liste neben dem zu löschenden Vorlagennamen auf **[!UICONTROL Delete]**.
1. Klicken Sie im Dialogfeld [!DNL Delete Template] auf **[!UICONTROL Delete.]**
1. (Optional) Führen Sie einen der folgenden Schritte aus:

   * Klicken Sie auf **[!UICONTROL History]**, um alle vorgenommenen Änderungen wiederherzustellen.

      Siehe [Verwenden der Option Verlauf](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Klicken **[!UICONTROL Live]**.

      Siehe [Live-Einstellungen anzeigen](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Klicken **[!UICONTROL Push Live]**.

      Siehe [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Anzeigen einer Vorschau der Präsentationsvorlage minimiert{#task_1757B6207CC74221AE4BFFE5674D320B}

Sie können **[!UICONTROL Preview minimized]** verwenden, um zu sehen, wie die reduzierte Gewichtung einer Präsentationsvorlage aussehen würde, wenn Sie sie minimieren möchten.

<!-- 

t_previewing_the_presentation_template_minimized.xml

 -->

Wenn Sie die Vorlage der Hauptpräsentation minimieren, sollten Sie daran denken, die Minimierung für eingeschlossene Vorlagen (mit geführten Tags) zu aktivieren, da diese Option nicht vererbbar ist.

Siehe [Reduzieren der Gewichtung einer Präsentationsvorlage auf der Seite...](../c-about-design-menu/c-about-templates.md#task_B09BB3CE89714DEAAE8D9A899CF3009E)

Sie müssen bereits eine Vorlage zur Vorschau der Vorlage minimiert hinzugefügt haben.

Siehe [Hinzufügen einer neuen Präsentations- oder Transportvorlagendatei](../c-about-design-menu/c-about-templates.md#task_73199757B6E748CAA604902FF913F012)

Sie können den XML-Code einer Transportvorlagendatei Vorschau haben.

Siehe [Vorschau der XML-Datei einer Transportvorlagendatei](../c-about-design-menu/c-about-templates.md#task_58C6C52078E14AD88D2B2F0B3C439AE8)

**Zur Vorschau der Präsentationsvorlage minimiert**

1. Klicken Sie im Produktmenü auf **[!UICONTROL Design]** > **[!UICONTROL Templates]**.
1. Klicken Sie auf der Seite [!DNL Templates] in der Dropdown-Liste neben dem Namen einer Präsentationsvorlage auf **[!UICONTROL Preview minimized]**.

   Verwenden Sie die Spalte **[!UICONTROL Type]** in der Tabelle &quot;Vorlagen&quot;, um die Vorlagen nach Präsentation und Transport zu sortieren.
1. (Optional) Markieren Sie auf der Seite [!DNL Preview Minimized Template] die Option **[!UICONTROL Wrap lines]**, um die Tags im definierten Fenster zu lesen.
1. Klicken **[!UICONTROL Close]**.
1. (Optional) Führen Sie einen der folgenden Schritte aus:

   * Klicken Sie auf **[!UICONTROL History]**, um alle vorgenommenen Änderungen wiederherzustellen.

      Siehe [Verwenden der Option Verlauf](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Klicken **[!UICONTROL Live]**.

      Siehe [Live-Einstellungen anzeigen](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Klicken **[!UICONTROL Push Live]**.

      Siehe [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Reduzieren der Gewichtung einer Präsentationsvorlage auf Ihrer Website {#task_B09BB3CE89714DEAAE8D9A899CF3009E}

Mit der Option **[!UICONTROL Minimize]** in der Vorlagentabelle können Sie die Gewichtung einer Präsentationsvorlage verringern.

<!-- 

t_reducing_the_page_weight_of_a_presentation_template.xml

 -->

Durch die Reduzierung der Seitenlänge der Vorlage können Sie die Inline-JavaScript- und CSS-Gewichtung dynamisch minimieren. Sie entfernen auch redundante Leerzeichen im HTML-Code. Die Minimierung der Gewichtung der Seite in Ihrer Präsentationsvorlage kann dazu beitragen, die Suchergebnisse schneller zu liefern.

Sie können das Erscheinungsbild der minimierten Präsentationsvorlage auch mit **[!UICONTROL Preview minimized]** Vorschau haben.

Siehe [Anzeigen einer Vorschau der Präsentationsvorlage minimiert](../c-about-design-menu/c-about-templates.md#task_1757B6207CC74221AE4BFFE5674D320B).

**[!UICONTROL To reduce the page weight of a presentation template on your website]**

1. Klicken Sie im Produktmenü auf **[!UICONTROL Design]** > **[!UICONTROL Templates]**.
1. Markieren Sie auf der Seite [!DNL Templates] unter der Spalte [!DNL Minimize] das Kästchen für eine oder mehrere Präsentationsvorlagendateien, die Sie auf Ihrer Website so gering wie möglich halten möchten.

   Verwenden Sie die Spalte **[!UICONTROL Type]** in der Tabelle [!DNL Templates], um die Vorlagen nach Präsentation und Transport zu sortieren.
1. (Optional) Führen Sie einen der folgenden Schritte aus:

   * Klicken Sie auf **[!UICONTROL History]**, um alle vorgenommenen Änderungen wiederherzustellen.

      Siehe [Verwenden der Option Verlauf](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Klicken **[!UICONTROL Live]**.

      Siehe [Live-Einstellungen anzeigen](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Klicken **[!UICONTROL Push Live]**.

      Siehe [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Standardvorlagendatei für die Präsentation auf Ihrer Website {#task_C1E8CE817E4D43E096167A347C54DD53} festlegen

Wenn Sie über mehrere Präsentationsvorlagen verfügen, können Sie angeben, welche Vorlage ursprünglich zur Anzeige der Suchergebnisse verwendet werden soll.

<!-- 

t_setting_the_default_presentation_template_file_to_use.xml

 -->

Sie können die Regeln vor der Suche, die Regeln nach der Suche und die Geschäftsregeln verwenden, um zu bestimmen, wann eine Ihrer anderen Präsentationsvorlagen verwendet werden soll.

Siehe [Info zu Vorsuchregeln](../c-about-rules-menu/c-about-pre-search-rules.md#concept_5BF84BB6FACB4645BA9CB7496A01CD1F).

Siehe [Über Regeln nach der Suche](../c-about-rules-menu/c-about-post-search-rules.md#concept_AF6ADFCC0ADF4A788003964939917FDE).

Siehe [Geschäftsregeln](../c-about-rules-menu/c-about-business-rules.md#concept_2A93D76216754D3D8412CDEA00BD26BD).

Es ist üblich, dass eine Regel wie &quot;Für jede Suche legen Sie die gewünschte Präsentationsvorlage auf xxxx fest.&quot; Bei einer solchen Regel hat eine Änderung der Standardvorlage auf der Seite &quot;Vorlagen&quot;keine Auswirkungen.

**[!UICONTROL To set the default presentation template file to use on your website]**

1. Klicken Sie im Produktmenü auf **[!UICONTROL Design]** > **[!UICONTROL Templates]**.
1. Klicken Sie auf der Seite [!DNL Templates] unter der Spalte [!DNL Default] auf das Optionsfeld der entsprechenden Vorlagendatei, die Sie als Standard verwenden möchten.

   Verwenden Sie die Spalte **[!UICONTROL Type]** in der Tabelle [!DNL Templates], um die Vorlagen nach Präsentation und Transport zu sortieren.
1. (Optional) Führen Sie einen der folgenden Schritte aus:

   * Klicken Sie auf **[!UICONTROL History]**, um alle vorgenommenen Änderungen wiederherzustellen.

      Siehe [Verwenden der Option Verlauf](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Klicken **[!UICONTROL Live]**.

      Siehe [Live-Einstellungen anzeigen](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Klicken **[!UICONTROL Push Live]**.

      Siehe [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Vorschau der XML-Datei einer Transportvorlagendatei {#task_58C6C52078E14AD88D2B2F0B3C439AE8}

Sie können [!DNL Preview] verwenden, um die XML einer von Ihnen hinzugefügten Transportvorlage zu überprüfen.

<!-- 

t_previewing_the_xml_of_a_transport_template_file.xml

 -->

Sie müssen bereits über eine Transportvorlage verfügen, die der Vorschau der XML-Datei der Vorlage hinzugefügt wurde.

Siehe [Hinzufügen einer neuen Präsentations- oder Transportvorlagendatei](../c-about-design-menu/c-about-templates.md#task_73199757B6E748CAA604902FF913F012).

Sie können minimierte Präsentationsvorlagendateien zur Ansicht ihrer reduzierten Gewichtung Vorschau haben.

Siehe [Anzeigen einer Vorschau der Präsentationsvorlage minimiert](../c-about-design-menu/c-about-templates.md#task_1757B6207CC74221AE4BFFE5674D320B).

**So erstellen Sie die XML-Vorschau einer Transportvorlagendatei**

1. Klicken Sie im Produktmenü auf **[!UICONTROL Design]** > **[!UICONTROL Templates]**.
1. Klicken Sie auf der Seite [!DNL Templates] in der Dropdown-Liste neben dem Namen der Transportvorlage auf **[!UICONTROL Preview]**.

   Verwenden Sie die Spalte **[!UICONTROL Type]** in der Tabelle [!DNL Templates], um die Vorlagen nach Präsentation und Transport zu sortieren.
1. Schließen Sie das Anzeigefenster und kehren Sie zu [!DNL site search/merchandising] zurück.
1. (Optional) Führen Sie einen der folgenden Schritte aus:

   * Klicken Sie auf **[!UICONTROL History]**, um alle vorgenommenen Änderungen wiederherzustellen.

      Siehe [Verwenden der Option Verlauf](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Klicken **[!UICONTROL Live]**.

      Siehe [Live-Einstellungen anzeigen](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Klicken **[!UICONTROL Push Live]**.

      Siehe [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

