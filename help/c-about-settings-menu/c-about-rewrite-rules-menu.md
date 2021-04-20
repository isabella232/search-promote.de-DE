---
description: Verwenden Sie das Menü Regeln umschreiben, um Crawl- und Such-URL- und Titelregeln festzulegen.
solution: Target
subtopic: Rewrite Rules
title: Menü "Regeln neu schreiben"
topic: Settings,Site search and merchandising
uuid: 77ee84dd-fdba-4d34-ae8e-2fe786599800
translation-type: tm+mt
source-git-commit: d015154efdccbb4c6a39a56907c0c337ec065c9f
workflow-type: tm+mt
source-wordcount: '10202'
ht-degree: 0%

---


# Über das Menü Regeln neu schreiben {#about-the-rewrite-rules-menu}

Verwenden Sie das Menü Regeln umschreiben, um Crawl- und Such-URL- und Titelregeln festzulegen.

## Informationen zu Crawl Liste Store URL Rules {#concept_B71CF4C8030A4A74A22C3BFE4DE3B865}

Crawl-URL-Regeln geben an, wie die URLs, auf die sie in Webinhalten stoßen, umgeschrieben werden. Sie können eine unbegrenzte Anzahl von Regeln und Bedingungen angeben und einen beliebigen Teil der aufgetretenen URLs bearbeiten.

<!-- 

c_about_crawl_list_store_url_rules.xml

 -->

Crawl-Regeln sind am nützlichsten, um dynamische Teile einer URL umzuschreiben, z. B. eine Sitzungskennung, die für jeden Kunden, der Ihre Website besucht, eindeutig ist. Sie können auch Umformulierungsregeln verwenden, um Teile einer URL, z. B. Abfragen, aus dem Suchroboter auszublenden. Standardmäßig werden keine Regeln angegeben und es wird keine URL-Umschreibung durchgeführt.

Während eine Website durchsucht wird, werden URLs für eingebetteten Inhalt in einer temporären Liste zusätzlicher zu durchsuchender Webseiten gespeichert. Bevor dieser Liste eine URL hinzugefügt wird, werden die Regeln zum Speichern von Umschreibungen darauf angewendet. Normalerweise werden Regeln zum Umschreiben von Speichern verwendet, um eine Sitzungs-ID aus einer URL zu entfernen oder um eine bestimmte Sitzungs-ID für das Crawling zu erzwingen. Wenn der Suchroboter eine URL aus der Liste abruft, werden die Retrieve-Umschreibungsregeln verwendet, um Teile dieser URL erneut zu manipulieren. Normalerweise werden die Abrufregeln verwendet, um zeitkritische Daten wieder in die URL einzufügen. Diese endgültige URL wird verwendet, um die Seite von Ihrer Website abzurufen.

