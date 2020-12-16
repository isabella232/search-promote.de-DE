---
description: Sie können die Ausgabe in einem beliebigen textbasierten Format, einschließlich XML oder JSON, anpassen.
seo-description: Sie können die Ausgabe in einem beliebigen textbasierten Format, einschließlich XML oder JSON, anpassen.
seo-title: Ausgabe der geführten Suche
solution: Target
title: Ausgabe der geführten Suche
topic: Appendices,Site search and merchandising
uuid: 234fd563-f249-42b0-88ca-c89b44f8df77
translation-type: tm+mt
source-git-commit: f21a3f7fe0aeaab517a5ca36da43594873b3e69a
workflow-type: tm+mt
source-wordcount: '6298'
ht-degree: 2%

---


# Ausgabe der geführten Suche{#guided-search-output}

Sie können die Ausgabe in einem beliebigen textbasierten Format, einschließlich XML oder JSON, anpassen.

## Ausgabe der geführten Suche {#concept_2A1BA3AD413848A1AC2A3ABC4FFE481F}

Das Ausgabeformat kann angepasst werden, um die facettierten, sortierten und anderen implementierungsspezifischen Entscheidungen zu unterstützen, die während des Entwurfsprozesses getroffen werden. Sie können das Format selbst anpassen, um bei Bedarf die Entwicklung des Frontend des Kunden zu vereinfachen.

Die gesamte Ausgabe ist innerhalb von `<result>`-Tags enthalten, und die meisten dynamischen Daten werden in `<![CDATA[ ]]>`-Tags eingeschlossen. Diese Organisation ermöglicht es, dass die Ergebnisse HTML- und andere Nicht-XML-Entitäten enthalten.

Wenn Links zu anderen Seiten bereitgestellt werden, werden sie in Form einer relativen URL dargestellt. Dieses Ergebnis enthält auch die Abfragen-Zeichenfolgenparameter, die übergeben werden, um das gewünschte Ergebnis zu generieren.

## Einführung in die geführte Suche {#section_95483980930C4325BAB50A40BD47245A}

Denken Sie beim Starten einer Implementierung der geführten Suche daran, dass [!DNL Adobe Search&Promote] für die Business Layer verantwortlich ist. Das heißt, die Logik, die umgibt, welche Ergebnisse und Facetten einem Kunden zu jeder Zeit gezeigt werden.

Wenn Sie das Webanwendung Frontend implementieren, das die Ergebnisse analysiert und als HTML anzeigt, beschränken Sie die Funktion auf &quot;Nur anzeigen&quot;. Mit anderen Worten, eine serverseitige Logik, die Sie zum Erstellen der Präsentationsschicht verwenden, trifft nicht die Entscheidungen darüber, was einem Kunden präsentiert werden soll, es sei denn, dies ist erforderlich. Die Geschäftsregeln funktionieren nicht wie erwartet, wenn das Front-End-Skript die Suchergebnisse ändert.

[!DNL Adobe Search&Promote] behält den Benutzerstatus der ausgewählten Suchoptimierungsoptionen mithilfe der URL-Parameter bei. Alle `<link>`-Knoten enthalten die relevanten Parameter der Kundenauswahl. Zu diesen Parametern können Breadcrumb, Paginierung, Sortierung und Facettenauswahl gehören. Falls zutreffend, werden `<undolink>`-Knoten zurückgegeben, damit ein Kunde eine Auswahl &quot;zurücksenden&quot;kann. Facets und Breadcrumbs Angebot dieser Linktypen.

## Arbeiten mit dem Suchserver {#section_8DBEACDECD714E59BDED6315E6041B8D}

Es wird eine REST-ähnliche API verwendet, mit der Sie interagieren können, um Suchen durchzuführen und Ergebnisse zu erhalten. Die gängigsten Formate für die Ergebnisse sind XML oder JSON.

Der Basis-URI ist mit einem bestimmten Konto und einer gestaffelten oder Live-Umgebung verknüpft. Sie können mehrere Aliase für den Basis-URI von Ihrem Kundenbetreuer anfordern. So ist beispielsweise einer fiktiven Firma namens Megacorp die folgenden beiden Basis-URLs zugeordnet:

* `https://search.megacorp.com `
* `https://stage.megacorp.com`

Der erste URI führt Suchen nach ihrem Liveindex und der zweite URI nach ihrem gestaffelten Index durch.

Suchanforderungen bestehen aus dem Basis-URI und einem Satz von CGI-Parametern oder Schlüssel-Wert-Paaren, die die gewünschte Suche nach dem Konto angeben, das mit dem Basis-URI verknüpft ist.

Es werden drei Formate von CGI-Parametern unterstützt. Standardmäßig ist Ihr Konto so konfiguriert, dass CGI-Parameter durch ein Semikolon ( `;`) getrennt werden, wie im folgenden Beispiel:

* `https://search.megacorp.com?q=shoes ;page=2`

Wenn Sie es vorziehen, können Sie Ihren Kundenbetreuer dazu veranlassen, Ihr Konto so zu konfigurieren, dass zur Trennung der CGI-Parameter das kaufmännische Und ( `&`) verwendet wird, wie im folgenden Beispiel:

* `https://search.megacorp.com?q=shoes &page=2`

Ein drittes Format, das so genannte SEO-Format, wird ebenfalls unterstützt, wenn anstelle des Trennzeichens und Gleichheitszeichens ein Schrägstrich ( `/`) verwendet wird, um &quot;saubere&quot;Links zu generieren, wie im folgenden Beispiel:

* `https://search.megacorp.com/q/shoes/page/2`

Jedes Mal, wenn das SEO-Format zum Senden einer Anforderung verwendet wird, werden alle Ausgabelinks im gleichen Format zurückgegeben.

## Suchparameter für Abfragen {#section_7ADA5E130E3040C9BE85D0D68EDD3223}

In der folgenden Tabelle werden die standardmäßigen &quot;Out-of-the-Box&quot;-Suchparameter beschrieben, die Sie verwenden können. Verarbeitungsregeln und Geschäftsregeln können auf Grundlage von benutzerdefinierten Parametern für die Abfrage erstellt werden, um benutzerdefinierte Geschäftslogik zu implementieren, die für Ihre Firma relevant ist. Sie können mit dem Beratungsteam zusammenarbeiten, um Dokumentation zu diesen Parametern zu erhalten.

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Suchparameter Abfrage </p> </th> 
   <th colname="col2" class="entry"> <p>Beispiel </p> </th> 
   <th colname="col3" class="entry"> <p>Beschreibung </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> q </span> </p> </td> 
   <td colname="col2"> <p> <span class="codeph"> q= Zeichenfolge  </span> </p> </td> 
   <td colname="col3"> <p> Gibt die Abfrage-Zeichenfolge für die Suche an. Dieser Parameter wird dem Backend-Suchparameter <span class="codeph"> sp_q </span> zugeordnet. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> q# </span> </p> </td> 
   <td colname="col2"> <p> <span class="codeph"> q#= Zeichenfolge  </span> </p> </td> 
   <td colname="col3"> <p>Nummerierte Parameter <span class="codeph"> q </span> und <span class="codeph"> x </span> führen eine facettierte Suche oder Suche in einem bestimmten Feld durch. </p> <p>Der Parameter <span class="codeph"> q </span> definiert den Begriff, nach dem Sie in der Facette suchen, als den entsprechenden numerischen Parameter <span class="codeph"> x </span>. Wenn Sie beispielsweise zwei Facetten mit den Namen Größe und Farbe haben, könnten Sie Folgendes haben: </p> <p> <span class="codeph"> q1=small;x1=size;q2=red;x2=color  </span> </p> <p>Dieser Parameter wird den Backend-Suchparametern <span class="codeph"> sp_q_exact_# </span> zugeordnet. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> x# </span> </p> </td> 
   <td colname="col2"> <p> <span class="codeph"> x#= Zeichenfolge  </span> </p> </td> 
   <td colname="col3"> <p> Nummerierte Parameter <span class="codeph"> q </span> und <span class="codeph"> x </span> führen eine facettierte Suche oder Suche in einem bestimmten Feld durch. </p> <p>Der Parameter <span class="codeph"> q </span> definiert den Begriff, nach dem Sie in der Facette suchen, als den entsprechenden numerischen Parameter <span class="codeph"> x </span>. Wenn Sie beispielsweise zwei Facetten mit den Namen Größe und Farbe haben, könnten Sie Folgendes haben: </p> <p> <span class="codeph"> q1=small;x1=size;q2=red;x2=color  </span> </p> <p>Dieser Parameter wird den Backend-Suchparametern <span class="codeph"> sp_x_# </span> zugeordnet. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> Erfassung </span> </p> </td> 
   <td colname="col2"> <p> <span class="codeph"> collection= string  </span> </p> </td> 
   <td colname="col3"> <p> Gibt die für die Suche zu verwendende Sammlung an. Dieser Parameter wird dem Backend-Suchparameter <span class="codeph"> sp_k </span> zugeordnet. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> count  </span> </p> </td> 
   <td colname="col2"> <p> <span class="codeph"> count= Zahl  </span> </p> </td> 
   <td colname="col3"> <p> Gibt die Gesamtanzahl der angezeigten Ergebnisse an. Die Standardeinstellung ist unter <span class="uicontrol"> Einstellungen </span> &gt; <span class="uicontrol"> Suchen </span> &gt; <span class="uicontrol"> Suchen </span> definiert. Dieser Parameter wird dem Backend-Suchparameter <span class="codeph"> sp_c </span> zugeordnet. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> page </span> </p> </td> 
   <td colname="col2"> <p> <span class="codeph"> page= number  </span> </p> </td> 
   <td colname="col3"> <p> Gibt die Seite der zurückgegebenen Ergebnisse an. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> rank  </span> </p> </td> 
   <td colname="col2"> <p> <span class="codeph"> rank= Feld  </span> </p> </td> 
   <td colname="col3"> <p> Gibt das Rankenfeld an, das für das statische Rang verwendet werden soll. Das Feld muss ein Feld vom Typ Rang mit einer Relevanz größer als 0 sein. Dieser Parameter wird dem Backend-Parameter <span class="codeph"> sp_sr </span> zugeordnet. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> gs_store  </span> </p> </td> 
   <td colname="col2"> <p> <span class="codeph"> gs_store= string  </span> </p> </td> 
   <td colname="col3"> <p> Gibt den zu suchenden Store an. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> sortieren  </span> </p> </td> 
   <td colname="col2"> <p> <span class="codeph"> sort= number  </span> </p> </td> 
   <td colname="col3"> <p> Gibt die Sortierreihenfolge an. "0"ist der Standardwert und wird nach Relevanzwert sortiert; "1" sortiert nach Datum; "-1"wird nicht sortiert. </p> <p>Benutzer können einen Feldnamen für den Wert des Parameters <span class="codeph"> sp_s </span> angeben. Beispielsweise sortiert <span class="codeph"> sp_s=title </span> die Ergebnisse nach den Werten, die im Titelfeld enthalten sind. Wenn ein Feldname für den Wert eines Parameters <span class="codeph"> sp_s </span> verwendet wird, werden die Ergebnisse nach diesem Feld sortiert und dann nach Relevanz untergeordnet. </p> <p>Gehen Sie wie folgt vor, um diese Funktion zu aktivieren: </p> 
    <ol id="ol_3894F81EA7BF4827A84DE8662111ABEF"> 
     <li id="li_C040C0B88F174A4885E1A8E721FD032A">Klicken Sie im Produktmenü auf <span class="uicontrol"> Einstellungen </span> &gt; <span class="uicontrol"> Metadaten </span> &gt; <span class="uicontrol"> Definitionen </span>. </li> 
     <li id="li_2E83C3A46D1B4BF991EABAD9D3E52B7D">Führen Sie auf der Seite <span class="wintitle"> Staged Definitions </span> einen der folgenden Schritte aus: 
      <ul id="ul_8018FEE10E0A4C96A74F84A897080580"> 
       <li id="li_E9A7CE43E2734F4D9522A1283CA111FB">Klicken Sie auf <span class="uicontrol"> Hinzufügen Neues Feld </span>. </li> 
       <li id="li_9D2434A321924FBD874569CA9AD2EEF7">Klicken Sie für einen bestimmten Feldnamen auf <span class="uicontrol"> </span> bearbeiten. </li> 
      </ul> </li> 
     <li id="li_90D5E3F4AC0A4A6189934A5589F69903">Klicken Sie in der Dropdown-Liste <span class="wintitle"> Sortieren </span> entweder auf <span class="uicontrol"> Aufsteigend </span> oder auf <span class="uicontrol"> Absteigend </span>. <p>Dieser Parameter wird dem Backend-Suchparameter <span class="codeph"> sp_s </span> zugeordnet. </p> </li> 
    </ol> </td> 
  </tr> 
 </tbody> 
</table>

## Integration mit Ihrem System {#section_91261B19A44A4E579B3FC9FAB9AD3665}

Die folgenden Empfehlungen gelten für die Integration in Ihr System.

* Kommunikation mit dem Suchserver.

   Sie können mit den [!DNL Adobe Search&Promote]-Webservern über HTTP-GET kommunizieren. Ihre Server generieren diese Anforderungen oder auf der Clientseite, die eine Ajax-Anforderung ausführen.
* Speichern des Suchverlaufs.

[!DNL Adobe Search&Promote] ist stateless, wenn der gesamte Status in der HTTP-Anforderung übergeben wird.
* Analyse der zurückgegebenen Ergebnisse.

   Es wird empfohlen, zum Analysieren der XML-Antwort einen SAX-basierten XML-Parser zu verwenden. Wenn Sie eine Ajax-Anforderung generieren, konfigurieren Sie [!DNL Adobe Search&Promote], um JSON-Antworten für diese Anforderungen zurückzugeben, um die Analyse der Antwort zu vereinfachen.

## JSON-Ausgabe der geführten Suche {#reference_EB8182A564DE4374BB84158F2AABEF74}

Tabellen, die die standardmäßige JSON-Antwortausgabe beschreiben.

