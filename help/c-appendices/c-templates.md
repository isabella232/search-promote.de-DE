---
description: 'null '
seo-description: 'null '
seo-title: Vorlagen
solution: Target
title: Vorlagen
topic: Appendices,Site search and merchandising
uuid: 78299032-dc23-4dfe-b68f-cd57b2b6d7d8
translation-type: tm+mt
source-git-commit: ca4156f80d7dbb85d2d56b6caf7c0f560299d86e
workflow-type: tm+mt
source-wordcount: '15139'
ht-degree: 3%

---


# Vorlagen{#templates}

## Vorlagen {#concept_A5CFB6BD805D49459A96219AF1B17842}

## Präsentationsvorlagen-Tags {#reference_F1BBF616BCEC4AD7B2548ECD3CA74C64}

Eine Liste von Site-Suchen/Merchandising-Tags und -Attributen für Präsentationsvorlagen.


Eine Präsentationsvorlage ist eine HTML-Datei, die Präsentationsvorlagen-Tags enthält, die von Site-Suche/Merchandising definiert werden. Diese Tags geben an, wie die Suchergebnisse, die Kunden sehen, formatiert sind.

Siehe [Vorlagen](../c-about-design-menu/c-about-templates.md#concept_06EB481B14864E18A8AE2BCD1D6EF0B5).

Sie können aus den folgenden Präsentations-Tag-Gruppen auswählen:

* [Erklärungen](../c-appendices/c-templates.md#section_82C5CA734D2941EB858FEFE3B695D2EC)
* [Ergebnisse](../c-appendices/c-templates.md#section_06F249C9F6AE4B0F8C32117E19DCC905)
* [Facets](../c-appendices/c-templates.md#section_EA4C5678D5864B89BAB4D0DFE62A4624)
* [Breadcrumb](../c-appendices/c-templates.md#section_9B39B71FA6EC49FA8D88AD8A3BA987F7)
* [Menüs](../c-appendices/c-templates.md#section_1D489ADF041F4351A66E5D5742125CA8)
* [Pagenav](../c-appendices/c-templates.md#section_2EE397635C514BBC8D668278EA314F35)
* [Kürzliche Suchvorgänge](../c-appendices/c-templates.md#section_8CD907521F584257B475595B01A5964B)
* [„Meinten Sie“-](../c-appendices/c-templates.md#section_C1EB3B9D8E1242798A6E04609D1E3543)
* [Autom.](../c-appendices/c-templates.md#section_897316BEE1454E839A56B565CA4AF018)
* [Speicher](../c-appendices/c-templates.md#section_A33E25DB5E67404A823BD9618665B773)
* [Zonen](../c-appendices/c-templates.md#section_B9B3179E000C42D492E1541F2FE44CB5)
* [Loopindikatoren](../c-appendices/c-templates.md#section_387322CA0AA843A2ACF2795C328673E9)
* [Verschiedene Sprachen](../c-appendices/c-templates.md#section_BFE8DC98E26F4D7BB60FEC54D9A5DC6C)

## Deklarationen {#section_82C5CA734D2941EB858FEFE3B695D2EC}

Deklarationen sind spezielle Tags mit geführter Deklaration, die Sie oben in einer Präsentationsvorlage auf der obersten Ebene festlegen können. Alle nachfolgenden Deklarationen werden ignoriert, einschließlich Deklarationen in eingeschlossenen Vorlagen.

<table> 
 <thead> 
  <tr> 
   <th colname="col01" class="entry"> </th> 
   <th colname="col1" class="entry"> <p>Tag </p> </th> 
   <th colname="col2" class="entry"> <p>Beschreibung </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col01"> <p>1 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-content-type-header content="content-type"&gt; </span> </p> </td> 
   <td colname="col2"> <p>Standardmäßig wird die Präsentationsvorlage mit einem Mime-Typ von text/html zurückgesendet. Sie können den Inhaltstyp für dieses Tag ändern. </p> <p>Deklarieren Sie dieses Tag in Ihrer Präsentationsvorlage so hoch wie möglich. Fügen Sie mit diesem Tag keinen anderen Text in derselben Zeile hinzu. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>2 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-xml-declare&gt; </span> </p> </td> 
   <td colname="col2"> <p> Wenn Sie XML zurückgeben, können Sie mit diesem Tag die XML-Deklaration erstellen. Machen Sie dieses Tag zur ersten Zeile in Ihrer Präsentationsvorlage. Wenn Sie dieses Tag verwenden, wird der Content-Type automatisch auf text/xml eingestellt, es sei denn, Sie überschreiben ihn mit <span class="codeph"> &lt;guided-content-type-header&gt; </span> in der ersten Zeile. Wenn Sie keine Zeichensätze angeben, wird standardmäßig UTF-8 verwendet. Dieses Tag ergibt die folgende Ausgabe in Ihrem XML-Dokument: </p> <p> <span class="codeph"> &lt;?xml version="1.0" encoding="charset-name" standalone="yes" ?&gt; </span> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Ergebnisse {#section_06F249C9F6AE4B0F8C32117E19DCC905}

<table> 
 <thead> 
  <tr> 
   <th colname="col01" class="entry"> </th> 
   <th colname="col1" class="entry"> <p>Tag </p> </th> 
   <th colname="col2" class="entry"> <p>Beschreibung </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col01"> <p>3 </p> </td> 
   <td colname="col1"> <p> 
     <!--In search-eng 1/31/13--> <span class="codeph"> &lt;guided-results&gt;&lt;/guided-results&gt; </span> </p> </td> 
   <td colname="col2"> <p>Das Tag mit geführten Ergebnissen definiert die Grenzen einer Ergebnisschleife. Auf alle Ergebnisse kann zugegriffen werden, indem ein <span class="codeph"> gsname </span>-Attribut angegeben wird. Wenn kein <span class="codeph"> gsname </span> angegeben ist, werden die Standardsuchergebnisse angezeigt. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>2 </p> </td> 
   <td colname="col1"> <p> 
     <!--In search-eng 1/31/13--> <span class="codeph"> &lt;guided-result-link&gt;&lt;/guided-result-link&gt; </span> </p> </td> 
   <td colname="col2"> <p>Um einen Link zu einem bestimmten Ergebnis zu erstellen, verwenden Sie das Tag <span class="codeph"> guided-result-link </span>. Durch Definieren des Attributs <span class="codeph"> gsname </span> können Sie ein Feld aus dem Index anstelle des standardmäßigen "loc"-Tags verwenden, das auf die "search-url" verweist. Alle anderen Attribute, z. B. class und Zielgruppe, können ebenfalls übergeben werden, die im resultierenden Anker-Tag ausgegeben werden. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>3 </p> </td> 
   <td colname="col1"> <p> 
     <!--In search-eng 1/31/13--> <span class="codeph"> &lt;guided-result-img gsname="fieldname"&gt; </span> </p> </td> 
   <td colname="col2"> <p>Das <span class="codeph"> &lt;guided-result-img&gt; </span>-Tag hilft beim Erstellen von Bild-Tags, anstatt Variablen in ein unbearbeitetes <span class="codeph">-img </span>-Tag einzubetten. </p> <p>Geben Sie das für den Bildpfad zu verwendende Feld im Attribut <span class="codeph"> gsname </span> an. Das Ergebnis ist ein <span class="codeph"> img </span>-Tag mit allen standardmäßigen HTML-Attributen, die Sie definiert haben und die übergeben wurden. Das folgende Beispiel: </p> <p> <code class="syntax html"> &lt;guided-result-img&nbsp;gsname="thumbnail" 
      &nbsp;class="thumb"&nbsp;border="0"/&gt; </code> </p> <p>becomes: </p> <p> <code class="syntax html"> &lt;img&nbsp;src="prod8172.jpg"&nbsp;class="thumb" 
      &nbsp;border="0"/&gt; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>4 </p> </td> 
   <td colname="col1"> <p> 
     <!--Updated to match search-eng version, 1/31/13; search-eng version does not have [escape...] Added ijson on 8/28/2015--> <span class="codeph"> &lt;guided-result-field gsname="fieldname"&gt; </span> </p> </td> 
   <td colname="col2"> <p> Alle Informationen, die in den Ergebnissen angezeigt werden sollen, werden als <span class="codeph"> &lt;guided-result-field&gt; </span>-Tag angezeigt (es sei denn, es werden automatisch generierende Tags wie das <span class="codeph"> &lt;guided-result-img&gt; </span>-Tag verwendet). </p> <p>Geben Sie den Namen des Suchindexfelds in <span class="codeph"> gsname </span> ein. Die exakte übergebene Zeichenfolge wird in der Vorlage ausgegeben. </p> <p>Sie können eine Escape-Option angeben, wenn dieses Feld anders als in der Transportvorlage angegeben auskommentiert werden soll. </p> <p>Diese Kodierung wird auf jede Kodierung angewendet, die in der Transportvorlage angegeben wurde. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>5 </p> </td> 
   <td colname="col1"> <p> 
     <span class="codeph"> &lt;guided-if&gt;&lt;/guided-if-result-field&gt; </span> </p> </td> 
   <td colname="col2"> <p>Dieser Satz von bedingten Tags ist "true", wenn im jeweiligen Feld Inhalte angezeigt werden sollen. Wenn kein Inhalt vorhanden ist, lautet die Bedingung "false". Mithilfe der Tags können Sie festlegen, ob umgebendes HTML angezeigt oder nicht angezeigt wird, wenn kein Wert vorhanden ist, ein anderes Bild angezeigt wird usw. </p> <p> <code class="syntax html"> &lt;guided-if-result-field&nbsp;gsname="thumbnail"&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-result-img&nbsp;gsname="thumbnail"&nbsp;class="thumb"&nbsp;/&gt; 
      &lt;guided-else-result-field&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&lt;img&nbsp;src="nothumb.jpg"&nbsp;class="nothumb"&nbsp;/&gt; 
      &lt;/guided-if-result-field&gt; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>6 </p> </td> 
   <td colname="col1"> <p> 
     <code> &lt;guided-if[-not]-result-wrap&gt; 
      &lt;guided-else-result-wrap&gt; 
      &lt;/guided-if[-not]-result-wrap&gt; </code> </p> </td> 
   <td colname="col2"> <p>Bei der Anzeige der Ergebnisse in Spalten wird mit diesem Tag ermittelt, ob das aktuelle Ergebnis das Ende einer Spalte markiert. </p> <p>Wenn die boolesche Bedingung "true"ist, wird am Ende des Ergebnisses HTML hinzugefügt, um die Zeile abzuschließen und eine neue Beginn zu erstellen. Wenn es sich um die letzte Zeile handelt, wird keine neue Zeile gestartet. </p> <p>Weitere Informationen zu diesem Tag finden Sie unter <span class="codeph"> &lt;guided-if-not-last&gt; </span>. </p> <p> <code class="syntax html"> &lt;guided-if-result-wrap&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/div&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-if-not-last&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;div&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/guided-if-not-last&gt; 
      &nbsp;&lt;/guided-if-result-wrap&gt; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>7 </p> </td> 
   <td colname="col1"> <p> 
     <!--In search-eng version, 1/31/13--> <span class="codeph"> &lt;guided-results-found&gt; </span> </p> </td> 
   <td colname="col2"> <p>Gibt eine 1 zurück, wenn die Back-End-Suchanfrage Ergebnisse zurückgegeben hat, und 0, wenn dies nicht der Fall war. Wenn kein <span class="codeph"> gsname </span> angegeben ist, geht das Tag von der primären Suche aus. Dieses Tag ist nützlich, um Logik an JavaScript-Routinen zu übergeben. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>8 </p> </td> 
   <td colname="col1"> <p> 
     <!--In search-eng version 1/31/13--> <span class="codeph"> &lt;guided-results-total&gt; </span> </p> </td> 
   <td colname="col2"> <p>Gibt die Gesamtanzahl der Ergebnisse im angegebenen Ergebnissatz zurück. Geht von der Standardsuche aus, wenn kein <span class="codeph"> gsname </span> angegeben wird. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>9 </p> </td> 
   <td colname="col1"> <p> 
     <!--In search-eng version 1/31/13--> <span class="codeph"> &lt;guided-results-lower&gt; </span> </p> </td> 
   <td colname="col2"> <p>Gibt die Ergebnisnummer des unteren Ergebnisses auf der Seite für den angegebenen Ergebnissatz zurück. Geht von der Standardsuche aus, wenn kein <span class="codeph"> gsname </span> angegeben wird. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>10 </p> </td> 
   <td colname="col1"> <p> 
     <!--In search-eng version 1/31/13--> <span class="codeph"> &lt;guided-results-upper&gt; </span> </p> </td> 
   <td colname="col2"> <p>Gibt die Ergebnisnummer des oberen Ergebnisses auf der Seite für den angegebenen Ergebnissatz zurück. Geht von der Standardsuche aus, wenn kein <span class="codeph"> gsname </span> angegeben wird. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>11 </p> </td> 
   <td colname="col1"> <p> 
     <!--Updated to match search-eng version 1/31/13--> 

    &amp;lt;/guided-if[-not]-results-found&amp;gt;   &lt;/p>  &lt;/td>
<td colname="col2"> <p>Zeigt Inhalt an, wenn Ergebnisse gefunden werden. Zeigt auch keine HTML-Ergebnisse an, wenn keine Ergebnisse gefunden werden. </p> <p> <code class="syntax html"> &lt;guided-if-results-found&nbsp;gsname="products"&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-results&nbsp;gsname="products"&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;... 
      &nbsp;&nbsp;&nbsp;&nbsp;&lt;/guided-results&gt; 
      &lt;guided-else-results-found&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;No&nbsp;results&nbsp;were&nbsp;found. 
      &lt;/guided-if-results-found&gt; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>12 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-result-title /&gt; </span> </p> </td> 
   <td colname="col2"> <p>Das <span class="codeph"> &lt;guided-result-title&gt; </span>-Tag gibt den Wert des Felds für die Titeltransportvorlage an, das mit <span class="codeph"> </span>-Transport-Tag angegeben wird. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>13 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-result-description /&gt; </span> </p> </td> 
   <td colname="col2"> <p>Das <span class="codeph"> &lt;guided-result-description&gt; </span>-Tag gibt den Wert des mit <span class="codeph"> &lt;description&gt; </span>-transport-Tags angegebenen Felds der Beschreibungstransportvorlage an. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>14 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-result-loc /&gt; </span> </p> </td> 
   <td colname="col2"> <p>Das &lt; <span class="codeph">-Tag guided-result-loc&gt; </span> gibt den Wert des Felds der LOC-Transportvorlage an, das mit <span class="codeph"> &lt;loc&gt; </span>-Transport-Tag angegeben wird. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>15 </p> </td> 
   <td colname="col1"> <p> 

    &amp;lt;/guided-if-result-field&amp;gt;   &lt;/p>  &lt;/td>
<td colname="col2"> <p>"True", wenn im jeweiligen Feld Inhalt angezeigt wird. Wenn kein Inhalt vorhanden ist, lautet die Bedingung "false". Verwenden Sie die Tags, um festzulegen, ob umliegende HTML-Elemente angezeigt werden, wenn kein Wert vorhanden ist, ein anderes Bild angezeigt wird usw. </p> <p> <code class="syntax html"> &lt;guided-if-result-field&nbsp;gsname="thumbnail"&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-result-img&nbsp;gsname="thumbnail"&nbsp;class="thumb"/&gt; 
      &lt;guided-else-result-field&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;img&nbsp;src="nothumb.jpg"&nbsp;class="nothumb"/&gt; 
      &lt;/guided-if-result-field&gt; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>16 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-result-attribute-table gsname="tablename"&gt; </span> </p> </td> 
   <td colname="col2"> <p>Dieses Tag stellt eine Schleife durch die Attributtabelle bereit, die in der Transportvorlage mit dem Tag <span class="codeph"> </span> transport definiert ist. Für die Anzeige der Attributfeldwerte steht das Tag <span class="codeph"> &lt;guided-result-attribute-table-field&gt; zur Verfügung. </span> Es ist auch möglich, das Tag plain <span class="codeph"> guided-result-field </span> innerhalb der Schleife für die Anzeige anderer Ergebnisfelder zu verwenden. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>17 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-result-attribute-table-field gsname="fieldname"&gt; </span> </p> </td> 
   <td colname="col2"> <p>Zeigt das Attributtabellenfeld an, wie in der Transportvorlage definiert. </p> <p> 

    ...
    
    &amp;lt;ul&amp;gt;
    
    &amp;lt;guided-result-attribute-table&amp;nbsp;gsname=&quot;downloads&quot;&amp;gt;
    &amp;nbsp;&amp;nbsp;&amp;lt;li&amp;gt;
    &amp;nbsp;&amp;nbsp;&amp;nbsp;&amp;nbsp;&amp;nbsp;&amp;lt;a&amp;nbsp;href=&quot;&amp;lt;guided -attribute-table-field&amp;nbsp;gsname=&quot;download_link&quot;&amp;nbsp;/&amp;gt;&quot;&amp;gt;
    &amp;nbsp;&amp;nbsp;&amp;nbsp;&amp;nbsp;&amp;nbsp;&amp;nbsp;&amp;nbsp;&amp;nbsp;&amp;nbsp;&amp;lt;guided-result-attribute-table-field&amp;nbsp;gsname=&quot;geleitet download_title&quot;&amp;nbsp;/&amp;gt;
    &amp;nbsp;&amp;nbsp;&amp;nbsp;&amp;nbsp;&amp;nbsp;&amp;lt;/a&amp;gt;&amp;nbsp;(&amp;lt;guided-result-field&amp;nbsp;gsname=&quot;title&quot;/&amp;gt;)
    &amp;nbsp;&amp;nbsp;&amp;lt;
    &amp;gt;&amp;lt;/guided-result-attribute-table&amp;gt;
    
    &amp;lt;/ul&amp;gt;
    
    ..
    
    &amp;lt;/guided-results&amp;gt;   &lt;/p>  &lt;/td>
</tr> 
  <tr> 
   <td colname="col01"> <p>18 </p> </td> 
   <td colname="col1"> <p> 
     <!--NEW for S&P 8.17.0 release in October 2014--> <span class="codeph"> &lt;guided-trace&gt; </span> </p> </td> 
   <td colname="col2"> <p>Gibt die in den Trace-Daten im allgemeinen Abschnitt der JSON-Datenausgabe enthaltenen Ablaufverfolgungsinformationen von der Transportvorlage für die jeweilige Suche aus. </p> <p>Wenn kein Suchname angegeben ist, wird <span class="codeph"> default </span> angenommen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>19 </p> </td> 
   <td colname="col1"> <p> 
     <!--NEW for S&P 8.17.0 release on October 30, 2014)--> <span class="codeph"> &lt;guided-result-trace /&gt; </span> </p> </td> 
   <td colname="col2"> <p>Gibt den JSON-Inhalt aus, der in den Ergebnissen &gt; Ablaufverfolgungsinformationen der JSON-Datenausgabe durch die Transportvorlage für das aktuelle Suchergebnis gefunden wird. </p> <p>Dieses Tag ist nur in der <span class="codeph"> &lt;guided-results&gt;&lt;/guided-results&gt; </span>-Schleife gültig. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Facets {#section_EA4C5678D5864B89BAB4D0DFE62A4624}

Facets sind Navigationskomponenten, mit denen Sie in die Suchergebnisse vordringen können. Mithilfe der Facetten-Tags können Sie verschiedene Facetten Ihrer Präsentationsvorlage anzeigen. Sie verweisen auf Facetten anhand des Namens.

Siehe [Über Facets](../c-about-design-menu/c-about-facets.md#concept_FA912B3B41EE493DB2F492D188457FF5).

Weitere Informationen finden Sie unter [Info zu Facet Rail](../c-about-design-menu/c-about-facet-rails.md#concept_1FDC8BCDFFC84A0889DA670F63D5F6DB).

Siehe [Dynamische Facets](../c-about-design-menu/c-about-dynamic-facets.md#concept_E65A70C9C2E04804BF24FBE1B3CAD899).

<table> 
 <thead> 
  <tr> 
   <th colname="col01" class="entry"> </th> 
   <th colname="col1" class="entry"> <p>Tag </p> </th> 
   <th colname="col2" class="entry"> <p>Beschreibung </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col01"> <p>1 </p> </td> 
   <td colname="col1"> <p> 
     <!--NEW 02/27/2014--> <span class="codeph"> &lt;guided-dynamic-facets&gt;&lt;/guided-dynamic-facets&gt; </span> </p> </td> 
   <td colname="col2"> 
    <!--NEW 2/2/2014--> <p>Ein Schleifenkontext für dynamische Facetten einer bestimmten Suche. </p> <p>Das <span class="codeph"> &lt;guided-facet&gt; </span>-Tag der Präsentationsvorlage wird so bearbeitet, dass das gsname-Attribut automatisch vom <span class="codeph"> &lt;guided-dynamic-facets&gt; </span>-Schleifenkontext bereitgestellt wird. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>2 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-facet-display-name gsname=" <span class="varname"> facetname </span>" /&gt; </span> </p> </td> 
   <td colname="col2"> <p>Gibt die Anzeigenbezeichnung der Facette zurück. </p> <p>Wenn die Facette das <span class="codeph"> &lt;display-name&gt; </span>-Tag in der Transportvorlage verwendet, wird der Inhalt dieses Tags zur Beschriftung. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>3 </p> </td> 
   <td colname="col1"> <p> 
     <!--In search-eng version 1/31/13--> <span class="codeph"> &lt;guided-facet-rail&gt;&lt;/guided-facet-rail&gt; </span> </p> </td> 
   <td colname="col2"> <p> Definiert einen Abschnitt in der Präsentationsvorlage, der als sich wiederholendes Muster für jede Facette in der Facettenleiste verwendet wird. </p> <p> Jede Facette, die zur Facettenleiste gehört, verwendet diesen Abschnitt, um ihre Ausgabe zu bewerten. </p> <p>Das folgende Beispiel zeigt eine Facettenleiste: </p> <p> <code class="syntax html"> &lt;guided-facet-rail&gt; 
      &nbsp;&nbsp;&lt;guided-facet&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-facet-display-name/&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;... 
      &nbsp;&nbsp;&nbsp;&nbsp;&lt;/guided-facet&gt; 
      &nbsp;&nbsp;&lt;/guided-facet-rail&gt; </code> </p> <p>Beachten Sie, dass folgende Tags das Attribut <span class="codeph"> gsname </span> nicht benötigen, wenn sich innerhalb des <span class="codeph"> &lt;guided-facet-rail&gt; </span>-Tags ein Wert befindet, da dieser zum Suchzeitpunkt dynamisch bestimmt wird und korrekt ersetzt wird: </p> 
    <ul id="ul_5B5ACAFD2B8848DDB27471AB9DA7BE6E"> 
     <li id="li_5A07E78D51FE4708879DD742C877FFFF">guided-facet </li> 
     <li id="li_B875DCACD7AB4FC890A456A6939AB657">guided-facet-display-name </li> 
     <li id="li_B70450749E864DE7BA401E3CD6EF5EB3">guided-facet-total-count </li> 
     <li id="li_DECDF5EF6FF7454F86C236D322F2BFEA">guided-facet-undo-link </li> 
     <li id="li_176949227AC14E8CA643A419E10F7B5A">guided-facet-undo-path </li> 
     <li id="li_B32D981281744462BC680F6EFEAC0069">guided-facet-verhalten </li> 
    </ul> <p>Die Sortierkriterien auf der Seite <span class="wintitle"> Facet Rail </span> bestimmen die Position der Facetten. Sie können die Sortierreihenfolge aus der Dropdown-Liste "Facets-Sortiermethode"auswählen. </p> <p> 
     <!--NEW 02/27/2014-->Dieses Tag kann optional einen gsname-Attributwert von  <span class="codeph"> _dynamic_facets annehmen,  </span>der einen Schleifenkontext für alle dynamischen Facetten für diese Suche bereitstellt. Diese vordefinierte Facet-Leiste wird auch in der Business Rules-Benutzeroberfläche für die Aktion <span class="codeph"> Push-Facette X in der Facet-Leiste '_dynamic_facets' angezeigt, um Y </span> zu positionieren." </p> <p>Weitere Informationen finden Sie unter <a href="../c-about-design-menu/c-about-facet-rails.md#concept_1FDC8BCDFFC84A0889DA670F63D5F6DB" format="dita" scope="local">Info zu Facet Rail </a>. </p> <p>Siehe auch <a href="../c-about-design-menu/c-about-dynamic-facets.md#concept_E65A70C9C2E04804BF24FBE1B3CAD899" format="dita" scope="local"> Über dynamische Facets </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>4 </p> </td> 
   <td colname="col1"> <p> 
     <!--Updated to match current search-eng version 1/31/13--> <span class="codeph"> &lt;guided-facet gsname=" <span class="varname"> facetname </span>" height=" <span class="varname"> 60px </span>" width=" <span class="varname"> 120px </span>"&gt;&lt;/guided-facet&gt; </span> </p> </td> 
   <td colname="col2"> <p>Verwenden Sie das Tag <span class="codeph"> mit einer geführten Facette </span>, um einen Bereich zu definieren, in dem sich alle Facetten-Tags auf eine bestimmte Facette beziehen. Dieses Tag ist auch ein boolescher Tag, der den gesamten Inhalt verbirgt, wenn keine Werte in der Facette vorhanden sind. In diesem Fall hat es keinen Sinn, die Facettenwerte auszugeben. </p> <p>Die Attribute für Höhe und Breite sind optional und die Abmessungen werden in Pixel (px) angegeben. Der Visual Rule Builder (VRB) verwendet diese beiden Attribute und zeigt ein gepunktetes Feld als interaktiven Platzhalter an, wenn die Facette ausgeblendet wird. </p> <p> Wenn sich der Anzeigename in der Facette befindet und die Facette ausgeblendet ist, wird auch der Name ausgeblendet. Wenn sich der Name jedoch außerhalb der Facette befindet, können Sie den Namen nur ausblenden, wenn ein <span class="codeph">-Tag </span> oder ein <span class="codeph">-Tag mit einem geführten-falls-facet-visible </span>-Tag um ihn herum umschlossen ist. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>5 </p> </td> 
   <td colname="col1"> <p> 
     <!--NEW, brought in from search-eng version, 1/31/13--> <span class="codeph"> &lt;guided-if&gt;&lt;/guided-if&gt; </span> </p> </td> 
   <td colname="col2"> <p>Dieses bedingte Tag ist "true", wenn die Anzahl der Facettenwerte über dem in der Konfiguration definierten Längenschwellenwert liegt. Verwenden Sie sie, um eine Facette als anderes Benutzeroberflächenelement anzuzeigen (z. B. eine abgeschnittene Liste oder ein Bildlauffeld), wenn die Liste zu lang ist. </p> <p> <code class="syntax xml"> &lt;guided-facet&nbsp;name="category"&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-if-facet-long&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;select&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-facet-values&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-facet-option&nbsp;/&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/guided-facet-values&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/select&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-else-facet-long&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-facet-values&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-facet-value-link&gt;&lt;guided-facet-value&nbsp;/&gt;&lt;/guided-facet-link&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/guided-facet-values&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&lt;/guided-if-facet-long&gt; 
      &lt;/guided-facet&gt; </code> </p> <p>Sie können diese Bedingung auch außerhalb des Kontexts eines Blocks mit dem Namen <span class="codeph"> guided-facet </span> verwenden, indem Sie direkt über das Attribut <span class="codeph"> gsname </span> auf eine bestimmte Facette verweisen. </p> <p> <code class="syntax html"> &lt;guided-if-facet-long&nbsp;gsname="category"&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;The&nbsp;category&nbsp;facet&nbsp;is&nbsp;very&nbsp;long! 
      &lt;/guided-if-facet-long&gt; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>6 </p> </td> 
   <td colname="col1"> <p> 
     <!--NEW, brought in from search-eng version, 1/31/13--> <span class="codeph"> &lt;guided-if&gt;&lt;/guided-if&gt; </span> </p> </td> 
   <td colname="col2"> <p>Dieses bedingte Tag ist "true", wenn auf die Facette mindestens einmal geklickt wird und derzeit ein Facettenwert ausgewählt ist. Es wird zum Anzeigen oder Ausblenden von HTML- oder gs-Tags verwendet, je nachdem, ob auf eine Facette geklickt wurde. </p> <p> <code class="syntax html"> &lt;guided-facet&nbsp;name="category"&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-if-facet-selected&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;This&nbsp;facet&nbsp;has&nbsp;been&nbsp;selected.&nbsp;&nbsp;You&nbsp;can&nbsp;no&nbsp;longer&nbsp;refine&nbsp;it. 
      &nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-else-facet-selected&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-facet-values&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-facet-value-link&gt;&lt;guided-facet-value&nbsp;/&gt;&lt;/guided-facet-link&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&lt;/guided-facet-values&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&lt;/guided-if-facet-selected&gt; 
      &lt;/guided-facet&gt; </code> </p> <p>Sie können diese Bedingung auch außerhalb des Kontexts eines Blocks mit dem Namen <span class="codeph"> guided-facet </span> verwenden, indem Sie direkt über das Attribut <span class="codeph"> gsname </span> auf eine bestimmte Facette verweisen. </p> <p> <code> &lt;guided-if-facet-selected&nbsp;gsname="category"&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;The&nbsp;category&nbsp;facet&nbsp;is&nbsp;selected! 
      &lt;/guided-if-facet-selected&gt; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>7 </p> </td> 
   <td colname="col1"> <p> 
     <!--NEW, brought in from search-eng version, 1/31/13--> <span class="codeph"> &lt;guided-if&gt;&lt;/guided-if&gt; </span> </p> </td> 
   <td colname="col2"> <p>Dieses bedingte Tag ist "true", wenn nur ein Facet-Wert vorhanden ist. Verwenden Sie das Tag, um die Anzeige der Facette zu ändern, wenn sie nicht in der Lage ist, die Ergebnisse zu verfeinern. </p> <p> <code class="syntax html"> &lt;guided-facet&nbsp;name="category"&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-if-facet-single&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Facet&nbsp;is&nbsp;not&nbsp;refinable. 
      &nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-else-facet-single&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-facet-values&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-facet-value-link&gt;&lt;guided-facet-value&nbsp;/&gt;&lt;/guided-facet-link&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/guided-facet-values&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&lt;/guided-if-facet-single&gt; 
      &lt;/guided-facet&gt; </code> </p> <p>Sie können diese Bedingung auch außerhalb des Kontexts eines Blocks mit dem Namen <span class="codeph"> guided-facet </span> verwenden, indem Sie direkt über das Attribut <span class="codeph"> gsname </span> auf eine bestimmte Facette verweisen. </p> <p> <code class="syntax html"> &lt;guided-if-facet-single&nbsp;gsname="category"&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;There&nbsp;is&nbsp;only&nbsp;one&nbsp;value&nbsp;in&nbsp;the&nbsp;category&nbsp;facet! 
      &lt;/guided-if-facet-single&gt; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>8 </p> </td> 
   <td colname="col1"> <p> 
     <!--Added 7/15/2014--> <span class="codeph"> &lt;guided-if&gt;&lt;/guided-if&gt; </span> </p> </td> 
   <td colname="col2"> <p>Dieses Bedingungs-Tag ist "true", wenn die Facette mehrseitig ausgewählt ist. Verwenden Sie das Tag, um die Anzeige der Facette innerhalb der Tags <span class="codeph"> &lt;guided-facet-rail&gt; </span> oder <span class="codeph"> &lt;guided-dynamic-facets&gt; zu ändern.</span> </p> <p> 

    &amp;nbsp;&amp;nbsp;&amp;nbsp;&amp;nbsp;&amp;lt;guided-if-facet-multiselect&amp;gt;
    &amp;nbsp;..
    &amp;nbsp;&amp;lt;guided-else-facet-multiselect&amp;gt;
    &amp;nbsp;...
    &amp;nbsp;&amp;lt;/guided-if-facet-multiselect&amp;gt;
    &amp;nbsp;&amp;nbsp;&amp;nbsp;&amp;nbsp;..
    &amp;nbsp;&amp;nbsp;&amp;nbsp;&amp;nbsp;&amp;lt;/guided-facet&amp;gt;
    &amp;nbsp;&amp;nbsp;&amp;lt;/guided-facet-rail&amp;gt   &lt;/p>  &lt;/td>
</tr> 
  <tr> 
   <td colname="col01"> <p>9 </p> </td> 
   <td colname="col1"> <p> 
     <!--In search-eng version 1/31/13--> <span class="codeph"> &lt;guided-facet-values&gt; facetname  </span>"]&gt;&lt;/guided-facet-values&gt; </span><span class="varname"> </span></p> </td> 
   <td colname="col2"> <p>Dies ist das Tag des Iterators für den Facettenwert. Sie können sie im Kontext eines Blocks mit dem Namen <span class="codeph"> guided-facet </span> definieren. In diesem Fall können Sie <span class="codeph"> <span class="varname"> gsname </span> </span> weglassen. Sie können sie auch außerhalb eines beliebigen <span class="codeph"> geführten-facets </span>-Blocks definieren. Das <span class="codeph"> <span class="varname">-gsname </span> </span>-Attribut muss jedoch angegeben werden, welche Facettenwerte angezeigt werden. </p> <p>Sie können dieses Tag auch verwenden, um die Facettenwerte außerhalb des Kontexts eines mit dem Namen <span class="codeph"> geführten Facets </span> anzuzeigen. Sie referenzieren eine bestimmte Facette direkt mit dem <span class="codeph"> <span class="varname"> gsname </span> </span>-Attribut. </p> <p> <code class="syntax html"> &lt;script&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;registerFacetValues('category',&nbsp;'&lt;guided-facet-values&nbsp;gsname="category"&gt;&lt;guided-facet-value/&gt;,&lt;/guided-facet-values&gt;'); 
      &lt;/script&gt; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>10 </p> </td> 
   <td colname="col1"> <p> 
     <!--Updated to match search-eng version 1/31/13--> <span class="codeph"> &lt;guided-facet-value&gt; </span> </p> </td> 
   <td colname="col2"> <p>Gibt die Zeichenfolge des aktuellen Facet-Werts aus. </p> <p>Standardmäßig ist der Wert HTML-Escape-Zeichen. Mit der Escape-Option können Sie die Escape-Methode ändern, mit der der Wert Escapezeichen verwendet wird. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>11 </p> </td> 
   <td colname="col1"> <p> 
     <!--In search-eng version 1/31/13--> <span class="codeph"> &lt;guided-facet-count /&gt; </span> </p> </td> 
   <td colname="col2"> <p>Gibt die Anzahl der Ergebnisse aus, die mit dem aktuellen Facet-Wert übereinstimmen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>12 </p> </td> 
   <td colname="col1"> <p> 
     <!--NEW, brought in from search-eng version, 1/31/13--> <span class="codeph"> &lt;guided-facet-value-link&gt;&lt;/guided-facet-value-link&gt; </span> </p> </td> 
   <td colname="col2"> <p>Erstellt einen Link um die Facet-Wertzeichenfolge, auf den der Besucher der Site klicken kann. Der Pfad wird automatisch generiert, um die Ergebnisse um den aktuellen Facettenwert einzugrenzen. Es unterstützt die direkte Übergabe jedes Attributs an das Anker-Tag. </p> <p> <code class="syntax html"> &lt;guided-facet-values&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-facet-value-link&nbsp;class="facetlink"&gt;&lt;guided-facet-value&nbsp;/&gt;&lt;/guided-facet-value-link&gt; 
      &lt;/guided-facet-values&gt; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>13 </p> </td> 
   <td colname="col1"> <p> 
     <!--Updated to match search-eng version 1/31/13--> <code> &lt;guided-if-facet-value-selected&gt; 
      &lt;guided-else-facet- 
      value-selected&gt; 
      &lt;/guided-if-facet-value-selected&gt; </code> </p> </td> 
   <td colname="col2"> <p>Ändert die Anzeige des Facettenwerts, wenn er aktuell ausgewählt ist. Wenn sie bereits ausgewählt wurde, ist sie in den meisten Fällen nicht mehr miteinander verknüpft. </p> <p> <code class="syntax html"> &lt;guided-facet-values&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-if-facet-value-selected&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;b&gt;&lt;guided-facet-value/&gt;&lt;/b&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-else-facet-value-selected&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-facet-link&gt;&lt;guided-facet-value/&gt;&lt;/guided-facet-link&gt;&nbsp;&nbsp;&nbsp; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/guided-if-facet-value-selected&gt; 
      &lt;/guided-facet-values&gt; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>14 </p> </td> 
   <td colname="col1"> <p> 
     <!--Updated to match search-eng version 1/31/13--> 

    &amp;lt;/guided-if[-not]-facet-value-ghost&amp;gt;   &lt;/p>  &lt;/td>
<td colname="col2"> <p>Ändert die Anzeige des Facettenwerts, wenn es sich um einen Ghost-Wert handelt. Wenn ein Facettenwert ein Ghost-Wert ist, wird er normalerweise in kursiver Form angezeigt, um anzugeben, dass der Wert fehlt oder "gehostet"ist. </p> <p>Der folgende Codeausschnitt ist ein Beispiel für einen Facettenblock: </p> <p> <code class="syntax html"> &lt;guided-facet-values&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-if-facet-value-selected&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;b&gt;&lt;guided-facet-value&nbsp;/&gt;&nbsp;(&lt;guided-facet-count&nbsp;/&gt;)&lt;/b&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-else-facet-value-selected&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-if-facet-value-ghost&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;i&gt;&lt;guided-facet-value&nbsp;/&gt;&nbsp;(0)&lt;/i&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-else-facet-value-ghost&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-facet-link&nbsp;class="link"&gt;&lt;guided-facet-value&nbsp;/&gt;&lt;/guided-facet-link&gt;&nbsp;(&lt;guided-facet-count&nbsp;/&gt;) 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/guided-if-facet-value-ghost&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&lt;/guided-if-facet-value-selected&gt; 
      &lt;/guided-facet-values&gt; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>15 </p> </td> 
   <td colname="col1"> <p> 
     <!--Updated to match search-eng version 1/31/13--> <span class="codeph"> &lt;guided-facet-undo-link gsname=" <span class="varname"> facetname </span>"&gt;&lt;/guided-facet-undo-link&gt; </span> </p> </td> 
   <td colname="col2"> <p>Zeigt einen Link zum Rückgängigmachen für eine bestimmte Facette an. Wenn mehrere ausgewählte Facetten vorhanden sind, hebt dieser Link die Auswahl aller Werte der jeweiligen Facette auf. Geben Sie dem Facetten einen Namen. Wenn die Facette derzeit nicht ausgewählt ist, ist der Link der aktuelle Pfad. </p> <p>Im Folgenden finden Sie ein Beispiel für die Verwendung dieses Tags: </p> <p> <code class="syntax html"> &lt;guided-if-facet-selected&nbsp;gsname="category"&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-facet-undo-link&nbsp;gsname="category"&gt;Undo&nbsp;Category&lt;/guided-facet-undo-link&gt; 
      &lt;/guided-if-facet-selected&gt; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>16 </p> </td> 
   <td colname="col1"> <p> <code> &lt;guided-if-facet-long [gsname="facetname"]&gt; 
      &lt;guided-else-facet-long&gt;&lt;/guided-if-facet-long&gt; </code> </p> </td> 
   <td colname="col2"> <p>Dieses bedingte Tag ist "true", wenn die Anzahl der Facettenwerte über dem in der Konfiguration definierten Längenschwellenwert liegt. Verwenden Sie sie, um eine Facette als anderes Benutzeroberflächenelement anzuzeigen (z. B. eine abgeschnittene Liste oder ein Bildlauffeld), wenn die Liste zu lang ist. </p> <p> <code class="syntax html"> &lt;guided-facet&nbsp;gsname="category"&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-if-facet-long&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;div&nbsp;class="long_facet"&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-facet-values&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-facet-link&gt;&lt;guided-facet-value/&gt;&lt;/guided-facet-link&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/guided-facet-values&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/div&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-else-facet-long&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;div&nbsp;class="facet"&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-facet-values&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-facet-link&gt;&lt;guided-facet-value/&gt;&lt;/guided-facet-link&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/guided-facet-values&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/div&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/guided-if-facet-long&gt; 
      &nbsp;&lt;/guided-facet&gt; </code> </p> <p>Sie können diese Bedingung auch außerhalb des Kontexts eines Blocks mit dem Namen <span class="codeph"> guided-facet </span> verwenden, indem Sie direkt auf eine bestimmte Facette verweisen, indem Sie das <span class="codeph"> <span class="varname"> gsname </span> </span>-Attribut verwenden. </p> <p> <code class="syntax html"> &lt;guided-if-facet-long&nbsp;gsname="category"&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;The&nbsp;category&nbsp;facet&nbsp;is&nbsp;very&nbsp;long! 
      &lt;/guided-if-facet-long&gt; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>17 </p> </td> 
   <td colname="col1"> <p> <code> &lt;guided-if-facet-selected [gsname="facetname"]&gt; 
      &lt;guided-else-facet-selected&gt;&lt;/guided-if-facet-selected&gt; </code> </p> </td> 
   <td colname="col2"> <p>Dieses bedingte Tag ist "true", wenn auf die Facette mindestens einmal geklickt wird und derzeit ein Facettenwert ausgewählt ist. Sie kann zum Anzeigen oder Ausblenden von HTML- oder gs-Tags verwendet werden, je nachdem, ob auf eine Facette geklickt wird. </p> <p> <code class="syntax html"> &lt;guided-facet&nbsp;gsname="category"&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-if-facet-selected&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;This&nbsp;facet&nbsp;has&nbsp;been&nbsp;selected.&nbsp;&nbsp;You&nbsp;can&nbsp;no&nbsp;longer&nbsp;refine&nbsp;it. 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-else-facet-selected&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-facet-values&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-facet-link&gt;&lt;guided-facet-value/&gt;&lt;/guided-facet-link&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/guided-facet-values&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/guided-if-facet-selected&gt; 
      &lt;/guided-facet&gt; </code> </p> <p>Sie können diese Bedingung auch außerhalb des Kontexts eines Blocks mit dem Namen <span class="codeph"> guided-facet </span> verwenden, indem Sie direkt über das Attribut <span class="codeph"> gsname </span> auf eine bestimmte Facette verweisen. </p> <p> <code class="syntax html"> &lt;guided-if-facet-selected&nbsp;gsname="category"&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;The&nbsp;category&nbsp;facet&nbsp;is&nbsp;selected! 
      &lt;/guided-if-facet-selected&gt; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>18 </p> </td> 
   <td colname="col1"> <p> <code> &lt;guided-if-facet-single [gsname="facetname"]&gt; 
      &lt;guided-else-facet-single&gt;&lt;/guided-if-facet-single&gt; </code> </p> </td> 
   <td colname="col2"> <p>Dieses bedingte Tag ist "true", wenn nur ein Facet-Wert vorhanden ist. Sie kann verwendet werden, um die Darstellung der Facette zu ändern, wenn sie nicht in der Lage ist, die Ergebnisse zu verfeinern. </p> <p> <code class="syntax html"> &lt;guided-facet&nbsp;gsname="category"&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-if-facet-single&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Facet&nbsp;is&nbsp;not&nbsp;refinable. 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-else-facet-single&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-facet-values&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-facet-link&gt;&lt;guided-facet-value/&gt;&lt;/guided-facet-link&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/guided-facet-values&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/guided-if-facet-single&gt; 
      &lt;/guided-facet&gt; </code> </p> <p>Sie können diese Bedingung auch außerhalb des Kontexts eines Blocks mit dem Namen <span class="codeph"> guided-facet </span> verwenden, indem Sie direkt auf eine bestimmte Facette verweisen, indem Sie das <span class="codeph"> <span class="varname"> gsname </span> </span>-Attribut verwenden. </p> <p> <code class="syntax html"> &lt;guided-if-facet-single&nbsp;gsname="category"&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;There&nbsp;is&nbsp;only&nbsp;one&nbsp;value&nbsp;in&nbsp;the&nbsp;category&nbsp;facet! 
      &lt;/guided-if-facet-single&gt; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>19 </p> </td> 
   <td colname="col1"> <p> <code> &lt;guided-if-facet-has-values [gsname="facetname"]&gt; 
      &lt;guided-else-facet-has-values&gt;&lt;/guided-if-facet-has-values&gt; </code> </p> </td> 
   <td colname="col2"> <p>Mit dieser Bedingung können Sie überprüfen, ob die angegebene Facette überhaupt Werte enthält. Sie können ihn verwenden, um anstelle einer leeren Facette eine andere Facette anzuzeigen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>20 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-facet-total-count gsname=" <span class="varname"> facetname </span>" /&gt; </span> </p> </td> 
   <td colname="col2"> <p>Gibt die Gesamtanzahl der Ergebnisse aus, die innerhalb der angegebenen Facette liegen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>21 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-facet-value gsname=" <span class="varname"> associated custom facet value </span>"&gt; </span> </p> </td> 
   <td colname="col2"> <p>Gibt die Zeichenfolge eines Werts aus, der der Facette zugeordnet ist. Einer Facette können 0 oder mehr Felder zugeordnet sein. Verknüpfte Felder sind selten vorhanden. Zur Unterstützung dieser Felder konfigurieren Sie die Transportvorlage. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>22 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-if-facet-value gsname=" <span class="varname"> associated custom facet value </span>" /&gt;&lt;guided-else-facet-value&gt;&lt;/guided-if-facet-value&gt; </span> </p> </td> 
   <td colname="col2"> <p>Prüft, ob der Facet-Wert einen zugewiesenen Feldwert hat. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>23 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-facet-link&gt; value  </span>"]+&gt;&lt;/guided-facet-link&gt; </span><span class="varname"> </span></p> </td> 
   <td colname="col2"> <p>Erstellt einen Link um die Facet-Wertzeichenfolge, auf den der Kunde klicken kann. Der Pfad wird automatisch generiert, um die Ergebnisse um den aktuellen Facettenwert einzugrenzen. Es unterstützt die direkte Übergabe jedes Attributs an das Anker-Tag. </p> <p> <code class="syntax html"> &lt;guided-facet-values&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-facet-link&nbsp;class="facetlink"&gt;&lt;guided-facet-value/&gt;&lt;/guided-facet-link&gt; 
      &lt;/guided-facet-values&gt; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>24 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-facet-value-path&gt; </span> </p> </td> 
   <td colname="col2"> <p>Erstellt einen eigenen Link zu einem Facettenwert. </p> <p> <code class="syntax html"> &lt;guided-facet-values&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-lt/&gt;a&nbsp;href="&lt;guided-facet-value-path/&gt;"&lt;guided-gt/&gt;&lt;guided-facet-value/&gt;&lt;/a&gt; 
      &lt;/guided-facet-values&gt; </code> </p> <p>Standardmäßig ist der Wert mit einem Escape-Zeichen versehen. Sie können jedoch eine weitere Kodierungsebene hinzufügen, indem Sie angeben, welcher Escape-Modus Sie mithilfe des Escape-Parameters verwenden möchten. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>25 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-facet-value-children&gt;&lt;/guided-facet-value-children&gt; </span> </p> </td> 
   <td colname="col2"> <p>Während <span class="codeph"> &lt;guided-facet-values&gt; </span> durch jeden Facettenwert iteriert wird, durchläuft dieses Tag alle untergeordneten Werte einer verschachtelten Facette. Verwenden Sie in diesem Tag die typischen facettierten Tags, um Links zu erstellen, Links rückgängig zu machen und Facettenwerte anzuzeigen. Dieses Tag muss sich innerhalb von <span class="codeph"> &lt;guided-facet-values&gt; </span> befinden, da es verschachtelte Schleifen ausführt. </p> <p>Ein Beispiel für die Verwendung dieses Tags ist Folgendes: </p> <p> <code class="syntax html"> &lt;guided-facet-values&gt; 
      &nbsp;&nbsp;&lt;guided-facet-link&nbsp;title='&lt;guided-facet-value&nbsp;/&gt;'&gt;&lt;guided-facet-value&nbsp;/&gt;&nbsp;(&lt;guided-facet-count&nbsp;/&gt;)&lt;/guided-facet-link&gt; 
      &nbsp;&nbsp;&lt;guided-if-facet-value-has-children&gt; 
      &nbsp;&nbsp;&nbsp;&lt;guided-facet-value-children&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-facet-link&nbsp;title='&lt;guided-facet-value&nbsp;/&gt;'&gt;&lt;guided-facet-value&nbsp;/&gt;&nbsp;(&lt;guided-facet-count&nbsp;/&gt;)&lt;/guided-facet-link&gt; 
      &nbsp;&nbsp;&nbsp;&lt;/guided-facet-value-children&gt; 
      &nbsp;&nbsp;&lt;/guided-if-facet-value-has-children&gt; 
      &lt;/guided-facet-values&gt; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>26 </p> </td> 
   <td colname="col1"> <p> <code> &lt;guided-if-facet-value-has-children&gt; 
      &lt;guided-else-facet- 
      value-has-children&gt; 
      &lt;/guided-if-facet-value-has-children&gt; </code> </p> </td> 
   <td colname="col2"> <p>Prüft, ob der aktuelle Facet-Wert untergeordnete Werte hat. Es wird empfohlen, die Tags <span class="codeph"> &lt;guided-facet-value-Children&gt; </span> zu verwenden. Die "else"-Klausel ist optional. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>27 </p> </td> 
   <td colname="col1"> <p> 

    &amp;lt;guided-else[-not]-facet-value-over-length-Schwellenwert&amp;gt;
    
    &amp;lt;/guided-if[-not]-facet-value-over-length-Schwellenwert&amp;gt;   &lt;/p>  &lt;/td>
<td colname="col2"> <p>Bestimmt, ob der aktuelle Facet-Wert in der Facettenwertschleife über dem Längenschwellenwert liegt. Normalerweise wird er verwendet, um Werte unterhalb des Schwellenwerts auf einer langen Facette anzuzeigen (es sei denn, der Benutzer hat zuvor einen Link "Mehr anzeigen"unter der Facette ausgewählt). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>28 </p> </td> 
   <td colname="col1"> <p> 

    &amp;lt;guided-else[-not]-facet-value-equals-length-Schwellenwert&amp;gt;
    
    &amp;lt;/guided-if[-not]-facet-value-equals-length-Schwellenwert&amp;gt;   &lt;/p>  &lt;/td>
<td colname="col2"> <p>Stellt fest, ob der aktuelle Facettenwert in der Facettenwertschleife dem Längenschwellenwert entspricht. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>29 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-facet-value-undo-link&gt;&lt;/guided-facet-value-undo-link&gt; </span> </p> </td> 
   <td colname="col2"> <p>Zeigt einen Link zum Rückgängigmachen für eine bestimmte Facette an. Verwenden Sie ihn, um einen Link zum Rückgängigmachen neben einem ausgewählten Facettenwert anzuzeigen. Da dieser Link zum Rückgängigmachen nur diesen ausgewählten Wert rückgängig macht, unterscheidet er sich von <span class="codeph"> &lt;guided-facet-undo-link&gt; </span>, wodurch die Auswahl aller ausgewählten Werte aufgehoben wird. </p> <p> <p>Hinweis:  Wenn die Facette nicht über ein Mehrfachauswahlverhalten verfügt, haben die beiden Rückgängig-Links dasselbe Verhalten. Das heißt, die Facette kann nur einen ausgewählten Wert haben. </p> </p> <p>Wenn die Facette derzeit nicht ausgewählt ist, ist der Link der aktuelle Pfad. Verwenden Sie dieses Tag nur in einer <span class="codeph"> guided-facet-values </span>-Schleife. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>30 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-facet-value-undo-path /&gt; </span> </p> </td> 
   <td colname="col2"> <p>Erstellen Sie einen eigenen Link zum Rückgängigmachen des Facet-Werts. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>31 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-facet-undo-path gsname=" <span class="varname"> facetname </span>" /&gt; </span> </p> </td> 
   <td colname="col2"> <p>Erstellen Sie einen eigenen Facettenrückgängig-Link. </p> <p> Ähnlich wie das <span class="codeph"> &lt;guided-facet-undo-link&gt; </span>-Tag, außer dass es Ihnen den Rohpfad zum Erstellen Ihres eigenen Rückgängig-Links gibt. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>32 </p> </td> 
   <td colname="col1"> <p> <code> &lt;guided-if-facet-value-matches facetname="facetname" value="value"&gt;&lt;guided-else-facet-value-matches&gt; 
      &lt;/guided-if-facet-value-matches&gt; </code> </p> </td> 
   <td colname="col2"> <p>HTML wird bedingt angezeigt, wenn die angegebene Facette den ausgewählten oder einen einzelnen Wert "value"hat. Dieser Tag-Satz wird häufig verwendet, um eine Facette anzuzeigen, die auf dem in einer anderen Facette ausgewählten Wert basiert. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>33 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-facet-behavior gsname=" <span class="varname"> facetname </span>" /&gt; </span> </p> </td> 
   <td colname="col2"> <p>Legen Sie das Verhalten einer Facette fest, z. B. normal, sticky oder multi-select. Es ist nützlich für Kunden, die XML-Ergebnisse erhalten und die die Darstellung der Facette je nach Verhalten dynamisch ändern möchten. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>34 </p> </td> 
   <td colname="col1"> <p> 

    &amp;lt;/guided-if-facet[-not]-visible&amp;gt;   &lt;/p>  &lt;/td>
<td colname="col2"> <p>Der Inhalt, den dieses Tag umschließt, wird je nach Sichtbarkeitsstatus der Facette ausgeblendet oder offen gelegt. Wenn eine Geschäftsregel die Facette direkt ausblendet oder einblendet, wird jeder Inhalt innerhalb der Facette ausgeblendet oder eingeblendet. Es ist nicht erforderlich, dass diese Tags die Facette umschließen. </p> <p> Normalerweise wird dieser Tag verwendet, um den Anzeigenamen auszublenden, wenn der Name außerhalb der Facette liegt. Wenn Sie dieses Tag um den Anzeigenamen verschieben, wird der Name ausgeblendet, wenn die Facette ausgeblendet wird. </p> <p>Dieses Tag ersetzt die Zone und hat viele der gleichen Leistungsvorteile wie die Verwendung von Zonen. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Breadcrumb {#section_9B39B71FA6EC49FA8D88AD8A3BA987F7}

Siehe [Info zu Breadcrumbs](../c-about-design-menu/c-about-breadcrumbs.md#concept_FB8A943C594A4A1593B118141DA61F03).

<table> 
 <thead> 
  <tr> 
   <th colname="col01" class="entry"> </th> 
   <th colname="col1" class="entry"> <p>Tag </p> </th> 
   <th colname="col2" class="entry"> <p>Beschreibung </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col01"> <p>3 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-breadcrumb&gt; breadcrumbname  </span>"]&gt;&lt;/guided-breadcrumb&gt; </span><span class="varname"> </span></p> </td> 
   <td colname="col2"> <p>Das Schleife-Tag für den Breadcrumb. Alle zwischen öffnenden und schließenden Tags liegenden Inhalte werden für jede Abfrage des aktuellen Status iteriert. </p> <p>Wenn <span class="codeph"> <span class="varname"> gsname </span> </span> weggelassen wird, wird die Breadcrumb namens "default"verwendet. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>2 </p> </td> 
   <td colname="col1"> <p> 
     <!--Matched search-eng version, 2/1/2013--> <span class="codeph"> &lt;guided-breadcrumb-link&gt;&lt;/guided-breadcrumb-link&gt; </span> </p> </td> 
   <td colname="col2"> <p>Erstellt einen Link im Breadcrumb. Das Standardverhalten ist "goto". Wenn sich der Link anders verhält, verwenden Sie das optionale Attribut <span class="codeph"> <span class="varname"> gsname </span> </span>, um "remove"oder "drop"anzugeben. Alle im Tag enthaltenen Attribute werden an das resultierende Anker-Tag weitergeleitet. </p> <p> <code class="syntax html"> &lt;guided-breadcrumb&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-breadcrumb-link&nbsp;gsname="remove"&nbsp;class="bc_link"&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-breadcrumb-value/&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/guided-breadcrumb-link&gt; 
      &lt;/guided-breadcrumb&gt; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>3 </p> </td> 
   <td colname="col1"> <p> 
     <!--Updated to search-eng version, 2/1/2013--> <span class="codeph"> &lt;guided-breadcrumb-value /&gt; </span> </p> </td> 
   <td colname="col2"> <p>Der Wert-Tag gibt den transformierten Wert der aktuellen Breadcrumb-Iteration aus. Sie wird nur im Kontext eines <span class="codeph"> guided-breadcrumb </span>-Blocks verwendet. </p> <p> <code class="syntax html"> &lt;guided-breadcrumb&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-breadcrumb-link&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-breadcrumb-value/&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/guided-breadcrumb-link&gt; 
      &lt;/guided-breadcrumb&gt; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>4 </p> </td> 
   <td colname="col1"> <p> 
     <!--Updated to search-eng version, 2/1/2013--> <span class="codeph"> &lt;guided-breadcrumb-label /&gt; </span> </p> </td> 
   <td colname="col2"> <p>Das label-Tag gibt eine Beschriftung für einen Breadcrumb-Wert aus, in der angegeben wird, welche Facette ausgewählt wurde, um dieses Breadcrumb-Element zu generieren. Sie wird nur im Kontext eines <span class="codeph"> guided-breadcrumb </span>-Blocks verwendet. </p> <p> <code class="syntax html"> &lt;guided-breadcrumb&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-breadcrumb-link&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-breadcrumb-label/&gt;:&nbsp;&lt;guided-breadcrumb-value/&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/guided-breadcrumb-link&gt; 
      &lt;/guided-breadcrumb&gt; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>5 </p> </td> 
   <td colname="col1"> <p> 
     <!--Updated to search-eng version, 2/1/2013--> <code> &lt;guided-if-breadcrumb-label&gt; 
      &lt;guided-else- 
      breadcrumb-label&gt; 
      &lt;guided-if-breadcrumb-label /&gt; </code> </p> </td> 
   <td colname="col2"> <p>Mit diesem bedingten Tag wird Inhalt bedingt angezeigt, wenn der aktuelle Breadcrumb-Wert eine Beschriftung enthält. Es wird verwendet, um nur Beschriftungen und damit zusammenhängenden Inhalt anzuzeigen, wenn ein Etikett tatsächlich existiert. Sie wird nur im Kontext eines <span class="codeph"> guided-breadcrumb </span>-Blocks verwendet. </p> <p> <code class="syntax html"> &lt;guided-breadcrumb&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-breadcrumb-link&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-if-breadcrumb-label&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-breadcrumb-label/&gt;: 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/guided-if-breadcrumb-label&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-breadcrumb-value/&gt;&lt;/guided-breadcrumb-link&gt; 
      &lt;/guided-breadcrumb&gt; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>6 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-breadcrumb-path&gt; </span> </p> </td> 
   <td colname="col2"> <p>Wird zum Erstellen eines eigenen Breadcrumb-Links verwendet. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Menüs {#section_1D489ADF041F4351A66E5D5742125CA8}

Siehe [Menüs](../c-about-design-menu/c-about-menus.md#concept_68123CE5CF4447B59217B5D721424E32).

<table> 
 <thead> 
  <tr> 
   <th colname="col01" class="entry"> </th> 
   <th colname="col1" class="entry"> <p>Tag </p> </th> 
   <th colname="col2" class="entry"> <p>Beschreibung </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col01"> <p>3 </p> </td> 
   <td colname="col1"> <p> 
     <!--Matched search-eng version, 2/1/2013--> <span class="codeph"> &lt;guided-menu gsname="menuname"&gt;&lt;/guided-menu&gt; </span> </p> </td> 
   <td colname="col2"> <p>Dies ist das Menü-Wert-Schleifeniterator-Tag. Verwenden Sie das Attribut <span class="codeph"> gsname </span>, um herauszufinden, welcher Satz von Menüelementen angezeigt wird. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>2 </p> </td> 
   <td colname="col1"> <p> 
     <!--Matched search-eng version, 2/1/2013--> <span class="codeph"> &lt;guided-menu-item-link&gt;&lt;/guided-menu-item-link&gt; </span> </p> </td> 
   <td colname="col2"> <p>Gibt Ihnen die URL zum Verfeinern der aktuellen Suche nach dem Menüelement. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>1 </p> </td> 
   <td colname="col1"> <p> 
     <!--Matched search-eng version, 2/1/2013--> <span class="codeph"> &lt;guided-menu-item-option&gt; </span> </p> </td> 
   <td colname="col2"> <p>Normalerweise wird ein Menü in einem Auswahlsteuerelement auf einer Vorlage angezeigt. Dieses Tag erleichtert die Erstellung des Select-Steuerelements, da es den HTML-Code zur Generierung der Option für das select-Steuerelement generiert. </p> <p>Beispielsweise der folgende Codeblock: </p> <p> <code class="syntax html"> &lt;select&nbsp;name="sort"&nbsp;onchange="gcGo(this);"&gt; 
      &lt;guided-menu&nbsp;gsname="sort"&gt; 
      &lt;guided-menu-item-option/&gt; 
      &lt;/guided-menu&gt; 
      &lt;/select&gt; </code> </p> <p>Kann HTML wie folgt generieren: </p> <p> <code class="syntax html"> &lt;select&nbsp;name="sort"&nbsp;onchange="gcGo(this);"&gt; 
      &nbsp;&nbsp;&lt;option&nbsp;value="?sort=relevance;sp_sfvl_field=product-type|category|size;"&nbsp;selected="selected"&gt;Sort&nbsp;by&nbsp;Relevance&lt;/option&gt; 
      &nbsp;&nbsp;&lt;option&nbsp;value="?sort=avail-code;sp_sfvl_field=product-type|category|size;"&gt;Sort&nbsp;by&nbsp;Availability&lt;/option&gt; 
      &nbsp;&nbsp;&lt;option&nbsp;value="?sort=price;sp_sfvl_field=product-type|category|size;"&gt;Sort&nbsp;by&nbsp;Price&lt;/option&gt; 
      &lt;/select&gt; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>4 </p> </td> 
   <td colname="col1"> <p> 
     <!--Matched search-eng version, 2/1/2013--> <span class="codeph"> &lt;guided-menu-item-value /&gt; </span> </p> </td> 
   <td colname="col2"> <p>Gibt die Zeichenfolge des mit dem Menü verknüpften Werts zurück. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>5 </p> </td> 
   <td colname="col1"> <p> 
     <!--Matched search-eng version, 2/1/2013--> <span class="codeph"> &lt;guided-menu-item-label /&gt; </span> </p> </td> 
   <td colname="col2"> <p>Gibt die Zeichenfolge der mit dem Menü verknüpften Beschriftung zurück. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>6 </p> </td> 
   <td colname="col1"> <p> 
     <!--Matched search-eng version, 2/1/2013--> <span class="codeph"> &lt;guided-menu-item-path /&gt; </span> </p> </td> 
   <td colname="col2"> <p>Gibt die Pfadzeichenfolge zurück. Verwenden Sie das Tag, wenn Sie dem Pfad einen Parameter hinzufügen und einen benutzerspezifischen Link erstellen möchten. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>7 </p> </td> 
   <td colname="col1"> <p> 
     <!--Updated to match search-eng version, 2/1/2013--> <code> &lt;guided-if-menu-item-selected&gt; 
      &lt;guided-else-menu- 
      item-selected&gt; 
      &lt;/guided-if-menu-item-selected&gt; </code> </p> </td> 
   <td colname="col2"> <p>Gibt eine 1 oder 0 zurück, die angibt, ob das aktuelle Menüelement ausgewählt ist. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Pagenav {#section_2EE397635C514BBC8D668278EA314F35}

Die Seitennavigations-Tags können verwendet werden, um eine Reihe von Links zu erstellen, die es einem Benutzer ermöglichen, die Suchergebnisse zu durchblättern.

<table> 
 <thead> 
  <tr> 
   <th colname="col01" class="entry"> </th> 
   <th colname="col1" class="entry"> <p>Tag </p> </th> 
   <th colname="col2" class="entry"> <p>Beschreibung </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col01"> <p>1 </p> </td> 
   <td colname="col1"> <p> 
     <!--Matched search-eng version, 2/1/2013--> <span class="codeph"> &lt;guided-pages&gt;&lt;/guided-pages&gt; </span> </p> </td> 
   <td colname="col2"> <p>Das loop-Tag für die Seitennavigation. Jeder Inhalt zwischen den öffnenden und schließenden Tags wird für jede Seite iteriert. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>2 </p> </td> 
   <td colname="col1"> <p> 
     <!--Matched search-eng version, 2/1/2013--> <span class="codeph"> &lt;guided-page-link&gt;&lt;/guided-page-link&gt; </span> </p> </td> 
   <td colname="col2"> <p>Erstellt einen Link in der Seitennavigation. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>3 </p> </td> 
   <td colname="col1"> <p> 
     <!--Matched search-eng version, 2/1/2013--> <span class="codeph"> &lt;guided-page-link gsname="first|prev|next|last|viewall|viewpages"&gt;&lt;/guided-page-link&gt; </span> </p> </td> 
   <td colname="col2"> <p>Erstellt einen Link zur ersten, vorherigen, nächsten oder letzten Seite. Sie können auch einen Link zur Ansicht aller Seiten auf einer Seite erstellen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>4 </p> </td> 
   <td colname="col1"> <p> 
     <!--Matched search-eng version, 2/1/2013--> <span class="codeph"> &lt;guided-page-number /&gt; </span> </p> </td> 
   <td colname="col2"> <p> Gibt eine Zeichenfolge mit der aktuellen Seitenzahl zurück. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>5 </p> </td> 
   <td colname="col1"> <p> 
     <!--Updated to match search-eng version, 2/1/2013--> <code> &lt;guided-if-page-selected&gt; 
      &lt;guided-else-page- 
      selected&gt; 
      &lt;/guided-if-page-selected&gt; </code> </p> </td> 
   <td colname="col2"> <p>Dieser Satz von bedingten Tags ist "true", wenn die Seite, die derzeit durchlaufen wird, ausgewählt ist. Normalerweise wird die Seitenzahl im Seitennavigationssteuerelement unterschiedlich angezeigt. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>6 </p> </td> 
   <td colname="col1"> <p> 
     <!--Updated to match search-eng version, 2/1/2013--> <code> &lt;guided-if[-not]-page-prev&gt; 
      &lt;guided-else-page- 
      prev&gt; 
      &lt;/guided-if[-not]-page-prev&gt; </code> </p> </td> 
   <td colname="col2"> <p> Dieser Satz von bedingten Tags ist wahr, wenn die aktuelle Seite eine vorherige Seite hat. Es wird normalerweise dazu verwendet, einen vorherigen Link in der Seitennavigation anzuzeigen, wenn dies sinnvoll ist. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>7 </p> </td> 
   <td colname="col1"> <p> 
     <!--Updated to match search-eng version, 2/1/2013--> <code> &lt;guided-if[-not]-page-next&gt; 
      &lt;guided-else-page- 
      next&gt; 
      &lt;/guided-if[-not]-page-next&gt; </code> </p> </td> 
   <td colname="col2"> <p> Dieser Satz von bedingten Tags ist wahr, wenn die aktuelle Seite eine nächste Seite hat. Es wird normalerweise dazu verwendet, einen vorherigen Link in der Seitennavigation anzuzeigen, wenn dies sinnvoll ist. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>8 </p> </td> 
   <td colname="col1"> <p> 
     <!--Updated to match search-eng version, 2/1/2013--> <code> &lt;guided-if[-not]-page-viewall&gt; 
      &lt;guided-else-page- 
      viewall&gt; 
      &lt;/guided-if[-not]-page-viewall&gt; </code> </p> </td> 
   <td colname="col2"> <p> Wenn eine Suche eine große Ergebnismenge zurückgibt, möchten Sie möglicherweise nicht die Möglichkeit zur Ansicht aller Ergebnisse Angebot haben. Daher können Sie diesen Satz bedingter Tags verwenden, um zu bestimmen, wann der Link "Ansicht - Alle"angezeigt werden soll. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>9 </p> </td> 
   <td colname="col1"> <p> 
     <!--Updated to match search-eng version, 2/1/2013--> <code> &lt;guided-if[-not]-page-viewpages&gt; 
      &lt;guided-else-page- 
      viewpages&gt; 
      &lt;/guided-if[-not]-page-viewpages&gt; </code> </p> </td> 
   <td colname="col2"> <p>Mit diesem Satz bedingter Tags können Sie festlegen, wann der Link "Ansichten-Seiten"angezeigt werden soll. Es wird normalerweise verwendet, um einem Kunden die Ansicht bestimmter Seiten zu ermöglichen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>10 </p> </td> 
   <td colname="col1"> <p> 
     <!--Updated to match search-eng version, 2/1/2013--> 

    &amp;lt;guided-else-page-link&amp;gt;
    &amp;lt;/guided-if[-not]-page-link&amp;gt;   &lt;/p>  &lt;/td>
<td colname="col2"> <p>Prüft, ob die Seitennavigation eine erste Seite, eine vorherige Seite, eine nächste Seite usw. hat. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>11 </p> </td> 
   <td colname="col1"> <p> 
     <!--Matched search-eng version, 2/1/2013--> <span class="codeph"> &lt;guided-page-total /&gt; </span> </p> </td> 
   <td colname="col2"> <p> Gibt eine Zeichenfolge mit der Gesamtanzahl der Seiten der Suchergebnisse zurück. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>12 </p> </td> 
   <td colname="col1"> <p> <code> &lt;guided-pagination gsname= 
      "pagination_name"&gt;&lt;/guided-pagination&gt; </code> </p> </td> 
   <td colname="col2"> <p>Verwenden Sie das Tag <span class="codeph"> für geführte Paginierung </span>, um einen Bereich zu definieren, in dem alle Paginierungs-Tags mit einer bestimmten Paginierungseinstellung in Verbindung stehen, falls Sie nur wenige Seitennavigationseinstellungen definiert haben. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>13 </p> </td> 
   <td colname="col1"> <p> 

    next|last|viewall|viewpages]/&amp;gt;   &lt;/p>  &lt;/td>
<td colname="col2"> <p>Erstellt einen eigenen Link in der Seitennavigation. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>14 </p> </td> 
   <td colname="col1"> <p> <code> &lt;guided-if-page-high-eq-last&gt; 
      &lt;guided-else-page- 
      high-eq-last&gt; 
      &lt;/guided-if-page-high-eq-last&gt; </code> </p> </td> 
   <td colname="col2"> <p>Prüft, ob die höchste Seite in der Seitennavigation der Gesamtanzahl der Seiten entspricht. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>15 </p> </td> 
   <td colname="col1"> <p> <code> &lt;guided-if-page-low-eq-first&gt; 
      &lt;guided-else-page-low-eq-first&gt; &lt;/guided-if-page-low-eq-first&gt; </code> </p> </td> 
   <td colname="col2"> <p>Prüft, ob die niedrigste Seite in der Seitennavigation mit der niedrigsten Seite identisch ist. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>16 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-if-page-is-multipage&gt; &lt;guided-else-page-is-multipage&gt; &lt;/guided-if-page-is-multipage&gt; </span> </p> </td> 
   <td colname="col2"> <p>Prüft, ob eine einzelne Ergebnisseite oder mehrere Ergebnisseiten vorhanden sind. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Kürzliche Suchvorgänge {#section_8CD907521F584257B475595B01A5964B}

Sie können die Tags der letzten Suchen verwenden, um eine Reihe von Links zu erstellen, über die ein Benutzer schnell eine vorherige Suche ausführen kann, wie im folgenden Beispiel:

```
<guided-if-recent-searches> 
    <span>Recent Searches</span><br/> 
    <guided-recent-searches> 
        <guided-recent-searches-link><guided-recent-searches-value></guided-recent-searches-link><br/> 
    </guided-recent-searches> 
    <guided-recent-searches-clear-link>Clear Recent Searches</guided-recent-searches-clear-link> 
</guided-if-recent-searches>
```

Siehe [Konfigurieren aktueller Suchvorgänge](../c-about-design-menu/t-configuring-recent-searches.md#task_E9E8ACA04C90484F8AFD5262167B2562).

<table> 
 <thead> 
  <tr> 
   <th colname="col01" class="entry"> </th> 
   <th colname="col1" class="entry"> <p>Tag </p> </th> 
   <th colname="col2" class="entry"> <p>Beschreibung </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col01"> <p>1 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-recent-searches&gt;&lt;/guided-recent-searches&gt; </span> </p> </td> 
   <td colname="col2"> <p>Das loop-Tag für die letzten Suchen. Jeder Inhalt zwischen den öffnenden und schließenden Tags wird für jede Seite iteriert. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>2 </p> </td> 
   <td colname="col1"> <p> <code> &lt;guided-recent-searches-link [attr="value"]+&gt; 
      &lt;/guided-recent-searches-link&gt; </code> </p> </td> 
   <td colname="col2"> <p>Ermöglicht den Aufbau eines Links zu einer kürzlich durchgeführten Suche. Es unterstützt die Übergabe von HTML-Attributen direkt an das Anker-Tag. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>3 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-recent-searches-path /&gt; </span> </p> </td> 
   <td colname="col2"> <p>Ermöglicht Ihnen das Abrufen des relativen URL-Pfads für eine kürzlich durchgeführte Suche in einer <span class="codeph"> geführten/kürzlich durchgeführten Suche </span>-Schleife. Normalerweise würden Sie <span class="codeph"> guided-previous-search-link </span> verwenden. Wenn Sie jedoch einen eigenen Link erstellen möchten, können Sie dieses Tag verwenden. Hier ein Beispiel: </p> <p> <code class="syntax html"> &lt;guided-lt/&gt;a&amp;nbsp;href="&lt;guided_recent_searches_path&gt;"&gt;&lt;guided-recent-searches-value&gt;&lt;/a&gt; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>4 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-recent-searches-value&gt; </span> </p> </td> 
   <td colname="col2"> <p>Ermöglicht die Erfassung des Begriffs "Abfrage", der mit einer kürzlich durchgeführten Suche verknüpft ist. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>5 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-recent-searches-clear-link&gt;&lt;/guided-recent-searches-clear-link&gt; </span> </p> </td> 
   <td colname="col2"> <p>Ermöglicht Ihnen das Angebot Ihrer Kunden, kürzlich gespeicherte Suchen zu löschen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>6 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-recent-searches-clear-path /&gt; </span> </p> </td> 
   <td colname="col2"> <p>Gibt den Pfad zurück, den <span class="codeph"> &lt;guided-previous-searches-clear-link&gt; </span> verwendet, damit Sie einen eigenen Link erstellen können. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>7 </p> </td> 
   <td colname="col1"> <p> 

    &amp;lt;/guided-if-last-searches&amp;gt;   &lt;/p>  &lt;/td>
<td colname="col2"> <p>Ermöglicht die Anzeige der letzten Suchen, wenn ein Kunde eine kürzlich durchgeführte Suche durchgeführt hat. </p> </td> 
  </tr> 
 </tbody> 
</table>

## „Meinten Sie“-{#section_C1EB3B9D8E1242798A6E04609D1E3543}

Mit den Tags &quot;Meinten Sie&quot;können Sie Links zu Vorschlägen erstellen, wenn eine Suche keine Ergebnisse zurückgibt und der Suchbegriff nicht im Kontowörterbuch steht. Im Folgenden finden Sie ein Beispiel für die Verwendung der Tags &quot;Meinten Sie&quot;:

```
<guided-if-suggestions> 
    <span>Did You Mean?</span><br/> 
    <guided-suggestions> 
        <guided-suggestion-link><guided-suggestion/></guided-suggestion-link><br/> 
    </guided-suggestions> 
</guided-if-suggestions>
```

Siehe [Info zu „Meinten Sie“](../c-about-linguistics-menu/c-about-did-you-mean.md#concept_7D4F3C29EF184B538B8AE2ECAE0CDC5E).

<table> 
 <thead> 
  <tr> 
   <th colname="col01" class="entry"> </th> 
   <th colname="col1" class="entry"> <p>Tag </p> </th> 
   <th colname="col2" class="entry"> <p>Beschreibung </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col01"> <p>3 </p> </td> 
   <td colname="col1"> <p> 
     <!--Matches search-eng version, 2/1/2013--> <span class="codeph"> &lt;guided-suggestions&gt;&lt;/guided-suggestions&gt; </span> </p> </td> 
   <td colname="col2"> <p>Dies ist das Schleife-Tag für Schleifen über die Vorschläge. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>2 </p> </td> 
   <td colname="col1"> <p> 
     <!--Matches search-eng version, 2/1/2013--> <span class="codeph"> &lt;guided-suggestion-link&gt;&lt;/guided-suggestion-link&gt; </span> </p> </td> 
   <td colname="col2"> <p>Erstellt einen Link zu der angegebenen Empfehlung. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>1 </p> </td> 
   <td colname="col1"> <p> 
     <!--Newly added from search-eng version, 2/1/2013--> <span class="codeph"> &lt;guided-suggestion-value /&gt; </span> </p> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>4 </p> </td> 
   <td colname="col1"> <p> 
     <!--Updated to match search-eng version, 2/1/2013--> <code> &lt;guided-if[-not]-suggestions&gt;&lt;guided-else[-not]- 
      suggestions&gt;&lt;/guided-if[-not]-suggestions&gt; </code> </p> </td> 
   <td colname="col2"> <p>Ermöglicht den Test, wenn Vorschläge vorhanden sind. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>5 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-suggestion-path /&gt; </span> </p> </td> 
   <td colname="col2"> <p>Gibt die Pfadzeichenfolge für die Empfehlung zurück. Sie können es verwenden, um ein eigenes Anker-Tag zu erstellen. Normalerweise wird <span class="codeph"> guided-recommendations-link </span> stattdessen verwendet. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>6 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-suggestion /&gt; </span> </p> </td> 
   <td colname="col2"> <p>Ein Vorschlag. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>7 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-suggestion-result-count /&gt; </span> </p> </td> 
   <td colname="col2"> <p>Ergebniszählung für die Empfehlung. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>8 </p> </td> 
   <td colname="col1"> <p> <code> &lt;guided-if[-not]-suggestion-autosearch&gt; 
      &lt;guided-else[-not]-suggestion-autosearch&gt; 
      &lt;/guided-if[-not]-suggestion-autosearch&gt; </code> </p> </td> 
   <td colname="col2"> <p>Ermöglicht den Test, ob die automatische Suche nach Vorschlägen für null Ergebnisse durchgeführt wurde, falls diese Funktion aktiviert ist. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>9 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-suggestion-original-query /&gt; </span> </p> </td> 
   <td colname="col2"> <p>Gibt die ursprüngliche Abfrage zurück, wenn die automatische Suche durchgeführt wurde. </p> <p>Verwendungsbeispiel: </p> <p> <code class="syntax html"> &lt;guided-if-suggestion-autosearch&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;Search&nbsp;for&nbsp;&lt;guided-query-param&nbsp;gsname="q"&nbsp;/&gt;&nbsp;instead&nbsp;of&nbsp;&lt;guided-suggestion-original-query&nbsp;/&gt; 
      &lt;/guided-if-suggestion-autosearch&gt; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>10 </p> </td> 
   <td colname="col1"> <p> <code> &lt;guided-if[-not]-suggestion-low-results&gt; 
      &lt;guided-else[-not]-suggestion-low-results&gt; 
      &lt;/guided-if[-not]-suggestion-low-results&gt; </code> </p> </td> 
   <td colname="col2"> <p>Diese Bedingung ist wahr, wenn Vorschläge aufgrund einer niedrigen Ergebniszahl vorliegen, falls diese Funktion aktiviert ist. </p> <p>Das folgende Beispiel zeigt die Verwendung dieses Tags: </p> <p> <code class="syntax html"> &lt;guided-if-suggestion-low-results&gt; 
      &nbsp;&nbsp;&nbsp;You&nbsp;have&nbsp;a&nbsp;low&nbsp;result&nbsp;count&nbsp;for&nbsp;&lt;guided-query-param&nbsp;gsname="q"&nbsp;/&gt;. 
      &nbsp;&nbsp;&nbsp;Did&nbsp;you&nbsp;mean:&nbsp;&lt;guided-suggestions&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-suggestion-link&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-suggestion&nbsp;/&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/guided-suggestion-link&gt;&lt;guided-if-not-last&gt;,&nbsp;&lt;/guided-if-not-last&gt; 
      &nbsp;&nbsp;&nbsp;&lt;/guided-suggestions&gt; 
      &lt;/guided-if-suggestion-low-results&gt; </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Automatische Vervollständigung {#section_897316BEE1454E839A56B565CA4AF018}

Die folgenden Tags können verwendet werden, um dem Suchformular automatisch gefüllt zu werden. Die Tags für den Kopfteil- und Formularinhalt sind erforderlich, damit die Funktion für die automatische Vervollständigung korrekt ausgeführt werden kann. Es wird empfohlen, die Tags anstelle der Hartkodierung der autocomplete JavaScript und CSS in Ihrer Präsentationsvorlage zu verwenden. Der Grund dafür ist, dass Tags es Ihren Vorlagen ermöglichen, alle neuen Cache-IDs für die Niederlage aufzunehmen, sobald Sie die Einstellungen für die automatische Vervollständigung ändern, ohne dass die Vorlage manuell aktualisiert werden muss.

Siehe [Info zum automatischen Ausfüllen](../c-about-auto-complete.md#concept_093A9CD754864BA79B456FE4BEB64578).

<table> 
 <thead> 
  <tr> 
   <th colname="col01" class="entry"> </th> 
   <th colname="col1" class="entry"> <p>Tag </p> </th> 
   <th colname="col2" class="entry"> <p>Beschreibung </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col01"> <p>3 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-if-autocomplete&gt; &lt;guided-else-autocomplete&gt; &lt;/guided-if-autocomplete&gt; </span> </p> </td> 
   <td colname="col2"> <p>Erkennt, ob die Funktion zum automatischen Ausfüllen aktiviert ist. Sie können die Tags verwenden, um optional den Kopf- und Formularinhalt aufzunehmen, der für das automatische Ausfüllen erforderlich ist. Auf diese Weise können Sie die Funktion aktivieren und deaktivieren und müssen Ihre Präsentationsvorlagen nicht ändern. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>2 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-ac-css /&gt; </span> </p> </td> 
   <td colname="col2"> <p>Wird im Kopf der Präsentationsvorlage verwendet und durch das entsprechende CSS-Skript ersetzt, das automatisch ausgefüllt wird. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>3 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-ac-form-content /&gt; </span> </p> </td> 
   <td colname="col2"> <p>Wird im Suchformular (zwischen den Tags <span class="codeph"> &lt;form&gt; </span> und <span class="codeph"> &lt;/form&gt; </span>) der Präsentationsvorlage verwendet, anstatt die automatisch ausgefüllten Tags im Formular fest zu kodieren. Die Tags werden durch den entsprechenden HTML-Code ersetzt, der erforderlich ist, damit die automatische Vervollständigung funktioniert. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>4 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-ac-javascript /&gt; </span> </p> </td> 
   <td colname="col2"> <p>Generiert die Links zum automatischen Vervollständigen-JavaScript. Für eine optimale Leistung wird empfohlen, dieses Tag am unteren Rand der Seite vor dem schließenden "body"-Tag zu platzieren. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Speicher {#section_A33E25DB5E67404A823BD9618665B773}

Verwenden Sie die folgenden Tags, um den Store, in dem sich ein Benutzer befindet, zu testen und anzuzeigen.

<table> 
 <thead> 
  <tr> 
   <th colname="col01" class="entry"> </th> 
   <th colname="col1" class="entry"> <p>Tag </p> </th> 
   <th colname="col2" class="entry"> <p>Beschreibung </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col01"> <p>1 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-store /&gt; </span> </p> </td> 
   <td colname="col2"> <p>Gibt den aktuellen Store aus. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>2 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-if-store-defined&gt; &lt;guided-else-store-defined&gt; &lt;/guided-if-store-defined&gt; </span> </p> </td> 
   <td colname="col2"> <p>Erkennt, ob sich der Benutzer in einem Store befindet. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>1 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-if-store gsname="store"&gt; &lt;guided-else-store&gt; &lt;/guided-if-store&gt; </span> </p> </td> 
   <td colname="col2"> <p>Erkennt, ob sich der Benutzer im Store befindet, den der Parameter <span class="codeph"> gsname </span> angibt. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Zonen {#section_B9B3179E000C42D492E1541F2FE44CB5}

<table> 
 <thead> 
  <tr> 
   <th colname="col01" class="entry"> </th> 
   <th colname="col1" class="entry"> <p>Tag </p> </th> 
   <th colname="col2" class="entry"> <p>Beschreibung </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col01"> <p>1 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-zone gsname="zone area"&gt; </span> </p> </td> 
   <td colname="col2"> <p>Sie können alle Inhalte in die Zonen-Tags einschließen, um eine Zone aus diesem Bereich zu erstellen. Auf diese Weise können Sie Geschäftsregeln verwenden, um die Zone nach Bedarf anzuzeigen. Standardmäßig werden Zonen immer angezeigt. Sie können die optionalen Such- und Facettenparameter verwenden, um anzugeben, welche Suche oder Facette mit der Zone verbunden ist. Mit dieser Funktion kann die Software Suchvorgänge oder Facetten überspringen, wenn eine Zone ausgeblendet wird, was die Suchleistung verbessert. Die Attribute für Höhe und Breite sind optional und werden verwendet, um zu konfigurieren, wie der Platzhalter im Visual Rule Builder angezeigt wird, wenn eine Zone entfernt wird. </p> <p> Verwenden Sie nach Möglichkeit das Tag <span class="codeph"> guided-if-facet[-not]-visible </span> anstelle der Zone. Die Präsentationsvorlage wird vereinfacht. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>2 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-if-zone gsname="zone area"&gt; &lt;guided-else-zone&gt; &lt;/guided-if-zone&gt; </span> </p> </td> 
   <td colname="col2"> <p>Mit diesem Tag-Satz können Sie testen, ob derzeit eine Zone angezeigt wird. Es ist nützlich, wenn Sie Inhalte an einer anderen Stelle auf der Seite haben, die nur angezeigt werden sollen, wenn die Zone angezeigt wird. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Schleifenindikatoren {#section_387322CA0AA843A2ACF2795C328673E9}

Sie können die folgenden Loopindikatoren in einem dieser Loopblöcke verwenden:

* guided-results
* guided-facet-values
* geführten Breadcrumb
* guided-menu-items
* guided-pages

<table> 
 <thead> 
  <tr> 
   <th colname="col01" class="entry"> </th> 
   <th colname="col1" class="entry"> <p>Tag </p> </th> 
   <th colname="col2" class="entry"> <p>Beschreibung </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col01"> <p>3 </p> </td> 
   <td colname="col1"> <p> 
     <!--Updated to match search-eng version, 2/1/2013--> <code> &lt;guided-if[-not]-first&gt;&lt;guided-else[-not]-first&gt; 
      &lt;/guided-if[-not]-first&gt; </code> </p> </td> 
   <td colname="col2"> <p>Diese Bedingung ist wahr, wenn die aktuelle Iteration die erste Iteration der Schleife ist. Das bedeutet nicht unbedingt das erste Ergebnis oder die erste Seite, sondern das erste. Wenn sich der Site-Besucher auf Seite 2 eines Ergebnissatzes befindet, der 10 pro Seite beträgt, ist die erste Iteration das Ergebnis 11. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>2 </p> </td> 
   <td colname="col1"> <p> 
     <!--Updated to match search-eng version, 2/1/2013--> <code> &lt;guided-if[-not]-last&gt;&lt;guided-else[-not]-last&gt; 
      &lt;/guided-if[-not]-last&gt; </code> </p> </td> 
   <td colname="col2"> <p>Diese Bedingung ist wahr, wenn die aktuelle Iteration die letzte Iteration der Schleife ist. Das bedeutet nicht unbedingt das letzte Ergebnis oder die letzte Seite, sondern das letzte Ergebnis im aktuellen Kontext (Seite). Wenn sich der Site-Besucher auf Seite 1 eines Ergebnissatzes befindet, der 200 Ergebnisse enthält, aber nur 10 Ergebnisse pro Seite hat, lautet die letzte Iteration result 10 anstelle von result 200. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>1 </p> </td> 
   <td colname="col1"> <p> 
     <!--Updated to match search-eng version, 2/1/2013--> <code> &lt;guided-if[-not]-odd&gt;&lt;guided-else[-not]-odd&gt; 
      &lt;/guided-if[-not]-odd&gt; </code> </p> </td> 
   <td colname="col2"> <p>Diese Bedingung ist wahr, wenn die aktuelle Iteration eine ungerade Iteration der Schleife ist (im Gegensatz zu einer geraden Iteration). Dies ist hilfreich, um unterschiedliche Zeilenfarben anzuzeigen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>4 </p> </td> 
   <td colname="col1"> <p> <code> &lt;guided-if[-not]-even&gt;&lt;guided-else[-not]-even&gt; 
      &lt;/guided-if[-not]-even&gt; </code> </p> </td> 
   <td colname="col2"> <p>Diese Bedingung ist wahr, wenn die aktuelle Iteration eine gerade Iteration der Schleife ist (im Gegensatz zu einer ungeraden Iteration). Dies ist hilfreich, um unterschiedliche Zeilenfarben anzuzeigen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>5 </p> </td> 
   <td colname="col1"> <p> <code> &lt;guided-if[-not]-alt&gt;&lt;guided-else[-not]-alt&gt; 
      &lt;/guided-if[-not]-alt&gt; </code> </p> </td> 
   <td colname="col2"> <p>Diese Bedingung ist wahr, wenn die aktuelle Iteration eine gerade Iteration der Schleife ist. Dies ist hilfreich, um unterschiedliche Zeilenfarben anzuzeigen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>6 </p> </td> 
   <td colname="col1"> <p> <code> &lt;guided-if[-not]-inner&gt;&lt;guided-else[-not]-inner&gt; 
      &lt;/guided-if[-not]-inner&gt; </code> </p> </td> 
   <td colname="col2"> <p>Umfasst den Text zwischen ihnen, wenn die aktuelle Iteration weder die erste noch die letzte ist. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>7 </p> </td> 
   <td colname="col1"> <p> <code> &lt;guided-if[-not]-outer&gt;&lt;guided-else[-not]-outer&gt; 
      &lt;/guided-if[-not]-outer&gt; </code> </p> </td> 
   <td colname="col2"> <p>Bezieht den Text zwischen ihnen ein, wenn die aktuelle Iteration die erste oder letzte ist. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>8 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-loop-index&gt; </span> </p> </td> 
   <td colname="col2"> <p>Eine Ganzzahl (beginnend mit 0), deren Wert für jede Iteration der Schleife inkrementiert wird. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>9 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-loop-counter&gt; </span> </p> </td> 
   <td colname="col2"> <p>Eine Ganzzahl (beginnend mit 1), deren Wert für jede Iteration der Schleife inkrementiert wird. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Verschiedene Sprachen {#section_BFE8DC98E26F4D7BB60FEC54D9A5DC6C}

Die folgenden Tags stehen zur Verfügung, damit Sie mit Ihrer Vorlage komplexere Dinge durchführen können, z. B. Ihre eigene Mini-Facette.

<table> 
 <thead> 
  <tr> 
   <th colname="col01" class="entry"> </th> 
   <th colname="col1" class="entry"> <p>Tag </p> </th> 
   <th colname="col2" class="entry"> <p>Beschreibung </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col01"> <p>3 </p> </td> 
   <td colname="col1"> <p> 
     <!--Updated to match search-eng, 2/1/2013--> <span class="codeph"> &lt;guided-current-path&gt; </span> </p> </td> 
   <td colname="col2"> <p>Gibt Ihnen den aktuellen Pfad an, der verwendet wird. Normalerweise wird er verwendet, um einen Link zu erstellen, der einen neuen Parameter zur vorhandenen Suche hinzufügt. Standardmäßig ist der Pfad mit URL-Escape-Zeichen versehen. Mit dem Parameter escape können Sie angeben, welcher Escape-Modus verwendet werden soll. </p> <p>Beispiel: </p> <p> <code class="syntax html"> &lt;a&nbsp;href="&lt;guided-current-path&nbsp;/&gt;&amp;lang=fr"&gt; 
      French&nbsp;Version </code> </p> <p>In diesem Beispiel verwendet eine Suchverarbeitungsregel lang, um die französische Version auszuwählen. </p> <p>Der aktuelle Pfad hat immer mindestens einen Parameter für die Abfrage. Wenn keine anderen Parameter für die Abfrage vorhanden sind, wird sie auf <span class="codeph"> q=* </span> gesetzt, was das Hinzufügen weiterer Parameter erleichtert. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>2 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> Basispfad  </span> </p> </td> 
   <td colname="col2"> <p> Wenn Sie einen Link mit dem Basepath erstellen möchten, verwenden Sie <span class="codeph"> / </span> am Beginn Ihrer <span class="codeph"> href </span> und fügen Sie einen Parameter hinzu. </p> <p> <code class="syntax html"> &lt;a&nbsp;href="/"&gt;All&nbsp;Products&lt;/a&gt; 
      Would&nbsp;create&nbsp;a&nbsp;link&nbsp;"All&nbsp;Products"&nbsp;to&nbsp;your 
      basepath,&nbsp;for&nbsp;example&nbsp;https://search.mycompany.com/ 
       </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>1 </p> </td> 
   <td colname="col1"> <p> 
     <!--Updated to match search-eng, 2/1/2013--> <span class="codeph"> &lt;guided-query-param gsname="query_parameter"&gt; </span> </p> </td> 
   <td colname="col2"> <p>Ermöglicht das Erfassen des vorhandenen Werts eines Abfrage-Parameters, der sich auf der URL befindet. Wenn Ihr Parameter nicht vorhanden ist, gibt dieses Tag eine leere Zeichenfolge zurück. Wenn Sie keine Escape-Option angeben, wird die zurückgegebene Zeichenfolge automatisch mit einem HTML-Escapezeichen versehen, können Sie HTML- oder URL-Escapezeichen angeben. </p> <p>Beispiel: </p> <p> 

    &amp;lt;guided-Abfrage-param&amp;nbsp;gsname=&quot;q&quot;&amp;nbsp;/&amp;gt;
    gibts&amp;nbsp;you&amp;nbsp;the&amp;nbsp;value&amp;nbsp;pants
    
    &amp;lt;guided-Abfrage-param&amp;nbsp;gsname=&quot;lang&quot;&amp;nbsp;
    &amp;nbsp;
    
    gibt&amp;nbsp;g;g;g;g;g;g;g;g&amp;nbsp;g;g;g;g;g;gsname=&quot;g;g;g;g;g;g;g;g;g;g;g&amp;nbsp;g&amp;nbsp;g&amp;nbsp;g;g&amp;nbsp;g;g;g;g;g;g;g;g;g;g;g;g;g;g;g;g;g;g;g;g;g;g;
    nbsp;g;g;g;g;g;g;g;g;g you&amp;nbsp;the&amp;nbsp;value&amp;nbsp;en
    &amp;lt;guided-Abfrage-param&amp;nbsp;gsname=&quot;test&quot;&amp;nbsp;/&amp;gt;
    gibts&amp;nbsp;you&amp;nbsp;an&amp;nbsp;empty&amp;nbsp;string&amp;nbsp;&amp;nbsp;&amp;nbsp; p;&amp;nbsp;&amp;nbsp;&amp;nbsp;   &lt;/p>  &lt;/td>
</tr> 
  <tr> 
   <td colname="col01"> <p>4 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-query-param-name gsname="param#" offset="offset_number" /&gt; </span> </p> </td> 
   <td colname="col2"> <p>Die geführte Suche hat den Begriff einer Abfrage, die im Breadcrumb-Steuerelement verwendet wird. <span class="codeph"> Mit guided-Abfrage-param-name  </span> können Sie Parameter als Teil eines Links in der Präsentationsvorlage definieren, bei dem die geführte Suche die richtige Abfrage für Sie ermittelt. Das <span class="codeph"> gsname </span> enthält ein "x", das durch die geführte Suche durch die richtige Zahl ersetzt wird. Der Versatzwert kann zwischen 0 und 15 liegen, wobei 0 bedeutet, dass die nächste verfügbare Abfrage verwendet wird. Eine 1 gibt an, dass Sie 1 hinzufügen möchten usw. </p> <p>In Kombination mit <span class="codeph"> geführte-current-path </span> können Sie einen eigenen Mini-Facet-Link erstellen oder eine zusätzliche Drilldown-Ebene zulassen. </p> <p>Beispiel: </p> <p> <code class="syntax html"> &lt;a&nbsp;href="&lt;guided-current-path 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;/&gt;&amp;&lt;guided-query-param-name&nbsp;gsname="q#"&nbsp;offset="0" 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;/&gt;=mens&amp;&lt;guided-query-param-name&nbsp;gsname="x#"&nbsp;offset="0" 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;/&gt;=category"&nbsp;&gt;Category:Men&lt;/a&gt;&nbsp; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; </code> </p> <p> <code class="syntax html"> &lt;a&nbsp;href="&lt;guided-current-path 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;/&gt;&amp;&lt;guided-query-param-name&nbsp;gsname="sp_q_exact_#"&nbsp;offset="0" 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;/&gt;=mens&amp;&lt;guided-query-param-name&nbsp;gsname="sp_x_#"&nbsp;offset="0" 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;/&gt;=category&amp;&lt;guided-query-param-name&nbsp;gsname="sp_q_exact_#"&nbsp;offset="1" 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;/&gt;=Jeans&amp;&lt;guided-query-param-name&nbsp;gsname="sp_x_#"&nbsp;offset="1" 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;/&gt;=product-type"&nbsp;&gt;Cat:Men&nbsp;-&nbsp;Product:Jeans&lt;/a&gt; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>5 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-include gsfile="filename" /&gt; </span> </p> </td> 
   <td colname="col2"> <p> Hiermit können Sie andere Vorlagendateien einschließen. Diese Funktion bedeutet, dass Sie mehrere Vorlagen mit Untervorlagen als Module erstellen können. </p> <p>Im folgenden Beispiel werden die Dateien <span class="filepath"> badcrumbs </span> und <span class="filepath"> facets </span> eingeschlossen: </p> <p> <code class="syntax html"> &lt;guided-include&nbsp;gsfile='breadcrumbs.tmpl'&nbsp;/&gt; 
      &lt;guided-include&nbsp;gsfile='facets.tmpl'&nbsp;/&gt; </code> </p> <p>Dynamische Includes werden nicht unterstützt. Das heißt, <span class="codeph"> gsfile </span> kann keine Variable sein. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>6 </p> </td> 
   <td colname="col1"> <p> 
     <!--NEW 1/17/2013--> <span class="codeph"> &lt;guided-search-time&gt; </span> </p> </td> 
   <td colname="col2"> <p> Gibt an, wie lange die Suche dauerte. Der zurückgegebene Suchzeitwert wird in ms angegeben. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>7 </p> </td> 
   <td colname="col1"> <p> 
     <!--NEW 1/17/2013--> <span class="codeph"> &lt;guided-fall-through-searches&gt; </span> </p> </td> 
   <td colname="col2"> <p> Gibt die Anzahl der Kernelsuchvorgänge zurück, mit denen die Seite der Suchergebnisse erstellt wird. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>8 </p> </td> 
   <td colname="col1"> <p> 
     <!--NEW 1/17/2013--> <span class="codeph"> &lt;guided-if-fall-through-search&gt;&lt;/guided-if-fall-through-search&gt; </span> </p> </td> 
   <td colname="col2"> <p>Prüft, ob die Anzahl der Hauptsuchvorgänge größer als eine ist. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>9 </p> </td> 
   <td colname="col1"> <p> <code> &lt;guided-if[-not]-even&gt;&lt;guided-else[-not]-even&gt; 
      &lt;/guided-if[-not]-even&gt; </code> </p> </td> 
   <td colname="col2"> <p>Diese Bedingung ist wahr, wenn die aktuelle Iteration eine gerade Iteration der Schleife ist (im Gegensatz zu einer ungeraden Iteration). Dies ist hilfreich, um unterschiedliche Zeilenfarben anzuzeigen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>10 </p> </td> 
   <td colname="col1"> <p> <code> &lt;guided-if[-not]-alt&gt;&lt;guided-else[-not]-alt&gt; 
      &lt;/guided-if[-not]-alt&gt; </code> </p> </td> 
   <td colname="col2"> <p>Diese Bedingung ist wahr, wenn die aktuelle Iteration eine gerade Iteration der Schleife ist. Dies ist hilfreich, um unterschiedliche Zeilenfarben anzuzeigen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>11 </p> </td> 
   <td colname="col1"> <p> <code> &lt;guided-if[-not]-inner&gt;&lt;guided-else[-not]-inner&gt; 
      &lt;/guided-if[-not]-inner&gt; </code> </p> </td> 
   <td colname="col2"> <p>Umfasst den Text zwischen ihnen, wenn die aktuelle Iteration weder die erste noch die letzte ist. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>12 </p> </td> 
   <td colname="col1"> <p> <code> &lt;guided-if[-not]-outer&gt;&lt;guided-else[-not]-outer&gt; 
      &lt;/guided-if[-not]-outer&gt; </code> </p> </td> 
   <td colname="col2"> <p>Bezieht den Text zwischen ihnen ein, wenn die aktuelle Iteration die erste oder letzte ist. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>13 </p> </td> 
   <td colname="col1"> <p> <code> &lt;guided-if-first-search&gt;&lt;guided-else-first-search&gt; 
      &lt;/guided-if-first-search&gt; </code> </p> </td> 
   <td colname="col2"> <p>Ermöglicht die Überprüfung, ob Sie die erste Suche durchführen (die Abfrage ist das Ergebnis einer Suche aus dem Suchfeld). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>14 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-search-url /&gt; </span> </p> </td> 
   <td colname="col2"> <p>Sie können dieses Tag in Ihrer Vorlage verwenden, um die Aktion des Suchformulars vor der Hartkodierung zu speichern. Es erkennt, wann Sie sich in der Staged- oder Live-Umgebung befinden und ändert sich entsprechend. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>15 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-if-query-param-defined gsname="query_parameter"&gt; &lt;guided-else-query-param-defined&gt; &lt;/guided-if-query-param-defined&gt; </span> </p> </td> 
   <td colname="col2"> <p>Mit diesem Tag-Satz können Sie testen, welche CGI-Parameter im Suchpfad definiert sind. Sie können die Werte der Parameter nur dann testen, wenn sie definiert sind. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>16 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-next-query-number&gt; </span> </p> </td> 
   <td colname="col2"> <p>Die Guided Search Engine, die die Vorlage steuert, hat die Vorstellung von Gleitkommazahlen, bei denen jeder neue Link, den die Engine generiert, die nächste verfügbare Abfrage verwendet. Mit diesem Tag können Sie die Anzahl der nächsten Abfragen oder Offsets erfassen, sodass Sie benutzerspezifische Links erstellen können, die in die Ergebnismenge vordringen. Mit dem Offset können Sie die nächste Abfrage einstellen. Wenn Sie beispielsweise eine Facette ausgewählt haben, ist die nächste Abfrage 2, bei einem Offset von 1 ist die zurückgegebene Abfrage 3. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>17 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-custom-var gsname="custom_variable"&gt; </span> </p> </td> 
   <td colname="col2"> <p>Hiermit können Sie den vorhandenen Wert einer benutzerspezifischen Variablen erfassen, die Ihre Verarbeitungsregeln definieren. Wenn Sie keine Escape-Option angeben, wird die zurückgegebene Zeichenfolge automatisch HTML-Escapezeichen zurückgegeben, können Sie entweder <span class="codeph"> html </span>, <span class="codeph"> url </span>, <span class="codeph"> js </span> oder <span class="codeph"> 0 </span> angeben. Wenn Sie eine Verarbeitungsregel verwenden, um einen eingehenden CGI-Parameter in eine benutzerdefinierte Variable zu kopieren und diese Variable dann in Ihrer Vorlage mit Escapeeinstellung "none"oder "js"anzuzeigen oder zu verwenden, können Sie eine XSS-Verwundbarkeit in Ihrer Suche erstellen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>18 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-if-custom-var-defined gsname="custom_variable"&gt; &lt;guided-else-custom-var-defined&gt; &lt;/guided-if-custom-var-defined&gt; </span> </p> </td> 
   <td colname="col2"> <p>Aktiviert das Testen, wenn eine benutzerdefinierte Variable in den Verarbeitungsregeln definiert ist (Abfrage bereinigen, Vorsuchverarbeitung und Nachsuchverarbeitung). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>19 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-general-field gsname="searchname" field="fieldname"&gt; </span> </p> </td> 
   <td colname="col2"> <p>Hiermit können Sie den Inhalt eines allgemeinen Felds anzeigen, das in der Transportvorlage definiert ist. Wenn Sie keine Escape-Option angeben, wird die zurückgegebene Zeichenfolge in dem Format kodiert, das Sie in der Transportvorlage für dieses Feld angegeben haben. Die Angabe einer Escape-Option wird auf jedes Format angewendet, das Sie wie in Ihrer Transportvorlage kodieren. Sie können entweder <span class="codeph"> html </span>, <span class="codeph"> url </span>, <span class="codeph"> js </span>, <span class="codeph"> json </span> oder <span class="codeph"> 0 </span> angeben. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>20 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-if-general-field gsname="searchname" field="fieldname"&gt; &lt;guided-else-general-field&gt; &lt;/guided-if-general-field&gt; </span> </p> </td> 
   <td colname="col2"> <p>Aktiviert das Testen, wenn der Inhalt eines allgemeinen Felds, wie in der Transportvorlage definiert, vorhanden ist. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>21 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-cookie-value gsname="cookie_name"&gt; </span> </p> </td> 
   <td colname="col2"> <p>Ermöglicht das Erfassen des Werts eines Cookies, vorausgesetzt, das Cookie ist verfügbar. Wenn Sie keine Escape-Option angeben, wird die zurückgegebene Zeichenfolge automatisch HTML-Escapezeichen zurückgegeben, können Sie entweder <span class="codeph"> html </span>, <span class="codeph"> url </span>, <span class="codeph"> js </span>, <span class="codeph"> json </span> oder <span class="codeph"> 0 </span> angeben. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>22 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-if-cookie gsname="cookie_name"&gt; &lt;guided-else-cookie&gt; &lt;/guided-if-cookie&gt; </span> </p> </td> 
   <td colname="col2"> <p>Aktiviert das Testen, wenn ein Cookie vorhanden ist. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>23 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-banner gsname="banner area"&gt; </span> </p> </td> 
   <td colname="col2"> <p>Gibt das Banner für einen bestimmten Bereich aus. Die optionalen Attribute für Breite und Höhe werden im Visual Rule Builder verwendet, um die Anzeige eines aussagekräftigen Platzhalters zu ermöglichen, damit Benutzer ein Banner auswählen können. Standardmäßig sind Banner nicht mit Escape-Zeichen versehen. Stattdessen sollten Sie HTML in die Präsentationsvorlage einfügen. Wenn Sie jedoch eine JSON-Vorlage erstellen, sollten Sie die Option "js escaping"verwenden. </p> <p>Beispiel: </p> <p> <code class="syntax html"> &lt;guided-banner&nbsp;gsname="top"&nbsp;width="400px" 
      &nbsp;height="50px"/&gt; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>24 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-if-banner-set gsname="banner area"&gt; &lt;guided-else-banner-set&gt; &lt;/guided-if-banner-set&gt; </span> </p> </td> 
   <td colname="col2"> <p>Aktiviert Tests, wenn ein Bannerbereich festgelegt ist. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>25 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-if-simulator-mode&gt; &lt;guided-else-simulator-mode&gt; &lt;/guided-if-simulator-mode&gt; </span> </p> </td> 
   <td colname="col2"> <p>Ermöglicht Ihnen die Erkennung, wann Sie Ihre Suche im Simulator oder im Visual Rule Builder anzeigen. Normalerweise wird er verwendet, um zusätzliche Debugging-Informationen für Sie anzuzeigen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>26 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-if-tnt-business-rules&gt; &lt;guided-else-tnt-business-rules&gt; &lt;/guided-if-tnt-business-rules&gt; </span> </p> </td> 
   <td colname="col2"> <p>Ermöglicht Ihnen, festzustellen, ob Geschäftsregeln auf eine <span class="keyword"> Adobe Target </span>-Kampagne verweisen. Es wird normalerweise im Rahmen der Integration mit <span class="keyword"> Adobe Target </span> verwendet, um zu verhindern, dass die <span class="keyword">-Zielgruppe </span>-Server erreicht werden, wenn dies nicht erforderlich ist. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>27 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-redirect /&gt; </span> </p> </td> 
   <td colname="col2"> <p>Standardmäßig werden Umleitungen automatisch ausgeführt. Wenn Sie jedoch die Site-Suche/das Merchandising so konfiguriert haben, dass eine XML- oder JSON-Antwort an Ihre Webanwendung zurückgegeben wird, können Sie entweder die 302/301-Antwort in Ihrer Webanwendung analysieren oder die Weiterleitung als Teil der Ergebnismenge an Sie weiterleiten lassen. Wenn Sie die Umleitung als Teil des Ergebnissatzes weiterleiten, kann dieses Tag in der Vorlage verwendet werden, um die Umleitungsposition auszugeben. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>28 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-if-redirect&gt; &lt;guided-else-redirect&gt; &lt;/guided-if-redirect&gt; </span> </p> </td> 
   <td colname="col2"> <p>Wenn Sie die Site-Suche/das Merchandising konfiguriert haben, um Umleitungen in der Ergebnismenge zurückzugeben, können Sie mit diesem Tag-Satz feststellen, ob eine Umleitung zur Ausgabe erfolgt. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>29 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-lt /&gt; &lt;guided-gt /&gt; </span> </p> </td> 
   <td colname="col2"> <p>Mit diesem Tag-Satz können Sie geführte Vorlagen-Tags in HTML-Attribute einbetten. </p> <p>Beispiel: </p> <p> <code class="syntax html"> &lt;guided-lt/&gt;div&nbsp;&lt;guided-if-facet-long&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;style="height:&nbsp;125px;&nbsp;overflow: 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;auto;"&lt;/guided-if-facet-long&gt;&lt;guided-gt/&gt; </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Transportvorlagen-Tags {#reference_227D199F5A7248049BE1D405C0584751}

Transportvorlagen sind XML-Vorlagen, die Daten aus der Backend-Suche an die Präsentationsebene der geführten Suche weiterleiten.

<!-- 

r_transport_template_tags.xml

 -->

In Ihrer Präsentationsebene können Sie über eine einzelne Präsentationsvorlage verfügen, die die Ergebnisse mehrerer Suchen darstellt. Bei jeder Suche kann dieselbe Transportvorlage oder eine benutzerdefinierte Transportvorlage verwendet werden, um die Daten an die Präsentationsebene zu übergeben.

Da die Transportvorlage nur zum Übermitteln von Daten an die Präsentationsebene verwendet wird, enthält sie keinerlei HTML, das die Anzeige der Suchergebnisse betrifft. Die Transportvorlage verwendet XML-Tags der Transportvorlage, um die Suchergebnisse zum Füllen der Komponenten der geführten Suche, wie Facetten, Breadcrumbs und Menüs, weiterzugeben. Innerhalb dieser Tags werden standardmäßige Tags für Suchvorlagen verwendet, um die tatsächlichen Werte anzuzeigen.

Siehe [Bearbeiten einer Präsentation oder einer Transportvorlage](../c-about-design-menu/c-about-templates.md#task_800E0E2265C34C028C92FEB5A1243EC3).

Siehe [Suchvorlagen-Tags](../c-appendices/c-templates.md#reference_F7AA3FF602314E42842BBC740D2CA1A4).

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Transportvorlagen-Tag </p> </th> 
   <th colname="col2" class="entry"> <p>Beschreibung </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-xml&gt;&lt;/guided-xml&gt; </span> </p> </td> 
   <td colname="col2"> <p>Die XML-Stamm-Tags, die die Präsentationsebene verwendet, um zu erkennen, was aus der Transportvorlage analysiert wird. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;general&gt;&lt;/general&gt; </span> </p> </td> 
   <td colname="col2"> <p>Tags umschließen Suchvorlagen-Tags, die Zusammenfassungsdaten basierend auf der Ergebnismenge bereitstellen. Normalerweise enthalten diese Tags Suchtags für die Gesamtanzahl der Ergebnisse, das niedrigere Ergebnis und das höchste Ergebnis. Sie können eine beliebige Anzahl zusätzlicher globaler Felder definieren, die Sie mit dem Tag <span class="codeph"> general-field </span> verwenden möchten, wie im folgenden Beispiel: </p> <p> <code class="syntax html"> &lt;general&gt; 
      &nbsp;&nbsp;&lt;total&gt;&lt;search-total&nbsp;/&gt;&lt;/total&gt; 
      &nbsp;&nbsp;&lt;lower&gt;&lt;search-lower&nbsp;/&gt;&lt;/lower&gt; 
      &nbsp;&nbsp;&lt;upper&gt;&lt;search-upper&nbsp;/&gt;&lt;/upper&gt; 
      &nbsp;&nbsp;&lt;general-field&nbsp;name="my_custom_field"&gt;Some&nbsp;global&nbsp;content&lt;/general-field&gt; 
      &lt;/general&gt; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;results&gt;&lt;/results&gt; </span> </p> </td> 
   <td colname="col2"> <p>Tags werden um die Suchergebnisse herum umschlossen, sodass die geführte Suche weiß, wo sie gesucht werden soll. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;result&gt;&lt;/result&gt; </span> </p> </td> 
   <td colname="col2"> <p>Tags werden um jedes Suchergebnis herum umschlossen, sodass die geführte Suche erkennt, wo der Inhalt für ein einzelnes Suchergebnis Beginn und endet, wie im folgenden Beispiel: </p> <code class="syntax html"> &lt;results&gt; 
     &nbsp;&nbsp;&lt;search-results&gt; 
     &nbsp;&nbsp;&nbsp;&nbsp;&lt;result&gt; 
     &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;index&gt;&lt;search-index&nbsp;/&gt;&lt;/index&gt; 
     &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;loc&gt;&lt;search-cdata&gt;&lt;search-url&nbsp;length="500"&nbsp;/&gt;&lt;/search-cdata&gt;&lt;/loc&gt; 
     &nbsp;&nbsp;&nbsp;&nbsp;&lt;/result&gt; 
     &nbsp;&nbsp;&lt;/search-results&gt; 
     &lt;/results&gt; </code> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;attribute-table name="tablename"&gt; </span> </p> </td> 
   <td colname="col2"> <p>Ermöglicht die Schleife jedes Elements in einer Liste mit mehreren Werten für ein einzelnes Ergebnis. Verwenden Sie dieses Tag nur in einem Ergebnis. Der Zweck besteht darin, dass Sie über Attribute, die zu einem Ergebnisfeld gehören, iterieren können, wie im folgenden Beispiel: </p> <code class="syntax html"> &lt;results&gt; 
     &nbsp;&nbsp;&lt;search-results&gt; 
     &nbsp;&nbsp;&nbsp;&nbsp;&lt;result&gt; 
     &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;index&gt;&lt;search-index&nbsp;/&gt;&lt;/index&gt; 
     &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;loc&gt;&lt;search-url&nbsp;/&gt;&lt;/loc&gt; 
     &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;title&gt;&lt;search-title&nbsp;/&gt;&lt;/title&gt; 
     &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;attribute-table&nbsp;name="downloads"&gt; 
     &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;field&nbsp;name="download_title"&gt;&lt;search-display-field&nbsp;name="download_title"&nbsp;/&gt;&lt;/field&gt; 
     &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;field&nbsp;name="download_link"&nbsp;delimiter="|"&gt;&lt;search-display-field&nbsp;name="download_link"&nbsp;/&gt;&lt;/field&gt; 
     &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/attribute-table&gt; 
     &nbsp;&nbsp;&nbsp;&nbsp;&lt;/result&gt; 
     &nbsp;&nbsp;&lt;/search-results&gt; 
     &lt;/results&gt; </code> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;facets&gt;&lt;/facets&gt; </span> </p> </td> 
   <td colname="col2"> <p>Gibt die Ergebnisse weiter, die die Facetten ausfüllen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 
     <!--NEW 2/27/2014--> <span class="codeph"> &lt;dynamic-facet&gt;&lt;/dynamic-facet&gt; </span> </p> </td> 
   <td colname="col2"> <p> Sie können eine Facette sowohl als dynamische Facette als auch als Mitglied einer Facettenleiste festlegen. Ihre Behandlung ist jedoch unabhängig von den entsprechenden Präsentationsvorlagen-Tags. </p> <p>Mit anderen Worten, das Verschachteln eines Facettenschienenschleiferkontexts in einem dynamischen Facettenschleiferkontext oder umgekehrt ist nicht zulässig. </p> <p>Bei Facetten, die sowohl dynamisch als auch per Schiene sind, sind nur die dynamischen Facetten sichtbar, die für eine bestimmte Suche zurückgegeben wurden. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;facet name="name"&gt;&lt;/facet&gt; </span> </p> </td> 
   <td colname="col2"> <p> Jede Facette verfügt über eigene Facetten-Tags, bei denen der Parameter name mit dem Facettennamen übereinstimmt. Suchtags werden für die Facettenwerte innerhalb der Facetten-Tags verwendet, wie im folgenden Beispiel: </p> <code class="syntax html"> &lt;facets&gt; 
     &nbsp;&nbsp;&lt;facet&nbsp;name="brand"&gt; 
     &nbsp;&nbsp;&nbsp;&nbsp;&lt;values&gt;&lt;search-field-value-list&nbsp;name="brand"&nbsp;quotes="no"&nbsp;commas="yes"&nbsp;data="values"&nbsp;sortby="values"&nbsp;/&gt;&lt;/values&gt; 
     &nbsp;&nbsp;&nbsp;&nbsp;&lt;counts&gt;&lt;search-field-value-list&nbsp;name="brand"&nbsp;quotes="no"&nbsp;commas="yes"&nbsp;data="counts"&nbsp;sortby="values"&nbsp;/&gt;&lt;/counts&gt; 
     &nbsp;&nbsp;&lt;/facet&gt; 
     &nbsp;&nbsp;&lt;facet&nbsp;name="category"&gt; 
     &nbsp;&nbsp;&nbsp;&nbsp;&lt;values&gt;&lt;search-field-value-list&nbsp;name="category"&nbsp;quotes="no"&nbsp;commas="yes"&nbsp;data="values"&nbsp;sortby="values"&nbsp;/&gt;&lt;/values&gt; 
     &nbsp;&nbsp;&nbsp;&nbsp;&lt;counts&gt;&lt;search-field-value-list&nbsp;name="category"&nbsp;quotes="no"&nbsp;commas="yes"&nbsp;data="counts"&nbsp;sortby="values"&nbsp;/&gt;&lt;/counts&gt; 
     &nbsp;&nbsp;&lt;/facet&gt; 
     &lt;/facets&gt; </code> <p> Konten mit formatierten Facetten können das dynamische Tag und das Tag der Anzeigenamen verwenden. Beide Tags erleichtern die Zuordnung zwischen formatierten Facetten und echten Facetten bei der Erstellung von Geschäftsregeln. </p> <code class="syntax html"> &lt;facets&gt; 
     &nbsp;&nbsp;&lt;facet&nbsp;name="facet_values01"&gt; 
     &nbsp;&lt;dynamic&gt;1&lt;/dynamic&gt; 
     &nbsp;&lt;display-names&gt;&lt;search-field-value-list&nbsp;name="facet_names01"&nbsp;quotes="no"&nbsp;commas="yes"&nbsp;data="values"&nbsp;sortby="values"&nbsp;/&gt;&lt;/display-names&gt; 
     &nbsp;&nbsp;&nbsp;&nbsp;&lt;values&gt;&lt;search-field-value-list&nbsp;name="facet_values01"&nbsp;quotes="no"&nbsp;commas="yes"&nbsp;data="values"&nbsp;sortby="values"&nbsp;/&gt;&lt;/values&gt; 
     &nbsp;&nbsp;&nbsp;&nbsp;&lt;counts&gt;&lt;search-field-value-list&nbsp;name="facet_values01"&nbsp;quotes="no"&nbsp;commas="yes"&nbsp;data="counts"&nbsp;sortby="values"&nbsp;/&gt;&lt;/counts&gt; 
     &nbsp;&nbsp;&lt;/facet&gt; </code> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-display-field separator=","&gt; </span> </p> </td> 
   <td colname="col2"> <p>Das <span class="codeph">-Trennzeichen </span> ermöglicht die Änderung des Trennzeichens, das verwendet wird, wenn Sie Daten aus dem Suchfeld für Listen ausgeben. Die Standardeinstellung ist ein Komma. </p> <p>Im Allgemeinen sollte das verwendete Trennzeichen etwas sein, das im Feldinhalt nicht leicht angezeigt wird. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;suggestions&gt;&lt;/suggestions&gt; </span> </p> </td> 
   <td colname="col2"> <p> Schließen Sie Ihre "Meinten Sie"-Vorschläge mit Tags ein, damit die geführte Suche erkennt, welche XML-Knoten Vorschläge enthalten. </p> <p>Siehe <a href="../c-about-linguistics-menu/c-about-did-you-mean.md#concept_7D4F3C29EF184B538B8AE2ECAE0CDC5E" type="concept" format="dita" scope="local">Info zu „Meinten Sie“</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;suggestion&gt;&lt;/suggestion&gt; </span> </p> </td> 
   <td colname="col2"> <p>Fügen Sie jeden der "Meinten Sie"-Vorschläge mit Tags ein, wie im folgenden Beispiel: </p> <code class="syntax html"> &lt;search-if-suggestions&gt; 
     &nbsp;&nbsp;&lt;suggestions&gt; 
     &nbsp;&nbsp;&nbsp;&nbsp;&lt;search-suggestions&gt; 
     &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;suggestion&gt;&lt;search-suggestion-text&nbsp;/&gt;&lt;/suggestion&gt; 
     &nbsp;&nbsp;&nbsp;&nbsp;&lt;/search-suggestions&gt; 
     &nbsp;&nbsp;&lt;/suggestions&gt; 
     &lt;/search-if-suggestions&gt; </code> <p>Siehe <a href="../c-about-linguistics-menu/c-about-did-you-mean.md#concept_7D4F3C29EF184B538B8AE2ECAE0CDC5E" type="concept" format="dita" scope="local">Info zu „Meinten Sie“</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Suchvorlagen-Tags {#reference_F7AA3FF602314E42842BBC740D2CA1A4}

Eine Suchvorlage ist eine HTML-Datei mit Vorlagen-Tags, die von Site-Suche/Merchandising definiert werden. Diese Tags geben an, wie die Suchergebnisse formatiert sind. Die folgende Referenz enthält eine kurze Beschreibung der einzelnen Suchvorlagen-Tags und ihrer Attribute.

<!-- 

r_search_template_tags.xml

 -->

>[!NOTE]
>
>Verwenden Sie nur Suchvorlagen-Tags in Transportvorlagendateien (.tpl).

Sie können aus den folgenden Suchvorlagen-Tag-Gruppen und Referenzmaterial auswählen.

Tags, die nur in der Ergebnisschleife gültig sind, umfassen Folgendes:

* [Ergebnisse-Schleife-Tags](../c-appendices/c-templates.md#section_D4DC7B4560144663972E8DBC3369C629)
* [Tags der Ergebnisschleife](../c-appendices/c-templates.md#section_80D68334E8D04A33937A6E58ABAAA320)
* [Bedingte Tags für die Ergebnisschleife](../c-appendices/c-templates.md#section_35C367969E384A06A9865E388F1F9360)
* [Ankerverknüpfungs-Tags der Ergebnisschleife](../c-appendices/c-templates.md#section_C5FAEF520E9E42ADAD1F90651922AA02)
* [Bedingte Tags für Schleifenposition](../c-appendices/c-templates.md#section_E0C29DDA09E043C9A396F36334F05EBB)

Zu den Tags, die für die gesamte Vorlage gültig sind, gehören:

* [Liste-Tags für Feldwerte](../c-appendices/c-templates.md#section_D3298B5F976447DBA0032B883DCC91B1)
* [Liste-Schleifentags für Feldwerte](../c-appendices/c-templates.md#section_0717FA09F0FC449CB916883B0500A60E)
* [Vorschlagen von Tags](../c-appendices/c-templates.md#section_C28EB8B4F7DC4E278A0F143BCFEEB1AC)
* [Vorlagen-Zeichenfolgen-Tags](../c-appendices/c-templates.md#section_67E3D529661F4F03A1FF469D9D658CAF)
* [Vorlagenanker-Verknüpfungs-Tags](../c-appendices/c-templates.md#section_3A51D27616C541E2B818CC52B2B856BA)
* [Bedingte Tags für Vorlagen](../c-appendices/c-templates.md#section_18D9BC66DE484881932FD2F7EA9D170D)
* [Steuerelemente-Tags für Vorlagen](../c-appendices/c-templates.md#section_45AFC414ACA74825B72FEAA8456F8DD2)

Referenzthemen zur Suchvorlage

* [Datumsformat-Zeichenfolgen](../c-appendices/c-templates.md#section_4BBDBBEF2B96414497617CD4B52D96E4)
* [Sprachkennung](../c-appendices/c-templates.md#section_0490DECC00E34691ADE5A9ED90A6D911)
* [Content-Type HTTP-Header angeben](../c-appendices/c-templates.md#section_AEED823E9938448A9EDB2F286D9CFD90)
* [Festlegen eines Zeichensatzes in einer HTML-Vorlage](../c-appendices/c-templates.md#section_E0D1816ABB5846BEBE9C26D5980CCBE6)
* [Festlegen eines Zeichensatzes in einer XML-Vorlage](../c-appendices/c-templates.md#section_17DC31CDCC104F5F8081466B41A96E9D)
* [Hinzufügen einer Suchvorlage in einer anderen](../c-appendices/c-templates.md#section_7D1FCD3D9E2340C291E354C9720E8BC0)

## Ergebnisse - Schleifentags {#section_D4DC7B4560144663972E8DBC3369C629}

Das Tag der Ergebnisschleife ist das Arbeitspferd des Vorlagensystems. Wenn das Tag während einer Suche auftritt, wird der HTML-Code wiederholt und andere Tags zwischen dem Start- und dem Ende der Ergebnisschleife-Tags. Dadurch werden alle anderen Tags durch Ihre Suchergebnisse ersetzt.

`<search-results> ... </search-results>`

Die Tags der Ergebnisschleife umschließen den HTML-Code, der die Suchergebnisse anzeigt. Der HTML-Code zwischen den Tags wird für jedes Ergebnis wiederholt und auf der Seite angezeigt.

Die folgenden Tags sind nur innerhalb der Ergebnisschleife gültig:

* [Tags der Ergebnisschleife](../c-appendices/c-templates.md#section_80D68334E8D04A33937A6E58ABAAA320)
* [Bedingte Tags für die Ergebnisschleife](../c-appendices/c-templates.md#section_35C367969E384A06A9865E388F1F9360)
* [Ankerverknüpfungs-Tags der Ergebnisschleife](../c-appendices/c-templates.md#section_C5FAEF520E9E42ADAD1F90651922AA02)
* [Bedingte Tags für Schleifenposition](../c-appendices/c-templates.md#section_E0C29DDA09E043C9A396F36334F05EBB)

## Ergebnisse-Schleife-Zeichenfolgen-Tags {#section_80D68334E8D04A33937A6E58ABAAA320}

Die folgenden Tags geben eine Zeichenfolge zurück.

Siehe [Informationen zu den Tags der Ergebnisschleife](../c-appendices/c-templates.md#section_D4DC7B4560144663972E8DBC3369C629).

<table> 
 <thead> 
  <tr> 
   <th colname="col01" class="entry"> </th> 
   <th colname="col1" class="entry"> <p>Tag </p> </th> 
   <th colname="col2" class="entry"> <p>Beschreibung </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col01"> <p>3 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-index&gt; </span> </p> </td> 
   <td colname="col2"> <p>Gibt den numerischen Index des aktuellen Ergebnisses zurück. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>2 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-title length="XX"&gt; </span> </p> </td> 
   <td colname="col2"> <p>Gibt den Seitentitel des aktuellen Ergebnisses zurück. Das optionale Attribut length wird verwendet, um die Länge der angezeigten Zeichenfolgen zu begrenzen, wobei der Standardwert 80 Zeichen ist. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>3 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-bodytext length="XX" encoding="html/javascript/json/perl/url/none"&gt; </span> </p> </td> 
   <td colname="col2"> <p>Gibt den Texttext ab dem Anfang der Seite zurück. Relevante Begriffe werden fett dargestellt. Das optionale Attribut length wird verwendet, um die Länge der angezeigten Zeichenfolgen zu begrenzen, wobei der Standardwert 80 Zeichen ist. Das Attribut "encoding"ist optional und kann Ausgabezeichen mit HTML-Kodierung (Standard), JavaScript-Kodierung, Perl-Kodierung oder ohne Kodierung kodieren. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>4 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-description length="XX" encoding="html/javascript/json/perl/url/none"&gt; </span> </p> </td> 
   <td colname="col2"> <p> Gibt die Beschreibung des aktuellen Ergebnisses zurück. Wenn das Meta-Beschreibungstag vorhanden ist und das Inhaltsattribut nicht leer ist, wird dieser Text angezeigt. Andernfalls wird der Anfang des Textes der Seite angezeigt. Das optionale Attribut length wird verwendet, um die Länge der angezeigten Zeichenfolgen zu begrenzen, wobei der Standardwert 80 Zeichen ist. </p> <p>Das optionale Attribut <span class="codeph"> encoding </span> bestimmt, ob die Ausgabe HTML-kodiert, JavaScript-kodiert, Perl-kodiert, URL-kodiert oder nicht kodiert ist, für die Ausgabe auf der Ergebnisseite. Der Standardwert von <span class="codeph"> encoding </span> ist <span class="codeph"> html </span>. Normalerweise müssen Sie das Kodierungsattribut nicht angeben. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>5 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-score rank="dynamic/static/dynamic-raw/static-raw/final-raw" precision="XX"&gt; </span> </p> </td> 
   <td colname="col2"> <p>Gibt das Ergebnis des aktuellen Ergebnisses zurück, das eine Zahl zwischen 0 und 100 ist. Wenn Sie ein Rangfeld unter <span class="uicontrol"> Optionen </span> &gt; <span class="uicontrol"> Metadaten </span> &gt; <span class="uicontrol"> Definitionen </span> definiert haben, können Sie den dynamischen Seitenstrang anzeigen, indem Sie das rank-Attribut auf dynamisch ( <span class="codeph"> &lt;search-score rank="dynamic"&gt; </span>) setzen. Sie können den Rang der statischen Seite anzeigen, indem Sie das Rang-Attribut auf statisch ( <span class="codeph"> &lt;search-score rank="static"&gt; </span>) setzen. Mit dem optionalen Präzisionsattribut können Sie die Anzahl der anzuzeigenden Dezimalstellen angeben. Der Standardwert ist 0, was das Ganzzahlergebnis anzeigt). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>6 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-date length="XX" none="text" date-format="date-format-string" gmt="yes/no" language="0/2/language-id"&gt; </span> </p> </td> 
   <td colname="col2"> <p>Gibt das Datum des aktuellen Ergebnisses zurück. Der optionale Textwert "none"wird angezeigt, wenn kein Datum mit dem aktuellen Ergebnis verknüpft ist. Wenn der optionale Wert "none"nicht angegeben wird, wird der Text "No Date"angezeigt, wenn kein Datum mit dem aktuellen Ergebnis verknüpft ist. </p> <p>Das Attribut "date-format"nimmt eine Datumsformat-Zeichenfolge im UNIX-Stil wie "%A", %B %d, %Y"(für "Montag, 25. Juli 2016"). "gmt"ist standardmäßig "yes"und steuert, ob der Zeitabschnitt der Datums-Zeichenfolge in GMT ("yes") oder in der Zeitzone des Kontos ("no") ausgegeben werden soll. </p> <p>Das Attribut "language"steuert die Konventionen für Sprache und Gebietsschema der Ausgabedatumszeichenfolge. "0" (Standard) bedeutet "Kontosprache verwenden". "2" bedeutet "Dokument-Sprache verwenden". Der Wert "language"1 ist für die zukünftige Verwendung reserviert. Jeder andere "language"-Wert wird als spezifischer Sprachbezeichner interpretiert, z. B. bedeutet "en_US" "Englisch (USA)". </p> <p>Das optionale Attribut length wird verwendet, um die Länge der angezeigten Zeichenfolgen zu begrenzen, wobei der Standardwert 80 Zeichen ist. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>7 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-size&gt; </span> </p> </td> 
   <td colname="col2"> <p>Gibt die Größe des aktuellen Ergebnisses in Byte zurück. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>8 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-url length="XX" encoding="html/javascript/json/perl/url/none"&gt; </span> </p> </td> 
   <td colname="col2"> <p>Gibt die URL des aktuellen Ergebnisses zurück. </p> <p>Verwenden Sie das optionale Attribut <span class="codeph"> length </span>, um die Länge der angezeigten Zeichenfolgen zu begrenzen, wobei die Standardeinstellung unbegrenzte Zeichen ist. </p> <p>Das Attribut <span class="codeph"> encoding </span> ist optional und kann Ausgabezeichen mit HTML-Kodierung, JavaScript-Kodierung, Perl-Kodierung oder ohne Kodierung kodieren. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>9 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-url-path-query length="XX"&gt; </span> </p> </td> 
   <td colname="col2"> <p>Gibt den Pfad und die Abfrage einschließlich des Fragezeichens der URL des aktuellen Ergebnisses zurück. </p> <p>Verwenden Sie das optionale Attribut <span class="codeph"> length </span>, um die Länge der angezeigten Zeichenfolgen zu begrenzen, wobei die Standardeinstellung unbegrenzte Zeichen ist. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>10 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-context length="XX" encoding="html/javascript/json/perl/url/none"&gt; </span> </p> </td> 
   <td colname="col2"> <p>Gibt die nächste Kontextzeile für den Suchbegriff zurück. Relevante Begriffe werden fett dargestellt. Rufen Sie dieses Tag wiederholt auf, um mehr als eine Kontextzeile für das aktuelle Ergebnis anzuzeigen. </p> <p>Verwenden Sie das optionale Attribut <span class="codeph"> length </span>, um die Länge der angezeigten Zeichenfolgen mit einer Standardlänge von 80 Zeichen zu beschränken. Das Attribut <span class="codeph"> length </span> wird ignoriert, wenn dieses Tag von <span class="codeph"> &lt;search-if-context&gt; </span>- oder <span class="codeph"> &lt;search-if-any-context&gt; </span>-Tag-Sets eingeschlossen wird, die ein length-Attribut enthalten. </p> <p>Das Attribut <span class="codeph"> encoding </span> ist optional und kann Ausgabezeichen mit HTML-Kodierung (Standard), JavaScript-Kodierung, Perl-Kodierung oder ohne Kodierung kodieren. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>11 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-display-field name="field-name" length="XX" none="text" date-format="date-format-string" gmt="yes/no" language="0/2/language-id" encoding="html/javascript/json/perl/url/none" quotes="yes/no" commas="yes/no" units="miles/kilometers" separator="|"&gt; </span> </p> </td> 
   <td colname="col2"> <p>Dieses erweiterte Tag zeigt den Inhalt des Metadatenfelds (URL, Titel, Desc, Schlüssel, Zielgruppe, Textkörper, Alt, Datum, Zeichensatz und Sprache oder Felder, die unter <span class="uicontrol"> Optionen </span> &gt; <span class="uicontrol"> Metadaten </span> &gt; Definitionen definiert sind) an, das für das aktuelle Ergebnis im Attribut <span class="codeph"> name </span> angegeben ist. Beispiel: </p> <p> <span class="codeph"> &lt;search-display-field name="title" length="70" none="no title"&gt; </span> </p> <p>Gibt den Titel der Seite für ein Suchergebnis aus. Wenn das optionale Attribut <span class="codeph"> none </span> angegeben ist, wird der zugehörige Wert nur dann auf der Ergebnisseite angezeigt, wenn dem Feld kein Inhalt zugeordnet ist. </p> <p>Die Attribute <span class="codeph"> date-format </span>, <span class="codeph"> gmt </span> und <span class="codeph"> language </span> sind nur relevant, wenn der Inhaltstyp des angegebenen Felds <span class="codeph"> date </span> ist. </p> <p>Das Attribut <span class="codeph"> date-format </span> nimmt eine Datumsformat-Zeichenfolge im UNIX-Stil wie <span class="codeph"> %A, %B %d, %Y </span> (für Montag, 25. Juli 2016). <span class="codeph"> gmt  </span> ist standardmäßig auf  <span class="codeph"> yes  </span> und steuert, ob der Zeitabschnitt der Datums-Zeichenfolge in GMT (  <span class="codeph"> yes  </span>) oder in der Zeitzone des Kontos (  <span class="codeph"> no  </span>) ausgegeben wird. </p> <p>Siehe <a href="../c-appendices/c-templates.md#section_4BBDBBEF2B96414497617CD4B52D96E4" type="section" format="dita" scope="local"> Datumsformat-Zeichenfolgen</a>. </p> <p>Das <span class="codeph">-Attribut language </span> steuert die Konventionen für Sprache und Gebietsschema der Ausgabedatumszeichenfolge. <span class="codeph"> 0  </span> (Standard) bedeutet "Kontosprache verwenden". <span class="codeph"> 2  </span> bedeutet "Dokument-Sprache verwenden". Die <span class="codeph"> Sprache </span> Wert <span class="codeph"> 1 </span> ist für die zukünftige Verwendung reserviert). Jeder andere <span class="codeph">-Wert </span> wird als spezifischer Sprachbezeichner interpretiert, z. B. <span class="codeph"> en_US </span> bedeutet "Englisch (USA)". </p> <p>Siehe <a href="../c-appendices/c-templates.md#section_0490DECC00E34691ADE5A9ED90A6D911" type="section" format="dita" scope="local"> Sprachkennungen</a>. </p> <p>Das optionale Attribut <span class="codeph"> length </span> wird verwendet, um die Länge der angezeigten Zeichenfolgen zu begrenzen, wobei der Standardwert 80 Zeichen ist. </p> <p>Das optionale Attribut <span class="codeph"> encoding </span> bestimmt, ob die Ausgabe HTML-kodiert, JavaScript-kodiert, Perl-kodiert, URL-kodiert oder nicht kodiert ist, für die Ausgabe auf der Ergebnisseite. Der Standardwert von <span class="codeph"> encoding </span> ist <span class="codeph"> html </span>. Normalerweise müssen Sie das Kodierungsattribut nicht angeben. </p> <p>Das optionale Attribut <span class="codeph"> gibt an, ob die einzelnen Elemente von Anführungszeichen (oder einfachen Anführungszeichen, wenn <span class="codeph"> encoding=perl </span>) umgeben sind. </span> Der Standardwert von <span class="codeph"> Anführungszeichen </span> ist <span class="codeph"> nein </span>. </p> <p>Das optionale Attribut <span class="codeph"> Kommas </span> bestimmt, ob die einzelnen Elemente durch Kommas getrennt werden. Der Standardwert von <span class="codeph"> Kommas </span> ist <span class="codeph"> yes </span>. Das <span class="codeph">-Komma </span>-Attribut wird bei Feldern ohne Liste ignoriert. </p> <p>Das optionale Attribut <span class="codeph"> unit </span> steuert die Entfernungseinheiten, die auf ein Ausgabefeld für die Suche nach der Nähe angewendet werden. Der Standardwert von <span class="codeph"> Einheiten </span> wird aus der Einstellung "Standardeinheiten"des Felds "Standort-Typ"bestimmt, das mit dem angegebenen Ausgabefeld für die Suche nach räumlicher Nähe verknüpft ist. </p> <p>Siehe <a href="../c-appendices/r-about-proximity-search.md#reference_45AC6BB50609431ABD31DA46EE65360D" type="reference" format="dita" scope="local"> Näherungssuche</a>. </p> <p>Das optionale <span class="codeph">-Trennzeichen </span> definiert das Einzelzeichen oder Trennzeichen, das zwischen den Werten der Ausgabe für Listen eingefügt wird. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>12 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-display-field-values name="field-name"&gt; ...&lt;search-display-field-values&gt; </span> </p> </td> 
   <td colname="col2"> <p>Dieses Tag erstellt eine Schleife zum Aufzählen von Metadatenfeldwerten (URL, Titel, Desc, Schlüssel, Zielgruppe, Textkörper, Alt, Datum, Zeichensatz und Sprache oder Felder, die unter <span class="uicontrol"> Optionen </span> &gt; <span class="uicontrol"> Metadaten </span> &gt; <span class="uicontrol"> Definitionen </span> definiert sind) für das aktuelle Ergebnis. Verschachteln Sie dieses Tag nicht in einem anderen <span class="codeph"> &lt;search-display-field-values&gt; </span>-Tag. Das <span class="codeph">-Attribut </span> gibt den Namen des Felds an, das die aufzuzählenden Werte enthält. Dieses Tag ist besonders nützlich bei Feldern, in denen das Attribut <span class="uicontrol"> der Zulassungslisten </span> markiert ist (unter <span class="uicontrol"> Optionen </span> &gt; <span class="uicontrol"> Metadaten </span> &gt; <span class="uicontrol"> Definitionen </span>). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>13 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-display-field-value date-format="date-format-string" gmt="yes/no" language="0/language-id" encoding="html/javascript/json/perl/url/none"&gt; </span> </p> </td> 
   <td colname="col2"> <p>Dieses Tag gibt den Metadatenfeldwert ( url, title, desc, keys, Zielgruppe, body, alt, date, charset und language oder die unter <span class="uicontrol"> Options </span> &gt; <span class="uicontrol"> Metadata </span> &gt; <span class="uicontrol"> Definitions </span> definierten Felder) für die aktuelle <span class="codeph"> &lt;search-display-field-values&gt;-Schleife aus. </span> Dieses Tag ist nur innerhalb einer <span class="codeph"> &lt;search-display-field-values&gt; </span>-Schleife gültig. Die Attribute <span class="codeph"> des Datumsformats </span>, <span class="codeph"> gmt </span> und <span class="codeph"> und </span> sind nur relevant, wenn der Inhaltstyp des im umschließenden <span class="codeph"> </span> &lt;a7/&gt;-Tag &lt;a7/&gt; angegebenen Feldnamens </span> datums &lt;a9/&gt; ist. <span class="codeph"> Das <span class="codeph">-Datumsformat </span> nimmt eine Datumsformat-Zeichenfolge im UNIX-Stil wie <span class="codeph"> "%A </span>, <span class="codeph"> %B </span> <span class="codeph"> %d </span>, <span class="codeph"> %Y </span>"(für "Montag, 25. Juli 2016"). Das Attribut <span class="codeph"> gmt </span> ist standardmäßig auf <span class="codeph"> yes </span> festgelegt und steuert, ob der Zeitabschnitt der Datums-Zeichenfolge in GMT ( <span class="codeph"> yes </span>) oder in der Zeitzone des Kontos ( <span class="codeph"> no </span>) ausgegeben wird. </span></p> <p>Das <span class="codeph">-Attribut language </span> steuert die Konventionen für Sprache und Gebietsschema der Ausgabedatumszeichenfolge. <span class="codeph"> 0  </span> (Standard) bedeutet "Kontosprache verwenden". Jeder andere <span class="codeph">-Wert </span> wird als spezifischer Sprachbezeichner interpretiert, z. B. <span class="codeph"> en_US </span> bedeutet "Englisch (USA)". </p> <p>Das optionale Attribut <span class="codeph"> encoding </span> bestimmt, ob die Ausgabe HTML-kodiert, JavaScript-kodiert, Perl-kodiert, URL-kodiert oder nicht kodiert ist, für die Ausgabe auf der Ergebnisseite. Der Standardwert von <span class="codeph"> encoding </span> ist <span class="codeph"> html </span>. Normalerweise müssen Sie das Kodierungsattribut nicht angeben. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>14 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-display-field-value-count name="field-name"&gt; </span> </p> </td> 
   <td colname="col2"> <p>Gibt die Gesamtanzahl der Werte im aktuellen Ergebnis für das Metadatenfeld aus (URL, Titel, Desc, Schlüssel, Zielgruppe, Textkörper, Alt, Datum, Zeichensatz und Sprache oder Felder, die unter <span class="uicontrol"> Optionen </span> &gt; <span class="uicontrol"> Metadaten </span> &gt; <span class="uicontrol"> Definitionen </span> definiert sind), die mit dem Namensattribut angegeben wurden. Dieses Tag kann an einer beliebigen Stelle in der Ergebnisschleife erscheinen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>15 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-display-field-value-counter&gt; </span> </p> </td> 
   <td colname="col2"> <p>Gibt den Zähler für die Ordinalschleife (1, 2, 3 usw.) für die aktuelle <span class="codeph"> &lt;search-display-field-values&gt; </span> aus. Dieses Tag ist nur innerhalb einer <span class="codeph"> &lt;search-display-field-values&gt; </span>-Schleife gültig. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>16 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-dynamic-facet-fields&gt; </span> </p> </td> 
   <td colname="col2"> <p>Beginnt einen Schleifenkontext für alle dynamischen Facettenfelder, die für diese Suche zurückgegeben werden. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>17 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-dynamic-facet-field-name&gt; </span> </p> </td> 
   <td colname="col2"> <p>Gibt den Namen des aktuellen dynamischen Facet-Felds für diese Schleifeniteration aus. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>18 </p> </td> 
   <td colname="col1"> <p> 
     <!--NEW for S&P 8.17.0 release on October 30 2014--> <span class="codeph"> &lt;search-result-trace encoding="html/javascript/ json/perl/url/none"&gt; </span> </p> </td> 
   <td colname="col2"> <p>Gibt Informationen zur Platzierung des aktuellen Ergebnisses aus, z. B. alle ergebnisbasierten Aktionen, die die Position des Ergebnisses beeinflussten. </p> <p>Das Ausgabeformat dieses Tags ist JSON, wie im folgenden Beispiel: </p> <p> <code> { 
      &nbsp;&nbsp;"sliceID":&nbsp;5, 
      &nbsp;&nbsp;"indexID":&nbsp;5894, 
      &nbsp;&nbsp;"finalScore":&nbsp;98.5, 
      &nbsp;&nbsp;"dynamicScore":&nbsp;15.3, 
      &nbsp;&nbsp;"staticScore":&nbsp;55.456, 
      &nbsp;&nbsp;"position":&nbsp;1, 
      &nbsp;&nbsp;"rbtaActionListID":&nbsp;117, 
      &nbsp;&nbsp;"rbtaActionID":&nbsp;57 
      } </code> </p> 
    <!--<p> Results added to the results set by way of <codeph>rbta</codeph> have a "naturalPosition" value of -1. </p>--> <p>Das Attribut <span class="codeph"> encoding </span> ist optional. der Standardwert ist <span class="codeph"> html </span>. </p> <p> <p>Hinweis:  Dieses Tag verfügt nur dann über eine Ausgabe, wenn <span class="codeph"> sp_trace=1 </span> mit den Hauptparametern für die Abfrage der Suche angegeben wird. </p> </p> <p>Siehe Zeile 48 in der Tabelle unter <a href="../c-appendices/c-cgiparameters.md#reference_582E85C3886740C98FE88CA9DF7918E8" format="dita" scope="local"> CGI-Parameter für die Backend-Suche</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Bedingte Tags für die Ergebnisschleife {#section_35C367969E384A06A9865E388F1F9360}

Die folgenden Tags enthalten den HTML-Code zwischen ihnen.

Siehe [Informationen zu den Tags der Ergebnisschleife](../c-appendices/c-templates.md#section_D4DC7B4560144663972E8DBC3369C629).

<table> 
 <thead> 
  <tr> 
   <th colname="col01" class="entry"> </th> 
   <th colname="col1" class="entry"> <p>Tag </p> </th> 
   <th colname="col2" class="entry"> <p>Beschreibung </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col01"> <p>3 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-if-title&gt; ...  &lt;/search-if-title&gt; </span> </p> <p> <span class="codeph"> &lt;search-if-not-title&gt; ...  &lt;/search-if-not-title&gt; </span> </p> </td> 
   <td colname="col2"> <p>Diese Tags enthalten den HTML-Code zwischen ihnen, wenn beim nächsten Aufruf von <span class="codeph"> &lt;search-title&gt; </span> der Dokument-Titel den Text zurückgibt (oder nicht zurückgibt). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>2 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-if-description length="XX"&gt; ... /search-if-description&gt;  </span> </p> <p> <span class="codeph"> &lt;search-if-not-description&gt; ...  &lt;/search-if-not-description&gt; </span> </p> </td> 
   <td colname="col2"> <p> Diese Tags enthalten den HTML-Code zwischen ihnen, wenn beim nächsten Aufruf von <span class="codeph"> &lt;search-description&gt; </span> der Dokument aus der Beschreibung zurückgegeben wird (oder nicht zurückgegeben wird). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>3 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-if-bodytext&gt; ...  &lt;/search-if-bodytext&gt; </span> </p> <p> <span class="codeph"> &lt;search-if-not-bodytext&gt; ...  &lt;/search-if-not-bodytext&gt; </span> </p> </td> 
   <td colname="col2"> <p>Diese Tags enthalten den HTML-Code zwischen ihnen, wenn beim nächsten Aufruf von <span class="codeph"> &lt;search-body-text&gt; </span> der Dokument-Textkörper zurückgegeben wird (oder nicht zurückgegeben wird). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>4 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-if-context length="XX"&gt; ...  &lt;/search-if-context&gt; </span> </p> <p> <span class="codeph"> &lt;search-if-not-context&gt; ...  &lt;/search-if-not-context&gt; </span> </p> </td> 
   <td colname="col2"> <p>Diese Tags enthalten den HTML-Code zwischen ihnen, wenn der nächste Aufruf von <span class="codeph"> &lt;search-context&gt; </span> eine nicht leere Kontextzeichenfolge zurückgibt (oder nicht zurückgibt). Das Attribut length setzt das Attribut length bei jedem geschlossenen <span class="codeph"> &lt;search-context&gt; </span>-Tag außer Kraft. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>5 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-if-any-context length="XX"&gt; ... /search-if-any-context&gt;  </span> </p> <p> <span class="codeph"> &lt;search-if-not-any-context&gt; ...  &lt;/search-if-not-any-context&gt; </span> </p> </td> 
   <td colname="col2"> <p>Diese Tags enthalten den HTML-Code zwischen ihnen, wenn mit dem Ergebnis eine Kontextzeichenfolge verknüpft ist (oder nicht). Das Attribut length setzt das Attribut length bei jedem geschlossenen <span class="codeph"> &lt;search-context&gt; </span>-Tag außer Kraft. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>6 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-if-score lower="XX" upper="yy" rank="dynamic/static/dynamic-raw/static-raw/final-raw"&gt; ...  &lt;/search-if-score&gt; </span> </p> <p> <span class="codeph"> &lt;search-if-not-score lower="XX" upper="yy" rank="dynamic/static"&gt; ...  &lt;/search-if-not-score&gt; </span> </p> </td> 
   <td colname="col2"> <p>Diese Tags enthalten den HTML-Code zwischen ihnen, wenn das Ergebnis des aktuellen Ergebnisses zwischen XX und YY liegt (oder nicht). Nützlich zum Hinzufügen von Aufzählungszeichen oder Grafiken, um anzuzeigen, wie relevant das Ergebnis ist. Wenn Sie ein Feld vom Typ Rang unter <span class="uicontrol"> Optionen </span> &gt; <span class="uicontrol"> Metadaten </span> &gt; <span class="uicontrol"> Definitionen </span> definiert haben, können Sie den dynamischen Seitenstrang überprüfen, indem Sie das Attribut rank auf dynamisch ( <span class="codeph"> &lt;search-if-score-rank="dynamic" lower=XX top=YY&gt; </span>) setzen. Sie können den Rang der statischen Seite überprüfen, indem Sie das Rang-Attribut auf statisch ( <span class="codeph"> &lt;search-if-score rank="static" lower=XX upper=YY&gt; </span>) setzen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>7 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-if-field name="field-name" value="value"&gt; ...  &lt;/search-if-field&gt; </span> </p> <p> <span class="codeph"> &lt;search-if-not-field name="field-name" value="value"&gt; ...  &lt;/search-if-not-field&gt; </span> </p> </td> 
   <td colname="col2"> <p>Diese erweiterten Tags enthalten den HTML-Code, je nachdem, ob das im Attribut "name"angegebene Feld Inhalt hat oder nicht. Wenn das optionale Attribut "value"angegeben ist, enthalten die Tags den HTML-Code zwischen ihnen, je nachdem, ob der angegebene Wert mit dem Wert für das Feld im aktuellen Ergebnis übereinstimmt (oder nicht übereinstimmt). Diese Tags funktionieren nur in der Ergebnisschleife (zwischen <span class="codeph"> &lt;search-results&gt; </span> und <span class="codeph"> &lt;/search-results&gt; </span>). </p> </td> 
  </tr> 
 </tbody> 
</table>

## Verankerungs-Link-Tags für die Ergebnisschleife {#section_C5FAEF520E9E42ADAD1F90651922AA02}

Siehe [Informationen zu den Tags der Ergebnisschleife](../c-appendices/c-templates.md#section_D4DC7B4560144663972E8DBC3369C629).

<table> 
 <thead> 
  <tr> 
   <th colname="col01" class="entry"> </th> 
   <th colname="col1" class="entry"> <p>Tag </p> </th> 
   <th colname="col2" class="entry"> <p>Beschreibung </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col01"> <p>3 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-link target="frame-name" hbx-enable="yes/no" hbx-linkid-name="field-name" hbx-linkid-none="text" hbx-linkid-length="XX"&gt; ...  &lt;/search-link&gt; </span> </p> </td> 
   <td colname="col2"> <p>Dieses Tag-Paar erstellt einen Ankerlink um den HTML-Code zwischen ihnen. Wenn auf den Link geklickt wird, wird die Ergebnisseite angezeigt. Ein optionales Zielgruppe-Attribut gibt das benannte Fenster an, in dem Frame-fähige Browser die Ergebnisseite anzeigen sollen. </p> <p>Setzen Sie das Attribut "hbx-enable"auf "yes", um die über HBX verfügbaren Analysen zu nutzen. Setzen Sie hbx-linkid-name auf den Namen eines Metadatenfelds, das Sie verfolgen möchten. Um beispielsweise Suchergebnisse nach SKU-Nummer zu verfolgen, setzen Sie hbx-linkid-name auf den Namen des Metadatenfelds, das SKU-Informationen enthält. </p> <p>Datumsfelder werden derzeit nicht unterstützt. Der Wert von hbx-linkid-name wird an die Link-ID im generierten Anker angehängt. Der Wert des Attributs "hbx-linkid-none"wird an die Link-ID angehängt, wenn das benannte Metadatenfeld leer ist. Der Wert von hbx-linkid-length begrenzt die Anzahl der aus dem Meta-Tag abgerufenen und angezeigten Zeichen. Die Standardanzahl an Zeichen ist 12. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>2 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-smart-link target="frame-name" hbx-enable="yes/no" hbx-linkid-name="field-name" hbx-linkid-none="text" hbx-linkid-length="XX"&gt; ...  &lt;/search-smart-link&gt; </span> </p> </td> 
   <td colname="col2"> <p>Dieses Tag-Paar ähnelt dem <span class="codeph"> &lt;search-link&gt; ... &lt;/search-link&gt; </span>-Tags. Wenn auf die generierten Ankerlinks geklickt wird, wird die Ergebnisseite angezeigt, wobei jedoch ein Bildlauf zum nächsten Anker-Tag vor dem Ergebnis durchgeführt wird. Bei PDF-Verknüpfungen zeigt der Acrobat-Viewer die Seite mit dem Ergebnis an. Ein optionales Zielgruppe-Attribut gibt das benannte Fenster an, in dem Frame-fähige Browser die Ergebnisseite anzeigen sollen. </p> <p>Setzen Sie das Attribut "hbx-enable"auf "yes", um die über HBX verfügbaren Analysen zu nutzen. Setzen Sie hbx-linkid-name auf den Namen eines Metadatenfelds, das Sie verfolgen möchten. Um beispielsweise Suchergebnisse nach SKU-Nummer zu verfolgen, setzen Sie hbx-linkid-name auf den Namen des Metadatenfelds, das SKU-Informationen enthält. </p> <p>Datumsfelder werden derzeit nicht unterstützt. Der Wert von hbx-linkid-name wird an die Link-ID im generierten Anker angehängt. Der Wert des Attributs "hbx-linkid-none"wird an die Link-ID angehängt, wenn das benannte Metadatenfeld leer ist. Der Wert von hbx-linkid-length begrenzt die Anzahl der aus dem Meta-Tag abgerufenen und angezeigten Zeichen. Die Standardanzahl an Zeichen ist 12. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>1 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-if-link-extension&gt; ...  &lt;/search-if-link-extension&gt; </span> </p> <p> <span class="codeph"> &lt;search-if-not-link-extension&gt; ...  &lt;/search-if-not-link-extension&gt; </span> </p> </td> 
   <td colname="col2"> <p>Diese Tags enthalten den HTML-Code zwischen ihnen, wenn ein Wertattribut eine Erweiterung angibt, die dem Ende der URL für das Ergebnis entspricht. Dieses Tag ist nützlich, um anhand der Linkerweiterung eine Grafik in die Suchergebnisse aufzunehmen. Das value-Attribut ist eine Liste einer oder mehrerer Erweiterungen (durch Leerzeichen getrennt) wie folgt: VALUE=".pdf" oder VALUE=".html .htm". </p> </td> 
  </tr> 
 </tbody> 
</table>

## Bedingte Tags für Schleifenposition {#section_E0C29DDA09E043C9A396F36334F05EBB}

Die folgenden Tags enthalten den Text zwischen ihnen bedingt. Sie können nur innerhalb der Tags &quot;Schleife&quot;angezeigt werden: &lt; `search-results>` und `<search-field-values>`. Sie werden verwendet, um die Position des aktuellen Ergebnisses innerhalb der Ergebnismenge zu testen.

Siehe [Informationen zu den Tags der Ergebnisschleife](../c-appendices/c-templates.md#section_D4DC7B4560144663972E8DBC3369C629).

<table> 
 <thead> 
  <tr> 
   <th colname="col01" class="entry"> </th> 
   <th colname="col1" class="entry"> <p>Tag </p> </th> 
   <th colname="col2" class="entry"> <p>Beschreibung </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col01"> <p>1 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-if-first&gt; ...  &lt;/search-if-first&gt; </span> </p> <p> <span class="codeph"> &lt;search-if-not-first&gt; ...  &lt;/search-if-not-first&gt; </span> </p> </td> 
   <td colname="col2"> <p>Diese Tags enthalten den Text zwischen ihnen, wenn das aktuelle Ergebnis das erste Ergebnis auf der Seite ist (oder nicht) (wenn es innerhalb von <span class="codeph"> </span> &lt;a1/&gt; verwendet wird) oder der erste Feldwert (wenn es innerhalb von <span class="codeph"> </span> &lt;a3/&gt; verwendet wird). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>2 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-if-last&gt; ...  &lt;/search-if-last&gt; </span> </p> <p> <span class="codeph"> &lt;search-if-not-last&gt; ...  &lt;/search-if-not-last&gt; </span> </p> </td> 
   <td colname="col2"> <p>Diese Tags enthalten den Text zwischen ihnen, wenn das aktuelle Ergebnis das letzte Ergebnis auf der Seite ist (oder nicht) (wenn es innerhalb von <span class="codeph"> </span> &lt;a1/&gt; verwendet wird) oder der letzte Feldwert (wenn es innerhalb von <span class="codeph"> </span> &lt;a3/&gt; verwendet wird). Dieses Tag kann verwendet werden, um eine Trennlinie zwischen den Ergebnissen einzufügen. Dadurch wird beispielsweise ein <span class="codeph"> &lt;hr&gt; </span>-Tag zwischen den Ergebnissen eingefügt: </p> <p> <code class="syntax html"> &lt;search-results&gt; 
      &nbsp;&nbsp;&nbsp;&lt;search-lt&gt;tr&lt;search-if-alt&gt;&nbsp;class="alt"&lt;/search-if-alt&gt;&lt;search-gt&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;td&gt;&lt;search-url&gt;&lt;/td&gt; 
      &nbsp;&nbsp;&nbsp;&lt;/tr&gt; 
      &lt;/search-results&gt; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>3 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-if-inner&gt; ...  &lt;/search-if-inner&gt; </span> </p> <p> <span class="codeph"> &lt;search-if-not-inner&gt; ...  &lt;/search-if-not-inner&gt; </span> </p> </td> 
   <td colname="col2"> <p>Diese Tags enthalten den Text zwischen ihnen, wenn das aktuelle Ergebnis weder das erste noch das letzte Ergebnis auf der Seite ist (wenn es innerhalb von <span class="codeph"> </span> &lt;a1/&gt; verwendet wird) oder nicht der erste oder letzte Feldwert ist (wenn es innerhalb von <span class="codeph"> </span> &lt;a3/&gt; verwendet wird). Die Nicht-Version des Tags prüft, ob das Ergebnis das erste oder das letzte ist. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>4 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-if-alt&gt; ...  &lt;/search-if-alt&gt; </span> </p> <p> <span class="codeph"> &lt;search-if-not-alt&gt; ...  &lt;/search-if-not-alt&gt; </span> </p> </td> 
   <td colname="col2"> <p>Diese Tags beinhalten den Text zwischen ihnen, wenn das aktuelle Ergebnis ein alternatives Ergebnis auf der Seite ist (oder nicht) (wenn es innerhalb von <span class="codeph"> </span> &lt;a1/&gt; verwendet wird) oder ein alternativer Feldwert (wenn es innerhalb von <span class="codeph"> </span> &lt;a3/&gt; verwendet wird). Die "alternativen"Ergebnisse sind das zweite, vierte, sechste usw. auf der Seite. In diesem Beispiel wird eine andere Klasse auf alternative Tabellenzeilen angewendet. Beachten Sie die Verwendung von <span class="codeph"> &lt;search-lt&gt; </span> und <span class="codeph"> &lt;search-gt&gt; </span>, damit das <span class="codeph"> &lt;search-if-alt&gt; </span>-Tag "innerhalb" des <span class="codeph"> &lt;tr&gt; </span>-Tags platziert werden kann. </p> <p> <code class="syntax html"> &nbsp;&nbsp;&nbsp;&nbsp;&lt;search-results&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;search-lt&gt;tr&lt;search-if-alt&gt;&nbsp;class="alt"&lt;/search-if-alt&gt;&lt;search-gt&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;td&gt;&lt;search-url&gt;&lt;/td&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/tr&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&lt;/search-results&gt; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>5 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-if-even&gt; ...  &lt;/search-if-even&gt; </span> </p> <p> <span class="codeph"> &lt;search-if-not-even&gt; ...  &lt;/search-if-not-even&gt; </span> </p> </td> 
   <td colname="col2"> <p>Diese Tags beinhalten den Text zwischen ihnen, wenn das aktuelle Ergebnis ein geraden Ergebnis ist (oder nicht) (wenn es innerhalb von <span class="codeph"> </span> verwendet wird) oder ein gerader Feldwert (wenn es innerhalb von <span class="codeph"> </span> &lt;a3/&gt; verwendet wird). Ein Suchergebnis wird geradezu nummeriert, wenn der <span class="codeph"> &lt;search-index&gt; </span>-Wert gleich ist. Mit anderen Worten, wenn ihre Position innerhalb der gesamten Ergebnismenge gleich ist. Dies kann sich von <span class="codeph"> &lt;search-if-alt&gt; </span> unterscheiden, das die Position eines Ergebnisses auf der Seite testet, nicht innerhalb der gesamten Ergebnismenge. Die folgenden beiden Tabellen illustrieren den Unterschied: </p> </td> 
  </tr> 
 </tbody> 
</table>

### Erste Seite, sp_n=1

<table>  
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Index </p> </th> 
   <th colname="col2" class="entry"> <p>Ergebnis </p> </th> 
   <th colname="col3" class="entry"> <p>Selbst? </p> </th> 
   <th colname="col4" class="entry"> <p>Alt? </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>3 </p> </td> 
   <td colname="col2"> <p>Erstes Ergebnis </p> </td> 
   <td colname="col3"> <p>Nein </p> </td> 
   <td colname="col4"> <p>Nein </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>2 </p> </td> 
   <td colname="col2"> <p>Zweites Ergebnis </p> </td> 
   <td colname="col3"> <p>Ja </p> </td> 
   <td colname="col4"> <p>Ja </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>1 </p> </td> 
   <td colname="col2"> <p>Drittes Ergebnis </p> </td> 
   <td colname="col3"> <p>Nein </p> </td> 
   <td colname="col4"> <p>Nein </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>4 </p> </td> 
   <td colname="col2"> <p>Viertes Ergebnis </p> </td> 
   <td colname="col3"> <p>Ja </p> </td> 
   <td colname="col4"> <p>Ja </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>5 </p> </td> 
   <td colname="col2"> <p>Fünftes Ergebnis </p> </td> 
   <td colname="col3"> <p>Nein </p> </td> 
   <td colname="col4"> <p>Nein </p> </td> 
  </tr> 
 </tbody> 
</table>

### Später Seite, sp_n=10

<table>  
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Index </p> </th> 
   <th colname="col2" class="entry"> <p>Ergebnis </p> </th> 
   <th colname="col3" class="entry"> <p>Selbst? </p> </th> 
   <th colname="col4" class="entry"> <p>Alt? </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>10 </p> </td> 
   <td colname="col2"> <p>Zehntes Ergebnis </p> </td> 
   <td colname="col3"> <p>Ja </p> </td> 
   <td colname="col4"> <p>Nein </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>11 </p> </td> 
   <td colname="col2"> <p>Elftes Ergebnis </p> </td> 
   <td colname="col3"> <p>Nein </p> </td> 
   <td colname="col4"> <p>Ja </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>12 </p> </td> 
   <td colname="col2"> <p>Zwölftes Ergebnis </p> </td> 
   <td colname="col3"> <p>Ja </p> </td> 
   <td colname="col4"> <p>Nein </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>13 </p> </td> 
   <td colname="col2"> <p>Dreizehntes Ergebnis </p> </td> 
   <td colname="col3"> <p>Nein </p> </td> 
   <td colname="col4"> <p>Ja </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>14 </p> </td> 
   <td colname="col2"> <p>Vierzehntes Ergebnis </p> </td> 
   <td colname="col3"> <p>Ja </p> </td> 
   <td colname="col4"> <p>Nein </p> </td> 
  </tr> 
 </tbody> 
</table>

Beachten Sie schließlich, dass `<search-if-even>` für Suchfeldwerte immer mit `<search-if-alt>` identisch ist, da Feldwerte nicht paginiert werden.

## Liste der Feldwerte {#section_D3298B5F976447DBA0032B883DCC91B1}

Die folgenden erweiterten Tags geben Feldwerte und zugehörige Daten aus dem gesamten Satz der Suchergebnisse aus. Diese Tags liefern nur die Ausgabe für Felder, die von den CGI-Parametern `sp-sfvl-field` in der Abfrage &quot;Suchen&quot;angegeben werden.

<table> 
 <thead> 
  <tr> 
   <th colname="col01" class="entry"> </th> 
   <th colname="col1" class="entry"> <p>Tag </p> </th> 
   <th colname="col2" class="entry"> <p>Beschreibung </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col01"> <p>3 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-field-value-list name="field-name" quotes="yes/no" commas="yes/no" data="values/counts/results" separator="X" sortby="none/values/counts/results" max-items="XX" date-format="date-format-string" gmt="yes/no" language="0/language-id" encoding="html/javascript/json/perl/url/none"&gt; </span> </p> </td> 
   <td colname="col2"> <p>Dieses Tag zeigt eine Liste mit eindeutigen Feldwerten, Wertzählungen oder Ergebniszahlen innerhalb des gesamten Ergebnissatzes an. </p> <p>Dieses Tag liefert nur die Ausgabe für Felder, die von den CGI-Parametern <span class="codeph"> sp_sfvl_field </span> in der Abfrage "Suchen"angegeben werden. Das optionale Attribut "Anführungszeichen"steuert, ob die einzelnen Elemente von Anführungszeichen (oder von einfachen Anführungszeichen, wenn encoding=perl) umgeben sind. Der Standardwert von "Anführungszeichen"ist "Ja". Das optionale Attribut "Kommas"steuert, ob die einzelnen Elemente durch Kommas getrennt werden. Der Standardwert von "commas"ist "yes". Das optionale Attribut "data"steuert, ob jeder eindeutige Feldwert ausgegeben wird (data="values"), die Gesamtanzahl der einzelnen eindeutigen Feldwerte ausgegeben wird (data="counts") oder die Anzahl der Ergebnisse, die jeden eindeutigen Wert enthalten (data="results"), ausgegeben wird. Der Standardwert von "data"ist "values". Bei Feldern ohne Liste sind data="counts" und data="results" identisch. Das Attribut "separator"definiert das einzelne Zeichen oder Trennzeichen, das zwischen den Werten der Ausgabe eingefügt werden soll. Das optionale Attribut "sortby" steuert die Reihenfolge der Ausgabe; sortby="none" bedeutet keine bestimmte Reihenfolge, sortby="values" bedeutet Sortierung nach Feldwerten (in aufsteigender oder absteigender Reihenfolge entsprechend der Sorting-Eigenschaft des Felds), sortby="counts" bedeutet Sortierung in absteigender Reihenfolge der Feldwerte und sortby="results" bedeutet Sortierung in absteigender Reihenfolge der Anzahl der Ergebnisse, die jeden Wert enthalten. </p> <p>Beachten Sie, dass sortby="counts" und sortby="results" für Felder ohne Liste gleichwertig sind. Das optionale Attribut "max-items"begrenzt die Anzahl der auszugebenden Elemente. Der Standardwert von "max-items"ist -1, d. h. "output all items". </p> <p>Es gibt eine absolute Grenze von 100 für max. Elemente. Die Attribute "date-format", "gmt"und "language"sind nur relevant, wenn der Inhaltstyp des angegebenen Felds "date"ist. Das Attribut "date-format"nimmt eine Datumsformat-Zeichenfolge im UNIX-Stil wie "%A", %B %d, %Y"(für "Montag, 25. Juli 2016"). "gmt"ist standardmäßig "yes"und steuert, ob der Zeitabschnitt der Datums-Zeichenfolge in GMT ("yes") oder in der Zeitzone des Kontos ("no") ausgegeben werden soll. </p> <p>Siehe <a href="../c-appendices/c-templates.md#section_4BBDBBEF2B96414497617CD4B52D96E4" type="section" format="dita" scope="local"> Datumsformat-Zeichenfolgen</a>. </p> <p>Das Attribut "language"steuert die Konventionen für Sprache und Gebietsschema der Ausgabedatumszeichenfolge. "0" (Standard) bedeutet "Kontosprache verwenden". Jeder andere "language"-Wert wird als spezifischer Sprachbezeichner interpretiert, z. B. bedeutet "en_US" "Englisch (USA)". Das optionale Attribut "encoding"steuert, ob die Zeichen der Ausgabestrategie HTML-kodiert, JavaScript-kodiert, Perl-kodiert, URL-kodiert oder nicht kodiert sind, für die Ausgabe auf der Ergebnisseite. Der Standardwert von "encoding"ist "html". </p> <p>Siehe <a href="../c-appendices/c-templates.md#section_0490DECC00E34691ADE5A9ED90A6D911" type="section" format="dita" scope="local"> Sprachkennungen</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>2 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-field-value-list-count name="field-name" value="field-value" results="yes/no"&gt; </span> </p> </td> 
   <td colname="col2"> <p>Dieses Tag zeigt die Zählungsinformationen für eine bestimmte Liste des Suchfelds an. Es gibt drei unterschiedliche Verwendungen für dieses Tag. Wenn nur das Attribut "name"angegeben ist, gibt dieses Tag die Anzahl der eindeutigen Werte für das benannte Feld innerhalb des gesamten Ergebnissatzes aus. Wenn beide Attribute "name"und "value"angegeben werden, gibt dieses Tag entweder die Gesamtanzahl des angegebenen Werts innerhalb des gesamten Ergebnissatzes (für results="no") oder die Gesamtanzahl der Ergebnisse mit dem angegebenen Wert im gesamten Ergebnissatz (für results="yes") aus. Der Standardwert von "results"ist "no". Hinweis: Bei Feldern ohne Liste sind results="yes" und results="no" gleichwertig. Der Wert von "results"wird ignoriert, wenn das Attribut "value"nicht angegeben wird. Dieses Tag liefert nur die Ausgabe für Felder, die von den CGI-Parametern <span class="codeph"> sp-sfvl-field </span> in der Abfrage "Suchen"angegeben werden. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>3 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-if-field-value-list-count name="field-name" value="field-value"&gt; ...  &lt;/search-if-field-value-list-count&gt; </span> </p> <p> <span class="codeph"> &lt;search-if-not-field-value-list-count name="field-name" value="field-value"&gt; ...  &lt;/search-if-not-field-value-list-count&gt; </span> </p> </td> 
   <td colname="col2"> <p>Diese Tags zeigen den HTML-Code zwischen ihnen an, wenn der äquivalente Aufruf von <span class="codeph"> &lt;search-field-value-Liste-count name="field-name" value="field-value"&gt; </span> mit den angegebenen Attributen einen Wert größer als null zurückgibt (oder nicht). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>4 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-if-single-field-value-list-count name="field-name"&gt; ...  &lt;/search-if-single-field-value-list-count&gt; </span> </p> </td> 
   <td colname="col2"> <p>Diese Tags zeigen den Inhalt zwischen ihnen an, wenn der entsprechende Aufruf von <span class="codeph"> &lt;search-field-value-Liste-count name="field-name" value="field-value"&gt; </span> mit den angegebenen Attributen einen einzelnen Wert zurückgibt (oder nicht). Dies wird in der Regel verwendet, wenn ein Konto Facetten-Slots verwendet. Bei Facettensteckplätzen ist es normalerweise nur sinnvoll, den Wertzeitpunkt anzuzeigen, wenn der zugehörige Namenseinschub ein einzelnes Element enthält. Diese Prüfung in der Transportvorlage ist effizienter als in der Präsentationsebene. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Feldwert-Liste-Schleifentags {#section_0717FA09F0FC449CB916883B0500A60E}

Die folgenden erweiterten Tags zählen Feldwerte und zugehörige Daten aus dem gesamten Satz von Suchergebnissen mit einem Schleifenkonstrukt auf und geben sie aus. Diese Tags liefern nur die Ausgabe für Felder, die von den CGI-Parametern `sp-sfvl-field` in der Abfrage &quot;Suchen&quot;angegeben werden.

<table> 
 <thead> 
  <tr> 
   <th colname="col01" class="entry"> </th> 
   <th colname="col1" class="entry"> <p>Tag </p> </th> 
   <th colname="col2" class="entry"> <p>Beschreibung </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col01"> <p>1 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-field-values name="field-name" sortby="none/values/counts/results" max-items="XX"&gt; ...  &lt;/search-field-values&gt; </span> </p> </td> 
   <td colname="col2"> <p>Dieses Tag erstellt eine Schleife zum Aufzählen von Feldwerten und zugehörigen Daten für ein bestimmtes Feld innerhalb des gesamten Ergebnissatzes. Verschachteln Sie dieses Tag nicht in einem anderen <span class="codeph"> &lt;search-field-values&gt; </span>-Tag. Das Attribut "name"gibt den Namen des Felds an, das die aufzuzählenden Werte enthält. Das optionale Attribut "sortby"steuert die Reihenfolge der Auflistungen: "none"bedeutet keine bestimmte Reihenfolge, "werte"die Sortierung nach Feldwerten (in auf- oder absteigender Reihenfolge gemäß der Sorting-Eigenschaft des Felds), sortby="counts" die Sortierung in absteigender Reihenfolge der Feldwerte und sortby="results" die Sortierung in absteigender Reihenfolge der Anzahl der Ergebnisse, die jeden Wert enthalten. </p> <p>Beachten Sie, dass sortby="counts" und sortby="results" für Felder ohne Liste gleichwertig sind. . Das optionale Attribut "max-items"begrenzt die Anzahl der Iterationen auf den angegebenen Wert. Der Standardwert für "max-items"ist -1, d. h. "enumerate all values". </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>2 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-field-value date-format="date-format-string" encoding="html/javascript/json/perl/url/none" gmt="yes/no" language="0/language-id"&gt; </span> </p> </td> 
   <td colname="col2"> <p>Dieses Tag gibt den Feldwert für die aktuelle &lt;search-field-values&gt; Schleifeniteration aus. Dieses Tag ist nur innerhalb einer <span class="codeph"> &lt;search-field-values&gt; </span>-Schleife gültig. Die Attribute "date-format", "gmt"und "language"sind nur relevant, wenn der Inhaltstyp des im umschließenden &lt;search-field-values&gt;-Tag angegebenen Feldnamens "date"ist. Das Attribut "date-format"nimmt eine Datumsformat-Zeichenfolge im UNIX-Stil wie "%A", %B %d, %Y"(für "Montag, 25. Juli 2020"). </p> <p>Siehe <a href="../c-appendices/c-templates.md#section_4BBDBBEF2B96414497617CD4B52D96E4" type="section" format="dita" scope="local"> Datumsformat-Zeichenfolgen</a>. </p> <p>Das optionale Attribut "encoding"steuert, ob die Zeichen der Ausgabestrategie HTML-kodiert, JavaScript-kodiert, Perl-kodiert, URL-kodiert oder nicht kodiert sind, für die Ausgabe auf der Ergebnisseite. Der Standardwert von "encoding"ist "none". Normalerweise müssen Sie das Kodierungsattribut nicht angeben. "gmt"ist standardmäßig "yes"und steuert, ob der Zeitabschnitt der Datums-Zeichenfolge in GMT ("yes") oder in der Zeitzone des Kontos ("no") ausgegeben werden soll. Das Attribut "language"steuert die Konventionen für Sprache und Gebietsschema der Ausgabedatumszeichenfolge. "0" (Standard) bedeutet "Kontosprache verwenden". Jeder andere "language"-Wert wird als spezifischer Sprachbezeichner interpretiert, z. B. bedeutet "en_US" "Englisch (USA)". </p> <p>Siehe <a href="../c-appendices/c-templates.md#section_0490DECC00E34691ADE5A9ED90A6D911" type="section" format="dita" scope="local"> Sprachkennungen</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>3 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-field-value-count results="yes/no"&gt; </span> </p> </td> 
   <td colname="col2"> <p>Dieses Tag gibt die mit der aktuellen <span class="codeph"> &lt;search-field-values&gt; </span>-Schleifenitation verknüpfte Anzahl aus. Die Ausgabenanzahl ist entweder die Anzahl der Ergebnisse im gesamten Ergebnissatz, der den Feldwert enthält (results="yes"), oder die Gesamtanzahl für den Feldwert im gesamten Ergebnissatz. Der Standardwert von "results"ist "no". </p> <p>Bei Feldern ohne Liste sind results="yes" und results="no" gleichwertig. Dieses Tag ist nur innerhalb einer <span class="codeph"> &lt;search-field-values&gt; </span>-Schleife gültig. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>4 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-field-value-counter&gt; </span> </p> </td> 
   <td colname="col2"> <p>Dieses Tag gibt den Ordinalzähler für die aktuelle <span class="codeph"> &lt;search-field-values&gt; </span>-Schleifenitation aus. Dieses Tag ist nur innerhalb einer <span class="codeph"> &lt;search-field-values&gt; </span>-Schleife gültig. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Vorschlagen von Tags {#section_C28EB8B4F7DC4E278A0F143BCFEEB1AC}

Suggest bietet einen benutzerfreundlichen &quot;Meinten Sie?&quot; Dienst zum Vorschlagen alternativer Suchbegriffe. Wenn ein Benutzer beispielsweise einen Suchbegriff falsch geschrieben hat, kann Suggest dem Benutzer helfen, Ergebnisse zu finden, indem er eine korrekte Schreibweise vorschlägt. Das System kann auch zugehörige Suchbegriffe vorschlagen, die einem Benutzer helfen, Ergebnisse zu erkennen. Beim Generieren von Vorschlägen verwendet der Suggest-Dienst zwei Wörterbücher: eine auf Basis der Kontosprache (eingestellt unter **[!UICONTROL Indexing]** > **[!UICONTROL Words and Languages]** > **[!UICONTROL Language]**) und die andere auf Basis der Suchbegriffe im Kontoindex.

>[!NOTE]
>
>Der Suggest-Dienst funktioniert nicht für Chinesisch, Japanisch oder Koreanisch.

<table> 
 <thead> 
  <tr> 
   <th colname="col01" class="entry"> </th> 
   <th colname="col1" class="entry"> <p>Tag </p> </th> 
   <th colname="col2" class="entry"> <p>Beschreibung </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col01"> <p>3 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-if-suggestions&gt; ...  &lt;/search-if-suggestions&gt; </span> </p> </td> 
   <td colname="col2"> <p>Umschließen Sie diese Tags mit beliebigen Vorlagen-Tags vom Typ "Vorschlagen", wie <span class="codeph"> &lt;search-recommendations&gt; </span>, <span class="codeph"> &lt;search-recommendations-link&gt; </span> usw. Wenn die Suche Vorschläge generiert, gibt die Suchmaschine alles zwischen dem Tag open und close aus und verarbeitet alles. Wenn die Suche keine Vorschläge generiert, wird keiner der verschachtelten Inhalte ausgegeben. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>2 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-suggestions&gt; ...  &lt;/search-suggestions&gt; </span> </p> </td> 
   <td colname="col2"> <p>Dieses Tag generiert die "Suggest"-Schleife, die eine Liste von vorgeschlagenen Suchbegriffen enthält (z. B. "beabsichtigen", "beabsichtigen" und "beabsichtigt" für eine Abfrage, die ursprünglich als "beabsichtigte" eingegeben wurde). Bei der Generierung der Liste von Begriffen wiederholt die Suchmaschine verschachtelte HTML- und/oder Vorlagen-Tags bis zum Fünffachen, was der maximalen Anzahl von Vorschlägen entspricht. Verwenden Sie das Attribut count, um die Anzahl der generierten Vorschläge anzugeben (zwischen 0 und 5). </p> <p>Das <span class="codeph"> &lt;search-recommendations&gt; </span>-Tag kann mehrmals auf der Seite angezeigt werden, um die Liste der Vorschläge zu wiederholen. Mehrere Vorschläge werden nach der Anzahl der Ergebnisse sortiert, die die einzelnen Erträge erbringen. </p> <p>Verschachteln Sie das <span class="codeph"> &lt;search-recommendations&gt; </span>-Tag zwischen open und close <span class="codeph"> &lt;search-if-recommendations&gt; </span>-Tags. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>3 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-suggestion-link&gt; ...  &lt;/search-suggestion-link&gt; </span> </p> </td> 
   <td colname="col2"> <p>Dieses Tag generiert eine Verknüpfung zur ursprünglichen Suchbegriff-Abfrage, wobei der ausgewählte vorgeschlagene Suchbegriff anstelle des ursprünglichen Begriffs verwendet wird. Das Tag akzeptiert und druckt einfach jedes beliebige HTML-Attribut wie Klasse, Zielgruppe und Stil aus. Das Tag kann auch ein URL-Attribut akzeptieren, dessen Wert als Basis-URL für den generierten Link verwendet wird. Die Tags können nur innerhalb der <span class="codeph"> &lt;search-recommendations&gt; </span>-Schleife angezeigt werden. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>4 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-suggestion-text /&gt; </span> </p> </td> 
   <td colname="col2"> <p>Dieses Tag gibt den derzeit vorgeschlagenen Begriff für die Abfrage aus (z. B. "planen"für eine Abfrage, die ursprünglich als "beabsichtigte"eingegeben wurde). Das Tag hat keine Attribute und kann nur in der <span class="codeph"> &lt;search-recommendations&gt; </span>-Schleife angezeigt werden. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>5 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-if-not-suggestions&gt; ...  &lt;/search-if-not-suggestions&gt; </span> </p> </td> 
   <td colname="col2"> <p>Wenn die Suche keine Vorschläge generiert, gibt die Suchmaschine alles zwischen dem Tag open und close aus und verarbeitet alles. Wenn die Suche Vorschläge generiert, wird keiner der verschachtelten Inhalte ausgegeben. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>6 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-if&gt; ...  &lt;/search-if&gt; </span> </p> </td> 
   <td colname="col2"> <p>Diese bedingten Tags enthalten den HTML-Code zwischen ihnen, je nachdem, ob der vorgeschlagene Begriff der erste Begriff in der Vorschlagsschleife ist. Die Tags müssen zwischen den Tags open und close <span class="codeph"> &lt;search-recommendations&gt; </span> stehen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>7 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-if&gt; ...  &lt;/search-if&gt; </span> </p> </td> 
   <td colname="col2"> <p>Diese bedingten Tags enthalten den HTML-Code zwischen ihnen, je nachdem, ob der vorgeschlagene Begriff der letzte Begriff in der Vorschlagsschleife ist. Die Tags müssen zwischen den Tags open und close <span class="codeph"> &lt;search-recommendations&gt; </span> stehen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>8 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-suggestion-index&gt; </span> </p> </td> 
   <td colname="col2"> <p>Dieses Tag gibt den numerischen Index des aktuellen vorgeschlagenen Suchbegriffs zurück. Das Tag muss zwischen den Tags open und close <span class="codeph"> &lt;search-recommendations&gt; </span> stehen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>9 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-suggestion-total&gt; </span> </p> </td> 
   <td colname="col2"> <p>Dieses Tag gibt die Gesamtanzahl der erstellten vorgeschlagenen Suchbegriffe zurück. Das Tag muss zwischen den Tags open und close <span class="codeph"> &lt;search-recommendations&gt; </span> stehen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>10 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-suggestion-result-count&gt; </span> </p> </td> 
   <td colname="col2"> <p>Dieses Tag gibt die Gesamtanzahl der Ergebnisse für den vorgeschlagenen Suchbegriff zurück. Das Tag muss zwischen den Tags open und close <span class="codeph"> &lt;search-recommendations&gt; </span> stehen. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Vorlagen-Zeichenfolgen-Tags {#section_67E3D529661F4F03A1FF469D9D658CAF}

Die folgenden Tags geben an diesem Punkt in der Vorlage eine Zeichenfolge in den HTML-Code aus.

<table> 
 <thead> 
  <tr> 
   <th colname="col01" class="entry"> </th> 
   <th colname="col1" class="entry"> <p>Tag </p> </th> 
   <th colname="col2" class="entry"> <p>Beschreibung </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col01"> <p>3 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-body&gt; </span> </p> </td> 
   <td colname="col2"> <p>Das HTML-Body-Tag mit allen Einstellungen für die Farbe des Suchlinks, die vom Abschnitt "Grundlegendes Aussehen"unter dem Link "Vorlage"festgelegt werden. hinzufügen Sie diesem Tag ein Hintergrundattribut, um Hintergrundbilder auf der Ergebnisseite anzuzeigen. Alle diesem Tag hinzugefügten Farbattribute setzen die Einstellungen für die Farbe des Suchlinks außer Kraft, die im Abschnitt "Grundlegender Look"festgelegt werden. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>2 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-header&gt; </span> </p> </td> 
   <td colname="col2"> <p>Der HTML-Code für die Kopfzeile der Suchergebnisse, wie im Abschnitt "Grundlegender Look"unter dem Link "Vorlage"festgelegt. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>3 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-cdata&gt; ...  &lt;/search-cdata&gt; </span> </p> </td> 
   <td colname="col2"> <p>Die Tags search-data werden durch ihre XML-Entsprechungen ersetzt: <span class="codeph"> &lt;search-cdata&gt; </span> wird durch <span class="codeph"> &lt;![CDATA[" und das &lt;/search-data&gt; </span>-Tag werden durch " <span class="codeph"> ]]&gt; </span>"ersetzt. Ein XML-Parser analysiert keine Informationen zwischen dem open- und close-Tag. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>4 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-query query-number="XX" encoding="html/javascript/json/perl/url/none"&gt; </span> </p> </td> 
   <td colname="col2"> <p>Die Abfrage, die der Besucher eingegeben hat. Das erweiterte, optionale Attribut "Abfrage-Nummer"steuert, welche Zeichenfolge für nummerierte Abfragen von diesem Tag ausgegeben wird. Beispiel: <span class="codeph"> &lt;search-Abfrage Abfrage-number=1&gt; </span> gibt den Inhalt des Parameters <span class="codeph"> sp_q_1 </span> cgi aus. Wenn "Abfrage-Nummer"nicht angegeben ist oder die Abfrage-Nummer "0"ist, wird die Hauptausgabe ( <span class="codeph"> sp_q </span>) ausgegeben. Das optionale Attribut "encoding"steuert, ob die Ausgabe HTML-kodiert, JavaScript-kodiert, Perl-kodiert, URL-kodiert oder nicht kodiert ist, für die Ausgabe auf der Ergebnisseite. Der Standardwert von "encoding"ist "html". Normalerweise müssen Sie das Kodierungsattribut nicht angeben. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>5 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-total&gt; </span> </p> </td> 
   <td colname="col2"> <p>Die Gesamtanzahl der Ergebnisse für diese Suche. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>6 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-count&gt; </span> </p> </td> 
   <td colname="col2"> <p>Die Anzahl der für diese Seite gemeldeten Ergebnisse. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>7 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-lower&gt; </span> </p> </td> 
   <td colname="col2"> <p>Die Anzahl des ersten Ergebnisses, das für diese Seite gemeldet wurde. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>8 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-upper&gt; </span> </p> </td> 
   <td colname="col2"> <p>Die Nummer des letzten Ergebnisses, das für diese Seite gemeldet wurde. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>9 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-prev-count&gt; </span> </p> </td> 
   <td colname="col2"> <p>Die Anzahl der Ergebnisse, die für die vorherige Seite gemeldet wurden. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>10 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-next-count&gt; </span> </p> </td> 
   <td colname="col2"> <p>Die Anzahl der für die nächste Seite gemeldeten Ergebnisse. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>11 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-time&gt; </span> </p> </td> 
   <td colname="col2"> <p>Die Zeit in Sekunden für diese Suche. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>12 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-logo&gt; </span> </p> </td> 
   <td colname="col2"> <p>Der HTML-Code für das Suchlogo, der für Ihr Konto konfiguriert ist, sofern vorhanden. Dieses Logo ist das Bild, das der Site-Suche/dem Merchandising gutgeschrieben wird. </p> <p>Die meisten Konten haben derzeit kein Suchlogo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>13 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-collection all="name"&gt; </span> </p> </td> 
   <td colname="col2"> <p>Die Sammlung der Ergebnisse für diese Suche. Das optionale Attribut "all"wird verwendet, um den Namen der Sammlung anzugeben, die die gesamte Website darstellt. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>14 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-form&gt; ...&lt;/search-form&gt; </span> </p> </td> 
   <td colname="col2"> <p>Fügt form-Tags vom Anfang bis zum Ende ein. Fügt die Attribute für Methode und Aktion in das Tag "begin form"ein. Akzeptiert zusätzliche Attribute, einschließlich des Attributs dir="RTL" für die Sprache sowie JavaScript-bezogene Attribute "name"und "onSubmit". </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>15 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-input-account&gt; </span> </p> </td> 
   <td colname="col2"> <p>Fügt ein Formulareingabe-Tag ein, das Ihre Kontonummer angibt. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>16 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-input-gallery&gt; </span> </p> </td> 
   <td colname="col2"> <p>Fügt ein Formulareingabe-Tag ein, das die Galeriennummer angibt. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>17 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-input-query query-number="XX"&gt; </span> </p> </td> 
   <td colname="col2"> <p>Fügt ein Formulareingabe-Tag ein, das die Abfrage-Zeichenfolge angibt. Das erweiterte, optionale Attribut "Abfrage-Nummer"steuert, welche nummerierte Abfrage für das Formulareingabe-Tag verwendet wird. Beispiel: <span class="codeph"> &lt;search-input-Abfrage Abfrage-number=1&gt; </span> gibt ein Formulareingabe-Tag für die <span class="codeph"> sp_q_1 </span>-Abfrage aus. Wenn "Abfrage-Nummer"nicht angegeben ist oder "Abfrage-Nummer"den Wert "0"hat, wird ein Eingabetag für die Abfrage <span class="codeph"> sp_q </span> eingefügt. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>18 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-input-collections all="name"&gt; </span> </p> </td> 
   <td colname="col2"> <p>Fügt ein form select-Tag und das zugehörige HTML ein, um das Auswahlmenü für Sammlungen anzuzeigen. Das optionale Attribut "all"wird verwendet, um den Namen der Sammlung anzugeben, die die gesamte Website darstellt. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>19 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-lt&gt; </span> </p> </td> 
   <td colname="col2"> <p>Fügt die Ausgabe eines der Suchvorlagen-Tags in andere HTML- oder Vorlagen-Tags auf der Ergebnisseite ein. <span class="codeph"> &lt;search-lt&gt; </span> fügt ein Kleiner-als-Zeichen ein. Die Verwendung von <span class="codeph"> &lt;search-lt&gt; und </span> <span class="codeph"> &lt;search-gt&gt; </span> bietet eine Möglichkeit, der Definition eines Tags zu entkommen, sodass Sie Suchvorlagen-Tags als Attributwerte verwenden können. Wenn die Vorlage als Antwort auf eine Suche wiedergegeben wird, ersetzt ein Kleiner-als-Zeichen (&lt;) das <span class="codeph"> &lt;search-lt&gt; </span>-Tag. Beispiel: <span class="codeph"> &lt;search-link&gt; </span> entspricht <span class="codeph"> &lt;search-lt&gt;a href="&lt;search-url&gt;"&lt;search-gt&gt; </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>20 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-gt&gt; </span> </p> </td> 
   <td colname="col2"> <p>Fügt die Ausgabe eines der Suchvorlagen-Tags in andere HTML- oder Vorlagen-Tags auf der Ergebnisseite ein. <span class="codeph"> &lt;search-gt&gt; </span> fügt ein Größer-Zeichen ein. Die Verwendung von <span class="codeph"> &lt;search-lt&gt; und </span> <span class="codeph"> &lt;search-gt&gt; </span> bietet eine Möglichkeit, der Definition eines Tags zu entkommen, sodass Sie andere Vorlagen-Tags als Attributwerte verwenden können. Wenn die Vorlage als Antwort auf eine Suche wiedergegeben wird, ersetzt ein Größer-als-Zeichen (&gt;) das <span class="codeph"> &lt;search-gt&gt; </span>-Tag. Beispiel: <span class="codeph"> &lt;search-link&gt; </span> entspricht <span class="codeph"> &lt;search-lt&gt;a href="&lt;search-url&gt;"&lt;search-gt&gt; </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>21 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-param name="param-name" length="XX" encoding="html/javascript/json/perl/url/none"&gt; </span> </p> </td> 
   <td colname="col2"> <p>Gibt den Wert des cgi-Parameters mit dem Namen "param-name"aus der aktuellen Suchanfrage zurück. Das optionale Attribut "encoding"steuert, ob die Ausgabe HTML-kodiert, JavaScript-kodiert, Perl-kodiert, URL-kodiert oder nicht kodiert ist, für die Ausgabe auf der Ergebnisseite. Der Standardwert von "encoding"ist "html". Normalerweise müssen Sie das Kodierungsattribut nicht angeben. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>22 </p> </td> 
   <td colname="col1"> <p> 
     <!--NEW for S&P 8.17.0 release on October 30 2014--> <span class="codeph"> &lt;search-trace encoding="html/javascript/ json/perl/url/none"&gt; </span> </p> </td> 
   <td colname="col2"> 
    <!--<p>This global core search template tag outputs a representation of the submitted core search query, including any "fuzzy-search" query term expansions that happen by way of synonyms, sound-alikes, and so forth. </p>--> <p>Das Attribut <span class="codeph"> encoding </span> ist optional. der Standardwert ist <span class="codeph"> json </span>. </p> <p> <p>Hinweis:  Dieses Tag verfügt nur dann über eine Ausgabe, wenn <span class="codeph"> sp_trace=1 </span> mit den Hauptparametern für die Abfrage der Suche angegeben wird. </p> </p> <p>Siehe Zeile 48 in der Tabelle unter <a href="../c-appendices/c-cgiparameters.md#reference_582E85C3886740C98FE88CA9DF7918E8" format="dita" scope="local"> CGI-Parameter für die Backend-Suche</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Vorlagenankerlink-Tags {#section_3A51D27616C541E2B818CC52B2B856BA}

Die folgenden Tags führen dazu, dass ein Ankerlink den HTML-Code zwischen beiden umschließt. Wenn auf den Ankerlink geklickt wird, wird eine weitere Ergebnisseite angezeigt. Das optionale Attribut &quot;count&quot;fordert, dass viele Ergebnisse auf der Seite angezeigt werden. Wenn nicht angegeben, wird die auf der aktuellen Seite angeforderte Anzahl verwendet. Das erweiterte optionale Attribut &quot;URL&quot;steuert die Domäne, an die der zugehörige Link weitergeleitet wird. Standardmäßig ist die Domäne `https://search.atomz.com/search/`, Sie können dies jedoch mithilfe des URL-Attributs ändern.

<table> 
 <thead> 
  <tr> 
   <th colname="col01" class="entry"> </th> 
   <th colname="col1" class="entry"> <p>Tag </p> </th> 
   <th colname="col2" class="entry"> <p>Beschreibung </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col01"> <p>3 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-next URL="https://search.yourdomain.com/search/"&gt; ...  &lt;/search-next&gt; </span> </p> <p> <span class="codeph"> &lt;search-prev URL="https://search.yourdomain.com/search/"&gt; ...  &lt;/search-prev&gt; </span> </p> </td> 
   <td colname="col2"> <p>Zeigt die nächste oder vorherige Seite der Ergebnisse an. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>2 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-sort-by-date URL="https://search.yourdomain.com/search/"&gt; ...  &lt;/search-sort-by-date&gt; </span> </p> <p> <span class="codeph"> &lt;search-sort-by-score URL="https://search.yourdomain.com/search/"&gt; ...  &lt;/search-sort-by-score&gt; </span> </p> </td> 
   <td colname="col2"> <p>Sortiert die Ergebnisse nach Datum oder Relevanz. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>3 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-show-summaries URL="https://search.yourdomain.com/search/"&gt; ...  &lt;/search-show-summaries&gt; </span> </p> <p> <span class="codeph"> &lt;search-hide-summaries URL="https://search.yourdomain.com/search/"&gt; ...  &lt;/search-hide-summaries&gt; </span> </p> </td> 
   <td colname="col2"> <p>Blendet die Zusammenfassungen ein oder aus. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Vorlagen für bedingte Tags {#section_18D9BC66DE484881932FD2F7EA9D170D}

Tags, die es Ihnen ermöglichen, HTML zwischen ihnen bedingt einzuschließen.

<table> 
 <thead> 
  <tr> 
   <th colname="col01" class="entry"> </th> 
   <th colname="col1" class="entry"> <p>Tag </p> </th> 
   <th colname="col2" class="entry"> <p>Beschreibung </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col01"> <p>3 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-if-results&gt; ...  &lt;/search-if-results&gt; </span> </p> <p> <span class="codeph"> &lt;search-if-not-results&gt; ...&lt;/search-if-not-results&gt; </span> </p> </td> 
   <td colname="col2"> <p>Diese Tags enthalten HTML, wenn die aktuelle Seite Suchergebnisse enthält (oder keine). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>2 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-if-prev-count&gt; ...  &lt;/search-if-prev-count&gt; </span> </p> <p> <span class="codeph"> &lt;search-if-not-prev-count&gt; ...  &lt;/search-if-not-prev-count&gt; </span> </p> <p> <span class="codeph"> &lt;search-if-next-count&gt; ...  &lt;/search-if-next-count&gt; </span> </p> <p> <span class="codeph"> &lt;search-if-not-next-count&gt; ...  &lt;/search-if-not-next-count&gt; </span> </p> </td> 
   <td colname="col2"> <p>Diese Tags enthalten HTML, wenn der vorherigen oder der nächsten Seite irgendein (oder keines) Ergebnis zugeordnet ist. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>3 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-if-sort-by-score&gt; ...  &lt;/search-if-sort-by-score&gt; </span> </p> <p> <span class="codeph"> &lt;search-if-not-sort-by-score&gt; ...  &lt;/search-if-not-sort-by-score&gt; </span> </p> <p> <span class="codeph"> &lt;search-if-sort-by-date&gt; ...  &lt;/search-if-sort-by-date&gt; </span> </p> <p> <span class="codeph"> &lt;search-if-not-sort-by-date&gt; ...  &lt;/search-if-not-sort-by-date&gt; </span> </p> </td> 
   <td colname="col2"> <p>Diese Tags enthalten HTML, wenn die aktuelle Seite nach Relevanz oder Datum sortiert ist oder nicht. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>4 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-if-show-summaries&gt; ...  &lt;/search-if-show-summaries&gt; </span> </p> <p> <span class="codeph"> &lt;search-if-hide-summaries&gt; ...  &lt;/search-if-hide-summaries&gt; </span> </p> </td> 
   <td colname="col2"> <p>Diese Tags enthalten HTML, wenn die aktuelle Seite Zusammenfassungen ein- oder ausblendet. Mit diesen Tags können Sie einen beliebigen Teil des Suchergebnisses ein- oder ausschließen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>5 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-if-input-collections&gt; ...  &lt;/search-if-input-collections&gt; </span> </p> <p> <span class="codeph"> &lt;search-if-not-input-collections&gt; ...  &lt;/search-if-not-input-collections&gt; </span> </p> </td> 
   <td colname="col2"> <p>Diese Tags enthalten HTML, wenn eine Sammlung in der Generierung der Suchergebnisse für die aktuelle Seite angegeben wurde. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>6 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-if-advanced&gt; ...  &lt;/search-if-advanced&gt; </span> </p> <p> <span class="codeph"> &lt;search-if-not-advanced&gt; ...  &lt;/search-if-not-advanced&gt; </span> </p> </td> 
   <td colname="col2"> <p>Diese Tags beinhalten HTML, wenn der CGI-Parameter <span class="codeph"> sp_advanced=1 </span> für die Abfrage der Suche angegeben wurde. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>7 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-if-bad-param name="parameter-name"&gt; ...  &lt;/search-if-bad-param&gt; </span> </p> <p> <span class="codeph"> &lt;search-if-not-bad-param name="parameter-name"&gt; ...  &lt;/search-if-not-bad-param&gt; </span> </p> </td> 
   <td colname="col2"> <p>Diese Tags schließen den HTML-Code zwischen ihnen ein oder aus, wenn der angegebene Parameter ungültig ist oder nicht. </p> <p>Derzeit wird nur der Parameter <span class="codeph"> sp_q_location[_#] </span> unterstützt. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>8 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-if-param name="param-name" value="param-value"&gt; ...  &lt;/search-if-param&gt; </span> </p> <p> <span class="codeph"> &lt;search-if-not-param name="param-name" value="param-value"&gt; ...  &lt;/search-if-not-param&gt; </span> </p> </td> 
   <td colname="col2"> <p>Diese erweiterten Tags enthalten den HTML-Code zwischen ihnen, je nachdem, ob der im Attribut "name"angegebene CGI-Parameter den im Attribut "value"angegebenen Wert hat. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>9 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-if-sort-by-field name="field-name"&gt; ...  &lt;/search-if-sort-by-field&gt; </span> </p> <p> <span class="codeph"> &lt;search-if-not-sort-by-field name="field-name"&gt; ...  &lt;/search-if-not-sort-by-field&gt; </span> </p> </td> 
   <td colname="col2"> <p>Diese erweiterten Tags enthalten den HTML-Code zwischen ihnen, wenn die aktuelle Seite nach dem angegebenen Feldnamen sortiert ist oder nicht. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Vorlagenformularsteuerungs-Tags {#section_45AFC414ACA74825B72FEAA8456F8DD2}

Tags, mit denen Sie den Standardauswahlstatus für Kontrollkästchen, Optionsfelder und Listen innerhalb eines `<form>` in der Suchvorlage steuern können.

<table> 
 <thead> 
  <tr> 
   <th colname="col01" class="entry"> </th> 
   <th colname="col1" class="entry"> <p>Tag </p> </th> 
   <th colname="col2" class="entry"> <p>Beschreibung </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col01"> <p>1 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-input&gt; </span> </p> </td> 
   <td colname="col2"> <p>Wird in einer Vorlage anstelle eines <span class="codeph"> &lt;input&gt; </span>-Tags verwendet. Wenn das Tag in den Browser geschrieben wird, ersetzt das Wort <span class="codeph"> input </span> <span class="codeph"> search-input </span> und alle anderen Informationen im Tag werden unverändert ausgegeben. Wenn außerdem der im Tag angegebene Name <span class="codeph"> als CGI-Parameter aufgelistet ist und der im Tag angegebene <span class="codeph">-Wert </span> den Wert für diesen CGI-Parameter darstellt, wird am Ende des Tags das Wort <span class="codeph">, das </span> markiert ist, hinzugefügt. </span> Auf diese Weise können Sie automatisch den Standard-Optionsfeld- oder Kontrollkästchen-Status in Ihrem Suchergebnis mit der aktuellen Abfrage identisch machen. </p> <p>Der HTML-Code für ein Kontrollkästchen könnte z. B. wie folgt aussehen: </p> <p> <span class="codeph"> &lt;input type="checkbox" name="sp_w" value="exact"&gt;Keine Übereinstimmung mit Geräuschen  </span> </p> <p>Der entsprechende Vorlagencode für dieses Kontrollkästchen lautet wie folgt: </p> <p> <span class="codeph"> &lt;search-input type="checkbox" name="sp_w" value="exact"&gt;Keine Übereinstimmung mit Geräuschen  </span> </p> <p>Wenn die CGI-Parameterzeichenfolge für die Abfrage <span class="codeph"> sp_w=exact </span> enthält, sieht das in den Browser mit den Suchergebnissen geschriebene Tag wie folgt aus (am Ende des Tags wird das Wort <span class="codeph"> markiert </span> eingefügt): </p> <p> <span class="codeph"> &lt;input type="checkbox" name="sp_w" value="exact" checked=""&gt;Keine Übereinstimmung mit Geräuschen  </span> </p> <p>Wenn die CGI-Parameterzeichenfolge für die Abfrage nicht <span class="codeph"> sp_w=exact </span> enthält, sieht das in den Browser mit den Suchergebnissen geschriebene Tag wie folgt aus (das Wort <span class="codeph">, das </span> markiert ist, wird im Tag nicht aufgelistet): </p> <p> <span class="codeph"> &lt;input type="checkbox" name="sp_w" value="exact"&gt;Keine Übereinstimmung mit Geräuschen  </span> </p> <p>Das <span class="codeph"> &lt;search-input&gt; </span>-Tag ist hilfreich, um Kontrollkästchen und Optionsfelder in Ihre Suchvorlage einzufügen. Wenn Sie Kontrollkästchen oder Optionsfelder haben, die Sie der <span class="codeph"> &lt;form&gt; </span> in Ihrer Suchvorlage hinzufügen möchten, verwenden Sie <span class="codeph"> &lt;search-input...&gt; </span> anstelle von <span class="codeph"> &lt;input...&gt; </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>2 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-select&gt; ...  &lt;/search-select&gt; </span> </p> <p> <span class="codeph"> &lt;search-option&gt; ...  &lt;/search-option&gt; </span> </p> </td> 
   <td colname="col2"> <p>Dropdown-Listen in einem <span class="codeph"> &lt;form&gt; </span>-Tag werden mit einem <span class="codeph"> &lt;select&gt; </span>-Tag gestartet und mit einem <span class="codeph"> &lt;/select&gt; </span>-Tag beendet. Der <span class="codeph">-Name </span> für den verknüpften CGI-Parameter wird im <span class="codeph"> </span>-Tag aufgelistet. Nach dem <span class="codeph"> </span>-Tag ist eine Liste von <span class="codeph"> </span>-Tags, die die Werte angeben, die im Feld "Liste"angezeigt werden sollen. </p> <p>Die Tags <span class="codeph"> &lt;search-select&gt; </span>, <span class="codeph"> &lt;/search-select&gt; </span>, <span class="codeph"> &lt;search-option&gt; und </span> &lt;/search-option&gt; </span> bieten eine ähnliche Funktionalität wie das <span class="codeph"> &lt;search-input&gt; </span>-Tag. <span class="codeph"> Das heißt, das Wort <span class="codeph"> ausgewählt </span> wird automatisch am Ende des <span class="codeph"> </span>-Tags hinzugefügt, das an den Browser gesendet wird, wenn der <span class="codeph">-Name </span> im <span class="codeph"> &lt;search-select&gt; </span>-Tag als CGI-Parameter aufgelistet ist und der <span class="codeph">-Wert </span> des CGI-Parameters angegeben ist. als <span class="codeph"> Wert </span> in einem bestimmten <span class="codeph"> &lt;search-option&gt; </span>-Tag aufgeführt. Auf diese Weise können Sie die standardmäßige Liste in Ihrem Suchergebnis automatisch mit der aktuellen Abfrage identisch machen. </span></p> <p>Ein typisches Feld für die Liste sieht beispielsweise wie folgt aus: </p> <p> <code class="syntax html"> &lt;select&nbsp;name="sp_x"&nbsp;size=1&gt; 
      &lt;option&nbsp;value="any"&nbsp;selected&gt;Anywhere&lt;/option&gt; 
      &lt;option&nbsp;value="title"&gt;Title&lt;/option&gt; 
      &lt;option&nbsp;value="desc"&gt;Description&lt;/option&gt; 
      &lt;option&nbsp;value="keys"&gt;Keywords&lt;/option&gt; 
      &lt;option&nbsp;value="body"&gt;Body&lt;/option&gt; 
      &lt;option&nbsp;value="alt"&gt;Alternate&nbsp;text&lt;/option&gt; 
      &lt;option&nbsp;value="url"&gt;URL&lt;/option&gt; 
      &lt;option&nbsp;value="target"&gt;Target&lt;/option&gt; 
      &lt;/select&gt; </code> </p> <p>Der entsprechende Vorlagencode für das Feld "Liste"lautet wie folgt: </p> <p> <code class="syntax html"> &lt;search-select&nbsp;name="sp_x"&nbsp;size=1&gt; 
      &lt;search-option&nbsp;value="any"&gt;Anywhere&lt;/search-option&gt; 
      &lt;search-option&nbsp;value="title"&gt;Title&lt;/search-option&gt; 
      &lt;search-option&nbsp;value="desc"&gt;Description&lt;/search-option&gt; 
      &lt;search-option&nbsp;value="keys"&gt;Keywords&lt;/search-option&gt; 
      &lt;search-option&nbsp;value="body"&gt;Body&lt;/search-option&gt; 
      &lt;search-option&nbsp;value="alt"&gt;Alternate&nbsp;text&lt;/search-option&gt; 
      &lt;search-option&nbsp;value="url"&gt;URL&lt;/search-option&gt; 
      &lt;search-option&nbsp;value="target"&gt;Target&lt;/search-option&gt; 
      &lt;/search-select&gt; </code> </p> <p>Wenn Sie Listen-Felder haben, die Sie der <span class="codeph"> &lt;form&gt; </span> in Ihrer Suchvorlage hinzufügen möchten, verwenden Sie <span class="codeph"> &lt;search-select...&gt; </span> anstelle von <span class="codeph"> </span>, <span class="codeph"> &lt;/search-select&gt; </span> &lt;a7/&gt; &lt;/select&gt; &lt;a7/&gt;.9/&gt;, <span class="codeph"> &lt;search-option...&gt; </span> anstelle von <span class="codeph"> &lt;option...&gt; </span> und <span class="codeph"> &lt;/search-option&gt; </span> anstelle von <span class="codeph"> &lt;/option&gt; </span>.</span><span class="codeph"> </span></p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>1 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-sort-by-field name="field-name" count="XX"&gt; ...  &lt;/search-sort-by-field&gt; </span> </p> </td> 
   <td colname="col2"> <p>Diese erweiterten Tags erstellen einen Ankerlink um den HTML-Code zwischen ihnen. Wenn auf diesen Anker geklickt wird, wird eine Seite mit Ergebnissen angezeigt, die auf dem angegebenen Feld sortiert sind. Das optionale Attribut <span class="codeph"> count </span> gibt die Anzahl der Ergebnisse an, die auf der Ergebnisseite angezeigt werden sollen. Wenn <span class="codeph"> count </span> weggelassen wird, wird die auf der aktuellen Seite verwendete Anzahl verwendet. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Datumsformat-Zeichenfolgen {#section_4BBDBBEF2B96414497617CD4B52D96E4}

Sie können die folgenden Konvertierungsspezifikationen in Datumsformat-Zeichenfolgen verwenden:

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Datumsformat-Zeichenfolge </p> </th> 
   <th colname="col2" class="entry"> <p>Beschreibung </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>%A </p> </td> 
   <td colname="col2"> <p> Entspricht der nationalen Darstellung des vollständigen Wochentagsnamens, z. B. "Montag". Die Einstellung in <span class="uicontrol"> Linguistik </span> &gt; <span class="uicontrol"> Wörter und Sprachen </span> &gt; <span class="uicontrol"> Sprache </span> bestimmt die nationale Vertretung. </p> <p>Siehe <a href="../c-about-linguistics-menu/c-about-words-and-language.md#concept_CEB4B9576F3C4E2EB87B352EEC738D79" type="concept" format="dita" scope="local"> Info zu Wörtern und Sprachen</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%a </p> </td> 
   <td colname="col2"> <p> Entspricht der nationalen Darstellung des abgekürzten Wochentagsnamens, wobei die Abkürzung die ersten drei Zeichen (z. B. "Mon") umfasst. Die Einstellung in <span class="uicontrol"> Linguistik </span> &gt; <span class="uicontrol"> Wörter und Sprachen </span> &gt; <span class="uicontrol"> Sprache </span> bestimmt die nationale Vertretung. </p> <p>Siehe <a href="../c-about-linguistics-menu/c-about-words-and-language.md#concept_CEB4B9576F3C4E2EB87B352EEC738D79" type="concept" format="dita" scope="local"> Info zu Wörtern und Sprachen</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%B </p> </td> 
   <td colname="col2"> <p> Entspricht der nationalen Darstellung des vollständigen Monatsnamens, z. B. "Juni". Die Einstellung in <span class="uicontrol"> Linguistik </span> &gt; <span class="uicontrol"> Wörter und Sprachen </span> &gt; <span class="uicontrol"> Sprache </span> bestimmt die nationale Vertretung. </p> <p>Siehe <a href="../c-about-linguistics-menu/c-about-words-and-language.md#concept_CEB4B9576F3C4E2EB87B352EEC738D79" type="concept" format="dita" scope="local"> Info zu Wörtern und Sprachen</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%b </p> </td> 
   <td colname="col2"> <p> Stimmt mit der nationalen Darstellung des abgekürzten Monatsnamens überein, wobei die Abkürzung die ersten drei Zeichen (z. B. "Jun") umfasst. Die Einstellung in <span class="uicontrol"> Linguistik </span> &gt; <span class="uicontrol"> Wörter und Sprachen </span> &gt; <span class="uicontrol"> Sprache </span> bestimmt die nationale Vertretung. </p> <p>Siehe <a href="../c-about-linguistics-menu/c-about-words-and-language.md#concept_CEB4B9576F3C4E2EB87B352EEC738D79" type="concept" format="dita" scope="local"> Info zu Wörtern und Sprachen</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%D </p> </td> 
   <td colname="col2"> <p>Entspricht "%m/%d/%y", z. B. "07/25/13". </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%d </p> </td> 
   <td colname="col2"> <p> Entspricht dem Tag des Monats als Dezimalzahl (01-31). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%e </p> </td> 
   <td colname="col2"> <p> Entspricht dem Tag des Monats als Dezimalzahl (1-31). Vor einstelligen Ziffern ist ein Leerzeichen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%H </p> </td> 
   <td colname="col2"> <p> Entspricht der 24-Stunden-Uhr als Dezimalzahl (00-23). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%h </p> </td> 
   <td colname="col2"> <p> Stimmt mit der nationalen Darstellung des abgekürzten Monatsnamens überein, wobei die Abkürzung die ersten drei Zeichen umfasst, z. B. "Jun"(identisch mit %b). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%I </p> </td> 
   <td colname="col2"> <p> Entspricht der 12-Stunden-Uhr als Dezimalzahl (01-12). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%j </p> </td> 
   <td colname="col2"> <p> Stimmt mit dem Tag des Jahres als Dezimalzahl (001-366) überein. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%k </p> </td> 
   <td colname="col2"> <p> Entspricht der 24-Stunden-Uhr als Dezimalzahl (0-23). Vor einstelligen Ziffern ist ein Leerzeichen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%l </p> </td> 
   <td colname="col2"> <p> Entspricht der 12-Stunden-Uhr als Dezimalzahl (1-12). Vor einstelligen Ziffern ist ein Leerzeichen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%M </p> </td> 
   <td colname="col2"> <p> Stimmt mit der Minute als Dezimalzahl (00-59) überein. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%m </p> </td> 
   <td colname="col2"> <p> Entspricht dem Monat als Dezimalzahl (01-12). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%p </p> </td> 
   <td colname="col2"> <p> Entspricht der nationalen Darstellung von "ante meridiem"oder "post meridiem", z. B. "PM". Die Einstellung in <span class="uicontrol"> Linguistik </span> &gt; <span class="uicontrol"> Wörter und Sprachen </span> &gt; <span class="uicontrol"> Sprache </span> bestimmt die nationale Vertretung. </p> <p>Siehe <a href="../c-about-linguistics-menu/c-about-words-and-language.md#concept_CEB4B9576F3C4E2EB87B352EEC738D79" type="concept" format="dita" scope="local"> Info zu Wörtern und Sprachen</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%R </p> </td> 
   <td colname="col2"> <p>Entspricht "%H:%M", z. B. "13:23". </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%r </p> </td> 
   <td colname="col2"> <p>Entspricht "%I:%M:%S %p", z. B. "01:23:45 PM". </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%S </p> </td> 
   <td colname="col2"> <p> Entspricht der zweiten Zahl als Dezimalzahl (00-60). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%T </p> </td> 
   <td colname="col2"> <p>Entspricht "%H:%M:%S", z. B. "13:26:47". </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%U </p> </td> 
   <td colname="col2"> <p> Stimmt mit der Wochennummer des Jahres (Sonntag als erster Wochentag) als Dezimalzahl (00-53) überein. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%v </p> </td> 
   <td colname="col2"> <p>Entspricht "%e-%b-%Y", z. B. "25-Juli-2013". </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%Y </p> </td> 
   <td colname="col2"> <p> Entspricht dem Jahr mit dem Jahrhundert als Dezimalzahl, z. B. "2013". </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%y </p> </td> 
   <td colname="col2"> <p> Entspricht dem Jahr ohne Jahrhundert als Dezimalzahl (00-99). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%Z </p> </td> 
   <td colname="col2"> <p> Stimmt mit dem Zeitzonennamen überein. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%% </p> </td> 
   <td colname="col2"> <p> Stimmt überein "%". </p> </td> 
  </tr> 
 </tbody> 
</table>

## Sprachkennungen {#section_0490DECC00E34691ADE5A9ED90A6D911}

Die folgende Tabelle enthält die Sprachenkennungen für jede unterstützte Sprache. Sie können diese Bezeichner als Werte für das optionale Attribut &quot;language&quot;in den folgenden Vorlagen-Tags verwenden:

* `search-date` und `search-display-field`.

   Siehe [Tags für die Ergebnisschleife](../c-appendices/c-templates.md#section_80D68334E8D04A33937A6E58ABAAA320).

* `search-field-value-list` Siehe Listen-Tags für  [Feldwerte](../c-appendices/c-templates.md#section_D3298B5F976447DBA0032B883DCC91B1).

* `search-field-value` Siehe  [Feldwert-Liste-Loop-Tags](../c-appendices/c-templates.md#section_0717FA09F0FC449CB916883B0500A60E).

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Sprache  </p> </th> 
   <th colname="col2" class="entry"> <p>Sprach-ID </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Bulgarisch (Bulgarien) </p> </td> 
   <td colname="col2"> <p> bg_BG </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Chinesisch (China) </p> </td> 
   <td colname="col2"> <p> zh_CN </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Chinesisch (Hongkong) </p> </td> 
   <td colname="col2"> <p> zh_HK </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Chinesisch (Singapur) </p> </td> 
   <td colname="col2"> <p>zh_SG </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Chinesisch (Taiwan) </p> </td> 
   <td colname="col2"> <p> zh_TW </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Tschechisch (Tschechische Republik) </p> </td> 
   <td colname="col2"> <p> cs_CZ </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dänisch (Dänemark) </p> </td> 
   <td colname="col2"> <p> da_DK </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Niederländisch (Belgien) </p> </td> 
   <td colname="col2"> <p> nl_BE </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Niederländisch (Niederlande) </p> </td> 
   <td colname="col2"> <p> nl_NL </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Englisch (Australien) </p> </td> 
   <td colname="col2"> <p> en_AU </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Englisch (Kanada) </p> </td> 
   <td colname="col2"> <p> en_CA </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Englisch (Großbritannien) </p> </td> 
   <td colname="col2"> <p> en_GB </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Englisch (USA) </p> </td> 
   <td colname="col2"> <p> en_US </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Französich (Belgien) </p> </td> 
   <td colname="col2"> <p> fr_BE </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Französisch (Kanada) </p> </td> 
   <td colname="col2"> <p>fr_CA </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Finnisch (Finnland) </p> </td> 
   <td colname="col2"> <p> fi_FI </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Französich (Frankreich) </p> </td> 
   <td colname="col2"> <p> fr_FR </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Französisch (Schweiz) </p> </td> 
   <td colname="col2"> <p> fr_CH </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Deutsch (Österreich) </p> </td> 
   <td colname="col2"> <p> de_AT </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Deutsch (Deutschland) </p> </td> 
   <td colname="col2"> <p> de_DE </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Deutsch (Schweiz) </p> </td> 
   <td colname="col2"> <p> de_CH </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Griechisch (Griechenland) </p> </td> 
   <td colname="col2"> <p> el_GR </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Irish Gäelic (Irland) </p> </td> 
   <td colname="col2"> <p> ga_IE </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Italienisch (Italien) </p> </td> 
   <td colname="col2"> <p> it_IT </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Japanisch (Japan) </p> </td> 
   <td colname="col2"> <p> ja_JP </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Koreanisch (Korea) </p> </td> 
   <td colname="col2"> <p> ko_KR </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Norwegisch (Norwegen) </p> </td> 
   <td colname="col2"> <p> no_NO </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Polnisch (Polen) </p> </td> 
   <td colname="col2"> <p> pl_PL </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Portugiesisch (Brasilien) </p> </td> 
   <td colname="col2"> <p> pt_BR </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Portugiesisch (Portugal) </p> </td> 
   <td colname="col2"> <p> pt_PT </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Russisch (ehemalige sowjetische Vereinigung) </p> </td> 
   <td colname="col2"> <p> ru_SU </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Slowakisch (Slowakei) </p> </td> 
   <td colname="col2"> <p> sk_SK </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Slowakisch (Slowenien) </p> </td> 
   <td colname="col2"> <p>sl_SI </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Spanisch (Mexiko) </p> </td> 
   <td colname="col2"> <p> es_MX </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Spanisch (Spanien) </p> </td> 
   <td colname="col2"> <p> es_ES </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Schwedisch (Schweden) </p> </td> 
   <td colname="col2"> <p> sv_SE </p> </td> 
  </tr> 
 </tbody> 
</table>

## Content-Type HTTP-Header {#section_AEED823E9938448A9EDB2F286D9CFD90} angeben

Sie können den Content-Type HTTP-Antwortheader mithilfe des folgenden Tags angeben:

`<search-content-type-header [content="MIME-type"] [charset="charset-name"]>`

Die Attribute `content` und `charset` sind optional. Dieses Tag sollte so früh wie möglich in der Vorlage erscheinen. Es wird außerdem empfohlen, dass sie vor `<search-html-meta-charset>` oder `<search-xml-decl>` angezeigt wird, da dies das Verhalten dieser Tags beeinflusst.

Wenn Sie das Attribut `content` nicht angeben, wird für den Wert von `MIME-type` standardmäßig der Wert festgelegt, der unter **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Content Types]** festgelegt wird. Wenn Sie ein `content`-Attribut angeben, wird es als standardmäßiges `content`-Attribut für das `<search-html-meta-charset>`-Tag verwendet.

Wenn Sie das Attribut `charset` nicht angeben, wird kein `charset`-Wert in die `content-type`-Kopfzeile geschrieben.

Wenn Sie `charset="1"` angeben, ist der tatsächliche Wert für `charset-name` der Wert des `sp_f`-CGI-Parameters. Wenn bei der Suche kein `sp_f`-CGI-Parameter gesendet wird, wird der tatsächliche Wert für `charset-name` aus Ihren Kontoeinstellungen gelesen. Sie können den mit Ihrem Konto verknüpften Zeichensatz unter **[!UICONTROL Settings]** > **[!UICONTROL My Profile]** > **[!UICONTROL Personal Information]** > **[!UICONTROL Character Encoding]** > &lt;a3/> Ansicht oder ändern.

Siehe [Konfigurieren Ihrer persönlichen Benutzerinformationen](../c-about-settings-menu/c-about-my-profile-menu.md#task_A11A3BE2527B4204B896E04303B04AA6).

Sie können einen bestimmten Zeichensatznamen auswählen, indem Sie ihn als `charset`-Wert angeben, z. B. `charset="iso-8859-1"` oder `charset="Shift-JIS"`.

Wenn Sie ein `charset`-Attribut angeben, wird es als standardmäßiges `charset`-Attribut für die `<search-html-meta-charset>`- und `<search-xml-decl>`-Tags verwendet und in die `content-type`-Kopfzeile ausgegeben.

## Festlegen eines Zeichensatzes in einer HTML-Vorlage {#section_E0D1816ABB5846BEBE9C26D5980CCBE6}

Die standardmäßigen HTML-Suchergebnisvorlagen geben den mit dem aktuellen Konto verknüpften Zeichensatz über das folgende Tag an:

`<search-html-meta-charset [content="MIME-type"] [charset="charset-name"]>`

Die Attribute für Inhalt und Zeichensatz sind optional. Dieses Tag muss im HTML-Abschnitt `<head>` der Vorlage angezeigt werden. Dieses Tag ergibt das folgende Tag auf der HTML-Seite, die aus der Vorlage generiert wurde:

`<meta http-equiv="content-type" content="MIME-type; charset=charset-name">`

Wenn Sie das Inhaltsattribut nicht angeben, wird der tatsächliche Wert von `MIME-type` standardmäßig auf einen von zwei Werten gesetzt. Wenn das `<search-content-type-header>`-Tag ein `content`-Attribut angegeben hat, wird dieser Wert verwendet. Andernfalls wird der Wert verwendet, der auf der Registerkarte **[!UICONTROL Templates]** > **[!UICONTROL Settings]** > **[!UICONTROL Content Type]** festgelegt wurde.

Wenn Sie das Attribut `charset` nicht angeben, wird als tatsächlicher Wert von `charset-name` standardmäßig einer von zwei Werten verwendet. Wenn das `<search-content-type-header>`-Tag ein `charset`-Attribut angegeben hat, wird dieser Wert verwendet. Andernfalls wird der tatsächliche Wert für `charset-name` aus Ihren Kontoeinstellungen gelesen. Sie können den mit Ihrem Konto verknüpften Zeichensatz unter **[!UICONTROL Settings]** > **[!UICONTROL My Profile]** > **[!UICONTROL Personal Information]** > **[!UICONTROL Character Encoding]** > &lt;a3/> Ansicht oder ändern.

Siehe [Konfigurieren Ihrer persönlichen Benutzerinformationen](../c-about-settings-menu/c-about-my-profile-menu.md#task_A11A3BE2527B4204B896E04303B04AA6).

Wenn Sie `charset="1"` angeben, ist der tatsächliche Wert für `charset-name` der Wert des `sp_f`-CGI-Parameters. Wenn bei der Suche kein `sp_f`-CGI-Parameter gesendet wird, ist der tatsächliche Wert für `charset-name` entweder der im `<search-content-type-header>`-Tag eingestellte Wert, falls er angegeben wurde, oder der Wert, der in Ihren Kontoeinstellungen festgelegt wird.

Sie können einen bestimmten Zeichensatznamen wie in `charset="charset-name"` angeben. Beispiel: `charset="iso-8859-1"` oder `charset="Shift-JIS"`.

Das `<search-html-meta-charset>`-Tag ist optional. Wenn Sie sie entfernen, nimmt der Browser die Standardwerte für `content-type` an, und zwar die folgenden: `content="text/html; charset=ISO-8859-1"`. Sie können auch festlegen, dass das `<search-html-meta-charset>`-Tag durch Ihr eigenes `http-equiv`-Tag ersetzt wird.

## Festlegen eines Zeichensatzes in einer XML-Vorlage {#section_17DC31CDCC104F5F8081466B41A96E9D}

Die Standard-XML-Suchergebnisvorlage gibt den Zeichensatz an, der dem aktuellen Konto mithilfe des folgenden Tags zugeordnet ist:

`<search-xml-decl [charset="charset-name"]>`

Das Attribut `charset` ist optional. Dieses Tag muss oben in der Vorlage, aber nach jedem `<search-content-type-header>`-Tag erscheinen. Dieses Tag führt zum folgenden Tag im XML-Dokument, das aus der Vorlage generiert wurde:

`<?xml version="1.0" encoding="charset-name" standalone="yes" ?>`

Wenn Sie nicht `charset` angeben, wird der tatsächliche Wert von `charset-name` standardmäßig auf einen von zwei Werten gesetzt. Wenn `<search-content-type-header>` ein `charset`-Attribut angegeben hat, wird dieser Wert verwendet. Andernfalls wird der tatsächliche Wert für `charset-name` aus Ihren Kontoeinstellungen gelesen. Sie können den mit Ihrem Konto verknüpften Zeichensatz unter **[!UICONTROL Settings]** > **[!UICONTROL My Profile]** > **[!UICONTROL Personal Information]** > **[!UICONTROL Character Encoding]** > &lt;a3/> Ansicht oder ändern.

Siehe [Konfigurieren Ihrer persönlichen Benutzerinformationen](../c-about-settings-menu/c-about-my-profile-menu.md#task_A11A3BE2527B4204B896E04303B04AA6).

Wenn Sie `charset="1"` angeben, ist der tatsächliche Wert für `charset-name` der Wert des `sp_f`-CGI-Parameters. Wenn bei der Suche kein `sp_f`-CGI-Parameter gesendet wird, ist der tatsächliche Wert für `charset-name` entweder der Wert, der im `<search-content-type-header>`-Tag festgelegt wird, wenn er angegeben wurde, oder der Wert, der in Ihren Kontoeinstellungen festgelegt wird.

Sie können einen bestimmten Zeichensatznamen wie in `charset="charset-name"` angeben, wenn Sie dies wünschen. Beispiel, `charset="iso-8859-1" or charset="Shift-JIS"`.

Sie können das `<search-xml-decl>`-Tag durch Ihr eigenes `?xml`-Tag ersetzen.

## Hinzufügen einer Suchvorlage in einem anderen {#section_7D1FCD3D9E2340C291E354C9720E8BC0}

Um eine Suchvorlage in eine andere einzuschließen, verwenden Sie das Tag `<search-include>` und setzen Sie das Dateiattribut auf den Namen der Vorlagendatei, die Sie einschließen möchten, wie im folgenden Beispiel dargestellt:

`<search-include file="seo/seo_search_title.tpl" />`

SEO-Suchvorlagensegmente befinden sich im Unterordner `seo/` und normale Suchvorlagen befinden sich im Unterordner `templates/`. Nur .tpl-Dateien sind aussagekräftig, um sie in diesen Kontext einzubeziehen.

## Verwalten mehrerer Transportvorlagen für Ihre Website {#reference_12AAB3B9F4C74C11956F1DBA95714C2F}

Sie können das Erscheinungsbild der Suchergebnisse auf Ihrer Website steuern, indem Sie für jeden Bereich verschiedene Suchtransportvorlagen verwenden.

<!-- 

r_managing_multiple_templates.xml

 -->

Um diese Art von Suchfunktion zu erreichen, können Sie Ihre Transportvorlagen in Site-Suche/Merchandising verwalten. Sie können auch Ihre Transportvorlagen in Publish verwalten. Wie die Site-Suche/das Merchandising können Sie mit &quot;Veröffentlichen&quot;mehrere Suchtransportvorlagen bearbeiten, Vorschauen erstellen und veröffentlichen.

Verwenden Sie den Parameter `sp_t`, um Ihre Suchformulare so einzurichten, dass sie eine bestimmte Transportvorlage verwenden (die nicht standardmäßig verwendet wird). Angenommen, Sie haben eine Suchvorlage namens &quot;Freigabe&quot;für den markierten Verkaufsbereich Ihrer Website. Sie verwenden das standardmäßige HTML-Suchformular mit dem folgenden zusätzlichen Formularcode:

`<input type=hidden name="sp_t" value="clearance">`

Wenn ein Kunde auf ein Standardformular klickt, das diese Codezeile enthält, wird die Suchtransportvorlage mit den Suchergebnissen angezeigt.

Siehe [Verwenden von Sammlungen in Suchformularen](../c-appendices/c-searchforms.md#reference_5A079AEEEFB84457892EF0870D0605C3).

Siehe [Verwenden von Frames mit Formularen](../c-appendices/c-searchforms.md#reference_82CDDDA1E37042E4849EBF7EA05407C5).

Siehe [Beispiel für ein erweitertes Suchformular](../c-appendices/c-searchforms.md#reference_82E1051918744EBA88A01E9E6AE42C4A).