Siehe [Über Crawl-Liste URL-Regeln abrufen](../c-about-settings-menu/c-about-rewrite-rules-menu.md#concept_EC8E2E48B99A458D8567B526C9827CBA).

Normalerweise verwenden Sie ausschließlich Store-URL-Regeln. Abrufen von URL-Regeln ist nur erforderlich, wenn URLs dynamische Daten wie eine Sitzungs-ID enthalten und sich diese dynamischen Daten im Laufe der Zeit ändern, um gültig zu bleiben. In diesem Fall verwenden Sie Store-URL-Regeln, um den neuesten Status der Daten aus den aufgetretenen URLs abzurufen. Anschließend verwenden Sie die URL-Regeln zum Abrufen, um diese Daten jeder URL hinzuzufügen, wenn der Suchroboter versucht, die Seite abzurufen.

Jede Regel wird mit einer Rewrite-Regel-Direktive (RewriteRule) und einer oder mehreren optionalen Umschreibungsbedingungen (RewriteCond) angegeben. Die Reihenfolge der Regeln ist wichtig. Der Regelsatz wird durch Regel durchlaufen. Wenn eine Regel übereinstimmt, durchläuft sie alle entsprechenden Umschreibungsbedingungen. Eine Crawl-URL-Regel wird wie folgt angegeben:

```
RewriteCond TestString CondPattern [Flags] 
RewriteRule Pattern Substitution [Flags]
```

Wenn eine eingebettete URL gefunden wird, versucht der Suchroboter, die URL mit dem Muster jeder Crawl-Regel abzustimmen. Wenn das Muster übereinstimmt, sucht die Rewrite-Engine nach entsprechenden RewriteCond-Anweisungen. Wenn keine Bedingungen vorhanden sind, wird die URL durch einen neuen Wert ersetzt, der aus der Ersetzungszeichenfolge erstellt wurde, und fährt mit der nächsten Regel im Regelsatz fort. Wenn Bedingungen vorhanden sind, werden sie in der Reihenfolge verarbeitet, in der sie aufgelistet sind. Die rewrite-Engine versucht, ein Bedingungsmuster (CondPattern) mit einer Testzeichenfolge (TestString) abzugleichen. Wenn beide übereinstimmen, wird die nächste Bedingung verarbeitet, bis keine weiteren Bedingungen verfügbar sind. Wenn alle Bedingungen übereinstimmen, wird die URL durch die in der Regel angegebene Substitution ersetzt. Wenn die Bedingung nicht erfüllt ist, schlagen die vollständigen Bedingungen und die entsprechende Regel fehl.

## Info zu RewriteRule-Direktiven {#section_162122340BB34F12BB9A36DC9349092B}

Eine RewriteRule-Direktive hat das folgende Formular:

```
           
<i>RewriteRule Pattern Substitution [Flags]</i> 
        
```

`Pattern` kann ein regulärer POSIX-Ausdruck sein, der auf die aktuelle URL angewendet wird. Die &quot;aktuelle URL&quot;kann von der ursprünglich angeforderten URL abweichen, da frühere Regeln möglicherweise bereits übereinstimmen und die URL geändert haben.

Siehe [Reguläre Ausdruck](../c-appendices/r-regular-expressions.md#reference_B5BA7D61D82E4109A01D2A2D964E3A6A).

Das Zeichen &quot;not&quot;(&#39;!&#39;) kann nicht verwendet werden. , um dem Muster ein Präfix zu geben. Mit dem Zeichen &quot;nicht&quot;können Sie ein Muster umkehren, d. h. nur dann &quot;true&quot;haben, wenn die aktuelle URL diesem Muster NICHT entspricht. Das Zeichen &quot;nicht&quot;kann verwendet werden, wenn es besser ist, einem negativen Muster zu entsprechen, oder als endgültige Standardregel.

>[!NOTE]
>
>Sie können nicht sowohl das Zeichen &quot;nicht&quot;als auch die gruppierten Platzhalter in einem Muster verwenden. Außerdem können Sie kein negatives Muster verwenden, wenn die Ersatzzeichenfolge $N enthält.

Sie können Klammern verwenden, um einen Rückverweis im Muster zu erstellen, auf den durch Substitution und CondPattern verwiesen werden kann.

**** SubstitutionDie URL wird durch die Ersatzzeichenfolge ersetzt, die Folgendes enthält:

Text: Text, der unverändert weitergegeben wird.

Rückverweise bieten Zugriff auf die gruppierten Teile (in Klammern) des Musters oder des CondPatters. Die folgenden beiden Typen von Rückverweisen:

* **RewriteRule** BackreferencesDiese Match-Rückverweise im entsprechenden RewriteRule-Muster und verwenden das Formular $N (0)  &lt;> Beispiel, `RewriteRule ^https:// ([^/]*) (.*)$ https://${tolower: $1} $2.`

* **RewriteCond-** RückverweiseDiese Übereinstimmungsrückverweise im zuletzt übereinstimmenden RewriteCond-CondPattern und in der Form %N (0  &lt;>

Variablen: Dies sind Variablen des Formulars %{NAME_OF_VARIABLE}, wobei NAME_OF_VARIABLE eine Zeichenfolge für den Namen einer definierten Variablen ist. Weitere Informationen zum Festlegen von Umgebung finden Sie unter `*[E]*`-Flag.

Funktionen: Dies sind Funktionen des Formulars ${NAME_OF_FUNCTION:key}, wobei NAME_OF_FUNCTION die folgenden ist:

* tolower macht alle Zeichen in Kleinbuchstaben *key*.
* toupper macht alle Zeichen in Großbuchstaben *key*.
* escape-URL-kodiert alle Zeichen in *key*.
* Die Zeichen &#39;a&#39;.z&#39;, &#39;A&#39;..&#39;Z&#39;, &#39;0&#39;..&#39;9&#39;, &#39;*&#39;, &#39;-&#39;, &#39;.&#39;, &#39;/&#39;, &#39;@&#39; und &#39;_&#39; bleiben unverändert. Leerzeichen werden in &quot;+&quot;übersetzt und alle anderen Zeichen in ihre %xx URL-kodierte Entsprechung umgewandelt.
* unescape wandelt &quot;+&quot;zurück in den Leerraum und alle %xx URL-kodierten Zeichen zurück in einzelne Zeichen.

>[!NOTE]
>
>Es gibt eine spezielle Ersatzzeichenfolge: `'-'` bedeutet &quot;KEINE Substitution&quot;. Die Zeichenfolge `'-'` wird häufig mit dem Flag C (chain) verwendet, sodass Sie eine URL mehreren Mustern zuordnen können, bevor eine Ersetzung erfolgt.

**Flags**

(Optional) Schließen Sie Flags in Klammern `[]` ein. Mehrere Flags sind kommagetrennt.

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Markierung </p> </th> 
   <th colname="col2" class="entry"> <p>Beschreibung </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> 'last|L' </p> </td> 
   <td colname="col2"> <p>Letzte Regel. </p> <p>Stoppt den Umschreibungsprozess und wendet keine zusätzlichen Umschreibungsregeln an. Verwenden Sie dieses Flag, um eine weitere Verarbeitung der aktuellen URL zu verhindern. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'next|N' </p> </td> 
   <td colname="col2"> <p>Nächste Runde. </p> <p> Führt den Umschreibungsprozess (beginnend mit der ersten Umschreibungsregel) unter Verwendung der URL der letzten Umschreibungsregel (nicht der ursprünglichen URL) aus. Achten Sie darauf, keine Deadloop zu erstellen! </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'chain|C' </p> </td> 
   <td colname="col2"> <p>Verkettet mit der nächsten Regel. </p> <p>Verkettet die aktuelle Regel mit der nächsten Regel (die auch mit der folgenden Regel verkettet werden kann usw.). Wenn eine Regel übereinstimmt, wird der Ersetzungsvorgang wie gewohnt fortgesetzt. Wenn die Regel nicht übereinstimmt, werden alle nachfolgenden verketteten Regeln übersprungen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'nocase|NC' </p> </td> 
   <td colname="col2"> <p>Kein Fall. </p> <p> Beim Muster wird nicht zwischen Groß- und Kleinschreibung unterschieden (d. h. es gibt keinen Unterschied zwischen "A-Z"und "a-z"), wenn das Muster mit der aktuellen URL übereinstimmt. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'skip|S=num' </p> </td> 
   <td colname="col2"> <p>Überspringen Sie die nächste Regel bzw. die nächsten Regeln. </p> <p> Wenn die aktuelle Regel übereinstimmt, zwingt dieses Flag die Umschreibungs-Engine, die nächsten Num-Regeln im Regelsatz zu überspringen. Verwenden Sie dieses Flag, um pseudo if-then-else-Konstrukte zu erstellen. Die letzte Regel der then-Klausel wird zu einem skip=N, wobei N die Anzahl der Regeln in der else-Klausel ist. </p> <p> <p>Hinweis:  Dieses Flag ist nicht das gleiche wie das "chain|C" Flag!) </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'env|E=VAR:VAL' </p> </td> 
   <td colname="col2"> <p>Legt die Umgebungsvariable fest. </p> <p>Erstellt eine Umgebungsvariable "VAR", die auf den Wert VAL eingestellt ist, wobei VAL reguläre Ausdruck-Rückverweise, $N und %N, enthalten kann, die erweitert werden. Sie können dieses Flag mehrmals verwenden, um mehrere Variablen festzulegen. Die Variablen können später in einem folgenden RewriteCond-Muster über %{VAR} dereferenziert werden. </p> <p>Verwenden Sie dieses Flag, um Informationen aus URLs zu entfernen und zu speichern. </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>Die Regeln zum Umschreiben speichern und die Regeln zum Umschreiben abrufen haben gemeinsame Variablenwerte. Aufgrund dieses Verhaltens können Sie eine Variable auf einen zeitempfindlichen Sessionid-Wert setzen, wenn eine eingebettete URL gefunden und gespeichert wird. Wenn die nächste URL aus der Liste für temporäre Datenspeicherung abgerufen wird, kann der neueste Wert für sessionid hinzugefügt werden, bevor die Seite abgerufen wird.

**Beispiel einer RewriteRule mit einer Funktion**

Angenommen, Sie verfügen über einen Server, der die Groß- und Kleinschreibung unterscheidet und die Zeichenfolgen `"www.mydomain.com"` und `"www.MyDomain.com"` unterschiedlich verarbeitet. Damit Ihr Server ordnungsgemäß funktioniert, stellen Sie sicher, dass die Domäne immer `"www.mydomain.com"` ist, auch wenn einige Dokumente Links enthalten, die auf `"www.MyDomain.com."` verweisen. Verwenden Sie dazu die folgende Regel:

```
RewriteRule  ^https:// 
<b>([^/]*)</b> 
<i>(.*)</i>$  https://${tolower:$1}$2
```

Diese Regel zum Umschreiben verwendet die Funktion `tolower`, um den Domänenteil einer URL umzuschreiben, um sicherzustellen, dass er immer in Kleinbuchstaben lautet, wie im Folgenden dargestellt:

1. Das Muster `(^https://([^/]*)(.*)$)` enthält einen Rückverweis `([^/]*)`, der allen Zeichen zwischen `https://` und dem ersten `/` in der URL entspricht. Das Muster enthält auch einen zweiten Rückverweis `(.*)`, der allen verbleibenden Zeichen in der URL entspricht.

1. Die Substitution `(https://${tolower:$1}$2)` weist die Suchmaschine an, die URL umzuschreiben, indem sie die Funktion `tolower` für den ersten Rückverweis `(https:// ${tolower:$1}$2)` verwendet, wobei der Rest der URL unverändert bleibt.`(https://${tolower:$1} $2)`

Daher wird eine URL des Formulars `https://www.MyDomain.com/INTRO/index.Html` in `https://www.mydomain.com/INTRO/index.Html` umgeschrieben.

## Info zu RewriteCond-Direktiven {#section_CD5A19B2D3204F73B645411931FC34A1}

Die RewriteCond-Direktive definiert eine Regelbedingung. Wenn eine RewriteCond einer RewriteRule vorangeht, wird die Regel nur verwendet, wenn ihr Muster mit dem aktuellen Titel übereinstimmt und die zusätzlichen Bedingungen gelten. Umformulierungsbedingungen haben die folgende Form:

```
           
<i>RewriteCond TestString CondPattern [Flags]</i> 
        
```

`TestString` ist eine Zeichenfolge, die die folgenden Konstrukte enthalten kann:

Text: Text, der unverändert weitergegeben wird.

Rückverweise bieten Zugriff auf die gruppierten Teile (in Klammern) des Musters oder des CondPatters. Die folgenden beiden Typen von Rückverweisen:

* **RewriteRule** BackreferencesDiese Match-Rückverweise im entsprechenden RewriteRule-Muster und verwenden das Formular $N (0)  &lt;> Beispiel, `RewriteRule ^https:// ([^/]*) (.*)$ https://${tolower: $1} $2`.

* **RewriteCond-** RückverweiseDiese Übereinstimmungsrückverweise im zuletzt übereinstimmenden RewriteCond-CondPattern und in der Form %N (0&lt;>

Variablen: Dies sind Variablen des Formulars %{NAME_OF_VARIABLE}, wobei NAME_OF_VARIABLE eine Zeichenfolge für den Namen einer definierten Variablen sein kann. Weitere Informationen zum Festlegen von Variablen finden Sie im Flag RewriteRule *`[E]`*.

Funktionen: Dies sind Funktionen des Formulars ${NAME_OF_FUNCTION:key}, wobei NAME_OF_FUNCTION die folgenden ist:

* tolower macht alle Zeichen in Kleinbuchstaben *key*.
* toupper macht alle Zeichen in Großbuchstaben *key*.
* escape-URL-kodiert alle Zeichen im Schlüssel. Die Zeichen &#39;a&#39;.z&#39;, &#39;A&#39;..&#39;Z&#39;, &#39;0&#39;..&#39;9&#39;, &#39;*&#39;, &#39;-&#39;, &#39;.&#39;, &#39;/&#39;, &#39;@&#39; und &#39;_&#39; bleiben unverändert, Leerzeichen werden in &#39;+&#39; übersetzt und alle anderen Zeichen werden in ihre `%xx` URL-kodierte Entsprechung umgewandelt.
* unescape wandelt &quot;+&quot;zurück in den Leerraum und alle `%xx` URL-Kodierungszeichen zurück in einzelne Zeichen.

**** CondPatternis ist ein standardmäßiger erweiterter regulärer Ausdruck mit einigen Ergänzungen. Der Musterzeichenfolge kann ein `!`-Zeichen (Ausrufezeichen) vorangestellt werden, um ein nicht übereinstimmendes Muster anzugeben. Anstelle der Zeichenfolgen mit regulären Ausdrücken können Sie eine der folgenden Sondervarianten verwenden:

>[!NOTE]
>
>Sie können diesen Tests auch ein Ausrufezeichen (&#39;!&#39;) voranstellen. ihre Bedeutung zu negieren.

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>CondPattern-Zeichenfolge </p> </th> 
   <th colname="col2" class="entry"> <p>Beschreibung </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> '&lt;CondPattern' </p> </td> 
   <td colname="col2"> <p>Lexisch weniger. </p> <p> Behandelt das CondPattern als einfache Zeichenfolge und vergleicht es wörtlich mit TestString. True, wenn TestString lexikalisch kleiner als CondPattern ist. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> '&gt;CondPattern' </p> </td> 
   <td colname="col2"> <p>Lexisch größer. </p> <p> Behandelt das CondPattern als einfache Zeichenfolge und vergleicht es wörtlich mit TestString. True, wenn TestString lexikalisch größer als CondPattern ist. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> '=CondPattern' </p> </td> 
   <td colname="col2"> <p>Lexisch gleich. </p> <p> Behandelt das CondPattern als einfache Zeichenfolge und vergleicht es wörtlich mit TestString. True, wenn TestString wörtlich mit CondPattern identisch ist, d. h., die beiden Zeichenfolgen sind exakt gleich (Zeichen nach Zeichen). Wenn CondPattern nur "" (zwei Anführungszeichen) ist, wird TestString mit der leeren Zeichenfolge verglichen. </p> </td> 
  </tr> 
 </tbody> 
</table>

**Flags**
 (optional) Schließen Flags in Klammern ein  `[]`. Mehrere Flags sind kommagetrennt.

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Markierung </p> </th> 
   <th colname="col2" class="entry"> <p>Beschreibung </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> 'nocase|NC' </p> </td> 
   <td colname="col2"> <p> Kein Fall. </p> <p>Durch dieses Flag wird die Groß-/Kleinschreibung des Tests nicht berücksichtigt, d. h. es gibt keinen Unterschied zwischen "A-Z"und "a-z"sowohl im erweiterten TestString als auch im CondPattern. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'ornext|OR' </p> </td> 
   <td colname="col2"> <p>Oder die nächste Bedingung. </p> <p>Verwenden Sie dieses Flag, um Regelbedingungen mit einem lokalen ODER anstelle des impliziten UND zu kombinieren. Ohne dieses Flag müssten Sie die Konstante/Regel mehrmals schreiben. </p> </td> 
  </tr> 
 </tbody> 
</table>

**Beispiel**

Einige Webseiten weisen eine CGI-Variable &quot;sessionid&quot;zu, wenn ein Besucher zum ersten Mal auf eine Site gelangt. Diese Variable wird zur Identifizierung des Besuchers verwendet. Wenn der Besucher durch die Site navigiert, wird die Variable weitergegeben. Da der Suchroboter wie ein Besucher Ihrer Site aussieht, wird ihm eine &quot;sessionid&quot;-Nummer zugewiesen. Der Suchroboter behält diesen einzelnen &quot;sessionid&quot;-Wert bei, selbst wenn eine zweite Site versucht, einen neuen Wert zuzuweisen. Um dies sicherzustellen, benötigen Sie zwei Umformulierungsregeln.

Die erste Regel dient zur Identifizierung und Speicherung der Variablen sessionid:

```
RewriteCond  %{sessionid}  !.+ 
RewriteRule  ^.+sessionid= 
<b>([^&#]+)</b>.*$  -   
<i>[E=sessionid:$1]</i>
```

Die RewriteRule verwendet ein E-Flag `([E=sessionid:$1])`, um der Variablen `sessionid` den aktuellen Wert des sessionid-CGI-Parameters zuzuweisen. Das `$1` verweist auf den ersten Rückverweis, der zwischen dem ersten Satz von Klammern im Muster der RewriteRule `([^&#]+)` enthalten ist.

Der reguläre Ausdruck `^&#]+` entspricht dem Teil einer URL zwischen dem Wort `sessionid` und dem nächsten Zeichen `**&**or**#**`. Da diese RewriteRule nur zum Erstellen des Ausgangswerts für die sessionid-Variable verwendet wird, wird keine Umschreibung durchgeführt. Beachten Sie, dass das Feld &quot;Ersetzen&quot;der Regel auf `-` eingestellt ist, um anzugeben, dass keine Umschreibung erforderlich ist.

RewriteCond untersucht die Variable `sessionid` ( `%{sessionid}`). Wenn es nicht einmal ein einzelnes Zeichen (!+), dann stimmt RewriteRule überein.

Bei Verwendung dieser Regel wird die URL als `https://www.domain.com/home/?sessionid=1234&function=start` gelesen und der Variablen `sessionid` den Wert `1234` zugewiesen.

Die zweite Regel wird zum Umschreiben aller URLs verwendet, die dem folgenden RewriteRule-Muster entsprechen:

```
RewriteRule   
<b>^(.+)</b>sessionid=[^&#]+ 
<i>(.*)$</i>  $1sessionid=%{sessionid}$2
```

Das RewriteRule-Muster enthält zwei Rückverweise: `(.+)` und `(.*)`. Der erste Rückverweis stimmt mit allen Zeichen vor `sessionid` überein. Der zweite Rückverweis entspricht allen Zeichen nach dem Abschluss von `&` oder `#`.

Das Substitutionsmuster schreibt die URL mit dem ersten Rückverweis, gefolgt von der Zeichenfolge &quot;sessionid=&quot;, gefolgt vom Wert der durch die erste Regel `%{sessionid}` definierten Sitzungs-ID-Variablen, gefolgt vom zweiten Rückverweis. `($1sessionid=%{sessionid} $2)`

Beachten Sie, dass diese RewriteRule keinen RewriteCond enthält. Daher wird für alle URLs, die mit der RewriteRule *Pattern* übereinstimmen, ein Umschreiben ausgelöst. Wenn der Wert der sessionid-Variablen ( `%{sessionid}`) `1234` ist, wird eine URL des Formulars `https://www.domain.com/products/?sessionid=5678&function=buy` als `https://www.domain.com/products/?sessionid=1234&function=buy` umgeschrieben

## Danksagung {#section_B17088EF38244496BC1DDD4ECF75EB5B}

Die rewrite Engine Software wurde ursprünglich von der Apache Group für die Verwendung im Apache HTTP Server Projekt (https://www.apache.org/) entwickelt.

## Hinzufügen einer Crawl-Listen-Store-URL-Regel {#task_22DD40DF95584B12BE8E6ECFBF579BCD}

Sie können URL-Regeln zum Speichern von Crawl-Listen hinzufügen, um anzugeben, wie die URLs, auf die in Webinhalten gestoßen wird, umgeschrieben werden. Sie können eine unbegrenzte Anzahl von Regeln und Bedingungen angeben und einen beliebigen Teil der aufgetretenen URLs bearbeiten.

<!-- 

t_adding_a_crawl_list_store_url_rule.xml

 -->

**So fügen Sie Crawl Liste Store-URL-Regeln hinzu**

1. Klicken Sie im Produktmenü auf **[!UICONTROL Settings]** > **[!UICONTROL Rewrite Rules]** > **[!UICONTROL Crawl List Store URL Rules]**.
1. Geben Sie im Feld [!DNL Crawl List Store URL Rules] die gewünschten Regeln ein.

   Leere Zeilen und Kommentarzeilen, die mit einem &quot;#&quot;(Hash) beginnen, sind zulässig.
1. (Optional) Geben Sie auf der Seite [!DNL Crawl List Store URL Rules] im Feld [!DNL Test Crawl List Store URL Rules] eine Test-URL ein, deren Crawl-Regeln Sie testen möchten, und klicken Sie dann auf **Test**.
1. Klicken Sie auf **Änderungen speichern**.
1. (Optional) Erstellen Sie Ihren Stage-Site-Index neu, wenn Sie die Vorschauen durchführen möchten.

   Siehe [Konfigurieren eines inkrementellen Indexes einer gestaffelten Website](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0).
1. (Optional) Führen Sie auf der Seite [!DNL Crawl List Store URL Rules] einen der folgenden Schritte aus:

   * Klicken Sie auf **[!UICONTROL History]**, um alle vorgenommenen Änderungen wiederherzustellen.

      Siehe [Verwenden der Option Verlauf](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Klicken **[!UICONTROL Live]**.

      Siehe [Live-Einstellungen anzeigen](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Klicken **[!UICONTROL Push Live]**.

      Siehe [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Informationen zu Crawl-Listen URL-Regeln abrufen {#concept_EC8E2E48B99A458D8567B526C9827CBA}

Crawl-URL-Regeln geben an, wie die URLs, auf die in Webinhalten gestoßen wird, umgeschrieben werden. Sie können eine unbegrenzte Anzahl von Regeln und Bedingungen angeben und einen beliebigen Teil der aufgetretenen URLs bearbeiten.

<!-- 

c_about_crawl_list_retrieve_url_rules.xml

 -->

Bevor die Auswirkungen der Regeln für Kunden sichtbar sind, stellen Sie sicher, dass Sie Ihren Site-Index neu erstellen.

Crawl-Regeln sind am nützlichsten, um dynamische Teile einer URL umzuschreiben, z. B. eine Sitzungskennung, die für jeden Kunden, der Ihre Website besucht, eindeutig ist. Sie können auch Umformulierungsregeln verwenden, um Teile einer URL, z. B. Abfragen, aus dem Suchroboter auszublenden. Standardmäßig werden keine Regeln angegeben und es wird keine URL-Umschreibung durchgeführt.

Während eine Website durchsucht wird, werden URLs für eingebetteten Inhalt in einer temporären Liste zusätzlicher zu durchsuchender Webseiten gespeichert. Wenn der Suchroboter eine URL aus der Liste abruft, werden die Regeln zum Umschreiben abrufen verwendet, um Teile dieser URL zu manipulieren. Normalerweise werden die Abrufregeln zum Einfügen zeitempfindlicher Daten in eine URL verwendet. Diese endgültige URL wird verwendet, um die Seite von Ihrer Website abzurufen.

Rückrufregeln sind nur erforderlich, wenn URLs dynamische Daten wie eine Sitzungs-ID enthalten und sich diese dynamischen Daten im Laufe der Zeit ändern, um gültig zu bleiben. In diesem Fall verwenden Sie Regeln zum Umschreiben speichern, um den neuesten Status der Daten aus den aufgetretenen URLs abzurufen. Anschließend verwenden Sie die Retrieve Rewrite Rules, um diese Daten jeder URL hinzuzufügen, wenn die Suchroboter die Seite abrufen.

Jede Regel wird mit einer Rewrite-Regel-Direktive (RewriteRule) und einer oder mehreren optionalen Umschreibungsbedingungen (RewriteCond) angegeben. Die Reihenfolge der Regeln ist wichtig. Der Regelsatz wird durch Regel durchlaufen. Wenn eine Regel übereinstimmt, durchläuft sie alle entsprechenden Umschreibungsbedingungen. Eine Crawl-URL-Regel wird wie folgt angegeben:

```
RewriteCond TestString CondPattern [Flags] 
RewriteRule Pattern Substitution [Flags]
```

Wenn eine eingebettete URL gefunden wird, versucht der Suchroboter, die URL mit dem Muster jeder Crawl-Regel abzustimmen. Wenn das Muster übereinstimmt, sucht die Rewrite-Engine nach entsprechenden RewriteCond-Anweisungen. Wenn keine Bedingungen vorhanden sind, wird die URL durch einen neuen Wert ersetzt, der aus der Ersetzungszeichenfolge erstellt wurde, und fährt mit der nächsten Regel im Regelsatz fort. Wenn Bedingungen vorhanden sind, werden sie in der Reihenfolge verarbeitet, in der sie aufgelistet sind. Die rewrite-Engine versucht, ein Bedingungsmuster (CondPattern) mit einer Testzeichenfolge (TestString) abzugleichen. Wenn beide übereinstimmen, wird die nächste Bedingung verarbeitet, bis keine weiteren Bedingungen verfügbar sind. Wenn alle Bedingungen übereinstimmen, wird die URL durch die in der Regel angegebene Substitution ersetzt. Wenn die Bedingung nicht erfüllt ist, schlagen die vollständigen Bedingungen und die entsprechende Regel fehl.

## Info zu RewriteRule-Direktiven {#section_32B24B29627946398AFBC5F869A610CB}

Eine RewriteRule-Direktive hat das folgende Formular:

```
           
<i>RewriteRule Pattern Substitution [Flags]</i> 
        
```

`Pattern` kann ein regulärer POSIX-Ausdruck sein, der auf die aktuelle URL angewendet wird. Die &quot;aktuelle URL&quot;kann von der ursprünglich angeforderten URL abweichen, da frühere Regeln möglicherweise bereits übereinstimmen und die URL geändert haben.

Siehe [Reguläre Ausdruck](../c-appendices/r-regular-expressions.md#reference_B5BA7D61D82E4109A01D2A2D964E3A6A).

Das Zeichen &quot;not&quot;(&#39;!&#39;) kann nicht verwendet werden. , um dem Muster ein Präfix zu geben. Mit dem Zeichen &quot;nicht&quot;können Sie ein Muster umkehren, d. h. nur dann &quot;true&quot;haben, wenn die aktuelle URL diesem Muster NICHT entspricht. Das Zeichen &quot;nicht&quot;kann verwendet werden, wenn es besser ist, einem negativen Muster zu entsprechen, oder als endgültige Standardregel.

>[!NOTE]
>
>Sie können nicht sowohl das Zeichen &quot;nicht&quot;als auch die gruppierten Platzhalter in einem Muster verwenden. Außerdem können Sie kein negatives Muster verwenden, wenn die Ersatzzeichenfolge $N enthält.

Sie können Klammern verwenden, um einen Rückverweis im Muster zu erstellen, auf den durch Substitution und CondPattern verwiesen werden kann.

**** SubstitutionDie URL wird durch die Ersatzzeichenfolge ersetzt, die Folgendes enthält:

Text: Text, der unverändert weitergegeben wird.

Rückverweise bieten Zugriff auf die gruppierten Teile (in Klammern) des Musters oder des CondPatters. Die folgenden beiden Typen von Rückverweisen:

* **RewriteRule** BackreferencesDiese Match-Rückverweise im entsprechenden RewriteRule-Muster und verwenden das Formular $N (0)  &lt;> Beispiel, `RewriteRule ^https:// ([^/]*) (.*)$ https://${tolower: $1} $2.`

* ** RewriteCond-Rückverweise** Diese Übereinstimmungsrückverweise im letzten übereinstimmenden RewriteCond-Muster und verwenden das Formular %N (0 &lt;= N &lt;= 9).

Variablen: Dies sind Variablen des Formulars %{NAME_OF_VARIABLE}, wobei NAME_OF_VARIABLE eine Zeichenfolge für den Namen einer definierten Variablen ist. Weitere Informationen zum Festlegen von Umgebung finden Sie unter *[E]*.

Funktionen: Dies sind Funktionen des Formulars ${NAME_OF_FUNCTION:key}, wobei NAME_OF_FUNCTION die folgenden ist:

* tolower macht alle Zeichen in Kleinbuchstaben *key*.
* toupper macht alle Zeichen in Großbuchstaben *key*.
* escape-URL-kodiert alle Zeichen in *key*.
* Die Zeichen &#39;a&#39;.z&#39;, &#39;A&#39;..&#39;Z&#39;, &#39;0&#39;..&#39;9&#39;, &#39;*&#39;, &#39;-&#39;, &#39;.&#39;, &#39;/&#39;, &#39;@&#39; und &#39;_&#39; bleiben unverändert. Leerzeichen werden in &quot;+&quot;übersetzt und alle anderen Zeichen in ihre %xx URL-kodierte Entsprechung umgewandelt.
* unescape wandelt &quot;+&quot;zurück in den Leerraum und alle %xx URL-kodierten Zeichen zurück in einzelne Zeichen.

>[!NOTE]
>
>Es gibt eine spezielle Ersatzzeichenfolge: &quot;-&quot; bedeutet &quot;KEINE Substitution&quot;. Die Zeichenfolge &quot;-&quot;wird häufig mit dem Flag &quot;C&quot;(chain) verwendet, sodass Sie eine URL mehreren Mustern zuordnen können, bevor eine Ersetzung erfolgt.

**Flags**

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Markierung </p> </th> 
   <th colname="col2" class="entry"> <p>Beschreibung </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> 'last|L' </p> </td> 
   <td colname="col2"> <p>Letzte Regel. </p> <p>Stoppt den Umschreibungsprozess und wendet keine zusätzlichen Umschreibungsregeln an. Verwenden Sie dieses Flag, um eine weitere Verarbeitung der aktuellen URL zu verhindern. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'next|N' </p> </td> 
   <td colname="col2"> <p>Nächste Runde. </p> <p> Führt den Umschreibungsprozess (beginnend mit der ersten Umschreibungsregel) unter Verwendung der URL der letzten Umschreibungsregel (nicht der ursprünglichen URL) aus. Achten Sie darauf, keine Deadloop zu erstellen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'chain|C' </p> </td> 
   <td colname="col2"> <p>Verkettet mit der nächsten Regel. </p> <p>Verkettet die aktuelle Regel mit der nächsten Regel (die auch mit der folgenden Regel verkettet werden kann usw.). Wenn eine Regel übereinstimmt, wird der Ersetzungsvorgang wie gewohnt fortgesetzt. Wenn die Regel nicht übereinstimmt, werden alle nachfolgenden verketteten Regeln übersprungen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'nocase|NC' </p> </td> 
   <td colname="col2"> <p>Kein Fall. </p> <p> Beim Muster wird nicht zwischen Groß- und Kleinschreibung unterschieden (d. h. es gibt keinen Unterschied zwischen "A-Z"und "a-z"), wenn das Muster mit der aktuellen URL übereinstimmt. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'skip|S=num' </p> </td> 
   <td colname="col2"> <p>Überspringen Sie die nächste Regel bzw. die nächsten Regeln. </p> <p> Wenn die aktuelle Regel übereinstimmt, zwingt dieses Flag die Umschreibungs-Engine, die nächsten Num-Regeln im Regelsatz zu überspringen. Verwenden Sie dieses Flag, um pseudo if-then-else-Konstrukte zu erstellen. Die letzte Regel der then-Klausel wird zu einem skip=N, wobei N die Anzahl der Regeln in der else-Klausel ist. </p> <p> <p>Hinweis:  Dieses Flag ist nicht das gleiche wie das "chain|C" Flag!) </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'env|E=VAR:VAL' </p> </td> 
   <td colname="col2"> <p>Legt die Umgebungsvariable fest. </p> <p>Erstellt eine Umgebungsvariable "VAR", die auf den Wert VAL eingestellt ist, wobei VAL reguläre Ausdruck-Rückverweise, $N und %N, enthalten kann, die erweitert werden. Sie können dieses Flag mehrmals verwenden, um mehrere Variablen festzulegen. Die Variablen können später in einem folgenden RewriteCond-Muster über %{VAR} dereferenziert werden. </p> <p>Verwenden Sie dieses Flag, um Informationen aus URLs zu entfernen und zu speichern. </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>Die Regeln zum Umschreiben speichern und die Regeln zum Umschreiben abrufen haben gemeinsame Variablenwerte. Aufgrund dieses Verhaltens können Sie eine Variable auf einen zeitempfindlichen Sessionid-Wert setzen, wenn eine eingebettete URL gefunden und gespeichert wird. Wenn die nächste URL aus der Liste für temporäre Datenspeicherung abgerufen wird, kann der neueste Wert für sessionid hinzugefügt werden, bevor die Seite abgerufen wird.

**Beispiel einer RewriteRule mit einer Funktion**

Angenommen, Sie haben einen Server, der die Groß- und Kleinschreibung berücksichtigt, der die Zeichenfolgen &quot;www.mydomain.com&quot;und &quot;www.MyDomain.com&quot;anders verarbeitet. Damit Ihr Server ordnungsgemäß funktioniert, müssen Sie sicherstellen, dass die Domäne immer &quot;www.mydomain.com&quot;lautet, auch wenn einige Dokumente Links enthalten, die auf &quot;www.MyDomain.com&quot;verweisen. Dazu können Sie die folgende Regel verwenden:

```
RewriteRule  ^https:// 
<b>([^/]*)</b> 
<i>(.*)</i>$  https://${tolower:$1}$2
```

Diese Regel zum Umschreiben verwendet die Funktion `tolower`, um den Domänenteil einer URL umzuschreiben, um sicherzustellen, dass er immer in Kleinbuchstaben lautet, wie im Folgenden dargestellt:

1. Das Muster `(^https://([^/]*)(.*)$)` enthält einen Rückverweis ** `([^/]*)`**, der allen Zeichen zwischen `https://` und dem ersten `/` in der URL entspricht. Das Muster enthält auch einen zweiten Rückverweis `(.*)`, der allen verbleibenden Zeichen in der URL entspricht.
1. Die Substitution `(https://${tolower:$1}$2)` weist die Suchmaschine an, die URL umzuschreiben, indem sie die Funktion `tolower` für den ersten Rückverweis `(https:// ${tolower:$1}$2)` verwendet, wobei der Rest der URL unverändert bleibt.`(https://${tolower:$1} $2)`

Daher wird eine URL des Formulars `https://www.MyDomain.com/INTRO/index.Html` in `https://www.mydomain.com/INTRO/index.Html` umgeschrieben.

## Info zu RewriteCond-Direktiven {#section_ADD642A24B68452CB98294A0BD687EC3}

Die RewriteCond-Direktive definiert eine Regelbedingung. Wenn eine RewriteCond einer RewriteRule vorangeht, wird die Regel nur verwendet, wenn ihr Muster mit dem aktuellen Titel übereinstimmt und die zusätzlichen Bedingungen gelten. Umformulierungsbedingungen haben die folgende Form:

```
           
<i>RewriteCond TestString CondPattern [Flags]</i> 
        
```

`TestString` ist eine Zeichenfolge, die die folgenden Konstrukte enthalten kann:

Text: Text, der unverändert weitergegeben wird.

Rückverweise bieten Zugriff auf die gruppierten Teile (in Klammern) des Musters oder des CondPatters. Die folgenden beiden Typen von Rückverweisen:

* **RewriteRule** BackreferencesDiese Match-Rückverweise im entsprechenden RewriteRule-Muster und verwenden das Formular $N (0)  &lt;> Beispiel, `RewriteRule ^https:// ([^/]*) (.*)$ https://${tolower: $1} $2`.

* **RewriteCond-** RückverweiseDiese Übereinstimmungsrückverweise im zuletzt übereinstimmenden RewriteCond-CondPattern und in der Form %N (0&lt;>

Variablen: Dies sind Variablen des Formulars %{NAME_OF_VARIABLE}, wobei NAME_OF_VARIABLE eine Zeichenfolge für den Namen einer definierten Variablen sein kann. Weitere Informationen zum Festlegen von Variablen finden Sie im Flag RewriteRule *`[E]`*.

Funktionen: Dies sind Funktionen des Formulars ${NAME_OF_FUNCTION:key}, wobei NAME_OF_FUNCTION die folgenden ist:

* tolower macht alle Zeichen in Kleinbuchstaben *key*.
* toupper macht alle Zeichen in Großbuchstaben *key*.
* escape-URL-kodiert alle Zeichen im Schlüssel. Die Zeichen &#39;a&#39;.z&#39;, &#39;A&#39;..&#39;Z&#39;, &#39;0&#39;..&#39;9&#39;, &#39;*&#39;, &#39;-&#39;, &#39;.&#39;, &#39;/&#39;, &#39;@&#39; und &#39;_&#39; bleiben unverändert, Leerzeichen werden in &#39;+&#39; übersetzt und alle anderen Zeichen werden in ihre %xx URL-kodierte Entsprechung umgewandelt.
* unescape wandelt &quot;+&quot;zurück in den Leerraum und alle %xx URL-Kodierungszeichen zurück in einzelne Zeichen.

**** CondPatternis ist ein standardmäßiger erweiterter regulärer Ausdruck mit einigen Ergänzungen. Der Musterzeichenfolge kann ein &#39;!&#39; vorangestellt werden -Zeichen (Ausrufezeichen), um ein nicht übereinstimmendes Muster anzugeben. Anstelle der Zeichenfolgen mit regulären Ausdrücken können Sie eine der folgenden Sondervarianten verwenden:

>[!NOTE]
>
>Sie können diesen Tests auch ein Ausrufezeichen (&#39;!&#39;) voranstellen. ihre Bedeutung zu negieren.

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>CondPattern-Zeichenfolge </p> </th> 
   <th colname="col2" class="entry"> <p>Beschreibung </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> '&lt;CondPattern' </p> </td> 
   <td colname="col2"> <p>Lexisch weniger. </p> <p> Behandelt das CondPattern als einfache Zeichenfolge und vergleicht es wörtlich mit TestString. True, wenn TestString lexikalisch kleiner als CondPattern ist. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> '&gt;CondPattern' </p> </td> 
   <td colname="col2"> <p>Lexisch größer. </p> <p> Behandelt das CondPattern als einfache Zeichenfolge und vergleicht es wörtlich mit TestString. True, wenn TestString lexikalisch größer als CondPattern ist. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> '=CondPattern' </p> </td> 
   <td colname="col2"> <p>Lexisch gleich. </p> <p> Behandelt das CondPattern als einfache Zeichenfolge und vergleicht es wörtlich mit TestString. True, wenn TestString wörtlich mit CondPattern identisch ist, d. h., die beiden Zeichenfolgen sind exakt gleich (Zeichen nach Zeichen). Wenn CondPattern nur "" (zwei Anführungszeichen) ist, wird TestString mit der leeren Zeichenfolge verglichen. </p> </td> 
  </tr> 
 </tbody> 
</table>

**Flags**
 (optional) Schließen Flags in Klammern ein  `[]`. Mehrere Flags sind kommagetrennt.

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Markierung </p> </th> 
   <th colname="col2" class="entry"> <p>Beschreibung </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> 'nocase|NC' </p> </td> 
   <td colname="col2"> <p> Kein Fall. </p> <p>Durch dieses Flag wird die Groß-/Kleinschreibung des Tests nicht berücksichtigt, d. h. es gibt keinen Unterschied zwischen "A-Z"und "a-z"sowohl im erweiterten TestString als auch im CondPattern. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'ornext|OR' </p> </td> 
   <td colname="col2"> <p>Oder die nächste Bedingung. </p> <p>Verwenden Sie dieses Flag, um Regelbedingungen mit einem lokalen ODER anstelle des impliziten UND zu kombinieren. Ohne dieses Flag müssten Sie die Konstante/Regel mehrmals schreiben. </p> </td> 
  </tr> 
 </tbody> 
</table>

**Beispiel**

Einige Webseiten weisen eine CGI-Variable &quot;sessionid&quot;zu, wenn ein Besucher zum ersten Mal auf eine Site gelangt. Diese Variable wird zur Identifizierung des Besuchers verwendet. Wenn der Besucher durch die Site navigiert, wird die Variable weitergegeben. Da der Suchroboter wie ein Besucher Ihrer Site aussieht, wird ihm eine &quot;sessionid&quot;-Nummer zugewiesen. Der Suchroboter behält diesen einzelnen &quot;sessionid&quot;-Wert bei, selbst wenn eine zweite Site versucht, einen neuen Wert zuzuweisen. Um dies sicherzustellen, benötigen Sie zwei Umformulierungsregeln.

Die erste Regel dient zur Identifizierung und Speicherung der Variablen sessionid:

```
RewriteCond  %{sessionid}  !.+ 
RewriteRule  ^.+sessionid= 
<b>([^&#]+)</b>.*$  -   
<i>[E=sessionid:$1]</i>
```

Die RewriteRule verwendet ein E-Flag `([E=sessionid:$1])`, um der Variablen `sessionid` den aktuellen Wert des sessionid-CGI-Parameters zuzuweisen. Das `$1` verweist auf den ersten Rückverweis, der zwischen dem ersten Satz von Klammern im Muster der RewriteRule `([^&#]+)` enthalten ist.

Der reguläre Ausdruck `^&#]+` entspricht dem Teil einer URL zwischen dem Wort `sessionid` und dem nächsten**&amp;**oder**#**Zeichen. Da diese RewriteRule nur zum Erstellen des Ausgangswerts für die sessionid-Variable verwendet wird, wird keine Umschreibung durchgeführt. Beachten Sie, dass das Feld &quot;Ersetzen&quot;der Regel auf `-` eingestellt ist, um anzugeben, dass keine Umschreibung erforderlich ist.

RewriteCond untersucht die Variable `sessionid` ( `%{sessionid}`). Wenn es nicht einmal ein einzelnes Zeichen (!+), dann stimmt RewriteRule überein.

Bei Verwendung dieser Regel wird die URL als `https://www.domain.com/home/?sessionid=1234&function=start` gelesen und der Variablen `sessionid` den Wert `1234` zugewiesen.

Die zweite Regel wird zum Umschreiben aller URLs verwendet, die dem folgenden RewriteRule-Muster entsprechen:

```
RewriteRule   
<b>^(.+)</b>sessionid=[^&#]+ 
<i>(.*)$</i>  $1sessionid=%{sessionid}$2
```

Das RewriteRule-Muster enthält zwei Rückverweise: `(.+)` und `(.*)`. Der erste Rückverweis stimmt mit allen Zeichen vor `sessionid` überein. Der zweite Rückverweis entspricht allen Zeichen nach dem Abschluss von `&` oder `#`.

Das Substitutionsmuster schreibt die URL mit dem ersten Rückverweis, gefolgt von der Zeichenfolge &quot;sessionid=&quot;, gefolgt vom Wert der durch die erste Regel `%{sessionid}` definierten Sitzungs-ID-Variablen, gefolgt vom zweiten Rückverweis. `($1sessionid=%{sessionid} $2)`

Beachten Sie, dass diese RewriteRule keinen RewriteCond enthält. Daher wird für alle URLs, die mit der RewriteRule *Pattern* übereinstimmen, ein Umschreiben ausgelöst. Wenn der Wert der sessionid-Variablen ( `%{sessionid}`) `1234` ist, wird eine URL des Formulars `https://www.domain.com/products/?sessionid=5678&function=buy` als `https://www.domain.com/products/?sessionid=1234&function=buy` umgeschrieben

## Danksagung {#section_EC3A1DAEB5A54C93A265CB119DF91E9F}

Die rewrite Engine Software wurde ursprünglich von der Apache Group für die Verwendung im Apache HTTP Server Projekt (https://www.apache.org/) entwickelt.

## Hinzufügen einer Crawl-Liste zum Abrufen von URL-Regeln {#task_94A28ED7DC404BFF9767DBB5ADEE6B7A}

Sie können Crawl-Listen URL-Regeln hinzufügen, um anzugeben, wie getretene URLs in Webinhalten umgeschrieben werden. Rückrufregeln sind nur erforderlich, wenn URLs dynamische Daten wie eine Sitzungs-ID enthalten und sich diese dynamischen Daten im Laufe der Zeit ändern, um gültig zu bleiben.

<!-- 

t_adding_crawl_list_retrieve_url_rules.xml

 -->

**So fügen Sie Crawl-Listen Abrufen von URL-Regeln hinzu**

1. Klicken Sie im Produktmenü auf **[!UICONTROL Settings]** > **[!UICONTROL Rewrite Rules]** > **[!UICONTROL Crawl List Retrieve URL Rules]**.
1. Geben Sie im Feld [!DNL Crawl List Retrieve URL Rules] die gewünschten Regeln ein.

   Leere Zeilen und Kommentarzeilen, die mit einem &quot;#&quot;(Hash) beginnen, sind zulässig.
1. (Optional) Geben Sie auf der Seite [!DNL Crawl List Retrieve URL Rules] im Feld [!DNL Test Crawl List Retrieve URL Rules] eine Test-URL ein, deren Crawl-Regeln Sie testen möchten, und klicken Sie dann auf **Test**.
1. Klicken Sie auf **Änderungen speichern**.
1. (Optional) Erstellen Sie Ihren Stage-Site-Index neu, wenn Sie die Vorschauen durchführen möchten.

   Siehe [Konfigurieren eines inkrementellen Indexes einer gestaffelten Website](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0).
1. (Optional) Führen Sie auf der Seite [!DNL Crawl List Retrieve URL Rules] einen der folgenden Schritte aus:

   * Klicken Sie auf **[!UICONTROL History]**, um alle vorgenommenen Änderungen wiederherzustellen.

      Siehe [Verwenden der Option Verlauf](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Klicken **[!UICONTROL Live]**.

      Siehe [Live-Einstellungen anzeigen](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Klicken **[!UICONTROL Push Live]**.

      Siehe [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Grundlagen zu Crawl-Titelregeln {#concept_BD3A576987DA4D93A998B0B9CDDC3C79}

Die Regeln für Crawl-Titel geben an, wie getragene Titel in Webinhalten umgeschrieben werden, bevor sie im Suchindex gespeichert werden.

<!-- 

c_about_crawl_title_rules.xml

 -->

Beispielsweise können Sie mit einer Regel zum Umschreiben einen Teil eines Titels entfernen, z. B. einen Unternehmensnamen. Während eine Website durchsucht wird, werden getragene Titel in einem temporären Puffer gespeichert. Bevor diesem Puffer jedoch ein Titel hinzugefügt wird, werden die Titelregeln darauf angewendet. Standardmäßig enthält die Site-Suche/das Merchandising keine Crawl-Titelregeln und nimmt keine Änderungen am Titel vor.

Bevor die Auswirkungen der Regeln für Kunden sichtbar sind, erstellen Sie Ihren Site-Index neu.

Mit der Verlaufsfunktion können Sie Änderungen an Crawl Title Rules schnell wiederherstellen.

Regeln können aus zwei Hauptelementen bestehen: die RewriteRule und die optionale RewriteCond. Sie können eine unbegrenzte Anzahl von Regeln und Bedingungen angeben. Die Reihenfolge dieser Regeln ist wichtig, da der Regelsatz durch Regel durchlaufen wird. Wenn eine Regel übereinstimmt, durchläuft sie alle (optionalen) entsprechenden Umschreibungsbedingungen. Crawl-URL-Regeln werden wie folgt festgelegt:

```
RewriteCond  
<i>TestString CondPattern [Flags]</i> 
RewriteRule  
<i>Pattern Substitution [Flags]</i> 
 
RewriteCond  
<i>TestString CondPattern [Flags]</i> 
RewriteRule  
<i>Pattern Substitution [Flags]</i>
```

Wenn ein Titel gefunden wird, versucht der Suchroboter, den Titel dem Muster jeder Crawl-Regel zuzuordnen. Wenn das Muster übereinstimmt, sucht die Rewrite-Engine nach entsprechenden RewriteCond-Anweisungen. Wenn keine Bedingungen vorhanden sind, wird die URL durch einen neuen Wert ersetzt, der aus der Ersetzungszeichenfolge erstellt wurde, und fährt mit der nächsten Regel im Regelsatz fort. Wenn Bedingungen vorhanden sind, werden sie in der Reihenfolge verarbeitet, in der sie aufgelistet sind. Die rewrite-Engine versucht, ein Bedingungsmuster (CondPattern) mit einer Testzeichenfolge (TestString) abzugleichen. Wenn beide übereinstimmen, wird die nächste Bedingung verarbeitet, bis keine weiteren Bedingungen verfügbar sind. Wenn alle Bedingungen übereinstimmen, wird die URL durch die in der Regel angegebene Substitution ersetzt. Wenn die Bedingung nicht erfüllt ist, schlagen die vollständigen Bedingungen und die entsprechende Regel fehl.

Geben Sie die Crawl URL-Regeln in das Textfeld ein und klicken Sie dann auf Änderungen speichern. Leere Zeilen und Kommentarzeilen, die mit einem &quot;#&quot;(Hash) beginnen, sind zulässig. Um die Suchregeln zu testen, können Sie eine Test-URL in das Textfeld &quot;Test Rewrite Rules&quot;eingeben und dann auf Test klicken.

## RewriteRule-Direktive {#section_669445C505754E838E14029D6583D9B6}

Jede RewriteRule-Direktive definiert eine Rewrite-Regel. Regeln werden in der Reihenfolge angewendet, in der sie aufgeführt sind. Eine Regel zum Umschreiben nimmt die folgende Form an:

```
RewriteRule Pattern Substitution [Flags]
```

**Bei** Patterns kann es sich um einen POSIX-regulären Ausdruck handeln, der auf den aktuellen Titel angewendet wird. Der &quot;aktuelle Titel&quot;unterscheidet sich vom ursprünglichen Titel, da frühere Regeln bereits übereinstimmen und ihn geändert haben.

Siehe [Reguläre Ausdruck](../c-appendices/r-regular-expressions.md#reference_B5BA7D61D82E4109A01D2A2D964E3A6A).

Sie können das Zeichen &quot;not&quot;(&#39;!&#39;) verwenden. , um dem Muster ein Präfix zu geben. Mit dem Zeichen &quot;nicht&quot;können Sie ein Muster umkehren, d. h. nur dann wahr sein, wenn der aktuelle Titel NICHT mit dem Muster übereinstimmt. Das Zeichen &quot;nicht&quot;kann verwendet werden, wenn es besser ist, einem negativen Muster zu entsprechen, oder als endgültige Standardregel. Hinweis: Sie können nicht sowohl das Zeichen &quot;nicht&quot;als auch die gruppierten Platzhalter in einem Muster verwenden. Außerdem können Sie kein negatives Muster verwenden, wenn die Ersatzzeichenfolge $N enthält.

Sie können Klammern verwenden, um einen Rückverweis zu erstellen, auf den durch Substitution und CondPattern verwiesen werden kann.

**** SubstitutionDer Titel wird durch die Ersatzzeichenfolge ersetzt. Die Zeichenfolge kann Folgendes enthalten:

Text - Text, der unverändert übergeben wird.

Rückverweise bieten Zugriff auf die gruppierten Teile (in Klammern) des Musters oder des CondPatters. Es gibt zwei Typen von Rückverweisen:

* RewriteRule-Rückverweise

   Diese entsprechen Rückverweisen im entsprechenden RewriteRule-Muster und nehmen das Format $N (0 &lt;= N &lt;= 9) an. Beispiel, `RewriteRule ^My[[:blank:]] (.*)$ ${toupper: $1}`
* RewriteCond-Rückverweise

   Diese entsprechen Rückverweisen im letzten übereinstimmenden RewriteCond CondPattern und haben das Format %N (0 &lt;= N &lt;= 9).

Variablen Dies sind Variablen des Formulars %{NAME_OF_VARIABLE}, wobei NAME_OF_VARIABLE eine Zeichenfolge für den Namen einer definierten Variablen sein kann. Weitere Informationen zum Festlegen von Umgebung finden Sie unter `[E]`-Flag.

Funktionen Dies sind Funktionen des Formulars ${NAME_OF_FUNCTION: key}, wobei NAME_OF_FUNCTION:

* tolower macht alle Zeichen in Kleinbuchstaben *key*.
* toupper macht alle Zeichen in Großbuchstaben *key*.

>[!NOTE]
>
>Es gibt eine spezielle Ersatzzeichenfolge: &quot;-&quot; bedeutet &quot;KEINE Substitution&quot;. Die Zeichenfolge &quot;-&quot;ist oft mit dem Flag C (chain) nützlich, sodass Sie einen Titel mehreren Mustern zuordnen können, bevor eine Ersetzung erfolgt.

**Flags**  (optional)

Flags sind in Klammern `[]`und mehrere Flags sind kommagetrennt:

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Markierung </p> </th> 
   <th colname="col2" class="entry"> <p>Beschreibung </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> 'last|L' </p> </td> 
   <td colname="col2"> <p>Letzte Regel. </p> <p> Beendet den Umschreibvorgang und wendet keine weiteren Umschreibungsregeln an. Verwenden Sie dieses Flag, um eine weitere Verarbeitung des aktuellen Titels zu verhindern. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'next|N' </p> </td> 
   <td colname="col2"> <p>Nächste Runde. </p> <p> Führt den Umschreibvorgang (beginnend mit der ersten Umschreibungsregel) unter Verwendung des Titels der letzten Umschreibungsregel und nicht des ursprünglichen Titels aus. Pass auf, dass du keine Sackgasse machst! </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'chain|C' </p> </td> 
   <td colname="col2"> <p>Verkettet mit der nächsten Regel. </p> <p>Verkettet die aktuelle Regel mit der nächsten Regel (die auch mit der folgenden Regel verkettet werden kann usw.). Wenn eine Regel übereinstimmt, wird der Ersetzungsvorgang wie gewohnt fortgesetzt. Wenn die Regel nicht übereinstimmt, werden alle nachfolgenden verketteten Regeln übersprungen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'nocase|NC' </p> </td> 
   <td colname="col2"> <p>Kein Fall. </p> <p>Beim Muster wird nicht zwischen Groß- und Kleinschreibung unterschieden (d. h. es gibt keinen Unterschied zwischen "A-Z"und "a-z"), wenn das Muster mit dem aktuellen Titel übereinstimmt. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'skip|S=num' </p> </td> 
   <td colname="col2"> <p>Nächste Regel oder Regeln überspringen. </p> <p> Wenn die aktuelle Regel übereinstimmt, zwingt dieses Flag die Umschreibungs-Engine, die nächsten Num-Regeln im Regelsatz zu überspringen. Verwenden Sie dies, um pseudo if-then-else-Konstrukte zu erstellen. Die letzte Regel der then-Klausel wird zu einem skip=N, wobei N die Anzahl der Regeln in der else-Klausel ist. (Hinweis: Dies ist nicht dasselbe wie die "chain|C" Fahne!) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'env|E=VAR:VAL' </p> </td> 
   <td colname="col2"> <p>Legen Sie die Variable "Umgebung"fest. </p> <p> Erstellt eine Umgebungsvariable "VAR", die auf den Wert VAL eingestellt ist, wobei VAL reguläre Ausdruck-Rückverweise ($N und %N) enthalten kann, die erweitert werden. Sie können dieses Flag mehrmals verwenden, um mehrere Variablen festzulegen. Die Variablen können später in einem folgenden RewriteCond-Muster über %{VAR} referenziert werden. Verwenden Sie dieses Flag, um Informationen aus Titeln zu entfernen und zu speichern. </p> </td> 
  </tr> 
 </tbody> 
</table>

## RewriteCond-Richtlinie (optional) {#section_D664B71DE3884E0790531804C49A3222}

Die RewriteCond-Direktive definiert eine Regelbedingung. Wenn eine RewriteCond einer RewriteRule vorangeht, wird die Regel nur verwendet, wenn ihr Muster mit dem aktuellen Titel übereinstimmt und die zusätzlichen Bedingungen gelten.

Umschreiben von Bedingungsanweisungen haben die folgende Form:

```
RewriteCond TestString CondPattern [Flags] 
```

**** TestString ist eine Zeichenfolge, die die folgenden Konstrukte enthalten kann:

Text - Text, der unverändert übergeben wird.

Rückverweise bieten Zugriff auf die gruppierten Teile (in Klammern) des Musters oder des CondPatters. Es gibt zwei Arten von Rückverweisen:

* RewriteRule-Rückverweise Diese Übereinstimmungen entsprechen Rückverweisen im entsprechenden RewriteRule-Muster und verwenden das Formular $N (0 &lt;= N &lt;= 9). Beispiel, `RewriteRule ^My[[:blank:]] (.*)$ ${toupper: $1}`
* RewriteCond-Rückverweise Diese Übereinstimmungen entsprechen Rückverweisen im letzten übereinstimmenden RewriteCond CondPattern und nehmen die Form %N (0 &lt;= N &lt;= 9) an.

Variablen Dies sind Variablen des Formulars %{NAME_OF_VARIABLE}, wobei NAME_OF_VARIABLE eine Zeichenfolge für den Namen einer definierten Variablen sein kann. Weitere Informationen zum Festlegen von Umgebung finden Sie unter `[E]`-Flag.

Funktionen Dies sind Funktionen des Formulars ${NAME_OF_FUNCTION:key}, wobei NAME_OF_FUNCTION:

* tolower macht alle Zeichen in Kleinbuchstaben *key*.
* toupper macht alle Zeichen in Großbuchstaben *key*.
* escape-URL-kodiert alle Zeichen im Schlüssel.
* Die Zeichen &#39;a&#39;.z&#39;, &#39;A&#39;..&#39;Z&#39;, &#39;0&#39;..&#39;9&#39;, &#39;*&#39;, &#39;-&#39;, &#39;.&#39;, &#39;/&#39;, &#39;@&#39; und &#39;_&#39; bleiben unverändert, Leerzeichen werden in &#39;+&#39; übersetzt und alle anderen Zeichen werden in ihre %xx URL-kodierte Entsprechung umgewandelt.
* unescape wandelt &quot;+&quot;zurück in den Leerraum und alle %xx URL-kodierten Zeichen zurück in einzelne Zeichen.

**** CondPatternis ist ein standardmäßiger erweiterter regulärer Ausdruck mit einigen Ergänzungen. Der Musterzeichenfolge kann ein &#39;!&#39; vorangestellt werden -Zeichen (Ausrufezeichen), um ein nicht übereinstimmendes Muster anzugeben. Anstelle von echten Zeichenfolgen für reguläre Ausdrücke können Sie eine der folgenden Sondervarianten verwenden.

>[!NOTE]
>
>Sie können allen diesen Tests ein Ausrufezeichen (&#39;!&#39;) voranstellen. ihre Bedeutung zu negieren.

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>CondPattern-Zeichenfolge </p> </th> 
   <th colname="col2" class="entry"> <p>Beschreibung </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> '&lt;CondPattern' </p> </td> 
   <td colname="col2"> <p>Ist lexikalisch unbedeutend. </p> <p>Behandelt das <i>CondPattern</i> als einfache Zeichenfolge und vergleicht es wörtlich mit <i>TestString</i>. True, wenn <i>TestString</i> lexikalisch kleiner als <i>CondPattern</i> ist. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> '&gt;CondPattern' </p> </td> 
   <td colname="col2"> <p>Ist lexikalisch größer. </p> <p>Behandelt das <i>CondPattern</i> als einfache Zeichenfolge und vergleicht es wörtlich mit <i>TestString</i>. True, wenn <i>TestString</i> lexikalisch größer als <i>CondPattern</i> ist. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> '=CondPattern' </p> </td> 
   <td colname="col2"> <p> Ist lexikalisch gleich. </p> <p>Behandelt das <i>CondPattern</i> als einfache Zeichenfolge und vergleicht es wörtlich mit <i>TestString</i>. True, wenn <i>TestString</i> wörtlich <i>CondPattern</i> entspricht, d. h., die beiden Zeichenfolgen sind exakt gleich (Zeichen nach Zeichen). Wenn <i>CondPattern</i> nur "" (zwei Anführungszeichen) ist, wird <i>TestString</i> mit der leeren Zeichenfolge verglichen. </p> </td> 
  </tr> 
 </tbody> 
</table>

**Flags**  (optional)

Flags sind in Klammern `[]`und mehrere Flags sind kommagetrennt:

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Markierung </p> </th> 
   <th colname="col2" class="entry"> <p>Beschreibung </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> 'nocase|NC' </p> </td> 
   <td colname="col2"> <p>Kein Fall. </p> <p> Macht den Test nicht empfindlich. Das heißt, es gibt keinen Unterschied zwischen 'A-Z' und 'a-z' sowohl im erweiterten <i>TestString</i> als auch im <i>CondPattern.</i> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'ornext|OR' </p> </td> 
   <td colname="col2"> <p> Oder die nächste Bedingung. </p> <p>Verwenden Sie dieses Flag, um Regelbedingungen mit einem lokalen ODER anstelle des impliziten UND zu kombinieren. Ohne dieses Flag müssten Sie die Konstante/Regel mehrmals schreiben. </p> </td> 
  </tr> 
 </tbody> 
</table>

**Beispiel**

Angenommen, Sie haben eine Firmenwebsite mit einem standardmäßigen Titelformat: &quot;Meine Firma&quot;gefolgt von einem Bindestrich und einer seitenspezifischen Beschreibung (&quot;Meine Firma - Willkommen&quot;oder &quot;Meine Firma - Neuigkeiten&quot;). Sie möchten &quot;Meine Firma -&quot; aus dem Titel entfernen und den gesamten Titel in Großbuchstaben umwandeln, wenn er die Site indiziert.

Die folgende Regel zum Umschreiben verwendet den Funktionstoupper, um nur den beschreibenden Teil eines Titels in Großschreibung umzuschreiben:

```
RewriteRule  ^My[[:blank:]]Company[[:blank:]]-[[:blank:]] 
<b>(.*)</b>$  ${toupper: 
<b>$1</b>}
```

Das Regelmuster `(^My[[:blank:]]Company[[:blank:]]-[[:blank:]] (.*))` enthält einen Rückverweis `(.*)`, der dem Titelinhalt entspricht, der auf &quot;Meine Firma-&quot;folgt. Denken Sie daran, dass ein Teil eines Musters mit Klammern ( ) einen Rückverweis erstellt, auf den durch die Substitution verwiesen werden kann. In diesem Beispiel schreibt die Substitution (${toupper:**$1**}) diesen Rückverweis (**$1**) mithilfe der Toupper-Funktion erneut.

So wird der Titel des Formulars &quot;Meine Firma - Willkommen&quot; in &quot;WICOME&quot; umgeschrieben.

**Bestätigung**

Die rewrite Engine Software wurde ursprünglich von der Apache Group für die Verwendung im Apache HTTP Server Projekt (https://www.apache.org/) entwickelt.

## Hinzufügen von Crawl-Titelregeln {#task_272BB4C603BA4C9ABDBEEB398798B101}

Sie können Crawl-Titelregeln hinzufügen, um anzugeben, wie die gefundenen Titel im Webinhalt umgeschrieben werden, bevor sie im Suchindex gespeichert werden.

<!-- 

t_adding_crawl_title_rules.xml

 -->

**So fügen Sie Crawl-Titelregeln hinzu**

1. Klicken Sie im Produktmenü auf **[!UICONTROL Settings]** > **[!UICONTROL Rewrite Rules]** > **[!UICONTROL Crawl Title Rules]**.
1. Geben Sie im Feld [!DNL Crawl Title Rules] die gewünschten Regeln ein.

   Leere Zeilen und Kommentarzeilen, die mit einem &quot;#&quot;(Hash) beginnen, sind zulässig.
1. (Optional) Geben Sie auf der Seite [!DNL Crawl Title Rules] im Feld [!DNL Test Crawl Title Rules] eine Test-URL ein, deren Suchregeln Sie testen möchten, und klicken Sie dann auf **Test**.
1. Klicken Sie auf **Änderungen speichern**.
1. (Optional) Erstellen Sie Ihren Stage-Site-Index neu, wenn Sie die Vorschauen durchführen möchten.

   Siehe [Konfigurieren eines inkrementellen Indexes einer gestaffelten Website](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0).
1. (Optional) Führen Sie auf der Seite [!DNL Crawl Title Rules] einen der folgenden Schritte aus:

   * Klicken Sie auf **[!UICONTROL History]**, um alle vorgenommenen Änderungen wiederherzustellen.

      Siehe [Verwenden der Option Verlauf](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Klicken **[!UICONTROL Live]**.

      Siehe [Live-Einstellungen anzeigen](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Klicken **[!UICONTROL Push Live]**.

      Siehe [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Informationen zu URL-Regeln für die Suche {#concept_017EC95E68844B6C8CC9F874F0EC8D3C}

Mit den Such-URL-Regeln wird festgelegt, wie die URLs in den Suchergebnissen Ihrer Website angezeigt werden sollen. Die Regeln arbeiten mit vollständigen URLs. Jeder Teil der URL kann manipuliert werden, einschließlich Abfragen-Argumenten, bei denen Sitzungs-ID-Informationen häufig aufbewahrt werden.

<!-- 

c_about_search_url_rules.xml

 -->

In der Regel werden URL-Regeln für die Suche verwendet, um eine Sitzungs-ID in eine URL einzufügen. Sie können jedoch auch URL-Regeln für die Suche verwenden, um den Domänennamen zu ändern, der mit Ihren Ergebnissen angezeigt wird. Standardmäßig werden keine Regeln angegeben und es wird keine URL-Änderung durchgeführt.

Die Regeln der Such-URL können aus zwei Hauptelementen bestehen: die RewriteRule und die optionale RewriteCond. Wenn eine URL als Teil eines Suchergebnisses enthalten ist, werden die Regeln verwendet, um sie zu bearbeiten. Sie können eine unbegrenzte Anzahl von Regeln und Bedingungen für die Such-URL angeben. Die Reihenfolge dieser Regeln ist wichtig, da der Regelsatz in einer Schleife von Regel zu Regel ausgeführt wird. Wenn eine Regel übereinstimmt, durchläuft die Software alle (optionalen) entsprechenden Umschreibungsbedingungen. Crawl-URL-Regeln werden wie folgt festgelegt:

```
RewriteCond  
<i>TestString CondPattern [Flags]</i> 
RewriteRule  
<i>Pattern Substitution [Flags]</i> 
 
RewriteCond  
<i>TestString CondPattern [Flags]</i> 
RewriteRule  
<i>Pattern Substitution [Flags]</i>
```

Bei der Verarbeitung einer URL versucht Site-Suche/Merchandising, sie dem Muster jeder Suchregel zuzuordnen. Wenn die Übereinstimmung fehlschlägt, stoppt die Umschreibungs-Engine die Verarbeitung der Regel und fährt mit der nächsten Regel im Satz fort. Wenn das Muster übereinstimmt, sucht die Rewrite-Engine nach entsprechenden RewriteCond-Anweisungen. Wenn keine Bedingungen vorhanden sind, wird die URL durch einen neuen Wert ersetzt. Dieser Wert wird aus der Ersatzzeichenfolge erstellt und mit der nächsten Regel im Regelsatz fortgesetzt. Wenn Bedingungen vorhanden sind, wird in der Reihenfolge, in der sie aufgeführt sind, die Verarbeitung dieser Bedingungen beschrieben. Die rewrite-Engine versucht, ein Bedingungsmuster (CondPattern) mit einer Testzeichenfolge (TestString) abzugleichen. Wenn beide übereinstimmen, wird die nächste Bedingung verarbeitet, bis keine weiteren Bedingungen verfügbar sind. Wenn alle Bedingungen übereinstimmen, wird die URL durch die in der Regel angegebene Substitution ersetzt. Wenn die Bedingung nicht erfüllt ist, schlagen die vollständigen Bedingungen und die entsprechende Regel fehl.

## Info zur RewriteRule-Direktive {#section_A3473B5B90B74DA1970213113A90591E}

Eine Regel zum Umschreiben nimmt die folgende Form an:

```
RewriteRule  
<i>Pattern Substitution [Flags]</i>
```

**Bei** Patterns kann es sich um einen POSIX-regulären Ausdruck handeln, der auf die aktuelle URL angewendet wird. Die &quot;aktuelle URL&quot;kann von der ursprünglichen URL abweichen, da frühere Regeln möglicherweise bereits übereinstimmen und sie geändert haben.

Siehe [Reguläre Ausdruck](../c-appendices/r-regular-expressions.md#reference_B5BA7D61D82E4109A01D2A2D964E3A6A).

Sie können das Zeichen &quot;not&quot;(&#39;!&#39;) verwenden. , um dem Muster ein Präfix zu geben. Mit dem Zeichen &quot;nicht&quot;können Sie ein Muster umkehren. Das heißt, es ist nur wahr, wenn die aktuelle URL NICHT mit dem Muster übereinstimmt. Sie können das Zeichen &quot;nicht&quot;verwenden, wenn es besser ist, einem negativen Muster zu entsprechen, oder als endgültige Standardregel. Beachten Sie, dass Sie nicht sowohl das Zeichen &quot;nicht&quot;als auch die gruppierten Platzhalter in einem Muster verwenden können. Außerdem können Sie kein negatives Muster verwenden, wenn die Ersatzzeichenfolge $N enthält.

Sie können Klammern verwenden, um einen Rückverweis zu erstellen, auf den durch Substitution und CondPattern verwiesen werden kann.

**** SubstitutionDie URL wird vollständig durch die Ersatzzeichenfolge ersetzt, die Folgendes enthalten kann:

Text - Text, der unverändert übergeben wird.

Rückverweise Ermöglicht den Zugriff auf die gruppierten Teile (in Klammern) des Musters oder des CondPatters. Es gibt zwei Arten von Rückverweisen:

RewriteRule-Rückverweise Diese Übereinstimmungen entsprechen Rückverweisen im entsprechenden RewriteRule-Muster und verwenden das Formular $N (0 &lt;= N &lt;= 9). Beispiel, `RewriteRule ^My[[:blank:]] (.*)$ ${toupper: $1}`

RewriteCond-Rückverweise - Diese Übereinstimmungen entsprechen Rückverweisen im letzten übereinstimmenden RewriteCond-CondPattern und nehmen die Form %N (0 &lt;= N &lt;= 9) an.

Funktionen: Dies sind Funktionen des Formulars ${NAME_OF_FUNCTION:key}, wobei NAME_OF_FUNCTION:

* tolower macht alle Zeichen in Kleinbuchstaben *key*.
* toupper macht alle Zeichen in Großbuchstaben *key*.
* escape-URL-kodiert alle Zeichen in *key*.
* Die Zeichen &#39;a&#39;.z&#39;, &#39;A&#39;..&#39;Z&#39;, &#39;0&#39;..&#39;9&#39;, &#39;*&#39;, &#39;-&#39;, &#39;.&#39;, &#39;/&#39;, &#39;@&#39; und &#39;_&#39; bleiben unverändert. Leerzeichen werden in &quot;+&quot;übersetzt. alle anderen Zeichen werden in ihre %xx URL-kodierte Entsprechung transformiert.
* unescape wandelt &quot;+&quot;zurück in den Leerraum und alle %xx URL-kodierten Zeichen zurück in einzelne Zeichen.

>[!NOTE]
>
>Es gibt eine spezielle Ersatzzeichenfolge: &quot;-&quot; bedeutet &quot;KEINE Substitution&quot;. Die Zeichenfolge &#39;-&#39; ist oft in Verbindung mit dem Flag C (chain) nützlich. Damit können Sie eine URL mehreren Mustern zuordnen, bevor eine Ersetzung erfolgt.

**Flags**  (optional)

Flags sind in Klammern `[]`und mehrere Flags sind kommagetrennt:

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Markierung </p> </th> 
   <th colname="col2" class="entry"> <p>Beschreibung </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> 'last|L' </p> </td> 
   <td colname="col2"> <p>Letzte Regel. </p> <p> Beenden Sie den Umschreibungsprozess und wenden Sie keine zusätzlichen Umschreibungsregeln an. Verwenden Sie dieses Flag, um eine weitere Verarbeitung der aktuellen URL zu verhindern. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'next|N' </p> </td> 
   <td colname="col2"> <p> Nächste Runde. </p> <p>Führen Sie den Umschreibungsprozess (beginnend mit der ersten Umschreibungsregel) unter Verwendung der URL der letzten Umschreibungsregel (nicht der ursprünglichen URL) erneut aus. Achten Sie darauf, dass Sie keine Totschleife erzeugen! </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'chain|C' </p> </td> 
   <td colname="col2"> <p> Verkettet mit der nächsten Regel. </p> <p>Dieses Flag ketten die aktuelle Regel mit der nächsten Regel, die auch an die folgende Regel gekettet werden kann usw. Wenn eine Regel übereinstimmt, wird der Ersetzungsvorgang wie gewohnt fortgesetzt. Wenn die Regel nicht übereinstimmt, werden alle nachfolgenden verketteten Regeln übersprungen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'nocase|NC' </p> </td> 
   <td colname="col2"> <p>Kein Fall. </p> <p>Durch dieses Flag wird die Groß-/Kleinschreibung des Musters nicht berücksichtigt. Mit anderen Worten, es gibt keinen Unterschied zwischen "A-Z"und "a-z", wenn das Muster mit der aktuellen URL übereinstimmt. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'skip|S=num' </p> </td> 
   <td colname="col2"> <p>Nächste Regel oder Regeln überspringen. </p> <p> Wenn die aktuelle Regel übereinstimmt, zwingt dieses Flag die Umschreibungs-Engine, die nächsten Num-Regeln im Regelsatz zu überspringen. Verwenden Sie dies, um pseudo if-then-else-Konstrukte zu erstellen. Die letzte Regel der then-Klausel wird zu einem skip=N, wobei N die Anzahl der Regeln in der else-Klausel ist. (Hinweis: Dies ist nicht dasselbe wie die "chain|C" Fahne!) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'env|E=VAR:VAL' </p> </td> 
   <td colname="col2"> <p>Legen Sie Umgebungsvariable fest. </p> <p> Dieses Flag erstellt eine Umgebungsvariable "VAR", die auf den Wert VAL gesetzt ist. VAL kann reguläre Ausdruck-Rückverweise, $N und %N, enthalten, die erweitert werden. Sie können dieses Flag mehrmals verwenden, um mehrere Variablen festzulegen. Die Variablen können später in einem folgenden RewriteCond-Muster über %{VAR} dereferenziert werden. Verwenden Sie dieses Flag, um Informationen aus URLs zu entfernen und zu speichern. </p> </td> 
  </tr> 
 </tbody> 
</table>

Beachten Sie, dass die Regeln zum Umschreiben speichern und die Regeln zum Umschreiben abrufen Variablenwerte gemeinsam nutzen. Aus diesem Grund können Sie eine Variable auf einen zeitempfindlichen Sessionid-Wert setzen, wenn eine eingebettete URL gefunden und gespeichert wird. Wenn die nächste URL aus der Liste für temporäre Datenspeicherung abgerufen wird, kann der neueste Wert für sessionid hinzugefügt werden, bevor die Seite abgerufen wird.

**Beispiel**

Angenommen, Sie verfügen über einen Server, auf dem die Groß- und Kleinschreibung beachtet wird. Die Zeichenfolgen &quot;www.mydomain.com&quot;und &quot;www.MyDomain.com&quot;werden unterschiedlich verarbeitet. Damit Ihr Server ordnungsgemäß funktioniert, müssen Sie sicherstellen, dass die Domäne immer &quot;www.mydomain.com&quot;lautet, auch wenn einige Dokumente Links enthalten, die auf &quot;www.MyDomain.com&quot;verweisen. Dazu können Sie die folgende Regel verwenden:

```
RewriteRule  ^https:// 
<b>([^/]*)</b> 
<i>(.*)</i>$  https://${tolower:$1}$2 
```

Diese Regel zum Umschreiben verwendet die Funktion &quot;tolower&quot;, um den Domänenteil einer URL umzuschreiben, um sicherzustellen, dass er immer in Kleinbuchstaben lautet:

1. Das Muster `(^https://([^/]*)(.*)$)` enthält einen Rückverweis **`([^/]*)`**, der allen Zeichen zwischen &quot;https://&quot;und dem ersten &quot;/&quot;in der URL entspricht. Das Muster enthält auch einen zweiten Rückverweis **(.*)**, die mit allen verbleibenden Zeichen in der URL übereinstimmt.

1. Die Substitution `(https://${tolower:$1}$2)` weist die Suchmaschine an, die URL umzuschreiben, indem sie die Funktion **tolower** beim ersten Rückverweis `(https://**${tolower:$1**}$2)` verwendet, wobei der Rest der URL unberührt bleibt `(https://${tolower:$1}*$2*)`.

Daher wird eine URL des Formulars `https://www.MyDomain.com/INTRO/index.Html` in `https://www.mydomain.com/INTRO/index.Html` umgeschrieben

**RewriteCond-Richtlinie**  (optional)

Die RewriteCond-Direktive definiert eine Regelbedingung. Wenn eine RewriteCond einer RewriteRule vorangeht, wird die Regel nur verwendet, wenn ihr Muster mit dem aktuellen Titel übereinstimmt und die zusätzlichen Bedingungen gelten.

Umschreiben von Bedingungsanweisungen haben die folgende Form:

```
RewriteCond  
<i>TestString CondPattern [Flags]</i>
```

** TestString ist eine Zeichenfolge, die die folgenden Konstrukte enthalten kann:

Text: Text, der unverändert weitergegeben wird.

Rückverweise bieten Zugriff auf die gruppierten Teile (in Klammern) des Musters oder des CondPatters. Es gibt zwei Arten von Rückverweisen:

* ** RewriteRule-Rückverweise** Diese Übereinstimmungen entsprechen Rückverweisen im entsprechenden RewriteRule-Muster und verwenden das Formular $N (0 &lt;= N &lt;= 9). Beispiel, `RewriteRule ^My[[:blank:]] (.*)$ ${toupper: $1}`

* **RewriteCond-** RückverweiseDiese Übereinstimmungsrückverweise im zuletzt übereinstimmenden RewriteCond-CondPattern und in der Form %N (0  &lt;>

Variablen Dies sind Variablen des Formulars %{NAME_OF_VARIABLE}, wobei NAME_OF_VARIABLE eine Zeichenfolge für den Namen einer definierten Variablen sein kann. Weitere Informationen zum Festlegen von Variablen finden Sie im Flag RewriteRule *`[E]`*.

>[!NOTE]
>
>Umformulierungsregeln verwenden im Allgemeinen Variablen. Alle CGI-Parameter der aktuellen URL werden automatisch in Variablen umgewandelt. Beispielsweise stellt die Such-URL `"https://search.atomz.com/search/?sp_a=sp00000000&sp_q="Product"&session=1234&id=5678"` automatisch vier Variablen bereit, auf die in den Umformulierungsregeln verwiesen werden kann. In diesem Beispiel wird eine Variable als &quot;session&quot;und ihr Wert &quot;1234&quot;und eine andere Variable als &quot;id&quot;und ihr Wert &quot;5678&quot;bezeichnet. (Die anderen beiden Variablen sind `sp_a` und `sp_q`.) Sie sollten alle erforderlichen Variablen als ausgeblendete Felder aus dem Suchformular auf Ihrer Webseite übergeben. In diesem Beispiel sollten Sie die Werte &quot;session&quot;und &quot;id&quot;übergeben, die den Website-Benutzer identifizieren, der die Suche durchführt. Um ein unsichtbares Feld im Suchformular zu übergeben, verwenden Sie ein Tag wie `<input type=hidden name="session" value="1234">`.

Funktionen Dies sind Funktionen des Formulars ${NAME_OF_FUNCTION:key}, wobei NAME_OF_FUNCTION:

* tolower macht alle Zeichen in Kleinbuchstaben *key*.
* toupper macht alle Zeichen in Großbuchstaben *key*.
* escape-URL-kodiert alle Zeichen in *key*. Die Zeichen &#39;a&#39;.z&#39;, &#39;A&#39;..&#39;Z&#39;, &#39;0&#39;..&#39;9&#39;, &#39;*&#39;, &#39;-&#39;, &#39;.&#39;, &#39;/&#39;, &#39;@&#39; und &#39;_&#39; bleiben unverändert, Leerzeichen werden in &#39;+&#39; übersetzt und alle anderen Zeichen werden in ihre %xx URL-kodierte Entsprechung umgewandelt.
* unescape wandelt &quot;+&quot;zurück in den Leerraum und alle %xx URL-Kodierungszeichen zurück in einzelne Zeichen.

**** CondPatternis ist ein standardmäßiger erweiterter regulärer Ausdruck mit einigen Ergänzungen. Der Musterzeichenfolge kann ein &#39;!&#39; vorangestellt werden -Zeichen (Ausrufezeichen), um ein nicht übereinstimmendes Muster anzugeben. Anstelle von echten Zeichenfolgen für reguläre Ausdrücke können Sie eine der folgenden Sondervarianten verwenden.

Mit einem Ausrufezeichen (&#39;!&#39;) können Sie all diesen Tests ein Präfix voranstellen. ihre Bedeutung zu negieren.

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>CondPattern-Zeichenfolge </p> </th> 
   <th colname="col2" class="entry"> <p>Beschreibung </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> '&lt;CondPattern' </p> </td> 
   <td colname="col2"> <p>Ist lexikalisch unbedeutend. </p> <p> Behandelt das <i>CondPattern</i> als einfache Zeichenfolge und vergleicht es wörtlich mit <i>TestString</i>. True, wenn <i>TestString</i> lexikalisch kleiner als <i>CondPattern</i> ist. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> '&gt;CondPattern' </p> </td> 
   <td colname="col2"> <p>Ist lexikalisch größer. </p> <p> Behandelt das <i>CondPattern</i> als einfache Zeichenfolge und vergleicht es wörtlich mit <i>TestString</i>. True, wenn <i>TestString</i> lexikalisch größer als <i>CondPattern</i> ist. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> '=CondPattern' </p> </td> 
   <td colname="col2"> <p>Ist lexikalisch gleich. </p> <p> Behandelt das <i>CondPattern</i> als einfache Zeichenfolge und vergleicht es wörtlich mit <i>TestString</i>. True, wenn <i>TestString</i> wörtlich gleich <i>CondPattern</i> ist. Das heißt, die beiden Zeichenfolgen sind exakt gleich (Zeichen nach Zeichen). Wenn <i>CondPattern</i> nur "" (zwei Anführungszeichen) ist, wird <i>TestString</i> mit der leeren Zeichenfolge verglichen. </p> </td> 
  </tr> 
 </tbody> 
</table>

**Flags**  (optional)

Flags sind in Klammern `[]`und mehrere Flags sind kommagetrennt:

&#39;nocase|NC&#39; (kein Fall): Dadurch wird die Groß-/Kleinschreibung beim Test nicht berücksichtigt. Mit anderen Worten, es gibt keinen Unterschied zwischen &#39;A-Z&#39; und &#39;a-z&#39; sowohl im erweiterten *TestString* als auch im *CondPattern*.

&#39;ornext|OR&#39; (oder nächste Bedingung): Verwenden Sie dies, um Regelbedingungen mit einem lokalen ODER anstelle des impliziten UND zu kombinieren. Ohne dieses Flag müssten Sie die Regel mehrmals schreiben.

**Beispiel**

Einige Webseiten weisen eine CGI-Variable &quot;sessionid&quot;zu, wenn ein Kunde zum ersten Mal auf eine Site gelangt. Diese Variable wird zur Identifizierung des Kunden verwendet. Wenn der Kunde die Site durchsucht, wird die Variable weitergeleitet. Da der Suchroboter wie ein Kunde Ihrer Site aussieht, wird ihm eine &quot;sessionid&quot;-Nummer zugewiesen. Der Suchroboter behält diesen einzelnen &quot;sessionid&quot;-Wert bei, selbst wenn eine zweite Site versucht, einen neuen Wert zuzuweisen. Um dies sicherzustellen, benötigen Sie die folgende Regel zum Umschreiben:

```
RewriteCond  %{sessionid}  .+ 
RewriteRule  ^ 
<b>(.+)</b>sessionid=[^&#]+ 
<i>(.*)</i>$   
<b>$1</b>sessionid=%{sessionid} 
<i>$2</i>
```

Das RewriteRule-Muster enthält zwei Rückverweise: (.+) und (.*). Der erste Rückverweis stimmt mit allen Zeichen vor &quot;sessionid=&quot;überein. Der zweite Rückverweis findet alle Zeichen nach dem Beenden von &quot;&amp;&quot;oder &quot;#&quot;des Sitzungsteilnehmers.

Das Substitutionsmuster schreibt die URL mit dem ersten Rückverweis um, gefolgt von der Zeichenfolge &quot;sessionid=&quot;, gefolgt vom Wert der Sitzungs-ID-Variablen, die als CGI-Parameter in der URL übergeben wurde, gefolgt vom zweiten Rückverweis. `($1sessionid=%{sessionid}$2)`.

Die Variable **RewriteCond** untersucht die Variable sessionid `(%{sessionid})`. Wenn es mindestens ein Zeichen enthält (.+), dann stimmt RewriteRule überein.

Wenn die Suchergebniskennung `"https://search.atomz.com/search/?sp_a=sp99999999&sp_q=word&sessionid=5678"` lautet, werden alle Suchergebnis-URLs so umgeschrieben, dass der &quot;sessionid&quot;-Wert &quot;5678&quot;anstelle des &quot;sessionid&quot;-Werts ist, auf den der Suchroboter gestoßen ist, als er Ihre Site durchsucht und die Links gespeichert hat.

**Bestätigung**

Die rewrite Engine Software wurde ursprünglich von der Apache Group für die Verwendung im Apache HTTP Server Projekt (https://www.apache.org/) entwickelt.

## Hinzufügen von URL-Regeln für die Suche {#task_50C77D1B53804AEEB20896F74265BD6F}

Sie können URL-Regeln für die Suche hinzufügen, um anzugeben, wie die URLs in den Suchergebnissen Ihrer Website angezeigt werden. Die Regeln arbeiten mit vollständigen URLs. Sie können einen beliebigen Teil der URL bearbeiten, einschließlich Abfragen-Argumenten, bei denen Sitzungs-ID-Informationen häufig aufbewahrt werden.

<!-- 

t_adding_search_url_rules.xml

 -->

**So fügen Sie URL-Regeln zur Suche hinzu**

1. Klicken Sie im Produktmenü auf **[!UICONTROL Settings]** > **[!UICONTROL Rewrite Rules]** > **[!UICONTROL Search URL Rules]**.
1. Geben Sie im Feld [!DNL Search URL Rules] die gewünschten Regeln ein.

   Leere Zeilen und Kommentarzeilen, die mit einem &quot;#&quot;(Hash) beginnen, sind zulässig.
1. (Optional) Geben Sie auf der Seite [!DNL Search URL Rules] im Feld [!DNL Test Search URL Rules] eine Test-URL ein, deren Crawl-Regeln Sie testen möchten, und klicken Sie dann auf **Test**.
1. Klicken Sie auf **Änderungen speichern**.
1. (Optional) Erstellen Sie Ihren Stage-Site-Index neu, wenn Sie die Vorschauen durchführen möchten.

   Siehe [Konfigurieren eines inkrementellen Indexes einer gestaffelten Website](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0).
1. (Optional) Führen Sie auf der Seite [!DNL Search URL Rules] einen der folgenden Schritte aus:

   * Klicken Sie auf **[!UICONTROL History]**, um alle vorgenommenen Änderungen wiederherzustellen.

      Siehe [Verwenden der Option Verlauf](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Klicken **[!UICONTROL Live]**.

      Siehe [Live-Einstellungen anzeigen](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Klicken **[!UICONTROL Push Live]**.

      Siehe [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Informationen zu Suchtitelregeln {#concept_C72D20F8DFF64EDE809AF4B72797E858}

Suchtitelregeln geben an, wie Titel in den Suchergebnissen Ihrer Website angezeigt werden. Jeder Teil des Titels kann bearbeitet werden.

<!-- 

c_about_search_title_rules.xml

 -->

Eine Umschreibungsregel kann verwendet werden, um einen Teil eines Titels zu entfernen, z. B. einen Unternehmensnamen. Standardmäßig enthält die Site-Suche/das Merchandising keine Titelregeln und nimmt keine Änderungen am Titel vor.

Titelregeln können aus zwei Hauptelementen bestehen: RewriteRule und optional RewriteCond. Es kann eine unbegrenzte Anzahl von Regeln und Bedingungen festgelegt werden. Die Reihenfolge dieser Regeln ist wichtig, da der Regelsatz von Regel zu Regel durchlaufen wird. Wenn eine Regel übereinstimmt, durchläuft die Software alle (optionalen) entsprechenden Umschreibungsbedingungen. Suchtitelregeln werden wie folgt festgelegt:

```
RewriteCond  
<i>TestString CondPattern [Flags]</i> 
RewriteRule  
<i>Pattern Substitution [Flags]</i> 
 
RewriteCond  
<i>TestString CondPattern [Flags]</i> 
RewriteRule  
<i>Pattern Substitution [Flags]</i>
```

Wenn ein Titel gefunden wird, versucht Site-Suche/Merchandising, ihn dem Muster jeder Crawl-Regel zuzuordnen. Wenn das Muster übereinstimmt, sucht die Rewrite-Engine nach entsprechenden RewriteCond-Anweisungen. Wenn keine Bedingungen vorhanden sind, wird der Titel durch einen neuen Wert ersetzt, der aus der Ersetzungszeichenfolge erstellt wurde, und mit der nächsten Regel im Regelsatz fortgesetzt. Wenn Bedingungen vorhanden sind, werden sie in der Reihenfolge verarbeitet, in der sie aufgelistet sind. Die rewrite-Engine versucht, ein Bedingungsmuster (CondPattern) mit einer Testzeichenfolge (TestString) abzugleichen. Wenn beide übereinstimmen, wird die nächste Bedingung verarbeitet, bis keine weiteren Bedingungen verfügbar sind. Wenn alle Bedingungen übereinstimmen, wird die URL durch die in der Regel angegebene Substitution ersetzt. Wenn die Bedingung nicht erfüllt ist, schlagen die vollständigen Bedingungen und die entsprechende Regel fehl.

## RewriteRule-Direktive {#section_3BF2B0FF89F74A26AE79D68FA3184B9B}

Jede RewriteRule-Direktive definiert eine Rewrite-Regel. Regeln werden in der Reihenfolge angewendet, in der sie aufgeführt sind. Eine Regel zum Umschreiben nimmt die folgende Form an:

```
RewriteRule Pattern Substitution [Flags]
```

**** MusterEin POSIX-regulärer Ausdruck, der auf den aktuellen Titel angewendet wird. Der &quot;aktuelle Titel&quot;kann vom ursprünglichen Titel abweichen, da frühere Regeln möglicherweise bereits übereinstimmen und ihn geändert haben.

Siehe [Reguläre Ausdruck](../c-appendices/r-regular-expressions.md#reference_B5BA7D61D82E4109A01D2A2D964E3A6A).

Sie können das Zeichen &quot;not&quot;(&#39;!&#39;) verwenden. , um dem Muster ein Präfix zu geben. Mit dem Zeichen &quot;nicht&quot;können Sie ein Muster umkehren. Dies bedeutet, dass &quot;true&quot;nur dann gilt, wenn der aktuelle Titel NICHT mit dem Muster übereinstimmt. Das Zeichen &quot;nicht&quot;kann verwendet werden, wenn es besser ist, einem negativen Muster zu entsprechen, oder als endgültige Standardregel. Hinweis: Sie können nicht sowohl das Zeichen &quot;nicht&quot;als auch die gruppierten Platzhalter in einem Muster verwenden. Außerdem können Sie kein negatives Muster verwenden, wenn die Ersatzzeichenfolge $N enthält.

Sie können Klammern verwenden, um einen Rückverweis zu erstellen, auf den durch Substitution und CondPattern verwiesen werden kann.

**** SubstitutionDer Titel wird vollständig durch die Ersatzzeichenfolge ersetzt, die Folgendes enthalten kann:

Text - Text, der unverändert übergeben wird.

**** RückverweiseGewähren Sie Zugriff auf die gruppierten Teile (in Klammern) des Musters oder des CondPatters. Es gibt zwei Typen von Rückverweisen:

* **RewriteRule** BackreferencesDiese Match-Rückverweise im entsprechenden RewriteRule-Muster und verwenden das Formular $N (0)  &lt;> Beispiel, `RewriteRule ^My[[:blank:]] (.*)$ ${toupper: $1}`

* ** RewriteCond-Rückverweise** Diese Übereinstimmungsrückverweise im letzten übereinstimmenden RewriteCond-Muster und verwenden das Formular %N (0 &lt;= N &lt;= 9).

**** VariablenDies sind Variablen des Formulars %{NAME_OF_VARIABLE}, wobei NAME_OF_VARIABLE eine Zeichenfolge für den Namen einer definierten Variablen sein kann. Weitere Informationen zum Festlegen von Umgebung finden Sie unter [E]. Variablen können auch im Suchformular definiert werden, das die Suchergebnisse generiert hat.

**** FunktionenDies sind Funktionen des Formulars ${NAME_OF_FUNCTION: key}, wobei NAME_OF_FUNCTION:

* tolower macht alle Zeichen in Kleinbuchstaben *key*.
* toupper macht alle Zeichen in Großbuchstaben *key*.

Es gibt eine spezielle Ersatzzeichenfolge: &quot;-&quot; bedeutet &quot;KEINE Substitution&quot;. Die Zeichenfolge &quot;-&quot;ist häufig in Verbindung mit dem Flag C (chain) nützlich, sodass Sie einen Titel mehreren Mustern zuordnen können, bevor eine Ersetzung erfolgt.

**Flags**  (optional)

Flags sind in Klammern `[]` und mehrere Flags sind kommagetrennt:

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Markierung </p> </th> 
   <th colname="col2" class="entry"> <p>Beschreibung </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> 'last|L' </p> </td> 
   <td colname="col2"> <p> Letzte Regel. </p> <p> Beenden Sie den Umschreibungsprozess und wenden Sie keine zusätzlichen Umschreibungsregeln an. Verwenden Sie dieses Flag, um eine weitere Verarbeitung des aktuellen Titels zu verhindern. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'next|N' </p> </td> 
   <td colname="col2"> <p>Nächste Runde. </p> <p> Führen Sie den Umschreibvorgang erneut aus (beginnend mit der ersten Umschreibungsregel) und verwenden Sie dabei den Titel der letzten Umschreibungsregel (nicht den ursprünglichen Titel!). Pass auf, dass du keine Sackgasse machst! </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'chain|C' </p> </td> 
   <td colname="col2"> <p>Verkettet mit der nächsten Regel. </p> <p> Dieses Flag ketten die aktuelle Regel mit der nächsten Regel (die auch an die folgende Regel usw. gekettet werden kann). Wenn eine Regel übereinstimmt, wird der Ersetzungsvorgang wie gewohnt fortgesetzt. Wenn die Regel nicht übereinstimmt, werden alle nachfolgenden verketteten Regeln übersprungen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'nocase|NC' </p> </td> 
   <td colname="col2"> <p> Kein Fall. </p> <p> Durch dieses Flag wird die Groß-/Kleinschreibung des Musters nicht berücksichtigt. Das heißt, es gibt keinen Unterschied zwischen "A-Z"und "a-z", wenn das Muster mit dem aktuellen Titel übereinstimmt. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'skip|S=num' </p> </td> 
   <td colname="col2"> <p> Nächste Regel oder Regeln überspringen. </p> <p> Wenn die aktuelle Regel übereinstimmt, zwingt dieses Flag die Umschreibungs-Engine, die nächsten Num-Regeln im Regelsatz zu überspringen. Verwenden Sie dies, um pseudo if-then-else-Konstrukte zu erstellen. Die letzte Regel der then-Klausel wird zu einem skip=N, wobei N die Anzahl der Regeln in der else-Klausel ist. (Dies ist nicht dasselbe wie die "chain|C"-Fahne!) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'env|E=VAR:VAL' </p> </td> 
   <td colname="col2"> <p>Legen Sie die Variable "Umgebung"fest. </p> <p> Dieses Flag erstellt eine Umgebungsvariable "VAR", die auf den Wert VAL gesetzt wird, wobei VAL reguläre Ausdruck-Rückverweise, $N und %N, enthalten kann, die erweitert werden. Sie können dieses Flag mehrmals verwenden, um mehrere Variablen festzulegen. Die Variablen können später in einem folgenden RewriteCond-Muster über %{VAR} referenziert werden. Verwenden Sie dieses Flag, um Informationen aus Titeln zu entfernen und zu speichern. </p> </td> 
  </tr> 
 </tbody> 
</table>

## RewriteCond-Richtlinie (optional) {#section_9D72B2AB454849A7B681BC39C506AAA3}

Die RewriteCond-Direktive definiert eine Regelbedingung. Wenn eine RewriteCond einer RewriteRule vorangeht, wird die Regel nur verwendet, wenn ihr Muster mit dem aktuellen Titel übereinstimmt und die zusätzlichen Bedingungen gelten.

Umschreiben von Bedingungsanweisungen haben die folgende Form:

```
RewriteCond TestString CondPattern [Flags]
```

**** TestString ist eine Zeichenfolge, die die folgenden Konstrukte enthalten kann:

Text - Text, der unverändert übergeben wird.

Rückverweise bieten Zugriff auf die gruppierten Teile (in Klammern) des Musters oder des CondPatters. Es gibt zwei Arten von Rückverweisen:

* **RewriteRule** BackreferencesDiese Match-Rückverweise im entsprechenden RewriteRule-Muster und verwenden das Formular $N (0)  &lt;> Beispiel, `RewriteRule ^My[[:blank:]] (.*)$ ${toupper: $1}`

* **RewriteCond-** RückverweiseDiese Übereinstimmungsrückverweise im zuletzt übereinstimmenden RewriteCond-CondPattern und in der Form %N (0  &lt;>

**** VariablenDies sind Variablen des Formulars %{NAME_OF_VARIABLE}, wobei NAME_OF_VARIABLE eine Zeichenfolge für den Namen einer definierten Variablen sein kann. Weitere Informationen zum Festlegen von Umgebung finden Sie unter `[E]`-Flag. Variablen können auch im Suchformular definiert werden, das die Suchergebnisse generiert hat.

**** FunktionenDies sind Funktionen des Formulars ${NAME_OF_FUNCTION:key}, wobei NAME_OF_FUNCTION:

* tolower macht alle Zeichen in Kleinbuchstaben *key*.
* toupper macht alle Zeichen in Großbuchstaben *key*.
* escape-URL-kodiert alle Zeichen in *key*.
* Die Zeichen &#39;a&#39;.z&#39;, &#39;A&#39;..&#39;Z&#39;, &#39;0&#39;..&#39;9&#39;, &#39;*&#39;, &#39;-&#39;, &#39;.&#39;, &#39;/&#39;, &#39;@&#39; und &#39;_&#39; bleiben unverändert, Leerzeichen werden in &#39;+&#39; übersetzt und alle anderen Zeichen werden in ihre %xx URL-kodierte Entsprechung umgewandelt.
* unescape wandelt &quot;+&quot;zurück in den Leerraum und alle %xx URL-kodierten Zeichen zurück in einzelne Zeichen.

Es gibt eine spezielle Ersatzzeichenfolge: &quot;-&quot; bedeutet &quot;KEINE Substitution&quot;. Die Zeichenfolge &quot;-&quot;ist häufig in Verbindung mit dem Flag C (chain) nützlich, sodass Sie eine URL mehreren Mustern zuordnen können, bevor eine Ersetzung erfolgt.

**** CondPatternEin standardmäßiger erweiterter regulärer Ausdruck mit einigen Ergänzungen. Der Musterzeichenfolge kann ein &#39;!&#39; vorangestellt werden -Zeichen (Ausrufezeichen), um ein nicht übereinstimmendes Muster anzugeben. Anstelle von echten Zeichenfolgen für reguläre Ausdrücke können Sie eine der folgenden Sondervarianten verwenden.

Diesen Tests kann auch ein Ausrufezeichen (&#39;!&#39;) vorangestellt werden. ihre Bedeutung zu negieren.

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>CondPattern-Zeichenfolge </p> </th> 
   <th colname="col2" class="entry"> <p>Beschreibung </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> '&lt;CondPattern' </p> </td> 
   <td colname="col2"> <p>Ist lexikalisch unbedeutend. </p> <p> Behandelt das <i>CondPattern</i> als einfache Zeichenfolge und vergleicht es wörtlich mit <i>TestString</i>. True, wenn <i>TestString</i> lexikalisch kleiner als <i>CondPattern</i> ist. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> '&gt;CondPattern' </p> </td> 
   <td colname="col2"> <p> Ist lexikalisch größer. </p> <p> Behandelt das <i>CondPattern</i> als einfache Zeichenfolge und vergleicht es wörtlich mit <i>TestString</i>. True, wenn <i>TestString</i> lexikalisch größer als <i>CondPattern</i> ist. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> '=CondPattern' </p> </td> 
   <td colname="col2"> <p>Ist lexikalisch gleich. </p> <p> Behandelt das <i>CondPattern</i> als einfache Zeichenfolge und vergleicht es wörtlich mit <i>TestString</i>. True, wenn <i>TestString</i> wörtlich gleich <i>CondPattern</i> ist. Das heißt, die beiden Zeichenfolgen sind exakt gleich (Zeichen nach Zeichen). Wenn <i>CondPattern</i> nur "" (zwei Anführungszeichen) ist, wird <i>TestString</i> mit der leeren Zeichenfolge verglichen. </p> </td> 
  </tr> 
 </tbody> 
</table>

**Flags**  (optional)

Flags sind in Klammern`[]` eingeschlossen und mehrere Flags sind kommagetrennt:

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Markierung </p> </th> 
   <th colname="col2" class="entry"> <p>Beschreibung </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> 'nocase|NC' (kein Fall) </p> </td> 
   <td colname="col2"> <p>Macht den Test nicht empfindlich. Das heißt, es gibt keinen Unterschied zwischen 'A-Z' und 'a-z' sowohl im erweiterten <i>TestString</i> als auch im <i>CondPattern</i>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'ornext|OR' (oder nächste Bedingung) </p> </td> 
   <td colname="col2"> <p> Verwenden Sie dies, um Regelbedingungen mit einem lokalen ODER anstelle des impliziten UND zu kombinieren. Ohne dieses Flag müssten Sie die Regel mehrmals schreiben. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Beispiel {#section_E7454FFE169E459AABD9D033651939CB}

Angenommen, Sie haben eine Firmenwebsite mit einem standardmäßigen Titelformat: &quot;Meine Firma&quot;gefolgt von einem Bindestrich und einer seitenspezifischen Beschreibung (&quot;Meine Firma - Willkommen&quot;oder &quot;Meine Firma - Neuigkeiten&quot;). Sie möchten &quot;Meine Firma -&quot; aus dem Titel entfernen und den gesamten Titel in Großbuchstaben umwandeln, wenn er die Site indiziert.

Die folgende Regel zum Umschreiben verwendet den Funktionstoupper, um nur den beschreibenden Teil eines Titels in Großschreibung umzuschreiben:

```
RewriteRule  ^My[[:blank:]]Company[[:blank:]]-[[:blank:]] 
<b>(.*)</b>$  ${toupper: 
<b>$1</b>} 
```

Das Regelmuster `(^My[[:blank:]]Company[[:blank:]]-[[:blank:]] (.*))` enthält einen Rückverweis **`(.*)`**, der dem Titelinhalt entspricht, der auf &quot;Meine Firma-&quot;folgt. Denken Sie daran, dass ein Teil eines Musters mit Klammern ( ) einen Rückverweis erstellt, auf den durch die Substitution verwiesen werden kann. In diesem Beispiel schreibt die Substitution (${toupper:**$1**}) diesen Rückverweis (**$1**) mithilfe der Toupper-Funktion erneut.

So wird der Titel des Formulars &quot;Meine Firma - Willkommen&quot; in &quot;WICOME&quot; umgeschrieben.

**Bestätigung**

Die rewrite Engine Software wurde ursprünglich von der Apache Group für die Verwendung im Apache HTTP Server Projekt (https://www.apache.org/) entwickelt.

## Hinzufügen von Suchtitelregeln {#task_155CECB74BE3444384EDBBD04F41515E}

Sie können Suchtitelregeln hinzufügen, um anzugeben, wie Titel in den Suchergebnissen Ihrer Website angezeigt werden. Sie können einen beliebigen Teil des Titels bearbeiten.

<!-- 

t_adding_search_title_rules.xml

 -->

**So fügen Sie Suchtitelregeln hinzu**

1. Klicken Sie im Produktmenü auf **[!UICONTROL Settings]** > **[!UICONTROL Rewrite Rules]** > **[!UICONTROL Search Title Rules]**.
1. Geben Sie im Feld [!DNL Search Title Rules] die gewünschten Regeln ein.

   Leere Zeilen und Kommentarzeilen, die mit einem &quot;#&quot;(Hash) beginnen, sind zulässig.
1. (Optional) Geben Sie auf der Seite [!DNL Search Title Rules] im Feld [!DNL Test Search Title Rules] einen Testtitel ein und klicken Sie dann auf **Test**.
1. Klicken Sie auf **Änderungen speichern**.
1. (Optional) Erstellen Sie Ihren Stage-Site-Index neu, wenn Sie die Vorschauen durchführen möchten.

   Siehe [Konfigurieren eines inkrementellen Indexes einer gestaffelten Website](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0).
1. (Optional) Führen Sie auf der Seite [!DNL Search Title Rules] einen der folgenden Schritte aus:

   * Klicken Sie auf **[!UICONTROL History]**, um alle vorgenommenen Änderungen wiederherzustellen.

      Siehe [Verwenden der Option Verlauf](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Klicken **[!UICONTROL Live]**.

      Siehe [Live-Einstellungen anzeigen](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Klicken **[!UICONTROL Push Live]**.

      Siehe [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