Siehe auch [JSON-Ausgabe der geführten Suche](../c-appendices/c-guidedsearchoutput.md#reference_EB8182A564DE4374BB84158F2AABEF74).

Sie können die JSON-Antwort auf Folgendes überprüfen:

* [Banner](../c-appendices/c-guidedsearchoutput.md#section_88519CAAD25F4BD49D5E517077745B0E)
* [Breadcrumb](../c-appendices/c-guidedsearchoutput.md#section_A7DB0F1DA9ED4CBCAE18395122F3E01E)
* [Facets](../c-appendices/c-guidedsearchoutput.md#section_65932C95931743A1BFAF1DF16D7E6D92)
* [Kopfzeile und Abfrage](../c-appendices/c-guidedsearchoutput.md#section_1D57062259CA46E0B4F598FA4EB37065)
* [Paginierung](../c-appendices/c-guidedsearchoutput.md#section_504E7AB570BD49AF9839530DC438EE96)
* [Kürzliche Suchvorgänge](../c-appendices/c-guidedsearchoutput.md#section_525816A0355C48F8970D89B8FC3F1FFF)
* [Ergebnisse](../c-appendices/c-guidedsearchoutput.md#section_41AC56BB0A084BF59379B06C8BEF2157)
* [Suchformular](../c-appendices/c-guidedsearchoutput.md#section_434DA13EA295474C99FFE9F14801CD0E)
* [Sortierung](../c-appendices/c-guidedsearchoutput.md#section_558853CD376F4D71BACF211D53085D55)
* [Vorschläge](../c-appendices/c-guidedsearchoutput.md#section_6EC104E1DDD94AC799B65E6E61A2FB3C)
* [Zonen](../c-appendices/c-guidedsearchoutput.md#section_AE53A498B440465EAF2286F2AE87D548)

## Banner {#section_88519CAAD25F4BD49D5E517077745B0E}

Beispiel:

```xml
<banners> 
 <banner> 
  <area><![CDATA[top-left]]></area> 
  <content><![CDATA[<img src="https://www.megacorp.com/discount.gif"/>]]></content> 
 </banner> 
</banners>
```

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Tags in Bannern </p> </th> 
   <th colname="col2" class="entry"> <p>Beschreibung </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;banner&gt; </span> </p> </td> 
   <td colname="col2"> <p> Ein einzelner Bannerknoten. Sie können über mehrere Bannerknoten verfügen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;area&gt; </span> </p> </td> 
   <td colname="col2"> <p> Der Bereich auf der Webseite, in dem das Banner angezeigt wird. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;Inhalt&gt; </span> </p> </td> 
   <td colname="col2"> <p> Der HTML-Inhalt für den Bannerbereich. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Breadcrumb {#section_A7DB0F1DA9ED4CBCAE18395122F3E01E}

Im folgenden Beispiel wird die Auswahl dem Breadcrumb hinzugefügt, sobald der Kunde durch die Facetten weiter herunterfährt. Jedes Element wird als `<breadcrumb-item>` dargestellt.

Beispiel:

```xml
 <breadcrumb> 
  <breadcrumb-item> 
   <link><![CDATA[?q=new+year]]></link> 
   <value><![CDATA[new year]]></value> 
  </breadcrumb-item> 
  <breadcrumb-item> 
   <link><![CDATA[?q=new+year;q1=Articles;x1=content-type]]></link> 
   <value><![CDATA[Articles]]></value> 
  </breadcrumb-item> 
 </breadcrumb> 
```

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Tags in Breadcrumb </p> </th> 
   <th colname="col2" class="entry"> <p>Beschreibung </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;link&gt; </span> </p> </td> 
   <td colname="col2"> <p> Ein Link zu den Suchergebnissen, der die gewünschte Ansicht anzeigt. Durch Klicken auf einen Breadcrumb-Link gelangt der Kunde zu einer Ansicht, in der alle nachfolgenden Verfeinerungen entfernt werden. Es stehen auch andere Optionen zur Verfügung. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;value&gt; </span> </p> </td> 
   <td colname="col2"> <p> Für den Kunden sichtbarer Text für das Breadcrumb-Element. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Facets {#section_65932C95931743A1BFAF1DF16D7E6D92}

Facets sind Verfeinerungsoptionen, die Kunden die Möglichkeit geben, nach den Ergebnissen zu filtern. Facets werden häufig für Kategorisierung, Preisbereiche, Farbauswahl und andere Attributverfeinerungen verwendet. Die Metadaten im Index sind die Antriebsfacetten.

Es ist üblich, Kategorisierungsfacetten auszublenden oder anzuzeigen, wenn ein Kunde sich durch die Kategorisierung nach unten bewegt. Die höchste Kategorisierungsebene (Kategorie) wird als Ebene 1 bezeichnet. Wenn ein Kunde auf eine Option der Stufe 1 klickt, werden die Optionen zur Tier-2-Verfeinerung (Unterkategorie) angezeigt und die Optionen der Ebene 1 werden ausgeblendet. Wenn ein Kunde auf die Option &quot;Ebene 2&quot;klickt, werden die Optionen für die Tier-3-Verfeinerung (Unterkategorie) angezeigt und die Optionen für Ebene 2 werden ausgeblendet. Wie oben erwähnt, werden diese Optionen ausgeblendet und angezeigt. Ihre Webanwendung wird dadurch nicht beeinträchtigt.

Jede Facette ist in `<facet-item>`-Tags enthalten. Im folgenden Beispiel wird eine Facette gezeigt, die es dem Kunden ermöglicht, die Suchergebnisse nach &quot;Urlaub&quot;zu verfeinern.

Beispiel:

```xml
 <facets> 
  <facet-item> 
   <facet-title><![CDATA[Holidays]]></facet-title> 
   <facet-value> 
    <label><![CDATA[New Year]]></label> 
    <link><![CDATA[?q=new+year;q1=Articles;q2=New+Year;x1=content-type;x2=holidays]]></link> 
    <count><![CDATA[11]]></count> 
   </facet-value> 
   <facet-value> 
    <label><![CDATA[Christmas]]></label> 
    <link><![CDATA[?q=new+year;q1=Articles;q2=Christmas;x1=content-type;x2=holidays]]></link> 
    <count><![CDATA[7]]></count> 
   </facet-value> 
   <facet-value> 
    <label><![CDATA[Chinese New Year]]></label> 
    <link><![CDATA[?q=new+year;q1=Articles;q2=Chinese+New+Year;x1=content-type;x2=holidays]]></link> 
    <count><![CDATA[2]]></count> 
   </facet-value> 
   <facet-value> 
    <label><![CDATA[Thanksgiving]]></label> 
    <link><![CDATA[?q=new+year;q1=Articles;q2=Thanksgiving;x1=content-type;x2=holidays]]></link> 
    <count><![CDATA[2]]></count> 
   </facet-value> 
   <facet-value> 
    <label><![CDATA[4th of July]]></label> 
    <link><![CDATA[?q=new+year;q1=Articles;q2=4th+of+July;x1=content-type;x2=holidays]]></link> 
    <count><![CDATA[1]]></count> 
   </facet-value> 
   <facet-value> 
    <label><![CDATA[Father&#39;s Day]]></label> 
    <link><![CDATA[?q=new+year;q1=Articles;q2=Father's+Day;x1=content-type;x2=holidays]]></link> 
    <count><![CDATA[1]]></count> 
   </facet-value> 
   <facet-value> 
    <label><![CDATA[Hanukkah]]></label> 
    <link><![CDATA[?q=new+year;q1=Articles;q2=Hanukkah;x1=content-type;x2=holidays]]></link> 
    <count><![CDATA[1]]></count> 
   </facet-value> 
   <facet-value> 
    <label><![CDATA[Mother&#39;s Day]]></label> 
    <link><![CDATA[?q=new+year;q1=Articles;q2=Mother's+Day;x1=content-type;x2=holidays]]></link> 
    <count><![CDATA[1]]></count> 
   </facet-value> 
   <facet-value> 
    <label><![CDATA[Valentine&#39;s Day]]></label> 
    <link><![CDATA[?q=new+year;q1=Articles;q2=Valentine's+Day;x1=content-type;x2=holidays]]></link> 
    <count><![CDATA[1]]></count> 
   </facet-value> 
  </facet-item> 
  <facet-item> 
   <facet-title><![CDATA[Seasons]]></facet-title> 
   <facet-value> 
    <label><![CDATA[Winter]]></label> 
    <link><![CDATA[?q=new+year;q1=Articles;q2=Winter;x1=content-type;x2=seasons]]></link> 
    <count><![CDATA[20]]></count> 
   </facet-value> 
   <facet-value> 
    <label><![CDATA[Summer]]></label> 
    <link><![CDATA[?q=new+year;q1=Articles;q2=Summer;x1=content-type;x2=seasons]]></link> 
    <count><![CDATA[7]]></count> 
   </facet-value> 
   <facet-value> 
    <label><![CDATA[Autumn]]></label> 
    <link><![CDATA[?q=new+year;q1=Articles;q2=Autumn;x1=content-type;x2=seasons]]></link> 
    <count><![CDATA[4]]></count> 
   </facet-value> 
   <facet-value> 
    <label><![CDATA[Spring]]></label> 
    <link><![CDATA[?q=new+year;q1=Articles;q2=Spring;x1=content-type;x2=seasons]]></link> 
    <count><![CDATA[2]]></count> 
   </facet-value> 
  </facet-item> 
 </facets> 
```

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Tags in Facets </p> </th> 
   <th colname="col2" class="entry"> <p>Beschreibung </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;facet-title&gt; </span> </p> </td> 
   <td colname="col2"> <p> Kundenorientierter Titel für die Facette. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;label&gt; </span> </p> </td> 
   <td colname="col2"> <p> Kundenorientierte Beschriftung für die Facettenoption. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;link&gt; </span> </p> </td> 
   <td colname="col2"> <p> Relativer Link zu Ergebnissen, die durch die Option verfeinert werden. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;count&gt; </span> </p> </td> 
   <td colname="col2"> <p> Die Anzahl der Ergebnisse in dieser verfeinerten Ergebnismenge. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;undolink&gt; </span> </p> </td> 
   <td colname="col2"> <p> Wenn ein Facettenwert ausgewählt ist, gibt der Knoten einen "Rückgängig-Link"zurück, über den ein Kunde die Ergebnisse zurückverfolgen kann. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Kopfzeile und Abfrage {#section_1D57062259CA46E0B4F598FA4EB37065}

Beispiel:

```xml
<result> 
 <query> 
  <user-query><![CDATA[new year]]></user-query> 
  <lower-results><![CDATA[1]]></lower-results> 
  <upper-results><![CDATA[16]]></upper-results> 
  <total-results><![CDATA[621]]></total-results> 
 </query> 
```

Zusammengenommen stellen diese Tags eine Meldung wie die folgende dar: &quot;Die Ergebnisse 1-16 von 621 für &quot;neues Jahr&quot;.&quot;

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Tags in der Kopfzeile und Abfrage </p> </th> 
   <th colname="col2" class="entry"> <p>Beschreibung </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;user-query&gt; </span> </p> </td> 
   <td colname="col2"> <p> Die mit der Anforderung gesendete Suchbegriffs-Abfrage. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;lower-results&gt; </span> </p> </td> 
   <td colname="col2"> <p> Die Elementnummer des ersten Ergebnisses auf dieser Seite. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;upper-results&gt; </span> </p> </td> 
   <td colname="col2"> <p> Die Elementnummer des letzten Ergebnisses auf dieser Seite. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;total-results&gt; </span> </p> </td> 
   <td colname="col2"> <p> Die Gesamtanzahl der Ergebnisse, die mit der Abfrage des Benutzers übereinstimmen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;custom-field&gt; </span> </p> </td> 
   <td colname="col2"> <p> Ein optionales Feld, das global für die Suchergebnisse gilt. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Paginierung {#section_504E7AB570BD49AF9839530DC438EE96}

Beispiel:

```xml
<pagination> 
 <total-pages><39></total-pages> 
 <pages> 
   <page position="first"></page> 
   <page position="last">?i=1;page=39;q=new+year;q1=Articles;x1=content-type]]></page> 
   <page position="previous"></page> 
   <page position="next">?i=1;page=2;q=new+year;q1=Articles;x1=content-type]]></page> 
   <page position="1" selected="true">?i=1;q=new+year;q1=Articles;x1=content-type]]></page> 
   <page position="2">?i=1;page=2;q=new+year;q1=Articles;x1=content-type]]></page> 
   <page position="3">?i=1;page=3;q=new+year;q1=Articles;x1=content-type]]></page> 
   <page position="4">?i=1;page=4;q=new+year;q1=Articles;x1=content-type]]></page> 
   <page position="5">?i=1;page=5;q=new+year;q1=Articles;x1=content-type]]></page> 
   <page position="6">?i=1;page=6;q=new+year;q1=Articles;x1=content-type]]></page> 
   <page position="7">?i=1;page=7;q=new+year;q1=Articles;x1=content-type]]></page> 
   <page position="8">?i=1;page=8;q=new+year;q1=Articles;x1=content-type]]></page> 
   <page position="9">?i=1;page=9;q=new+year;q1=Articles;x1=content-type]]></page> 
   <page position="10">?i=1;page=10;q=new+year;q1=Articles;x1=content-type]]></page> 
 </pages> 
</pagination> 
```

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Tags in der Paginierung </p> </th> 
   <th colname="col2" class="entry"> <p>Beschreibung </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;total-pages&gt; </span> </p> </td> 
   <td colname="col2"> <p> Gesamtanzahl der Ergebnisseiten, basierend auf der Anzahl der Ergebnisse geteilt durch die Anzahl der Ergebnisse pro Seite. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;page position="first"&gt; </span> </p> </td> 
   <td colname="col2"> <p> Enthält einen relativen Link zur ersten Seite in der Ergebnismenge, es sei denn, der Kunde zeigt bereits Seite 1 an. In diesem Fall ist er leer. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;page position="last"&gt; </span> </p> </td> 
   <td colname="col2"> <p> Enthält einen relativen Link zur letzten Seite in der Ergebnismenge, es sei denn, der Kunde zeigt die letzte Seite an. In diesem Fall ist er leer. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;page position="previous"&gt; </span> </p> </td> 
   <td colname="col2"> <p> Enthält einen relativen Link zur vorherigen Seite im Ergebnissatz, es sei denn, der Kunde zeigt Seite 1 an; in diesem Fall ist er leer. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;page position="next"&gt; </span> </p> </td> 
   <td colname="col2"> <p> Enthält einen relativen Link zur letzten Seite in der Ergebnismenge, es sei denn, der Kunde zeigt die letzte Seite an. In diesem Fall ist er leer. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;page position="x"&gt;</span> </p> </td> 
   <td colname="col2"> <p> Enthält einen relativen Link zu einer bestimmten Seitenzahl. Es werden zehn zusammenhängende Seitenzahlen angezeigt. Auf Seite 1 wären es die Seiten 1-10. Am Ende der Ergebnismenge (in diesem Fall 39) wären es die Seiten 30-39. Beispiel: In der Mitte des Ergebnissatzes, Seite 15, wären es die Seiten 11-20. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> selected="true"&gt;  </span> </p> </td> 
   <td colname="col2"> <p> Gilt als Attribut für die aktuell ausgewählte Seite. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Kürzliche Suchvorgänge {#section_525816A0355C48F8970D89B8FC3F1FFF}

Die Funktion &quot;Letzte Suchen&quot;ist eine Cookie-basierte Funktion, die nur funktioniert, wenn Sie die Cookie-Informationen an die Server weiterleiten.

Beispiel:

```xml
<recent-searches> 
 <recent-search> 
  <search-term><![CDATA[shoes]]></search-term> 
  <link><![CDATA[?q=shoes]]></link> 
 </recent-search> 
</recent-searches> 
```

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Tags in "Zuletzt verwendete Suchen" </p> </th> 
   <th colname="col2" class="entry"> <p>Beschreibung </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;recent-search&gt; </span> </p> </td> 
   <td colname="col2"> <p> Ein einzelner Knoten für die aktuelle Suche. Sie können über mehrere Nodes der letzten Suche verfügen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-term&gt; </span> </p> </td> 
   <td colname="col2"> <p> Der Begriff, nach dem der Kunde zuvor gesucht hat. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;link&gt; </span> </p> </td> 
   <td colname="col2"> <p> Links zur vorherigen Suche. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Ergebnisse {#section_41AC56BB0A084BF59379B06C8BEF2157}

Der Ergebnissatz ist ein anpassbarer Bereich der JSON-Antwort. Jeder Index ist in den Feldbenennungsmechanismen von Metadaten eindeutig. Es gibt allgemeine Felder, die für jedes Ergebnis zurückgegeben werden, z. B. Titel, Beschreibung und URL. Alle Metadaten, die für eine Seite im Index definiert sind, können jedoch in jedem Ergebnisknoten verwendet werden. Kategorisierung, Preise, Farben und Miniaturansichten sind nur einige der Optionen, die Sie auf ein Ergebnis anwenden können, um überzeugendere Suchergebnisse zu erzielen.

Das Ergebnisformat wird basierend auf den für Ihre Implementierung spezifischen Metadaten angepasst. Hier finden Sie alle Ergebnisdaten, die in den Ergebnissen angezeigt werden sollen, einschließlich URLs für Miniaturbilder.

Darüber hinaus ist es möglich, mehrere Ergebniszonen innerhalb der Seite zu konfigurieren, z. B. &quot;Vorgestellte Ergebnisse&quot;oder separate Ergebnisabschnitte &quot;Produkte&quot;und &quot;Inhalt&quot;. In diesen Fällen werden mehrere Ergebniszonen im HTML-Code bereitgestellt, obwohl Facetten nur mit der primären Ergebnismenge verknüpft sind.

Beispiel:

```xml
 <results> 
  <result> 
    <index><![CDATA[1]]></index> 
    <result-title><![CDATA[New Year's Eve Slumber Party]]></result-title> 
    <url><![CDATA[https://mysite.com/parties/new-years-eve-slumber-party-705199/]]></url> 
    <meta-description><![CDATA[Fun New Year's celebration ideas for your kids]]></meta-description> 
    <category><![CDATA[parties]]></category> 
    <content-type><![CDATA[Articles]]></content-type> 
    <small-thumbnail-img><![CDATA[https://mysite.com/assets/cms/parties/new-years-eve-

slumber-party-parties-photo-80-FF1200SLEEPA18.jpg]]></small-thumbnail-img> 
    <large-thumbnail-img><![CDATA[https://mysite.com/assets/cms/parties/new-years-eve- 
slumber-party-parties-photo-160-FF1200SLEEPA18.jpg]]></large-thumbnail-img> 
    <byline><![CDATA[Nancy Mades]]></byline> 
    <blurb><![CDATA[Fun New Year's celebration ideas for your kids]]></blurb> 
  </result>   
  <result> 
    <index><![CDATA[2]]></index> 
    <result-title><![CDATA[10 Holiday Traditions to Start This Year]]></result-title> 
    <url><![CDATA[https://mysite.com/parties/10-holiday-traditions-to-start-this-year-704781/]]></url> 
    <meta-description><![CDATA[Reader ideas to make Thanksgiving, Christmas, and New Year's even more magical]]></meta-description> 
    <category><![CDATA[parties]]></category> 
    <content-type><![CDATA[Articles]]></content-type> 
    <small-thumbnail-img><![CDATA[https://mysite.com/assets/cms/parties/10-holiday- 
traditions-to-start-this-year-parties-photo-80-FF1107HOLIA01.jpg]]></small-thumbnail-img> 
    <large-thumbnail-img><![CDATA[https://mysite.com/assets/cms/parties/10-holiday- 
traditions-to-start-this-year-parties-photo-160-FF1107HOLIA01.jpg]]></large-thumbnail-img> 
    <byline><![CDATA[Julie Taylor]]></byline> 
    <blurb><![CDATA[Reader ideas to make Thanksgiving, Christmas, and New Year's even more magical]]></blurb> 
  </result>   
  <result> 
    <index><![CDATA[3]]></index> 
    <result-title><![CDATA[A Perfect New Year's Eve]]></result-title> 
    <url><![CDATA[https://mysite.com/parties/a-perfect-new-years-eve-705258/]]></url> 
    <meta-description><![CDATA[You can turn New Year's into a celebration for the whole family.]]></meta-description> 
    <category><![CDATA[parties]]></category> 
    <content-type><![CDATA[Articles]]></content-type> 
    <byline><![CDATA[Teri Keough]]></byline> 
    <blurb><![CDATA[You can turn New Year's into a celebration for the whole family.]]></blurb> 
  </result>   
  <result> 
    <index><![CDATA[4]]></index> 
    <result-title><![CDATA[New Year's Fun and Games]]></result-title> 
    <url><![CDATA[https://mysite.com/parties/new-years-fun-and-games-705220/]]></url> 
    <meta-description><![CDATA[Craft, game and food ideas for a New Year's celebration with kids.]]></meta-description> 
    <category><![CDATA[parties]]></category> 
    <content-type><![CDATA[Articles]]></content-type> 
    <byline><![CDATA[Charlotte Meryman]]></byline> 
    <blurb><![CDATA[Craft, game and food ideas for a New Year's celebration with kids.]]></blurb> 
  </result>   
  <result> 
    <index><![CDATA[5]]></index> 
    <result-title><![CDATA[11 Great Ways to Start the New Year]]></result-title> 
    <url><![CDATA[https://mysite.com/parties/11-great-ways-to-start-the-new-year-705552/]]></url> 
    <meta-description><![CDATA[11 New Family Traditions to Start This Year from My Magazine]]></meta-description> 
    <category><![CDATA[parties]]></category> 
    <content-type><![CDATA[Articles]]></content-type> 
    <byline><![CDATA[Emily Block]]></byline> 
    <blurb><![CDATA[11 New Family Traditions to Start This Year from My Magazine]]></blurb> 
  </result>   
  <result> 
    <index><![CDATA[6]]></index> 
    <result-title><![CDATA[Celebrating Chinese New Year]]></result-title> 
    <url><![CDATA[https://mysite.com/parties/celebrating-chinese-new-year-705260/]]></url> 
    <meta-description><![CDATA[Crafts, food, and games to help you celebrate Chinese New Year.]]></meta-description> 
    <category><![CDATA[parties]]></category> 
    <content-type><![CDATA[Articles]]></content-type> 
    <blurb><![CDATA[Crafts, food, and games to help you celebrate Chinese New Year.]]></blurb> 
  </result>   
  <result> 
    <index><![CDATA[7]]></index> 
    <result-title><![CDATA[New Year's Eve, Family Style]]></result-title> 
    <url><![CDATA[https://mysite.com/holidays/new-years-eve-family-style-701283/]]></url> 
    <meta-description><![CDATA[Start a family New Year's Eve tradition by having an evening of kid-focused fun at home]]></meta-description> 
    <category><![CDATA[holidays]]></category> 
    <content-type><![CDATA[Articles]]></content-type> 
    <blurb><![CDATA[Start a family New Year's Eve tradition by having an evening of kid-focused fun at home]]></blurb> 
  </result>   
  <result> 
    <index><![CDATA[8]]></index> 
    <result-title><![CDATA[Chinese New Year Activities]]></result-title> 
    <url><![CDATA[https://mysite.com/crafts/chinese-new-year-activities-710345/]]></url> 
    <meta-description><![CDATA[Activities for celebrating Chinese New Year.]]></meta-description> 
    <category><![CDATA[crafts]]></category> 
    <content-type><![CDATA[Articles]]></content-type> 
    <blurb><![CDATA[Activities for celebrating Chinese New Year.]]></blurb> 
  </result>   
  <result> 
    <index><![CDATA[9]]></index> 
    <result-title><![CDATA[More Organized in the New Year]]></result-title> 
    <url><![CDATA[https://mysite.com/holidays/more-organized-in-the-new-year-701284/]]></url> 
    <meta-description><![CDATA[Tips for getting your household more organized--and getting the kids to help.]]></meta-description> 
    <category><![CDATA[holidays]]></category> 
    <content-type><![CDATA[Articles]]></content-type> 
    <blurb><![CDATA[Tips for getting your household more organized--and getting your kids to help out.]]></blurb> 
  </result>   
  <result> 
    <index><![CDATA[10]]></index> 
    <result-title><![CDATA[Checklists: Year-End Safety Checklist]]></result-title> 
    <url><![CDATA[https://mysite.com/holidays/checklists-year-end-safety-checklist-701352/]]></url> 
    <meta-description><![CDATA[Make sure that your home is safe with our year-end safety checklist!]]></meta-description> 
    <category><![CDATA[holidays]]></category> 
    <content-type><![CDATA[Articles]]></content-type> 
    <blurb><![CDATA[Make sure that your home is safe with our year-end safety checklist!]]></blurb> 
  </result>   
 </results> 
</customer-result> 
```

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Tags in Ergebnissen </p> </th> 
   <th colname="col2" class="entry"> <p>Beschreibung </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;index&gt; </span> </p> </td> 
   <td colname="col2"> <p> Die Seriennummer des Ergebnisses in diesem Ergebnissatz. In diesem Beispiel, bei dem pro Seite zehn Ergebnisse angezeigt werden, hätte das erste Element auf Seite 2 der Ergebnisse den Index 11. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;result-title&gt; </span> </p> </td> 
   <td colname="col2"> <p> Der kundenorientierte Titel für diese Seite. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;url&gt; </span> </p> </td> 
   <td colname="col2"> <p> Die URL für diese Seite. Es wird zum Erstellen eines Hyperlinks verwendet, über den der Kunde durch die Ergebnisse klicken kann. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Suchformular {#section_434DA13EA295474C99FFE9F14801CD0E}

Beispiel:

```xml
<search-form> 
 <include-tnt-mbox>1 </included-tnt-mbox> 
 <autocomplete> 
  <css><![CDATA[<!--link rel="stylesheet" type="te 
        xt/css"href="//content.atomz.com/sp000000a8/publish/autoc 
        omplete_styles.css?sp_css_cache_ver=2" /-->]]> 
  </css> 
  <form-content><![CDATA[<div id="autocomplete"></div>]]> 
  </form-content> 
  <js><![CDATA[<script type="text/javascript" 
   src="//content.atomz.com/sp100491de/publish/autoc 
   omplete_data.js?sp_js_cache_ver=3"></script>]]> 
  </js> 
 </autcomplete> 
 <hidden-parameters> 
  <parameter> 
   <name><![CDATA[store]]></name> 
   <value><![CDATA[mens]]></value> 
  </parameter> 
 </hidden-parameters> 
</search-form>
```

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Tags im Suchformular </p> </th> 
   <th colname="col2" class="entry"> <p>Beschreibung </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;include-tnt-mbox&gt; </span> </p> </td> 
   <td colname="col2"> <p> Optional. Wenn Sie im JSON vorhanden sind, gibt der Wert 1 an, dass Ihr Konto mit <span class="keyword"> Test&amp;Zielgruppe </span> verknüpft ist und mindestens eine Geschäftsregel in einem A:B-Test enthält. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;autocomplete&gt; </span> </p> </td> 
   <td colname="col2"> <p> Optional. Bei der Verwendung der automatischen Vervollständigung wird dieser Knoten angezeigt, um anzugeben, dass die CSS- und JavaScript-Datei zusammen mit dem Inhalt im Formular auf der Seite vorhanden ist. Diese Felder ändern sich in der Regel nur, wenn jemand eine Einstellung für die automatische Vervollständigung geändert hat. In solchen Fällen wird das Feld xxx_cache_ver inkrementiert, um die Ungültigmachung des zwischengespeicherten Inhalts im Browser Ihres Kunden zu erzwingen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;css&gt; </span> </p> </td> 
   <td colname="col2"> <p> Die mit der automatischen Vervollständigung verknüpfte CSS. Es wird empfohlen, dieses Tag hoch auf der Seite zu platzieren, um das Rendern der Seite zu verbessern. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;form-content&gt; </span> </p> </td> 
   <td colname="col2"> <p> Inhalte, die in Ihrer Suche erforderlich sind, damit das Dienstprogramm für die automatische Vervollständigung mit der richtigen Steuerung verknüpft wird. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;js&gt; </span> </p> </td> 
   <td colname="col2"> <p> Benutzerdefiniertes JavaScript, das für die automatische Vervollständigung erforderlich ist. Es wird empfohlen, dieses Tag auf der Seite niedrig zu platzieren, um das Rendern der Seite zu verbessern. Das YUI-JavaScript ist auch zum automatischen Ausfüllen erforderlich. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;hidden-parameters&gt; </span> </p> </td> 
   <td colname="col2"> <p> Enthält alle ausgeblendeten Parameter (Name und Wert), die in das Suchformular aufgenommen werden sollen. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Sortierung {#section_558853CD376F4D71BACF211D53085D55}

Das folgende Beispiel zeigt die Daten eines dreiteiligen Sortierungsmenüs. Das Menü ermöglicht es dem Kunden, nach Relevanz, Titel oder Bewertung zu sortieren. Das aktuell ausgewählte Element enthält das Attribut &quot;selected=true&quot;. &quot;. Wählen Sie immer eine Relevanzoption, damit der Kunde zu den ursprünglich angezeigten Standardsuchergebnissen zurückkehren kann.

Beispiel:

```xml
 <sort> 
  <sort-item selected="true"> 
   <label><![CDATA[Relevance]]></label> 
   <value><![CDATA[relevance]]></value> 
   <link><![CDATA[]]></link> 
  </sort-item> 
  <sort-item> 
   <label><![CDATA[Title]]></label> 
   <value><![CDATA[title]]></value> 
   <link><![CDATA[?q=new+year;q1=Articles;sort=title;x1=content-type]]></link>     
  </sort-item> 
  <sort-item> 
   <label><![CDATA[Rating]]></label> 
   <value><![CDATA[user-rating]]></value> 
   <link><![CDATA[?q=new+year;q1=Articles;sort=user-rating;x1=content-type]]></link>     
  </sort-item> 
 </sort>
```

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Tags im Menü "Sortieren" </p> </th> 
   <th colname="col2" class="entry"> <p>Beschreibung </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;label&gt; </span> </p> </td> 
   <td colname="col2"> <p> Der kundenorientierte Text für die Option. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;value&gt; </span> </p> </td> 
   <td colname="col2"> <p> Stellt den Wert des Parameters für die Zeichenfolge der Abfrage "sort"für diese Option dar. Dieses Tag ist nicht erforderlich, wenn der <span class="codeph"> &lt;link&gt; </span>-Wert verwendet wird. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;link&gt; </span> </p> </td> 
   <td colname="col2"> <p> Bei den nicht ausgewählten Optionen enthält der Parameter <span class="codeph"> &lt;link&gt; </span> den relativen Link, der denselben Ergebnissatz zurückgibt, sortiert nach dem neuen Sortierparameter. Dieses Feld ist für die derzeit ausgewählte Sortieroption leer. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Vorschläge {#section_6EC104E1DDD94AC799B65E6E61A2FB3C}

Vorschläge werden zurückgegeben, wenn nur wenige Ergebnisse oder keine Ergebnisse vorliegen. Dieser Knoten enthält Begriffe, die zu erfolgreichen Abfragen führen und auf der Seite &quot;Keine Ergebnisse&quot;angezeigt werden können. Der Link wird auch zurückgegeben, damit ein Kunde zur neuen Abfrage springen kann.

Beispiel:

```xml
 <suggestions> 
  <suggestion-item> 
   <link><![CDATA[?q=video]]></link> 
   <word><![CDATA[video]]> 
```

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Tags in Vorschlägen </p> </th> 
   <th colname="col2" class="entry"> <p>Beschreibung </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;link&gt; </span> </p> </td> 
   <td colname="col2"> <p>Ein relativer Link, über den ein Hyperlink zu Suchergebnissen für den Empfehlungsbegriff erstellt wird. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;word&gt; </span> </p> </td> 
   <td colname="col2"> <p>Der vorgeschlagene Begriff. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Zonen {#section_AE53A498B440465EAF2286F2AE87D548}

Beispiel:

```xml
<zones> 
 <zone> 
  <name><![CDATA[best-sellers]]></name> 
  <display><![CDATA[1]]></display> 
 </zone> 
</zones> 
```

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Tags in Zonen </p> </th> 
   <th colname="col2" class="entry"> <p>Beschreibung </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;zone&gt; </span> </p> </td> 
   <td colname="col2"> <p> Ein einzelner Zonenknoten. Sie können über mehrere Zonen-Nodes verfügen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;name&gt; </span> </p> </td> 
   <td colname="col2"> <p> Der Name der Zone. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;display&gt; </span> </p> </td> 
   <td colname="col2"> <p> 1 oder 0, um anzugeben, ob die Zone angezeigt wird oder nicht. Der eigentliche Bereichsinhalt kann ein statischer Bereich auf Ihrer Webseite oder in Ihren Suchergebnissen sein, z. B. beste Verkäufer oder verwandte Produkte. </p> </td> 
  </tr> 
 </tbody> 
</table>

## XML-Ausgabe der geführten Suche {#reference_D93E859A277643068B10AE7A61C973EA}

Tabellen, die die Standard-XML-Antwortausgabe beschreiben.

Sie können die XML-Antwort auf Folgendes überprüfen:

* [Banner](../c-appendices/c-guidedsearchoutput.md#section_6A19EC26DD3B494194AAA788151B78B5)
* [Breadcrumb](../c-appendices/c-guidedsearchoutput.md#section_E48A71B0EBDB4EDDA7587009AD865488)
* [Facets](../c-appendices/c-guidedsearchoutput.md#section_5CEB1F966C004FFEA3CF675638966E25)
* [Kopfzeile und Abfrage](../c-appendices/c-guidedsearchoutput.md#section_802835E19BCB48239C6770A1B72DFFF8)
* [Paginierung](../c-appendices/c-guidedsearchoutput.md#section_72DB86DDE1284B1EA295CFFBC16A3150)
* [Kürzliche Suchvorgänge](../c-appendices/c-guidedsearchoutput.md#section_BCA2DDD17F264CF6BA11634E1A514E28)
* [Ergebnisse](../c-appendices/c-guidedsearchoutput.md#section_EC496F5CA2634158891455E2F6DF6833)
* [Suchformular](../c-appendices/c-guidedsearchoutput.md#section_F92D8C3D37174A10A4E26CAFF3F3DF89)
* [Sortierung](../c-appendices/c-guidedsearchoutput.md#section_32DC50A103BF491BA3665A5CADCCAADE)
* [Vorschläge](../c-appendices/c-guidedsearchoutput.md#section_D81BCE46F0AF443695DF9C4BA084B716)
* [Zonen](../c-appendices/c-guidedsearchoutput.md#section_15D8AA585F3246799968BA88EE2C9FC2)

## Banner {#section_6A19EC26DD3B494194AAA788151B78B5}

Beispiel:

```xml
<banners> 
 <banner> 
  <area><![CDATA[top-left]]></area> 
  <content><![CDATA[<img src="https://www.megacorp.com/discount.gif"/>]]></content> 
 </banner> 
</banners>
```

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Tags in Bannern </p> </th> 
   <th colname="col2" class="entry"> <p>Beschreibung </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;banner&gt; </span> </p> </td> 
   <td colname="col2"> <p> Ein einzelner Bannerknoten. Sie können über mehrere Bannerknoten verfügen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;area&gt; </span> </p> </td> 
   <td colname="col2"> <p> Der Bereich auf der Webseite, in dem das Banner angezeigt wird. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;Inhalt&gt; </span> </p> </td> 
   <td colname="col2"> <p> Der HTML-Inhalt für den Bannerbereich. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Breadcrumb {#section_E48A71B0EBDB4EDDA7587009AD865488}

Im folgenden Beispiel wird die Auswahl dem Breadcrumb hinzugefügt, sobald der Kunde durch die Facetten weiter herunterfährt. Jedes Element wird als `<breadcrumb-item>` dargestellt.

Beispiel:

```xml
 <breadcrumb> 
  <breadcrumb-item> 
   <link><![CDATA[?q=new+year]]></link> 
   <value><![CDATA[new year]]></value> 
  </breadcrumb-item> 
  <breadcrumb-item> 
   <link><![CDATA[?q=new+year;q1=Articles;x1=content-type]]></link> 
   <value><![CDATA[Articles]]></value> 
  </breadcrumb-item> 
 </breadcrumb> 
```

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Tags in Breadcrumb </p> </th> 
   <th colname="col2" class="entry"> <p>Beschreibung </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;link&gt; </span> </p> </td> 
   <td colname="col2"> <p> Ein Link zu den Suchergebnissen, der die gewünschte Ansicht anzeigt. Durch Klicken auf einen Breadcrumb-Link gelangt der Kunde zu einer Ansicht, in der alle nachfolgenden Verfeinerungen entfernt werden. Es stehen auch andere Optionen zur Verfügung. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;value&gt; </span> </p> </td> 
   <td colname="col2"> <p> Für den Kunden sichtbarer Text für das Breadcrumb-Element. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Facets {#section_5CEB1F966C004FFEA3CF675638966E25}

Facets sind Verfeinerungsoptionen, die Kunden die Möglichkeit geben, nach den Ergebnissen zu filtern. Facets werden häufig für Kategorisierung, Preisbereiche, Farbauswahl und andere Attributverfeinerungen verwendet. Die Metadaten im Index sind die Antriebsfacetten.

Es ist üblich, Kategorisierungsfacetten auszublenden oder anzuzeigen, wenn ein Kunde sich durch die Kategorisierung nach unten bewegt. Die höchste Kategorisierungsebene (Kategorie) wird als Ebene 1 bezeichnet. Wenn ein Kunde auf eine Option der Stufe 1 klickt, werden die Optionen zur Tier-2-Verfeinerung (Unterkategorie) angezeigt und die Optionen der Ebene 1 werden ausgeblendet. Wenn ein Kunde auf die Option &quot;Ebene 2&quot;klickt, werden die Optionen für die Tier-3-Verfeinerung (Unterkategorie) angezeigt und die Optionen für Ebene 2 werden ausgeblendet. Wie oben erwähnt, werden diese Optionen ausgeblendet und angezeigt. Ihre Webanwendung wird dadurch nicht beeinträchtigt.

Jede Facette ist in `<facet-item>`-Tags enthalten. Im folgenden Beispiel wird eine Facette gezeigt, die es dem Kunden ermöglicht, die Suchergebnisse nach &quot;Urlaub&quot;zu verfeinern.

Beispiel:

```xml
 <facets> 
  <facet-item> 
   <facet-title><![CDATA[Holidays]]></facet-title> 
   <facet-value> 
    <label><![CDATA[New Year]]></label> 
    <link><![CDATA[?q=new+year;q1=Articles;q2=New+Year;x1=content-type;x2=holidays]]></link> 
    <count><![CDATA[11]]></count> 
   </facet-value> 
   <facet-value> 
    <label><![CDATA[Christmas]]></label> 
    <link><![CDATA[?q=new+year;q1=Articles;q2=Christmas;x1=content-type;x2=holidays]]></link> 
    <count><![CDATA[7]]></count> 
   </facet-value> 
   <facet-value> 
    <label><![CDATA[Chinese New Year]]></label> 
    <link><![CDATA[?q=new+year;q1=Articles;q2=Chinese+New+Year;x1=content-type;x2=holidays]]></link> 
    <count><![CDATA[2]]></count> 
   </facet-value> 
   <facet-value> 
    <label><![CDATA[Thanksgiving]]></label> 
    <link><![CDATA[?q=new+year;q1=Articles;q2=Thanksgiving;x1=content-type;x2=holidays]]></link> 
    <count><![CDATA[2]]></count> 
   </facet-value> 
   <facet-value> 
    <label><![CDATA[4th of July]]></label> 
    <link><![CDATA[?q=new+year;q1=Articles;q2=4th+of+July;x1=content-type;x2=holidays]]></link> 
    <count><![CDATA[1]]></count> 
   </facet-value> 
   <facet-value> 
    <label><![CDATA[Father&#39;s Day]]></label> 
    <link><![CDATA[?q=new+year;q1=Articles;q2=Father's+Day;x1=content-type;x2=holidays]]></link> 
    <count><![CDATA[1]]></count> 
   </facet-value> 
   <facet-value> 
    <label><![CDATA[Hanukkah]]></label> 
    <link><![CDATA[?q=new+year;q1=Articles;q2=Hanukkah;x1=content-type;x2=holidays]]></link> 
    <count><![CDATA[1]]></count> 
   </facet-value> 
   <facet-value> 
    <label><![CDATA[Mother&#39;s Day]]></label> 
    <link><![CDATA[?q=new+year;q1=Articles;q2=Mother's+Day;x1=content-type;x2=holidays]]></link> 
    <count><![CDATA[1]]></count> 
   </facet-value> 
   <facet-value> 
    <label><![CDATA[Valentine&#39;s Day]]></label> 
    <link><![CDATA[?q=new+year;q1=Articles;q2=Valentine's+Day;x1=content-type;x2=holidays]]></link> 
    <count><![CDATA[1]]></count> 
   </facet-value> 
  </facet-item> 
  <facet-item> 
   <facet-title><![CDATA[Seasons]]></facet-title> 
   <facet-value> 
    <label><![CDATA[Winter]]></label> 
    <link><![CDATA[?q=new+year;q1=Articles;q2=Winter;x1=content-type;x2=seasons]]></link> 
    <count><![CDATA[20]]></count> 
   </facet-value> 
   <facet-value> 
    <label><![CDATA[Summer]]></label> 
    <link><![CDATA[?q=new+year;q1=Articles;q2=Summer;x1=content-type;x2=seasons]]></link> 
    <count><![CDATA[7]]></count> 
   </facet-value> 
   <facet-value> 
    <label><![CDATA[Autumn]]></label> 
    <link><![CDATA[?q=new+year;q1=Articles;q2=Autumn;x1=content-type;x2=seasons]]></link> 
    <count><![CDATA[4]]></count> 
   </facet-value> 
   <facet-value> 
    <label><![CDATA[Spring]]></label> 
    <link><![CDATA[?q=new+year;q1=Articles;q2=Spring;x1=content-type;x2=seasons]]></link> 
    <count><![CDATA[2]]></count> 
   </facet-value> 
  </facet-item>  
 </facets> 
```

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Tags in Facets </p> </th> 
   <th colname="col2" class="entry"> <p>Beschreibung </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;facet-title&gt; </span> </p> </td> 
   <td colname="col2"> <p> Kundenorientierter Titel für die Facette. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;label&gt; </span> </p> </td> 
   <td colname="col2"> <p> Kundenorientierte Beschriftung für die Facettenoption. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;link&gt; </span> </p> </td> 
   <td colname="col2"> <p> Relativer Link zu Ergebnissen, die durch die Option verfeinert werden. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;count&gt; </span> </p> </td> 
   <td colname="col2"> <p> Die Anzahl der Ergebnisse in dieser verfeinerten Ergebnismenge. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;undolink&gt; </span> </p> </td> 
   <td colname="col2"> <p> Wenn ein Facettenwert ausgewählt ist, gibt der Knoten einen "Rückgängig-Link"zurück, über den ein Kunde die Ergebnisse zurückverfolgen kann. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Kopfzeile und Abfrage {#section_802835E19BCB48239C6770A1B72DFFF8}

Beispiel:

```xml
<?xml version="1.0" encoding="utf-8" standalone="yes" ?> 
<result> 
 <query> 
  <user-query><![CDATA[new year]]></user-query> 
  <lower-results><![CDATA[1]]></lower-results> 
  <upper-results><![CDATA[16]]></upper-results> 
  <total-results><![CDATA[621]]></total-results> 
 </query> 
```

Zusammengenommen stellen diese Tags eine Meldung wie die folgende dar: &quot;Die Ergebnisse 1-16 von 621 für &quot;neues Jahr&quot;.&quot;

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Tags in Kopfzeile und Abfrage </p> </th> 
   <th colname="col2" class="entry"> <p>Beschreibung </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;user-query&gt; </span> </p> </td> 
   <td colname="col2"> <p> Die mit der Anforderung gesendete Suchbegriffs-Abfrage. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;lower-results&gt; </span> </p> </td> 
   <td colname="col2"> <p> Die Elementnummer des ersten Ergebnisses auf dieser Seite. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;upper-results&gt; </span> </p> </td> 
   <td colname="col2"> <p> Die Elementnummer des letzten Ergebnisses auf dieser Seite. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;total-results&gt; </span> </p> </td> 
   <td colname="col2"> <p> Die Gesamtanzahl der Ergebnisse, die mit der Abfrage des Benutzers übereinstimmen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;custom-field&gt; </span> </p> </td> 
   <td colname="col2"> <p> Ein optionales Feld, das global für die Suchergebnisse gilt. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Paginierung {#section_72DB86DDE1284B1EA295CFFBC16A3150}

Beispiel:

```xml
<pagination> 
 <total-pages><39></total-pages> 
 <pages> 
   <page position="first"></page> 
   <page position="last">?i=1;page=39;q=new+year;q1=Articles;x1=content-type]]></page> 
   <page position="previous"></page> 
   <page position="next">?i=1;page=2;q=new+year;q1=Articles;x1=content-type]]></page> 
   <page position="1" selected="true">?i=1;q=new+year;q1=Articles;x1=content-type]]></page> 
   <page position="2">?i=1;page=2;q=new+year;q1=Articles;x1=content-type]]></page> 
   <page position="3">?i=1;page=3;q=new+year;q1=Articles;x1=content-type]]></page> 
   <page position="4">?i=1;page=4;q=new+year;q1=Articles;x1=content-type]]></page> 
   <page position="5">?i=1;page=5;q=new+year;q1=Articles;x1=content-type]]></page> 
   <page position="6">?i=1;page=6;q=new+year;q1=Articles;x1=content-type]]></page> 
   <page position="7">?i=1;page=7;q=new+year;q1=Articles;x1=content-type]]></page> 
   <page position="8">?i=1;page=8;q=new+year;q1=Articles;x1=content-type]]></page> 
   <page position="9">?i=1;page=9;q=new+year;q1=Articles;x1=content-type]]></page> 
   <page position="10">?i=1;page=10;q=new+year;q1=Articles;x1=content-type]]></page> 
 </pages> 
</pagination> 
```

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Tags in der Paginierung </p> </th> 
   <th colname="col2" class="entry"> <p>Beschreibung </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;total-pages&gt; </span> </p> </td> 
   <td colname="col2"> <p> Gesamtanzahl der Ergebnisseiten, basierend auf der Anzahl der Ergebnisse geteilt durch die Anzahl der Ergebnisse pro Seite. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;page position="first"&gt; </span> </p> </td> 
   <td colname="col2"> <p> Enthält einen relativen Link zur ersten Seite in der Ergebnismenge, es sei denn, der Kunde zeigt bereits Seite 1 an. In diesem Fall ist er leer. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;page position="last"&gt; </span> </p> </td> 
   <td colname="col2"> <p> Enthält einen relativen Link zur letzten Seite in der Ergebnismenge, es sei denn, der Kunde zeigt die letzte Seite an. In diesem Fall ist er leer. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;page position="previous"&gt; </span> </p> </td> 
   <td colname="col2"> <p> Enthält einen relativen Link zur vorherigen Seite im Ergebnissatz, es sei denn, der Kunde zeigt Seite 1 an; in diesem Fall ist er leer. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;page position="next"&gt; </span> </p> </td> 
   <td colname="col2"> <p> Enthält einen relativen Link zur letzten Seite in der Ergebnismenge, es sei denn, der Kunde zeigt die letzte Seite an. In diesem Fall ist er leer. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;page position="x"&gt;</span> </p> </td> 
   <td colname="col2"> <p> Enthält einen relativen Link zu einer bestimmten Seitenzahl. Es werden zehn zusammenhängende Seitenzahlen angezeigt. Auf Seite 1 wären es die Seiten 1-10. Am Ende der Ergebnismenge (in diesem Fall 39) wären es die Seiten 30-39. Beispiel: In der Mitte des Ergebnissatzes, Seite 15, wären es die Seiten 11-20. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> selected="true"&gt;  </span> </p> </td> 
   <td colname="col2"> <p> Gilt als Attribut für die aktuell ausgewählte Seite. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Kürzliche Suchvorgänge {#section_BCA2DDD17F264CF6BA11634E1A514E28}

Die Funktion &quot;Letzte Suchen&quot;ist eine Cookie-basierte Funktion, die nur funktioniert, wenn Sie die Cookie-Informationen an die Server weiterleiten.

Beispiel:

```xml
<recent-searches> 
 <recent-search> 
  <search-term><![CDATA[shoes]]></search-term> 
  <link><![CDATA[?q=shoes]]></link> 
 </recent-search> 
</recent-searches> 
```

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Tags in "Zuletzt verwendete Suchen" </p> </th> 
   <th colname="col2" class="entry"> <p>Beschreibung </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;recent-search&gt; </span> </p> </td> 
   <td colname="col2"> <p> Ein einzelner Knoten für die aktuelle Suche. Sie können über mehrere Nodes der letzten Suche verfügen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-term&gt; </span> </p> </td> 
   <td colname="col2"> <p> Der Begriff, nach dem der Kunde zuvor gesucht hat. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;link&gt; </span> </p> </td> 
   <td colname="col2"> <p> Links zur vorherigen Suche. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Ergebnisse {#section_EC496F5CA2634158891455E2F6DF6833}

Der Ergebnissatz ist ein anpassbarer Bereich der XML-Antwort. Jeder Index ist in den Feldbenennungsmechanismen von Metadaten eindeutig. Es gibt allgemeine Felder, die für jedes Ergebnis zurückgegeben werden, z. B. Titel, Beschreibung und URL. Alle Metadaten, die für eine Seite im Index definiert sind, können jedoch in jedem Ergebnisknoten verwendet werden. Kategorisierung, Preise, Farben und Miniaturansichten sind nur einige der Optionen, die Sie auf ein Ergebnis anwenden können, um überzeugendere Suchergebnisse zu erzielen.

Das Ergebnisformat wird basierend auf den für Ihre Implementierung spezifischen Metadaten angepasst. Hier finden Sie alle Ergebnisdaten, die in den Ergebnissen angezeigt werden sollen, einschließlich URLs für Miniaturbilder.

Darüber hinaus ist es möglich, mehrere Ergebniszonen innerhalb der Seite zu konfigurieren, z. B. &quot;Vorgestellte Ergebnisse&quot;oder separate Ergebnisabschnitte &quot;Produkte&quot;und &quot;Inhalt&quot;. In diesen Fällen werden mehrere Ergebniszonen im HTML-Code bereitgestellt, obwohl Facetten nur mit der primären Ergebnismenge verknüpft sind.

Beispiel:

```xml
 <results> 
  <result> 
    <index><![CDATA[1]]></index> 
    <result-title><![CDATA[New Year's Eve Slumber Party]]></result-title> 
    <url><![CDATA[https://mysite.com/parties/new-years-eve-slumber-party-705199/]]></url> 
    <meta-description><![CDATA[Fun New Year's celebration ideas for your kids]]></meta-description> 
    <category><![CDATA[parties]]></category> 
    <content-type><![CDATA[Articles]]></content-type> 
    <small-thumbnail-img><![CDATA[https://mysite.com/assets/cms/parties/new-years-eve-

slumber-party-parties-photo-80-FF1200SLEEPA18.jpg]]></small-thumbnail-img> 
    <large-thumbnail-img><![CDATA[https://mysite.com/assets/cms/parties/new-years-eve- 
slumber-party-parties-photo-160-FF1200SLEEPA18.jpg]]></large-thumbnail-img> 
    <byline><![CDATA[Nancy Mades]]></byline> 
    <blurb><![CDATA[Fun New Year's celebration ideas for your kids]]></blurb> 
  </result>   
  <result> 
    <index><![CDATA[2]]></index> 
    <result-title><![CDATA[10 Holiday Traditions to Start This Year]]></result-title> 
    <url><![CDATA[https://mysite.com/parties/10-holiday-traditions-to-start-this-year-704781/]]></url> 
    <meta-description><![CDATA[Reader ideas to make Thanksgiving, Christmas, and New Year's even more magical]]></meta-description> 
    <category><![CDATA[parties]]></category> 
    <content-type><![CDATA[Articles]]></content-type> 
    <small-thumbnail-img><![CDATA[https://mysite.com/assets/cms/parties/10-holiday- 
traditions-to-start-this-year-parties-photo-80-FF1107HOLIA01.jpg]]></small-thumbnail-img> 
    <large-thumbnail-img><![CDATA[https://mysite.com/assets/cms/parties/10-holiday- 
traditions-to-start-this-year-parties-photo-160-FF1107HOLIA01.jpg]]></large-thumbnail-img> 
    <byline><![CDATA[Julie Taylor]]></byline> 
    <blurb><![CDATA[Reader ideas to make Thanksgiving, Christmas, and New Year's even more magical]]></blurb> 
  </result>   
  <result> 
    <index><![CDATA[3]]></index> 
    <result-title><![CDATA[A Perfect New Year's Eve]]></result-title> 
    <url><![CDATA[https://mysite.com/parties/a-perfect-new-years-eve-705258/]]></url> 
    <meta-description><![CDATA[You can turn New Year's into a celebration for the whole family.]]></meta-description> 
    <category><![CDATA[parties]]></category> 
    <content-type><![CDATA[Articles]]></content-type> 
    <byline><![CDATA[Teri Keough]]></byline> 
    <blurb><![CDATA[You can turn New Year's into a celebration for the whole family.]]></blurb> 
  </result>   
  <result> 
    <index><![CDATA[4]]></index> 
    <result-title><![CDATA[New Year's Fun and Games]]></result-title> 
    <url><![CDATA[https://mysite.com/parties/new-years-fun-and-games-705220/]]></url> 
    <meta-description><![CDATA[Craft, game and food ideas for a New Year's celebration with kids.]]></meta-description> 
    <category><![CDATA[parties]]></category> 
    <content-type><![CDATA[Articles]]></content-type> 
    <byline><![CDATA[Charlotte Meryman]]></byline> 
    <blurb><![CDATA[Craft, game and food ideas for a New Year's celebration with kids.]]></blurb> 
  </result>   
  <result> 
    <index><![CDATA[5]]></index> 
    <result-title><![CDATA[11 Great Ways to Start the New Year]]></result-title> 
    <url><![CDATA[https://mysite.com/parties/11-great-ways-to-start-the-new-year-705552/]]></url> 
    <meta-description><![CDATA[11 New Family Traditions to Start This Year from My Magazine]]></meta-description> 
    <category><![CDATA[parties]]></category> 
    <content-type><![CDATA[Articles]]></content-type> 
    <byline><![CDATA[Emily Block]]></byline> 
    <blurb><![CDATA[11 New Family Traditions to Start This Year from My Magazine]]></blurb> 
  </result>   
  <result> 
    <index><![CDATA[6]]></index> 
    <result-title><![CDATA[Celebrating Chinese New Year]]></result-title> 
    <url><![CDATA[https://mysite.com/parties/celebrating-chinese-new-year-705260/]]></url> 
    <meta-description><![CDATA[Crafts, food, and games to help you celebrate Chinese New Year.]]></meta-description> 
    <category><![CDATA[parties]]></category> 
    <content-type><![CDATA[Articles]]></content-type> 
    <blurb><![CDATA[Crafts, food, and games to help you celebrate Chinese New Year.]]></blurb> 
  </result>   
  <result> 
    <index><![CDATA[7]]></index> 
    <result-title><![CDATA[New Year's Eve, Family Style]]></result-title> 
    <url><![CDATA[https://mysite.com/holidays/new-years-eve-family-style-701283/]]></url> 
    <meta-description><![CDATA[Start a family New Year's Eve tradition by having an evening of kid-focused fun at home]]></meta-description> 
    <category><![CDATA[holidays]]></category> 
    <content-type><![CDATA[Articles]]></content-type> 
    <blurb><![CDATA[Start a family New Year's Eve tradition by having an evening of kid-focused fun at home]]></blurb> 
  </result>   
  <result> 
    <index><![CDATA[8]]></index> 
    <result-title><![CDATA[Chinese New Year Activities]]></result-title> 
    <url><![CDATA[https://mysite.com/crafts/chinese-new-year-activities-710345/]]></url> 
    <meta-description><![CDATA[Activities for celebrating Chinese New Year.]]></meta-description> 
    <category><![CDATA[crafts]]></category> 
    <content-type><![CDATA[Articles]]></content-type> 
    <blurb><![CDATA[Activities for celebrating Chinese New Year.]]></blurb> 
  </result>   
  <result> 
    <index><![CDATA[9]]></index> 
    <result-title><![CDATA[More Organized in the New Year]]></result-title> 
    <url><![CDATA[https://mysite.com/holidays/more-organized-in-the-new-year-701284/]]></url> 
    <meta-description><![CDATA[Tips for getting your household more organized--and getting the kids to help.]]></meta-description> 
    <category><![CDATA[holidays]]></category> 
    <content-type><![CDATA[Articles]]></content-type> 
    <blurb><![CDATA[Tips for getting your household more organized--and getting your kids to help out.]]></blurb> 
  </result>   
  <result> 
    <index><![CDATA[10]]></index> 
    <result-title><![CDATA[Checklists: Year-End Safety Checklist]]></result-title> 
    <url><![CDATA[https://mysite.com/holidays/checklists-year-end-safety-checklist-701352/]]></url> 
    <meta-description><![CDATA[Make sure that your home is safe with our year-end safety checklist!]]></meta-description> 
    <category><![CDATA[holidays]]></category> 
    <content-type><![CDATA[Articles]]></content-type> 
    <blurb><![CDATA[Make sure that your home is safe with our year-end safety checklist!]]></blurb> 
  </result>   
 </results> 
</customer-result> 
```

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Tags in Ergebnissen </p> </th> 
   <th colname="col2" class="entry"> <p>Beschreibung </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;index&gt; </span> </p> </td> 
   <td colname="col2"> <p> Die Seriennummer des Ergebnisses in diesem Ergebnissatz. In diesem Beispiel, bei dem pro Seite zehn Ergebnisse angezeigt werden, hätte das erste Element auf Seite 2 der Ergebnisse den Index 11. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;result-title&gt; </span> </p> </td> 
   <td colname="col2"> <p> Der kundenorientierte Titel für diese Seite. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;url&gt; </span> </p> </td> 
   <td colname="col2"> <p> Die URL für diese Seite. Es wird zum Erstellen eines Hyperlinks verwendet, über den der Kunde durch die Ergebnisse klicken kann. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Suchformular {#section_F92D8C3D37174A10A4E26CAFF3F3DF89}

Beispiel:

```xml
<search-form> 
 <include-tnt-mbox>1 </included-tnt-mbox> 
 <autocomplete> 
  <css><![CDATA[<!--link rel="stylesheet" type="te 
        xt/css"href="//content.atomz.com/sp000000a8/publish/autoc 
        omplete_styles.css?sp_css_cache_ver=2" /-->]]> 
  </css> 
  <form-content><![CDATA[<div id="autocomplete"></div>]]> 
  </form-content> 
  <js><![CDATA[<script type="text/javascript" 
   src="//content.atomz.com/sp100491de/publish/autoc 
   omplete_data.js?sp_js_cache_ver=3"></script>]]> 
  </js> 
 </autcomplete> 
 <hidden-parameters> 
  <parameter> 
   <name><![CDATA[store]]></name> 
   <value><![CDATA[mens]]></value> 
  </parameter> 
 </hidden-parameters> 
</search-form>
```

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Tags im Suchformular </p> </th> 
   <th colname="col2" class="entry"> <p>Beschreibung </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;include-tnt-mbox&gt; </span> </p> </td> 
   <td colname="col2"> <p> Optional. Wenn der Wert 1 in der XML vorhanden ist, gibt er an, dass Ihr Konto mit <span class="keyword"> Test&amp;Zielgruppe </span> verknüpft ist und mindestens eine Geschäftsregel enthält, die in einem A:B-Test enthalten ist. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;autocomplete&gt; </span> </p> </td> 
   <td colname="col2"> <p> Optional. Bei der Verwendung der automatischen Vervollständigung wird dieser Knoten angezeigt, um anzugeben, dass die CSS- und JavaScript-Datei zusammen mit dem Inhalt im Formular auf der Seite vorhanden ist. Diese Felder ändern sich in der Regel nur, wenn jemand eine Einstellung für die automatische Vervollständigung geändert hat. In solchen Fällen wird das Feld xxx_cache_ver inkrementiert, um die Ungültigmachung des zwischengespeicherten Inhalts im Browser Ihres Kunden zu erzwingen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;css&gt; </span> </p> </td> 
   <td colname="col2"> <p> Die mit der automatischen Vervollständigung verknüpfte CSS. Es wird empfohlen, dieses Tag hoch auf der Seite zu platzieren, um das Rendern der Seite zu verbessern. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;form-content&gt; </span> </p> </td> 
   <td colname="col2"> <p> Inhalte, die in Ihrer Suche erforderlich sind, damit das Dienstprogramm für die automatische Vervollständigung mit der richtigen Steuerung verknüpft wird. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;js&gt; </span> </p> </td> 
   <td colname="col2"> <p> Benutzerdefiniertes JavaScript, das für die automatische Vervollständigung erforderlich ist. Es wird empfohlen, dieses Tag auf der Seite niedrig zu platzieren, um das Rendern der Seite zu verbessern. Das YUI-JavaScript ist auch zum automatischen Ausfüllen erforderlich. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;hidden-parameters&gt; </span> </p> </td> 
   <td colname="col2"> <p> Enthält alle ausgeblendeten Parameter (Name und Wert), die in das Suchformular aufgenommen werden sollen. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Sortierung {#section_32DC50A103BF491BA3665A5CADCCAADE}

Das folgende Beispiel zeigt die Daten eines dreiteiligen Sortierungsmenüs. Das Menü ermöglicht es dem Kunden, nach Relevanz, Titel oder Bewertung zu sortieren. Das aktuell ausgewählte Element enthält das Attribut &quot;selected=true&quot;. &quot;. Wählen Sie immer eine Relevanzoption, damit der Kunde zu den ursprünglich angezeigten Standardsuchergebnissen zurückkehren kann.

Beispiel:

```xml
 <sort> 
  <sort-item selected="true"> 
   <label><![CDATA[Relevance]]></label> 
   <value><![CDATA[relevance]]></value> 
   <link><![CDATA[]]></link> 
  </sort-item> 
  <sort-item> 
   <label><![CDATA[Title]]></label> 
   <value><![CDATA[title]]></value> 
   <link><![CDATA[?q=new+year;q1=Articles;sort=title;x1=content-type]]></link>     
  </sort-item> 
  <sort-item> 
   <label><![CDATA[Rating]]></label> 
   <value><![CDATA[user-rating]]></value> 
   <link><![CDATA[?q=new+year;q1=Articles;sort=user-rating;x1=content-type]]></link>     
  </sort-item> 
 </sort>
```

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Tags im Menü "Sortieren" </p> </th> 
   <th colname="col2" class="entry"> <p>Beschreibung </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;label&gt; </span> </p> </td> 
   <td colname="col2"> <p> Der kundenorientierte Text für die Option. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;value&gt; </span> </p> </td> 
   <td colname="col2"> <p> Stellt den Wert des Parameters für die Zeichenfolge der Abfrage "sort"für diese Option dar. Dieses Tag ist nicht erforderlich, wenn der <span class="codeph"> &lt;link&gt; </span>-Wert verwendet wird. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;link&gt; </span> </p> </td> 
   <td colname="col2"> <p> Bei den nicht ausgewählten Optionen enthält der Parameter <span class="codeph"> &lt;link&gt; </span> den relativen Link, der denselben Ergebnissatz zurückgibt, sortiert nach dem neuen Sortierparameter. Dieses Feld ist für die derzeit ausgewählte Sortieroption leer. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Vorschläge {#section_D81BCE46F0AF443695DF9C4BA084B716}

Vorschläge werden zurückgegeben, wenn nur wenige Ergebnisse oder keine Ergebnisse vorliegen. Dieser Knoten enthält Begriffe, die zu erfolgreichen Abfragen führen und auf der Seite &quot;Keine Ergebnisse&quot;angezeigt werden können. Der Link wird auch zurückgegeben, damit ein Kunde zur neuen Abfrage springen kann.

Beispiel:

```xml
 <suggestions> 
  <suggestion-item> 
   <link><![CDATA[?q=video]]></link> 
   <word><![CDATA[video]]> 
```

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Tags in Vorschlägen </p> </th> 
   <th colname="col2" class="entry"> <p>Beschreibung </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;link&gt; </span> </p> </td> 
   <td colname="col2"> <p>Ein relativer Link, über den ein Hyperlink zu Suchergebnissen für den Empfehlungsbegriff erstellt wird. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;word&gt; </span> </p> </td> 
   <td colname="col2"> <p>Der vorgeschlagene Begriff. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Zonen {#section_15D8AA585F3246799968BA88EE2C9FC2}

Beispiel:

```xml
<zones> 
 <zone> 
  <name><![CDATA[best-sellers]]></name> 
  <display><![CDATA[1]]></display> 
 </zone> 
</zones> 
```

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Tags in Zonen </p> </th> 
   <th colname="col2" class="entry"> <p>Beschreibung </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;zone&gt; </span> </p> </td> 
   <td colname="col2"> <p> Ein einzelner Zonenknoten. Sie können über mehrere Zonen-Nodes verfügen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;name&gt; </span> </p> </td> 
   <td colname="col2"> <p> Der Name der Zone. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;display&gt; </span> </p> </td> 
   <td colname="col2"> <p> 1 oder 0, um anzugeben, ob die Zone angezeigt wird oder nicht. Der eigentliche Bereichsinhalt kann ein statischer Bereich auf Ihrer Webseite oder in Ihren Suchergebnissen sein, z. B. beste Verkäufer oder verwandte Produkte. </p> </td> 
  </tr> 
 </tbody> 
</table>

## XML-Ausgabe der geführten Suche für Adobe Experience Manager {#reference_DBE13C606C3A4BB185DE53F88D0D3048}

Tabellen, die die Standard-XML-Antwortausgabe für AEM (Adobe Experience Manager) beschreiben.

Siehe auch . [XML-Ausgabe der geführten Suche](../c-appendices/c-guidedsearchoutput.md#reference_D93E859A277643068B10AE7A61C973EA)

Sie können die XML-Antwort auf Folgendes überprüfen:

* [Banner](../c-appendices/c-guidedsearchoutput.md#section_B16EDC5533FA4494AC9983AA7357CBE3)
* [Breadcrumbs](../c-appendices/c-guidedsearchoutput.md#section_49EA7043FBE44315A79A4E738BE30114)
* [Benutzerdefinierte Felder](../c-appendices/c-guidedsearchoutput.md#section_38DD31AFE5DD4263A63644AFF484E0F4)
* [Facets](../c-appendices/c-guidedsearchoutput.md#section_BE98990E3DD748A1BD4E0CA322314B79)
* [Header](../c-appendices/c-guidedsearchoutput.md#section_5305B1DC5774439485CA0665DB683F9C)
* [Menüs und Sortieren](../c-appendices/c-guidedsearchoutput.md#section_A34CBB645DBF4C70A12A5B7E81211295)
* [Paginierung](../c-appendices/c-guidedsearchoutput.md#section_E52F81C6A6EB4B8F996157B657EC540F)
* [Abfrage](../c-appendices/c-guidedsearchoutput.md#section_3DAA1013F09742869B80F6A361816E6C)
* [Kürzliche Suchvorgänge](../c-appendices/c-guidedsearchoutput.md#section_17F942F6EC07456DABED7A483AC08446)
* [Ergebnisse](../c-appendices/c-guidedsearchoutput.md#section_155A80B8C4F641678DD9C8F257108412)
* [Suchformular](../c-appendices/c-guidedsearchoutput.md#section_9E4B99D4FEDC49629F6C7E866F3A7493)
* [Vorschläge](../c-appendices/c-guidedsearchoutput.md#section_2899FACB9AD84F60B3687C1B4EF09E15)
* [Vorlage](../c-appendices/c-guidedsearchoutput.md#section_1E2BB2F274B04F5491A4CCCC38F507BD)
* [Zonen](../c-appendices/c-guidedsearchoutput.md#section_26C4A947E7B1474A8E37D86D9579B93E)

## Banner {#section_B16EDC5533FA4494AC9983AA7357CBE3}

Mit der Site-Suche/dem Merchandising können Banner eines Kunden verwaltet und die Banner in verschiedene Teile einer Webseite eingefügt werden.

Beispiel-Banner:

Im Folgenden finden Sie ein Beispiel für ein Banner, das im Bereich der Seiten &quot;top&quot;platziert wird.

```xml
   <banners> 
       <banner> 
           <area><![CDATA[top]]></area> 
           <content><![CDATA[<div style="color:#70A100">We have custom shipping</div>]]></content> 
       </banner> 
    </banners> 
```

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Knoten </p> </th> 
   <th colname="col2" class="entry"> <p>Übergeordneter Knoten </p> </th> 
   <th colname="col3" class="entry"> <p>Beschreibung </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Banner </p> </td> 
   <td colname="col2"> <p>Kundenergebnisse </p> </td> 
   <td colname="col3"> <p>Enthält 0-n Bannerknoten, die jeden Bannerbereich und den in diesen Bereich eingefügten Inhalt kennzeichnen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Banner </p> </td> 
   <td colname="col2"> <p>Banner </p> </td> 
   <td colname="col3"> <p>Ein einzelner Bannerknoten. Sie können über mehrere Bannerknoten verfügen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>area </p> </td> 
   <td colname="col2"> <p>Banner </p> </td> 
   <td colname="col3"> <p>Der Bereich auf der Webseite, in dem das Banner angezeigt wird. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>content </p> </td> 
   <td colname="col2"> <p>Banner </p> </td> 
   <td colname="col3"> <p>Der Bannerinhalt. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Breadcrumbs {#section_49EA7043FBE44315A79A4E738BE30114}

Mehrere Breadcrumbs werden unterstützt. Sie können Breadcrumbs und das entsprechende Verhalten in **[!UICONTROL Design]** > **[!UICONTROL Navigation]** > **[!UICONTROL Breadcrumbs]** definieren. Außerdem müssen Sie jedem von Ihnen definierten Breadcrumb einen eindeutigen Namen zuweisen. Der XML-Knoten breadcrumbs durchläuft alle definierten Breadcrumbs. Es wird empfohlen, nur einen Breadcrumb in den Suchergebnissen anzuzeigen.

Im folgenden Beispiel wird die Auswahl dem Breadcrumb hinzugefügt, sobald der Kunde durch die Facetten weiter herunterfährt. Jedes Element wird als `<breadcrumb-item>` dargestellt.

Beispiel für einen Breadcrumb-Knoten:

```xml
    <breadcrumbs> 
  <breadcrumb> 
            <name><![CDATA[default]]></name> 
     <breadcrumb-item> 
   <link><![CDATA[?i=1;q=mens;sp_cs=UTF-8;view=xml]]></link> 
   <value><![CDATA[mens]]></value> 
                <label><![CDATA[]]></label> 
      </breadcrumb-item> 
     <breadcrumb-item> 
   <link><![CDATA[?i=1;q=mens;q1=Channel;sp_cs=UTF-8;view=xml;x1=brand]]></link> 
   <value><![CDATA[Channel]]></value> 
                <label><![CDATA[brand]]></label> 
      </breadcrumb-item> 
   </breadcrumb> 
    </breadcrumbs> 
```

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Knoten </p> </th> 
   <th colname="col2" class="entry"> <p>Übergeordneter Knoten </p> </th> 
   <th colname="col3" class="entry"> <p>Beschreibung </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Breadcrumbs </p> </td> 
   <td colname="col2"> <p>Kundenergebnisse </p> </td> 
   <td colname="col3"> <p> Enthält 0-n Breadcrumb-Knoten, die jede Breadcrumb definieren. Die meisten Kunden haben nur einen Breadcrumb. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Breadcrumb </p> </td> 
   <td colname="col2"> <p>Breadcrumbs </p> </td> 
   <td colname="col3"> <p> Enthält die untergeordneten Knoten, die die Definition eines Breadcrumbs definieren. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>name </p> </td> 
   <td colname="col2"> <p>Breadcrumb </p> </td> 
   <td colname="col3"> <p> Der Name des Breadcrumbs. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>breadcrumb-item </p> </td> 
   <td colname="col2"> <p>Ein einzelner Artikel innerhalb des Breadcrumbs. Jedes Element gibt einen Schritt in der Spur an, wenn der Benutzer die Ergebnismenge verringert. </p> </td> 
   <td colname="col3"> <p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>link </p> </td> 
   <td colname="col2"> <p>breadcrumb-item </p> </td> 
   <td colname="col3"> <p> Ein Link zu den Suchergebnissen, der die gewünschte Ansicht anzeigt. Durch Klicken auf einen Breadcrumb-Link gelangt der Kunde zu einer Ansicht, in der alle nachfolgenden Verfeinerungen entfernt werden. Es stehen auch andere Optionen zur Verfügung, z. B. Ablegen und Entfernen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>value </p> </td> 
   <td colname="col2"> <p>breadcrumb-item </p> </td> 
   <td colname="col3"> <p> Für den Kunden sichtbarer Text für das Breadcrumb-Element. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Titel </p> </td> 
   <td colname="col2"> <p>breadcrumb-item </p> </td> 
   <td colname="col3"> <p> Das label-Tag gibt eine Beschriftung für einen Breadcrumb-Wert aus, in der angegeben wird, welche Facette ausgewählt wurde, um dieses Breadcrumb-Element zu generieren. Es wird nur im Kontext eines Breadcrumb-Blocks verwendet. Für die Abfrage ist dies leer. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Benutzerdefinierte Felder {#section_38DD31AFE5DD4263A63644AFF484E0F4}

Benutzerdefinierte Felder sind verschiedene Variablensammlungen mit einem globalen Kontext. Normalerweise wird es verwendet, um Variablen für SEO-Zwecke weiterzugeben, die in den Metadaten der Suchergebnisseite festgelegt sind.

Beispiel für einen benutzerdefinierten Feldknoten:

```xml
    <custom-fields> 
        <custom-field name="seo-search-title"><![CDATA[Geometrixx Search Results]]></custom-field> 
        <custom-field name="seo-search-keywords"><![CDATA[]]></custom-field> 
    </custom-fields> 
```

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Knoten </p> </th> 
   <th colname="col2" class="entry"> <p>Übergeordneter Knoten </p> </th> 
   <th colname="col3" class="entry"> <p>Beschreibung </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>custom-fields </p> </td> 
   <td colname="col2"> <p>Kundenergebnisse </p> </td> 
   <td colname="col3"> <p> Kann 0-n untergeordnete Knoten enthalten, die benutzerdefinierte Felder definieren. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>custom-field </p> </td> 
   <td colname="col2"> <p>custom-fields </p> </td> 
   <td colname="col3"> <p> Optional. Enthält einen Wert für ein bestimmtes benutzerdefiniertes Feld, der durch das Namensattribut angegeben wird. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Facets {#section_BE98990E3DD748A1BD4E0CA322314B79}

Facets sind Verfeinerungsoptionen, die Kunden die Möglichkeit geben, nach den Ergebnissen zu filtern. Facets werden häufig für Kategorisierung, Preisbereiche, Farbauswahl und andere Attributverfeinerungen verwendet. Facets basieren auf den Metadaten im Index.

Es ist üblich, Kategorisierungsfacetten auszublenden oder anzuzeigen, wenn ein Kunde sich durch die Kategorisierung nach unten bewegt. Die höchste Kategorisierungsebene (Kategorie) wird als Ebene 1 bezeichnet. Wenn ein Kunde auf eine Option der Stufe 1 klickt, werden die Optionen zur Tier-2-Verfeinerung (Unterkategorie) angezeigt und die Optionen der Ebene 1 werden ausgeblendet. Wenn ein Kunde auf die Option &quot;Ebene 2&quot;klickt, werden die Optionen für die Tier-3-Verfeinerung (Unterkategorie) angezeigt und die Tier-2-Optionen werden ausgeblendet. Wie oben erwähnt, werden diese Optionen ausgeblendet und angezeigt. Ihre Webanwendung hat keine Auswirkungen auf sie.

Jede Facette ist in `<facet-item>`-Tags enthalten. Im folgenden Beispiel wird eine Facette gezeigt, mit der der Kunde die Suchergebnisse nach &quot;Feiertag&quot;präzisieren kann.

Beispiel für einen Facettenblock:

```xml
<facets>          
     <facet> 
         <facet-title><![CDATA[Department]]></facet-title> 
                <behavior><![CDATA[sticky]]></behavior> 
                <selected>1</selected> 
                <undo-link><![CDATA[?i=1;lang=enus;q=*;q1=Armora+Jeans;sp_staged=1;view=xml;x1=brand]]></undo-link> 
      <facet-value> 
          <selected><![CDATA[true]]></selected> 
              <label><![CDATA[Mens]]></label> 
       <link><![CDATA[?i=1;lang=enus;q=*;q1=Armora+Jeans;q2=Mens;sp_staged=1;view=xml;x1=brand;x2=leveli]]></link> 
       <count><![CDATA[3]]></count> 
                        <undolink><![CDATA[?i=1;lang=enus;q=*;q1=Armora+Jeans;sp_staged=1;view=xml;x1=brand]]></undolink> 
      </facet-value> 
      </facet> 
     <facet> 
         <facet-title><![CDATA[Sub-Category]]></facet-title> 
                <behavior><![CDATA[sticky]]></behavior> 
                <selected>0</selected> 
      <facet-value>           
              <label><![CDATA[Apparel]]></label> 
       <link><![CDATA[?i=1;lang=enus;q=*;q1=Mens;q2=Armora+Jeans;q3=Apparel;sp_staged=1;view=xml;x1=leveli;x2=brand;x3=levelii]]></link> 
       <count><![CDATA[3]]></count>                         
      </facet-value>   
      </facet>         
     <facet> 
         <facet-title><![CDATA[Brand]]></facet-title> 
                <behavior><![CDATA[multi-select]]></behavior> 
                <selected>1</selected> 
                <undo-link><![CDATA[?i=1;lang=enus;q=*;q1=Mens;sp_staged=1;view=xml;x1=leveli]]></undo-link> 
      <facet-value>        
              <label><![CDATA[Amoura]]></label> 
       <link><![CDATA[?i=1;lang=enus;q=*;q1=Mens;q2=Armora+Jeans|Amoura;sp_staged=1;view=xml;x1=leveli;x2=brand]]></link> 
       <count><![CDATA[9]]></count>                         
      </facet-value>   
      <facet-value>         
              <label><![CDATA[Armora]]></label> 
       <link><![CDATA[?i=1;lang=enus;q=*;q1=Mens;q2=Armora+Jeans|Armora;sp_staged=1;view=xml;x1=leveli;x2=brand]]></link> 
       <count><![CDATA[12]]></count>                        
      </facet-value>   
      <facet-value> 
          <selected><![CDATA[true]]></selected> 
              <label><![CDATA[Armora Jeans]]></label> 
       <link><![CDATA[?i=1;lang=enus;q=*;q1=Mens;q2=Armora+Jeans|Armora+Jeans;sp_staged=1;view=xml;x1=leveli;x2=brand]]></link> 
 
       <count><![CDATA[3]]></count> 
                        <undolink><![CDATA[?i=1;lang=enus;q=*;q1=Mens;sp_staged=1;view=xml;x1=leveli]]></undolink> 
      </facet-value>   
      <facet-value>           
              <label><![CDATA[Art of Grooming]]></label> 
       <link><![CDATA[?i=1;lang=enus;q=*;q1=Mens;q2=Armora+Jeans|Art+of+Grooming;sp_staged=1;view=xml;x1=leveli;x2=brand]]></link> 
       <count><![CDATA[4]]></count>                         
      </facet-value>   
      <facet-value>          
              <label><![CDATA[Bear Co.]]></label> 
       <link><![CDATA[?i=1;lang=enus;q=*;q1=Mens;q2=Armora+Jeans|Bear+Co.;sp_staged=1;view=xml;x1=leveli;x2=brand]]></link> 
       <count><![CDATA[1]]></count> 
      </facet-value> 
      <facet-value>      
              <label><![CDATA[Citizens]]></label> 
       <link><![CDATA[?i=1;lang=enus;q=*;q1=Mens;q2=Armora+Jeans|Citizens;sp_staged=1;view=xml;x1=leveli;x2=brand]]></link> 
       <count><![CDATA[4]]></count> 
      </facet-value> 
      <facet-value> 
              <label><![CDATA[D&amp;B]]></label> 
       <link><![CDATA[?i=1;lang=enus;q=*;q1=Mens;q2=Armora+Jeans|D%26B;sp_staged=1;view=xml;x1=leveli;x2=brand]]></link> 
       <count><![CDATA[17]]></count> 
      </facet-value> 
      <facet-value> 
              <label><![CDATA[David Yuri]]></label> 
       <link><![CDATA[?i=1;lang=enus;q=*;q1=Mens;q2=Armora+Jeans|David+Yuri;sp_staged=1;view=xml;x1=leveli;x2=brand]]></link> 
       <count><![CDATA[2]]></count>    
      </facet-value>   
      </facet> 
    </facets> 
```

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Knoten </p> </th> 
   <th colname="col2" class="entry"> <p>Übergeordneter Knoten </p> </th> 
   <th colname="col3" class="entry"> <p>Beschreibung </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Facets </p> </td> 
   <td colname="col2"> <p>Kundenergebnisse </p> </td> 
   <td colname="col3"> <p>Der Container facets-Knoten mit 0-n untergeordneten Knoten, die jede Facette darstellen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>facet </p> </td> 
   <td colname="col2"> <p>Facets </p> </td> 
   <td colname="col3"> <p> Eine einzelne Facetteninstanz. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>facet-title </p> </td> 
   <td colname="col2"> <p>facet </p> </td> 
   <td colname="col3"> <p>Kundenorientierter Titel für die Facette. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Verhalten </p> </td> 
   <td colname="col2"> <p>facet </p> </td> 
   <td colname="col3"> <p>Das Verhalten der Facette. Beispiel: normal, sticky oder multi-select. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ausgewählt </p> </td> 
   <td colname="col2"> <p>facet </p> </td> 
   <td colname="col3"> <p>1, wenn die Facette einen ausgewählten Wert hat, andernfalls 0. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Rückgängig-Verknüpfung </p> </td> 
   <td colname="col2"> <p>facet </p> </td> 
   <td colname="col3"> <p> Wird nur angezeigt, wenn die Facette ausgewählt wurde. "Rückgängig"-Link stellt die gesamte Facette wieder her. Wenn es sich beispielsweise um eine Mehrfachauswahl-Facette handelt, werden alle ausgewählten Optionen für die Facette deaktiviert. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>facet-value </p> </td> 
   <td colname="col2"> <p>facet </p> </td> 
   <td colname="col3"> <p>Enthält alle einzelnen Facettenelemente, die zur Facette gehören. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ausgewählt </p> </td> 
   <td colname="col2"> <p>facet-value </p> </td> 
   <td colname="col3"> <p>Wenn das aktuelle Element mit der Facette ausgewählt ist, ist diese Node vorhanden und auf "true"eingestellt. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Titel </p> </td> 
   <td colname="col2"> <p>facet-value </p> </td> 
   <td colname="col3"> <p>Kundenorientierte Beschriftung für die Facettenoption. Standardmäßig sollte dies bereits mit HTML-Escapezeichen versehen sein. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>link </p> </td> 
   <td colname="col2"> <p>facet-value </p> </td> 
   <td colname="col3"> <p> Relativer Link zu Ergebnissen, die durch die Option weiter optimiert werden. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>count </p> </td> 
   <td colname="col2"> <p>facet-value </p> </td> 
   <td colname="col3"> <p>Die Anzahl der Ergebnisse in dieser verfeinerten Ergebnismenge. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Rückgängig-Verknüpfung </p> </td> 
   <td colname="col2"> <p>facet-value </p> </td> 
   <td colname="col3"> <p>Wenn ein Facettenwert ausgewählt ist, gibt die Node einen "Rückgängig-Link"zurück, über den ein Kunde die Auswahl dieser Facettenauswahl rückgängig machen kann. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Header {#section_5305B1DC5774439485CA0665DB683F9C}

Beispiel:

```xml
xml version="1.0" encoding="utf-8" standalone="yes" 
```

## Menüs und Sortieren {#section_A34CBB645DBF4C70A12A5B7E81211295}

Es werden Menüs zum Sortieren der Ergebnisse unterstützt und die Anzahl der pro Seite zurückzugebenden Ergebnisse wird geändert. Es unterstützt auch ein Navigationsmenü, das für die Verwendung von &quot;Suche als Navigation&quot;nützlich ist. Ein Konto kann mehrere Menüs desselben Typs definieren und eines der Menüs für die Präsentation verwenden.

Beispielmenüknoten:

Das folgende Beispiel zeigt die Daten für ein dreiseitiges Sortierungsmenü und ein Navigationsmenü. Das Sortierungsmenü ermöglicht es dem Kunden, nach Relevanz, Titel oder Bewertung zu sortieren. Das aktuell ausgewählte Element enthält das Attribut &quot;selected=true&quot;. &quot;. Wählen Sie immer eine Relevanzoption, damit der Kunde zu den ursprünglich angezeigten Standardsuchergebnissen zurückkehren kann.

```xml
<menus> 
        <menu> 
           <name><![CDATA[sort]]></name>         
             <item selected="true"> 
          <label><![CDATA[Relevance]]></label> 
          <value><![CDATA[relevance]]></value> 
          <link><![CDATA[ ]]></link> 
             </item> 
             <item> 
          <label><![CDATA[Lowest Price]]></label> 
          <value><![CDATA[Price]]></value> 
          <link><![CDATA[?i=1;q=mens;sort=Price;sp_cs=UTF-8;sp_staged=1;view=xml]]></link>     
             </item> 
             <item> 
          <label><![CDATA[Highest Price]]></label> 
          <value><![CDATA[Price_r]]></value> 
          <link><![CDATA[?i=1;q=mens;sort=Price_r;sp_cs=UTF-8;sp_staged=1;view=xml]]></link>     
             </item> 
             <item> 
          <label><![CDATA[Brand]]></label> 
          <value><![CDATA[brand]]></value> 
          <link><![CDATA[?i=1;q=mens;sort=brand;sp_cs=UTF-8;sp_staged=1;view=xml]]></link>     
             </item> 
        </menu> 
        <menu> 
            <name><![CDATA[ss_head_nav]]></name>   
                    <item> 
                        <label><![CDATA[WOMEN'S]]></label> 
          <value><![CDATA[?q1=Womens;sp_sfvl_field=levelii|leveli|brand|leveliii;x=0;x1=leveli;y=0;view=nav;top=1]]></value> 
          <link><![CDATA[?q1=Womens;sp_sfvl_field=levelii|leveli|brand|leveliii;x=0;x1=leveli;y=0;view=nav;top=1;i=1;m_ss_head_nav=WOMEN'S]]></link> 
                    </item> 
                    <item> 
                        <label><![CDATA[MEN'S]]></label> 
          <value><![CDATA[/q1/Mens/x1/leveli/view/nav/top/1/]]></value> 
          <link><![CDATA[/q1/Mens/x1/leveli/view/nav/top/1/]]></link> 
                    </item> 
                    <item> 
                        <label><![CDATA[JEWELRY & ACCESSORIES]]></label> 
          <value><![CDATA[?q1=Jewelry+%26+Accessories&sp_sfvl_field=levelii|leveli|brand|leveliii&x1=leveli&view=nav&top=1]]></value> 
          <link><![CDATA[?q1=Jewelry+%26+Accessories&sp_sfvl_field=levelii|leveli|brand|leveliii&x1=leveli&view=nav&top=1;i=1;m_ss_head_nav=JEWELRY+%26+ACCESSORIES]]></link> 
                    </item> 
                    <item> 
                        <label><![CDATA[BEAUTY & FRAGRANCE]]></label> 
          <value><![CDATA[?q1=Beauty+%26+Fragrance;sp_sfvl_field=levelii|leveli|brand|leveliii;x1=leveli;view=nav;top=1]]></value> 
          <link><![CDATA[?q1=Beauty+%26+Fragrance;sp_sfvl_field=levelii|leveli|brand|leveliii;x1=leveli;view=nav;top=1;i=1;m_ss_head_nav=BEAUTY+%26+FRAGRANCE]]></link> 
                    </item> 
                    <item> 
                        <label><![CDATA[GIFTS & HOME]]></label> 
          <value><![CDATA[?q1=Gifts+%26+Home;sp_sfvl_field=levelii|leveli|brand|leveliii;x1=leveli;view=nav;top=1]]></value> 
          <link><![CDATA[?q1=Gifts+%26+Home;sp_sfvl_field=levelii|leveli|brand|leveliii;x1=leveli;view=nav;top=1;i=1;m_ss_head_nav=GIFTS+%26+HOME]]></link> 
                    </item> 
                    <item> 
                        <label><![CDATA[CHILDREN & TOYS]]></label> 
          <value><![CDATA[?q1=Children+%26+Toys;sp_sfvl_field=levelii|leveli|brand|leveliii;x1=leveli;view=nav;top=1]]></value> 
          <link><![CDATA[?q1=Children+%26+Toys;sp_sfvl_field=levelii|leveli|brand|leveliii;x1=leveli;view=nav;top=1;i=1;m_ss_head_nav=CHILDREN+%26+TOYS]]></link> 
                    </item> 
                    <item> 
                        <label><![CDATA[ELECTRONICS]]></label> 
          <value><![CDATA[?q1=Electronics+%26+Toys;sp_sfvl_field=levelii|leveli|brand|leveliii;x1=leveli;view=nav;top=1]]></value> 
          <link><![CDATA[?q1=Electronics+%26+Toys;sp_sfvl_field=levelii|leveli|brand|leveliii;x1=leveli;view=nav;top=1;i=1;m_ss_head_nav=ELECTRONICS]]></link> 
                    </item> 
        </menu> 
    </menus> 
```

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Knoten </p> </th> 
   <th colname="col2" class="entry"> <p>Übergeordneter Knoten </p> </th> 
   <th colname="col3" class="entry"> <p>Beschreibung </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Menüs </p> </td> 
   <td colname="col2"> <p>Kundenergebnisse </p> </td> 
   <td colname="col3"> <p>Enthält 0-n untergeordnete Knoten, die jedes Menü definieren. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Menü </p> </td> 
   <td colname="col2"> <p>Menüs </p> </td> 
   <td colname="col3"> <p>Einzelinstanz eines Menüs (entspricht einem Menü, das unter <span class="uicontrol"> Design </span> &gt; <span class="uicontrol"> Navigation </span> &gt; <span class="uicontrol"> Menüs </span> definiert ist). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>name </p> </td> 
   <td colname="col2"> <p>Menü </p> </td> 
   <td colname="col3"> <p>Name des Menüs. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Element </p> </td> 
   <td colname="col2"> <p>Menü </p> </td> 
   <td colname="col3"> <p>Definiert jedes Element im Menü. Das ausgewählte optionale Attribut ist auf "true"gesetzt, wenn das angegebene Menüelement aktuell ausgewählt ist. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Titel </p> </td> 
   <td colname="col2"> <p>Element </p> </td> 
   <td colname="col3"> <p>Der kundenorientierte Text für den Menüpunkt. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>value </p> </td> 
   <td colname="col2"> <p>Element </p> </td> 
   <td colname="col3"> <p>Stellt den Wert des Menüelements dar (der Parameterwert der Abfrage, auf den das Menü festgelegt ist). Dieses Tag ist nicht erforderlich, wenn der Wert &lt;link&gt; verwendet wird. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>link </p> </td> 
   <td colname="col2"> <p>Element </p> </td> 
   <td colname="col3"> <p>Bei den nicht ausgewählten Optionen enthält der Parameter &lt;link&gt; den relativen Link, der denselben Ergebnissatz zurückgibt, jedoch mit angewendeter Menüoption. Dieses Feld ist für die derzeit ausgewählte Sortieroption leer. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Paginierung {#section_E52F81C6A6EB4B8F996157B657EC540F}

Die Ergebnismengen werden auf mehrere Seiten aufgeteilt. Normalerweise zeigen Kunden 10 bis 20 Ergebnisse auf einer Seite an. Nachfolgende Ergebnisse werden auf der nächsten Seite angezeigt. Mit der Paginierungs-XML können Sie eine Reihe von Navigationslinks erstellen, damit Ihre Kunden die Ergebnisse seitenweise durchsuchen können. Es stehen vier Navigationslinks zur Verfügung: first, last, next und previous. Mit jedem Link können Kunden schnell durch die Seiten navigieren, sodass sie die gesuchten Seiten schnell überprüfen und verfeinern können.

Das folgende Beispiel zeigt die Paginierung für eine Suche, die sich auf der ersten Seite befindet und deren Paginierung so konfiguriert ist, dass Links zu fünf Seiten angezeigt werden.

Beispielpaginierung:

```xml
    <pagination> 
        <total-pages><![CDATA[112]]></total-pages> 
        <pages> 
     <page position="first"><![CDATA[]]></page> 
     <page position="last"><![CDATA[?i=1;page=112;q=*;sp_cs=UTF-8;sp_staged=1;view=xml]]></page> 
     <page position="next"><![CDATA[?i=1;page=2;q=*;sp_cs=UTF-8;sp_staged=1;view=xml]]></page> 
            <page position="1" selected="true"><![CDATA[?i=1;q=*;sp_cs=UTF-8;sp_staged=1;view=xml]]></page> 
            <page position="2"><![CDATA[?i=1;page=2;q=*;sp_cs=UTF-8;sp_staged=1;view=xml]]></page> 
            <page position="3"><![CDATA[?i=1;page=3;q=*;sp_cs=UTF-8;sp_staged=1;view=xml]]></page> 
            <page position="4"><![CDATA[?i=1;page=4;q=*;sp_cs=UTF-8;sp_staged=1;view=xml]]></page> 
            <page position="5"><![CDATA[?i=1;page=5;q=*;sp_cs=UTF-8;sp_staged=1;view=xml]]></page> 
        </pages> 
    </pagination> 
```

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Knoten </p> </th> 
   <th colname="col2" class="entry"> <p>Übergeordneter Knoten </p> </th> 
   <th colname="col3" class="entry"> <p>Beschreibung </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Paginierung </p> </td> 
   <td colname="col2"> <p>Kundenergebnisse </p> </td> 
   <td colname="col3"> <p> Gesamtanzahl der Ergebnisseiten, basierend auf der Anzahl der Ergebnisse geteilt durch die Anzahl der Ergebnisse pro Seite. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>total-pages </p> </td> 
   <td colname="col2"> <p>Paginierung </p> </td> 
   <td colname="col3"> <p>Die Gesamtanzahl der Seiten, auf denen die Suchergebnisse verteilt sind. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Seiten </p> </td> 
   <td colname="col2"> <p>Paginierung </p> </td> 
   <td colname="col3"> <p>Enthält 0-n-Seiten-Nodes, die jede Seite in der Paginierung definieren. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Seite </p> </td> 
   <td colname="col2"> <p>Seiten </p> </td> 
   <td colname="col3"> <p>Es gibt vier spezielle Seiten-Nodes: first, last, previous und next. Diese vier Seiten sind optional und werden nur dann in der Ergebnismenge angezeigt, wenn sie sinnvoll sind. Wenn Sie sich beispielsweise auf Seite 1 befinden, gibt es keinen Link "Zurück". Alle anderen Seiten geben eine Position an. Die Anzahl der aufgelisteten Seiten hängt von der "Anzahl der Links zu Seiten"ab, die in der Paginierungs-Benutzeroberfläche konfiguriert ist. Das Attribut "selected"gibt die Seite an, auf der sich der Kunde derzeit befindet. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Abfrage {#section_3DAA1013F09742869B80F6A361816E6C}

Beispielknoten Abfrage:

```xml
    <query> 
        <user-query><![CDATA[mens]]></user-query> 
 <lower-results><![CDATA[1]]></lower-results> 
 <upper-results><![CDATA[12]]></upper-results> 
 <total-results><![CDATA[265]]></total-results> 
    </query> 
```

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Knoten </p> </th> 
   <th colname="col2" class="entry"> <p>Übergeordneter Knoten </p> </th> 
   <th colname="col3" class="entry"> <p>Beschreibung </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>query </p> </td> 
   <td colname="col2"> <p>Kundenergebnisse </p> </td> 
   <td colname="col3"> <p> Ein globaler Knoten, der eine Übersicht über die Abfrage bietet. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>user-Abfrage </p> </td> 
   <td colname="col2"> <p>abfrage </p> </td> 
   <td colname="col3"> <p> Der gesuchte Suchbegriff. Wenn <span class="uicontrol"> Haben Sie </span> aufgrund des ursprünglichen Begriffs automatisch nach einem vorgeschlagenen Begriff gesucht haben, ohne Ergebnisse zu erzielen, wird dieser in dem neuen Suchbegriff übernommen, der gesucht wurde (siehe Knoten "Vorschläge", um den ursprünglichen Suchbegriff abzurufen). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>niedrigere Ergebnisse </p> </td> 
   <td colname="col2"> <p>abfrage </p> </td> 
   <td colname="col3"> <p> Die Elementnummer des ersten Ergebnisses auf dieser Seite. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>obere Ergebnisse </p> </td> 
   <td colname="col2"> <p>abfrage </p> </td> 
   <td colname="col3"> <p> Die Elementnummer des letzten Ergebnisses auf dieser Seite. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>total-results </p> </td> 
   <td colname="col2"> <p>abfrage </p> </td> 
   <td colname="col3"> <p> Die Gesamtanzahl der Ergebnisse, die mit der Abfrage des Benutzers übereinstimmen. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Kürzliche Suchvorgänge {#section_17F942F6EC07456DABED7A483AC08446}

Die Funktion &quot;Letzte Suchen&quot;ist eine Cookie-basierte Funktion, die nur funktioniert, wenn Sie die Cookie-Informationen an die Server für die Site-Suche/das Merchandising weiterleiten.

Beispiel für kürzlich durchgeführte Suchen:

```xml
    <recent-searches> 
        <clear-link><![?q=womens&gscr=clear]]></clear-link> 
        <recent-search> 
            <link><![?q=mens]]></link> 
            <label><![CDATA[mens]]></label> 
        <recent-search> 
    </recent-searches> 
```

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Knoten </p> </th> 
   <th colname="col2" class="entry"> <p>Übergeordneter Knoten </p> </th> 
   <th colname="col3" class="entry"> <p>Beschreibung </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>last-searches </p> </td> 
   <td colname="col2"> <p>Kundenergebnisse </p> </td> 
   <td colname="col3"> <p>Der Knoten ist nur vorhanden, wenn die Suche kürzlich durchsucht wurde. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>clear-link </p> </td> 
   <td colname="col2"> <p>last-searches </p> </td> 
   <td colname="col3"> <p>Der relative Pfad, durch den alle zuletzt durchgeführten Suchen des Kunden gelöscht werden. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>previous-search </p> </td> 
   <td colname="col2"> <p>last-searches </p> </td> 
   <td colname="col3"> <p>Definiert in den letzten Suchvorgängen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>link </p> </td> 
   <td colname="col2"> <p>previous-search </p> </td> 
   <td colname="col3"> <p>Der Pfad zum Erstellen eines Links, der eine Suche durchführt, die der Benutzer vor kurzem durchgeführt hat. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Titel </p> </td> 
   <td colname="col2"> <p>previous-search </p> </td> 
   <td colname="col3"> <p>Für die kürzlich durchgeführte Suche wird die Anzeige des Kunden angezeigt. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Ergebnisse {#section_155A80B8C4F641678DD9C8F257108412}

Der Ergebnissatz ist ein anpassbarer Bereich der XML-Antwort. Jeder Index ist in den Feldbenennungsmechanismen von Metadaten eindeutig. Es gibt allgemeine Felder, die für jedes Ergebnis zurückgegeben werden, z. B. Titel, Beschreibung und URL. Alle Metadaten, die für eine Seite im Index definiert sind, können jedoch in jedem Ergebnisknoten verwendet werden. Kategorisierung, Preise, Farben und Miniaturansichten sind nur einige der Optionen, die Sie auf ein Ergebnis anwenden können, um überzeugendere Suchergebnisse zu erzielen.

Das Ergebnisformat wird basierend auf den für Ihre Implementierung spezifischen Metadaten angepasst. Hier finden Sie alle Ergebnisdaten, die in den Ergebnissen angezeigt werden sollen, einschließlich URLs für Miniaturbilder.

Darüber hinaus ist es möglich, mehrere Ergebniszonen innerhalb der Seite zu konfigurieren, z. B. &quot;Vorgestellte Ergebnisse&quot;oder separate Ergebnisabschnitte &quot;Produkte&quot;und &quot;Inhalt&quot;. In diesen Fällen werden mehrere Ergebniszonen im HTML-Code bereitgestellt, obwohl Facetten nur mit der primären Ergebnismenge verknüpft sind.

Beispielergebnisknoten:

```xml
    <results> 
        <result-set> 
            <name><![CDATA[default]]></name> 
         <result> 
                    <field name="index"><![CDATA[1]]></field> 
                    <field name="sku"><![CDATA[200190]]></field> 
                    <field name="pagename"><![CDATA[Relaxed Paint Splattered]]></field> 
 
                    <field name="img_sm_url"><![CDATA[https://geometrixx.com/images/08_geometrixx_icon_men.jpg]]></field> 
      <field name="brand"><![CDATA[Armora Jeans]]></field> 
      <field name="price"><![CDATA[195]]></field> 
      <field name="foundIn"><![CDATA[Mens,  
            Apparel,  
          Denim]]></field> 
         </result>   
         <result> 
                    <field name="index"><![CDATA[2]]></field> 
                    <field name="sku"><![CDATA[200195]]></field> 
                    <field name="pagename"><![CDATA[Tumbled Jeans]]></field> 
 
                    <field name="img_sm_url"><![CDATA[https://geometrixx.com/images/08_geometrixx_icon_men.jpg]]></field> 
      <field name="brand"><![CDATA[Armora Jeans]]></field> 
      <field name="price"><![CDATA[235]]></field> 
      <field name="foundIn"><![CDATA[Mens,  
            Apparel,  
          Denim]]></field> 
         </result>    
         <result> 
                    <field name="index"><![CDATA[3]]></field> 
                    <field name="sku"><![CDATA[200196]]></field> 
                    <field name="pagename"><![CDATA[Montana Relaxed]]></field> 
 
                    <field name="img_sm_url"><![CDATA[https://geometrixx.com/images/08_geometrixx_icon_men.jpg]]></field> 
      <field name="brand"><![CDATA[Armora Jeans]]></field> 
      <field name="price"><![CDATA[220]]></field> 
      <field name="foundIn"><![CDATA[Mens,  
            Apparel,  
          Denim]]></field> 
         </result>         
        </result-set>   
    </results> 
```

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Knoten </p> </th> 
   <th colname="col2" class="entry"> <p>Übergeordneter Knoten </p> </th> 
   <th colname="col3" class="entry"> <p>Beschreibung </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Ergebnisse </p> </td> 
   <td colname="col2"> <p>Kundenergebnisse </p> </td> 
   <td colname="col3"> <p>Der Container-Knoten für 0-n Ergebnissätze. Null-Ergebnismengen bedeutet, dass Sie eine spezielle ergebnislose Landingpage haben. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>result-set </p> </td> 
   <td colname="col2"> <p>Ergebnisse </p> </td> 
   <td colname="col3"> <p>Eine eingehende Suche kann mehrere Suchen auslösen. Jeder Ergebnissatz enthält die Ergebnisse einer bestimmten benannten Suche, die durchgeführt wurde. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>name </p> </td> 
   <td colname="col2"> <p>result-set </p> </td> 
   <td colname="col3"> <p>Der Name der Suche, zu der die Ergebnismenge gehört. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ergebnis </p> </td> 
   <td colname="col2"> <p>result-set </p> </td> 
   <td colname="col3"> <p>Enthält alle Felder, die mit einem einzelnen Ergebnis für die Ergebnismenge verknüpft sind. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Feld referenziert werden </p> </td> 
   <td colname="col2"> <p>Ergebnis </p> </td> 
   <td colname="col3"> <p>Das Attribut name definiert den Namen des Felds innerhalb des angezeigten Indexes. Der Wert ist der tatsächliche Wert für dieses Feld. Bei einigen Ergebnissen können Felder fehlen, die für das jeweilige Ergebnis nicht relevant sind. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Suchformular {#section_9E4B99D4FEDC49629F6C7E866F3A7493}

Das Suchformular ist im Ergebnissatz enthalten, damit Kunden ihr Suchformular dynamisch erstellen können. Dieser Schritt ist optional. Die meisten Kunden haben ein festes Suchformular. Sie ermöglicht es Kunden jedoch, festzustellen, ob das Suchformular eine Test&amp;Zielgruppe-mbox benötigt, basierend auf mindestens einer Geschäftsregel, die einen A:B-Test durchführt. Gleichermaßen können Kunden automatisch die neueste automatisch vervollständigte CSS und JavaScript abrufen.

Beispiel für XML des Suchformulars:

```xml
    <search-form> 
        <include-tnt-mbox>1</include-tnt-mbox> 
        <autocomplete> 
            <enabled>1</enabled> 
            <css><![CDATA[<link rel="stylesheet" type="text/css" href="https://content.t1.atomz.com/sp10043554/stage/autocomplete_styles.css?sp_js_param=2" /> 
]]></css> 
 
            <form-content><![CDATA[<div id="autocomplete"></div> 
<input type="hidden" name="sp_staged" id="sp_staged" value="1" /> 
]]></form-content> 
            <javascript><![CDATA[<script type="text/javascript" src="https://ajax.googleapis.com/ajax/libs/yui/2.6.0/build/utilities/utilities.js"></script> 
<script type="text/javascript" src="https://ajax.googleapis.com/ajax/libs/yui/2.6.0/build/datasource/datasource-min.js"></script> 
<script type="text/javascript" src="https://ajax.googleapis.com/ajax/libs/yui/2.6.0/build/autocomplete/autocomplete-min.js"></script> 
<script type="text/javascript" src="https://content.t1.atomz.com/sp10043554/stage/autocomplete_data.js?sp_js_param=3"></script>]]></javascript> 
        </autocomplete> 
    </search-form> 
```

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Knoten </p> </th> 
   <th colname="col2" class="entry"> <p>Übergeordneter Knoten </p> </th> 
   <th colname="col3" class="entry"> <p>Beschreibung </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>search-form </p> </td> 
   <td colname="col2"> <p>Kundenergebnisse </p> </td> 
   <td colname="col3"> <p>Enthält Daten zum Versenden des Suchformulars. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>include-tnt-mbox </p> </td> 
   <td colname="col2"> <p> search-form </p> </td> 
   <td colname="col3"> <p>Technisch gesehen benötigen Sie im Suchformular nur eine mbox, wenn Sie mindestens eine Geschäftsregel für einen A:B-Test der Zielgruppe verwenden. Dieser Knoten gibt an, ob Sie eine mbox benötigen oder nicht, um die Anzahl der Treffer auf den Test&amp;Zielgruppe-Servern zu reduzieren. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>autocomplete </p> </td> 
   <td colname="col2"> <p>search-form </p> </td> 
   <td colname="col3"> <p>Der untergeordnete Knoten des Houses steht in Zusammenhang mit der automatischen Vervollständigung. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>aktiviert </p> </td> 
   <td colname="col2"> <p>autocomplete </p> </td> 
   <td colname="col3"> <p>Auf 1 setzen, wenn das Suchkonto automatisch gefüllt wird. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>css </p> </td> 
   <td colname="col2"> <p> autocomplete </p> </td> 
   <td colname="col3"> <p> CSS für die automatische Vervollständigung. Platzieren Sie diesen Knoten so hoch wie möglich auf der Seite. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> form-content </p> </td> 
   <td colname="col2"> <p>autocomplete </p> </td> 
   <td colname="col3"> <p>Inhalt, der in das Suchformular eingefügt wird. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>javascript </p> </td> 
   <td colname="col2"> <p>autocomplete </p> </td> 
   <td colname="col3"> <p>JavaScript für die automatische Vervollständigung. Platzieren Sie diesen Knoten so niedrig wie möglich auf der Seite. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Vorschläge {#section_2899FACB9AD84F60B3687C1B4EF09E15}

Kunden können die Funktionalität von **[!UICONTROL Did You Mean]** auf drei Arten konfigurieren: Vorschläge machen, weil keine Ergebnisse, automatisch nach der ersten Empfehlung suchen, wenn wir keine Ergebnisse haben, oder Vorschläge aufgrund von niedrigen Ergebnissen (wo die Vorschläge eine höhere Ergebniszahl haben). Alle Vorschläge liefern Ergebnisse.

Dieser Recommendations-Knoten enthält die Begriffe, die zu erfolgreichen Abfragen führen. Der Link wird auch zurückgegeben, damit ein Kunde zur neuen Abfrage springen kann.

Beispielausgabe für den Vorschlag aufgrund von 0 Ergebnissen:

```xml
    <suggestions> 
        <auto-searched>0</auto-searched> 
        <suggestions-low-results>0</suggestions-low-results> 
 <suggestion-item> 
     <link><![CDATA[?i=1;q=arcade;sp_cs=UTF-8;view=xml]]></link> 
     <word><![CDATA[arcade]]></word> 
 </suggestion-item>    
    </suggestions>
```

Beispielausgabe für die automatische Suche nach einem Vorschlag:

```xml
    <suggestions> 
        <auto-searched>1</auto-searched> 
        <orig-query><![CDATA[arcace]]></orig-query> 
        <suggestions-low-results>0</suggestions-low-results>         
    </suggestions> 
```

Beispielausgabe für Vorschläge aufgrund niedriger Ergebnisse:

```xml
   <suggestions> 
        <auto-searched>0</auto-searched> 
        <suggestions-low-results>1</suggestions-low-results> 
 <suggestion-item> 
     <link><![CDATA[?i=1;q=coffee;sp_cs=UTF-8;view=xml]]></link> 
     <word><![CDATA[coffee]]></word> 
 </suggestion-item>  
    </suggestions> 
```

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Knoten </p> </th> 
   <th colname="col2" class="entry"> <p>Übergeordneter Knoten </p> </th> 
   <th colname="col3" class="entry"> <p>Beschreibung </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Vorschlag </p> </td> 
   <td colname="col2"> <p>Kundenergebnisse </p> </td> 
   <td colname="col3"> <p> Enthält untergeordnete Knoten, die Vorschläge definieren, sofern vorhanden. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>automatisch durchsucht </p> </td> 
   <td colname="col2"> <p>Vorschläge </p> </td> 
   <td colname="col3"> <p> Falls vorhanden, zeigt an, ob Site-Suche/Merchandising automatisch nach einem neuen Begriff gesucht hat, weil keine Ergebnisse vorliegen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>orig-Abfrage </p> </td> 
   <td colname="col2"> <p>Vorschläge </p> </td> 
   <td colname="col3"> <p> Wenn Site-Suche/Merchandising automatisch nach dem ersten Vorschlag sucht, zeigt die Abfrage des Benutzers im Knoten Abfrage den Suchbegriff an, nach dem gesucht wird. Dieser Knoten zeigt den ursprünglichen Begriff der Abfrage. Durch die Kombination dieser beiden Funktionen können Kunden Strukturen wie "Suche nach Arcade statt Arcace"erstellen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>recommendations-low-results </p> </td> 
   <td colname="col2"> <p>Vorschläge </p> </td> 
   <td colname="col3"> <p>Falls vorhanden, zeigt an, ob Site-Suche/Merchandising Vorschläge macht, da der aktuelle Suchbegriff niedrige Ergebnisse und einen Vorschlag, der deutlich höhere Ergebnisse liefert. Die beiden Schwellenwerte können unter <span class="uicontrol"> Meinten Sie </span> konfiguriert werden. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>recommendations-item </p> </td> 
   <td colname="col2"> <p>Vorschläge </p> </td> 
   <td colname="col3"> <p>Enthält 0-n-Knoten mit den verschiedenen Vorschlägen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>link </p> </td> 
   <td colname="col2"> <p>recommendations-item </p> </td> 
   <td colname="col3"> <p>Enthält den Pfad zum Erstellen eines Links zum vorgeschlagenen Begriff. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>word </p> </td> 
   <td colname="col2"> <p>recommendations-item </p> </td> 
   <td colname="col3"> <p> Enthält das vorgeschlagene Wort. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Vorlage {#section_1E2BB2F274B04F5491A4CCCC38F507BD}

Es wird die Möglichkeit unterstützt, eine auf den Ergebnissen basierende Sucherfahrung des Kunden zu wechseln. Dazu gehört auch das Wechseln zwischen verschiedenen Vorlagen mit einem anderen Layout der Suchergebnisse. Sie haben z. B. eine Vorlage mit einer Raster-Ansicht von Produkten, wenn Sie viele Produkte haben. Sie können auch eine Spotlight-Vorlage verwenden, wenn Sie ein einzelnes Ergebnis mit weiteren Details anzeigen. Sie können auch eine Vorlage &quot;Keine Ergebnisse&quot;verwenden, wenn eine Suche keine Ergebnisse liefert. Der Vorlagenknoten gibt an, welche Vorlage zum Anzeigen der Suchergebnisse verwendet wird.

Beispielvorlage:

```xml
<template><![CDATA[grid]]></template>
```

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Knoten </p> </th> 
   <th colname="col2" class="entry"> <p>Übergeordneter Knoten </p> </th> 
   <th colname="col3" class="entry"> <p>Beschreibung </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>bearbeiten </p> </td> 
   <td colname="col2"> <p>Kundenergebnisse </p> </td> 
   <td colname="col3"> <p>Gibt den Namen der Vorlage an, mit der die Suchergebnisse angezeigt werden. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Zonen {#section_26C4A947E7B1474A8E37D86D9579B93E}

Zonen sind Abschnitte der Seiten, die durch Geschäftsregeln aktiviert oder deaktiviert werden können. Eine Zone kann alle Inhalte enthalten, einschließlich, aber nicht beschränkt auf, Facetten, Suchen, Breadcrumbs, statischen Inhalt. Die Zonen auf der Kundenwebseite sollten denselben Bereichen zugeordnet werden wie die Site-Suche/das Merchandising.

Beispiel für Zonen-Nodes:

```xml
    <zones> 
        <zone> 
            <name><![CDATA[brand-facet]]></name> 
            <display>1</display> 
        </zone> 
    </zones> 
```

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Knoten </p> </th> 
   <th colname="col2" class="entry"> <p>Übergeordneter Knoten </p> </th> 
   <th colname="col3" class="entry"> <p>Beschreibung </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Zonen </p> </td> 
   <td colname="col2"> <p>Kundenergebnisse </p> </td> 
   <td colname="col3"> <p>Enthält 0-n Zonen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>zone </p> </td> 
   <td colname="col2"> <p>Zonen </p> </td> 
   <td colname="col3"> <p> Ein einzelner Zonenknoten. Sie können über mehrere Zonen-Nodes verfügen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>name </p> </td> 
   <td colname="col2"> <p>zone </p> </td> 
   <td colname="col3"> <p>Der Name der Zone. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>display </p> </td> 
   <td colname="col2"> <p>1 oder 0, die angibt, ob die Zone, die dem Zonennamen entspricht, ein- oder ausgeblendet wird. </p> </td> 
   <td colname="col3"> <p> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Beispiele {#reference_64B7D8D228AF4B8D90EDF4DE507B0F84}

Beispielausgabe für eine *-Suche auf einer fiktiven Website namens &quot;Geometrixx&quot;und eine Beispielpräsentationsvorlage, mit der die Beispielausgabe erstellt wird.

* [Beispielausgabe](../c-appendices/c-guidedsearchoutput.md#section_515C000A18B847D59097D0A9CCC02636)
* [Beispiel einer Präsentationsvorlage](../c-appendices/c-guidedsearchoutput.md#section_AD42571DFB88491AA7F0FDF0929EBE97)

## Beispielausgabe {#section_515C000A18B847D59097D0A9CCC02636}

Beispielausgabe für eine * Suche auf einer fiktiven Website namens Geometrixx.

```xml
<?xml version="1.0" encoding="utf-8" standalone="yes" ?> 
<customer-results> 
    <query> 
        <user-query><![CDATA[*]]></user-query> 
 <lower-results><![CDATA[1]]></lower-results> 
 <upper-results><![CDATA[12]]></upper-results> 
 <total-results><![CDATA[1337]]></total-results> 
    </query> 
 
    <custom-fields> 
 
        <custom-field name="seo-search-title"><![CDATA[Geometrixx Search Results]]></custom-field> 
        <custom-field name="seo-search-keywords"><![CDATA[]]></custom-field> 
    </custom-fields> 
 
    <menus> 
 
        <menu> 
           <name>sort</name>

             <item selected="true"> 
 
          <label><![CDATA[Relevance]]></label> 
          <value><![CDATA[relevance]]></value> 
          <link><![CDATA[ ]]></link> 
             </item>

             <item> 
          <label><![CDATA[Lowest Price]]></label> 
          <value><![CDATA[Price]]></value> 
          <link><![CDATA[?i=1;q=*;sort=Price;sp_cs=UTF-8;sp_staged=1;view=xml]]></link>     
             </item>

             <item> 
          <label><![CDATA[Highest Price]]></label> 
          <value><![CDATA[Price_r]]></value> 
          <link><![CDATA[?i=1;q=*;sort=Price_r;sp_cs=UTF-8;sp_staged=1;view=xml]]></link>     
             </item>

             <item> 
          <label><![CDATA[Brand]]></label> 
          <value><![CDATA[brand]]></value> 
          <link><![CDATA[?i=1;q=*;sort=brand;sp_cs=UTF-8;sp_staged=1;view=xml]]></link>     
             </item>

        </menu> 
        <menu> 
            <name><![CDATA[ss_head_nav]]></name>

                    <label><![CDATA[WOMEN'S]]></label> 
      <value><![CDATA[?q1=Womens;sp_sfvl_field=levelii|leveli|brand|leveliii;x=0;x1=leveli;y=0;view=nav;top=1]]></value> 
      <link><![CDATA[?q1=Womens;sp_sfvl_field=levelii|leveli|brand|leveliii;x=0;x1=leveli;y=0;view=nav;top=1;i=1;m_ss_head_nav=WOMEN'S]]></link>

                    <label><![CDATA[MEN'S]]></label> 
      <value><![CDATA[/q1/Mens/x1/leveli/view/nav/top/1/]]></value> 
      <link><![CDATA[/q1/Mens/x1/leveli/view/nav/top/1/]]></link>

                    <label><![CDATA[JEWELRY & ACCESSORIES]]></label> 
      <value><![CDATA[?q1=Jewelry+%26+Accessories&sp_sfvl_field=levelii|leveli|brand|leveliii&x1=leveli&view=nav&top=1]]></value> 
      <link><![CDATA[?q1=Jewelry+%26+Accessories&sp_sfvl_field=levelii|leveli|brand|leveliii&x1=leveli&view=nav&top=1;i=1;m_ss_head_nav=JEWELRY+%26+ACCESSORIES]]></link>

                    <label><![CDATA[BEAUTY & FRAGRANCE]]></label> 
      <value><![CDATA[?q1=Beauty+%26+Fragrance;sp_sfvl_field=levelii|leveli|brand|leveliii;x1=leveli;view=nav;top=1]]></value> 
      <link><![CDATA[?q1=Beauty+%26+Fragrance;sp_sfvl_field=levelii|leveli|brand|leveliii;x1=leveli;view=nav;top=1;i=1;m_ss_head_nav=BEAUTY+%26+FRAGRANCE]]></link>

                    <label><![CDATA[GIFTS & HOME]]></label> 
      <value><![CDATA[?q1=Gifts+%26+Home;sp_sfvl_field=levelii|leveli|brand|leveliii;x1=leveli;view=nav;top=1]]></value> 
      <link><![CDATA[?q1=Gifts+%26+Home;sp_sfvl_field=levelii|leveli|brand|leveliii;x1=leveli;view=nav;top=1;i=1;m_ss_head_nav=GIFTS+%26+HOME]]></link>

                    <label><![CDATA[CHILDREN & TOYS]]></label> 
      <value><![CDATA[?q1=Children+%26+Toys;sp_sfvl_field=levelii|leveli|brand|leveliii;x1=leveli;view=nav;top=1]]></value> 
      <link><![CDATA[?q1=Children+%26+Toys;sp_sfvl_field=levelii|leveli|brand|leveliii;x1=leveli;view=nav;top=1;i=1;m_ss_head_nav=CHILDREN+%26+TOYS]]></link>

                    <label><![CDATA[ELECTRONICS]]></label> 
      <value><![CDATA[?q1=Electronics+%26+Toys;sp_sfvl_field=levelii|leveli|brand|leveliii;x1=leveli;view=nav;top=1]]></value> 
      <link><![CDATA[?q1=Electronics+%26+Toys;sp_sfvl_field=levelii|leveli|brand|leveliii;x1=leveli;view=nav;top=1;i=1;m_ss_head_nav=ELECTRONICS]]></link>

        </menu> 
    </menus> 
 
    <breadcrumbs> 
  <breadcrumb> 
            <name><![CDATA[default]]></name> 
       
  <breadcrumb-item> 
    <link><![CDATA[?i=1;q=*;sp_cs=UTF-8;sp_staged=1;view=xml]]></link> 
    <value><![CDATA[*]]></value> 
                        <label><![CDATA[]]></label> 
   </breadcrumb-item> 
          
   </breadcrumb> 
 
    </breadcrumbs> 
 
    <suggestions> 
        <auto-searched>0</auto-searched> 
         
        <suggestions-low-results>0</suggestions-low-results> 
         
    </suggestions> 
 
    <pagination> 
        <total-pages><![CDATA[112]]></total-pages> 
 
        <pages> 
     <page position="first"><![CDATA[]]></page> 
     <page position="last"><![CDATA[?i=1;page=112;q=*;sp_cs=UTF-8;sp_staged=1;view=xml]]></page> 
      
     <page position="next"><![CDATA[?i=1;page=2;q=*;sp_cs=UTF-8;sp_staged=1;view=xml]]></page>

                <page position="1" selected="true"><![CDATA[?i=1;q=*;sp_cs=UTF-8;sp_staged=1;view=xml]]></page>

                <page position="2"><![CDATA[?i=1;page=2;q=*;sp_cs=UTF-8;sp_staged=1;view=xml]]></page>

                <page position="3"><![CDATA[?i=1;page=3;q=*;sp_cs=UTF-8;sp_staged=1;view=xml]]></page>

                <page position="4"><![CDATA[?i=1;page=4;q=*;sp_cs=UTF-8;sp_staged=1;view=xml]]></page>

                <page position="5"><![CDATA[?i=1;page=5;q=*;sp_cs=UTF-8;sp_staged=1;view=xml]]></page>

        </pages> 
    </pagination> 
 
    <facets>  
         
     <facet-item> 
         <facet-title><![CDATA[Department]]></facet-title> 
                <selected>0</selected>

      <facet-value> 
           
              <label><![CDATA[Womens]]></label> 
 
       <link><![CDATA[?i=1;q=*;q1=Womens;sp_cs=UTF-8;sp_staged=1;view=xml;x1=leveli]]></link> 
       <count><![CDATA[219]]></count> 
                         
      </facet-value> 
   
      <facet-value> 
           
              <label><![CDATA[Mens]]></label> 
       <link><![CDATA[?i=1;q=*;q1=Mens;sp_cs=UTF-8;sp_staged=1;view=xml;x1=leveli]]></link> 
       <count><![CDATA[202]]></count> 
                         
      </facet-value> 
   
      <facet-value>

              <label><![CDATA[Beauty &amp; Fragrance]]></label> 
       <link><![CDATA[?i=1;q=*;q1=Beauty+%26+Fragrance;sp_cs=UTF-8;sp_staged=1;view=xml;x1=leveli]]></link> 
       <count><![CDATA[169]]></count> 
                         
      </facet-value> 
   
      <facet-value> 
           
              <label><![CDATA[Children &amp; Toys]]></label> 
       <link><![CDATA[?i=1;q=*;q1=Children+%26+Toys;sp_cs=UTF-8;sp_staged=1;view=xml;x1=leveli]]></link> 
       <count><![CDATA[209]]></count> 
                         
      </facet-value>

      <facet-value> 
           
              <label><![CDATA[Electronics &amp; Toys]]></label> 
       <link><![CDATA[?i=1;q=*;q1=Electronics+%26+Toys;sp_cs=UTF-8;sp_staged=1;view=xml;x1=leveli]]></link> 
       <count><![CDATA[200]]></count> 
                         
      </facet-value> 
   
      <facet-value> 
           
              <label><![CDATA[Gifts &amp; Home]]></label> 
       <link><![CDATA[?i=1;q=*;q1=Gifts+%26+Home;sp_cs=UTF-8;sp_staged=1;view=xml;x1=leveli]]></link> 
       <count><![CDATA[156]]></count>

      </facet-value> 
   
      <facet-value> 
           
              <label><![CDATA[Jewelry &amp; Accessories]]></label> 
       <link><![CDATA[?i=1;q=*;q1=Jewelry+%26+Accessories;sp_cs=UTF-8;sp_staged=1;view=xml;x1=leveli]]></link> 
       <count><![CDATA[182]]></count> 
                         
      </facet-value> 
   
      </facet-item> 
  
    </facets> 
 
    <results> 
        <result-set> 
            <name><![CDATA[default]]></name> 
               
         <result> 
                    <field name="index"><![CDATA[1]]></field> 
      <field name="brand"><![CDATA[Citizens]]></field> 
      <field name="price"><![CDATA[149]]></field> 
      <field name="foundIn"><![CDATA[Womens,  
            Apparel,  
          Denim]]></field> 
         </result>   
        
         <result> 
 
                    <field name="index"><![CDATA[2]]></field> 
      <field name="brand"><![CDATA[One For All]]></field> 
      <field name="price"><![CDATA[145]]></field> 
      <field name="foundIn"><![CDATA[Womens,  
            Apparel,  
          Denim]]></field> 
         </result>   
        
         <result> 
                    <field name="index"><![CDATA[3]]></field> 
      <field name="brand"><![CDATA[Citizens]]></field> 
      <field name="price"><![CDATA[208]]></field> 
 
      <field name="foundIn"><![CDATA[Womens,  
            Apparel,  
          Denim]]></field> 
         </result>   
        
         <result> 
                    <field name="index"><![CDATA[4]]></field> 
      <field name="brand"><![CDATA[Vera Watson]]></field> 
      <field name="price"><![CDATA[850]]></field> 
      <field name="foundIn"><![CDATA[Womens,  
            Dresses,  
          Day]]></field> 
         </result>   
        
         <result> 
                    <field name="index"><![CDATA[5]]></field> 
 
      <field name="brand"><![CDATA[Ray Laredo]]></field> 
      <field name="price"><![CDATA[195]]></field> 
      <field name="foundIn"><![CDATA[Children &amp; Toys,  
            Apparel,  
          Boys Toddler (2T-4T)]]></field> 
         </result>   
        
         <result> 
                    <field name="index"><![CDATA[6]]></field> 
      <field name="brand"><![CDATA[Ray Laredo]]></field> 
      <field name="price"><![CDATA[80]]></field> 
      <field name="foundIn"><![CDATA[Children &amp; Toys,  
            Apparel,  
          Boys Toddler (2T-4T)]]></field> 
 
         </result>   
        
         <result> 
                    <field name="index"><![CDATA[7]]></field> 
      <field name="brand"><![CDATA[Petrol]]></field> 
      <field name="price"><![CDATA[85]]></field> 
      <field name="foundIn"><![CDATA[Children &amp; Toys,  
            Apparel,  
          Boys Toddler (2T-4T)]]></field> 
         </result>   
        
         <result> 
                    <field name="index"><![CDATA[8]]></field> 
      <field name="brand"><![CDATA[Woolberry]]></field> 
 
      <field name="price"><![CDATA[280]]></field> 
      <field name="foundIn"><![CDATA[Children &amp; Toys,  
            Apparel,  
          Boys Toddler (2T-4T)]]></field> 
         </result>   
        
         <result> 
                    <field name="index"><![CDATA[9]]></field> 
      <field name="brand"><![CDATA[Petrol]]></field> 
      <field name="price"><![CDATA[149]]></field> 
      <field name="foundIn"><![CDATA[Children &amp; Toys,  
            Apparel,  
          Boys Toddler (2T-4T)]]></field> 
         </result>   
        
         <result> 
 
                    <field name="index"><![CDATA[10]]></field> 
      <field name="brand"><![CDATA[Ray Laredo]]></field> 
      <field name="price"><![CDATA[55]]></field> 
      <field name="foundIn"><![CDATA[Children &amp; Toys,  
            Apparel,  
          Boys Toddler (2T-4T)]]></field> 
         </result>   
        
         <result> 
                    <field name="index"><![CDATA[11]]></field> 
      <field name="brand"><![CDATA[Petrol]]></field> 
      <field name="price"><![CDATA[45]]></field> 
 
      <field name="foundIn"><![CDATA[Children &amp; Toys,  
            Apparel,  
          Boys Toddler (2T-4T)]]></field> 
         </result>   
        
         <result> 
                    <field name="index"><![CDATA[12]]></field> 
      <field name="brand"><![CDATA[Ray Laredo]]></field> 
      <field name="price"><![CDATA[47]]></field> 
      <field name="foundIn"><![CDATA[Children &amp; Toys,  
            Apparel,  
          Boys Toddler (2T-4T)]]></field> 
         </result>   
      
        </result-set>   
    </results>

    <banners> 
         
            <banner> 
                <area><![CDATA[top]]></area> 
                <content><![CDATA[<div style="color:#70A100">We have custom shipping</div>]]></content> 
            </banner>

    </banners> 
 
    <zones> 
        <zone> 
 
            <name><![CDATA[brand-facet]]></name> 
            <display>1</display> 
        </zone> 
    </zones> 
 
    <search-form> 
        <include-tnt-mbox>1</include-tnt-mbox> 
        <autocomplete> 
 
            <enabled>1</enabled> 
            <css><![CDATA[<link rel="stylesheet" type="text/css" href="https://content.t1.atomz.com/sp10043554/stage/autocomplete_styles.css?sp_js_param=2" /> 
]]></css> 
            <form-content><![CDATA[<div id="autocomplete"></div> 
<input type="hidden" name="sp_staged" id="sp_staged" value="1" /> 
]]></form-content> 
            <javascript><![CDATA[<script type="text/javascript" src="https://ajax.googleapis.com/ajax/libs/yui/2.6.0/build/utilities/utilities.js"></script> 
<script type="text/javascript" src="https://ajax.googleapis.com/ajax/libs/yui/2.6.0/build/datasource/datasource-min.js"></script> 
<script type="text/javascript" src="https://ajax.googleapis.com/ajax/libs/yui/2.6.0/build/autocomplete/autocomplete-min.js"></script> 
<script type="text/javascript" src="https://content.t1.atomz.com/sp10043554/stage/autocomplete_data.js?sp_js_param=3"></script>]]></javascript> 
        </autocomplete> 
    </search-form> 
 
</customer-results> 
```

## Beispiel für eine Präsentationsvorlage {#section_AD42571DFB88491AA7F0FDF0929EBE97}

Im Folgenden finden Sie ein Beispiel für eine Präsentationsvorlage, mit der die Beispielausgabe oben erstellt wird.

```xml
<?xml version="1.0" encoding="utf-8" standalone="yes" ?> 
<customer-results> 
    <query> 
        <user-query><![CDATA[<guided-query-param gsname="q" />]]></user-query> 
 <lower-results><![CDATA[<guided-results-lower>]]></lower-results> 
 <upper-results><![CDATA[<guided-results-upper>]]></upper-results> 
 <total-results><![CDATA[<guided-results-total>]]></total-results> 
    </query> 
 
    <custom-fields> 
        <custom-field name="seo-search-title"><![CDATA[Geometrixx Search Results]]></custom-field> 
        <custom-field name="seo-search-keywords"><![CDATA[<guided-general-field gsname="default" field="seo_search_keywords"/>]]></custom-field> 
    </custom-fields> 
 
    <menus> 
 
        <menu> 
           <name>sort</name> 
     <guided-menu gsname="sort"> 
         <guided-if-menu-item-selected> 
             <item selected="true"> 
          <label><![CDATA[<guided-menu-item-label />]]></label> 
          <value><![CDATA[<guided-menu-item-value />]]></value> 
          <link><![CDATA[ ]]></link> 
             </item> 
        <guided-else-menu-item-selected> 
             <item> 
          <label><![CDATA[<guided-menu-item-label />]]></label> 
          <value><![CDATA[<guided-menu-item-value />]]></value> 
          <link><![CDATA[<guided-menu-item-path />]]></link>     
             </item> 
        </guided-if-menu-item-selected> 
    </guided-menu> 
        </menu> 
        <menu> 
            <name><![CDATA[ss_head_nav]]></name> 
            <guided-menu gsname="ss_head_nav"> 
                <guided-if-menu-item-selected> 
                    <item selected="true"> 
                    <label><![CDATA[<guided-menu-item-label />]]></label> 
      <value><![CDATA[<guided-menu-item-value />]]></value> 
      <link><![CDATA[<guided-menu-item-path />]]></link> 
                <guided-else-menu-item-selected> 
                    <label><![CDATA[<guided-menu-item-label />]]></label> 
      <value><![CDATA[<guided-menu-item-value />]]></value> 
      <link><![CDATA[<guided-menu-item-path />]]></link> 
                </guided-if-menu-item-selected> 
            </guided-menu>  
        </menu> 
    </menus> 
 
    <breadcrumbs> 
  <breadcrumb> 
            <name><![CDATA[default]]></name> 
      <guided-breadcrumb gsname="default"> 
  <breadcrumb-item> 
    <link><![CDATA[<guided-breadcrumb-path gsname="goto">]]></link> 
    <value><![CDATA[<guided-breadcrumb-value />]]></value> 
                        <label><![CDATA[<guided-breadcrumb-label>]]></label> 
   </breadcrumb-item> 
         </guided-breadcrumb> 
   </breadcrumb> 
    </breadcrumbs> 
 
    <suggestions> 
        <auto-searched><guided-if-suggestion-autosearch>1<guided-else-suggestion-autosearch>0</guided-if-suggestion-autosearch></auto-searched> 
        <guided-if-suggestion-autosearch><orig-query><![CDATA[<guided-suggestion-original-query/>]]></orig-query></guided-if-suggestion-autosearch> 
        <suggestions-low-results><guided-if-suggestion-low-results>1<guided-else-suggestion-low-results>0</guided-if-suggestion-low-results></suggestions-low-results> 
        <guided-suggestions> 
     <suggestion-item> 
         <link><![CDATA[<guided-suggestion-path />]]></link> 
  <word><![CDATA[<guided-suggestion />]]></word> 
     </suggestion-item> 
 </guided-suggestions> 
    </suggestions> 
 
    <pagination> 
        <total-pages><![CDATA[<guided-page-total />]]></total-pages> 
        <pages> 
     <page position="first"><![CDATA[<guided-page-path gsname="first" />]]></page> 
     <page position="last"><![CDATA[<guided-page-path gsname="last" />]]></page> 
     <guided-if-page-prev><page position="prev"><![CDATA[<guided-page-path gsname="prev" />]]></page></guided-if-page-prev> 
     <guided-if-page-next><page position="next"><![CDATA[<guided-page-path gsname="next" />]]></page></guided-if-page-next> 
     <guided-if-page-viewall><page position="viewall"><![CDATA[<guided-page-path gsname="viewall" />]]></page></guided-if-page-viewall> 
     <guided-if-page-viewpages><page position="viewall"><![CDATA[<guided-page-path gsname="viewpages" />]]></page></guided-if-page-viewpages> 
 
     <guided-pages> 
                <guided-if-page-selected><page position="<guided-page-number />" selected="true"><![CDATA[<guided-page-path />]]></page> 
  <guided-else-page-selected><page position="<guided-page-number />"><![CDATA[<guided-page-path />]]></page> 
  </guided-if-page-selected> 
     </guided-pages> 
        </pages> 
    </pagination> 
 
    <facets>  
        <guided-facet gsname="leveli"> 
     <facet-item> 
         <facet-title><![CDATA[Department]]></facet-title> 
                <selected><guided-if-facet-selected>1<guided-else-facet-selected>0</guided-if-facet-selected></selected> 
                <guided-if-facet-selected><undo-link><![CDATA[<guided-facet-undo-path gsname="leveli">]]></undo-link></guided-if-facet-selected> 
  <guided-facet-values> 
      <facet-value> 
          <guided-if-facet-value-selected><selected><![CDATA[true]]></selected></guided-if-facet-value-selected> 
              <label><![CDATA[<guided-facet-value>]]></label> 
       <link><![CDATA[<guided-facet-value-path />]]></link> 
       <count><![CDATA[<guided-facet-count>]]></count> 
                        <guided-if-facet-value-selected><undolink><![CDATA[<guided-facet-value-undo-path />]]></undolink></guided-if-facet-value-selected> 
      </facet-value> 
  </guided-facet-values> 
      </facet-item> 
 </guided-facet> 
    </facets> 
 
    <results> 
        <result-set> 
            <name><![CDATA[default]]></name> 
            <guided-results gsname="default">   
         <result> 
                    <field name="index"><![CDATA[<guided-result-index />]]></field> 
      <field name="brand"><![CDATA[<guided-result-field gsname="brand" />]]></field> 
      <field name="price"><![CDATA[<guided-result-field gsname="price" />]]></field> 
      <field name="foundIn"><![CDATA[<guided-if-result-field gsname="leveli"><!--tmpl_var name='leveli'-->, </guided-if-result-field> 
            <guided-if-result-field gsname="levelii"><!--tmpl_var name='levelii'-->, </guided-if-result-field> 
          <guided-if-result-field gsname="leveliii"><!--tmpl_var name='leveliii'--></guided-if-result-field>]]></field> 
         </result>   
     </guided-results> 
        </result-set>   
    </results> 
 
    <guided-if-recent-searches> 
    <recent-searches> 
        <clear-link><guided-recent-searches-clear-path/></clear-link> 
        <guided-recent-searches> 
            <recent-search> 
                <link><guided-recent-searches-path></link> 
                <label><guided-recent-searches-value></label> 
            <recent-search> 
        </guided-recent-searches> 
    </recent-searches> 
    </guided-if-recent-searches> 
 
    <banners> 
        <guided-if-banner-set gsname="top"> 
            <banner> 
                <area><![CDATA[top]]></area> 
                <content><![CDATA[<guided-banner gsname="top">]]></content> 
            </banner> 
        </guided-if-banner-set> 
        <guided-if-banner-set gsname="bottom"> 
            <banner> 
                <area><![CDATA[bottom]]></area> 
                <content><![CDATA[<guided-banner gsname="bottom">]]></content> 
            </banner> 
        </guided-if-banner-set> 
    </banners> 
 
    <zones> 
        <zone> 
            <name><![CDATA[brand-facet]]></name> 
            <display><guided-if-zone gsname="brand-facet">1<guided-else-zone>0</guided-if-zone></display> 
        </zone> 
    </zones> 
 
    <search-form> 
        <include-tnt-mbox><guided-if-tnt-business-rules>1<guided-else-tnt-business-rules>0</guided-if-tnt-business-rules></include-tnt-mbox> 
        <autocomplete> 
            <enabled><guided-if-autocomplete>1<guided-else-autocomplete>0</guided-if-autocomplete></enabled> 
            <css><![CDATA[<guided-ac-css/>]]></css> 
            <form-content><![CDATA[<guided-ac-form-content/>]]></form-content> 
            <javascript><![CDATA[<guided-ac-javascript/>]]></javascript> 
        </autocomplete> 
    </search-form> 
 
</customer-results> 
```

