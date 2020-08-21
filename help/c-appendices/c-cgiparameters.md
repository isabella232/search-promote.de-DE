---
description: 'null '
seo-description: 'null '
seo-title: CGI-Parameter
solution: Target
title: CGI-Parameter
topic: Appendices,Site search and merchandising
uuid: a5f43547-bc15-44aa-ba23-6b8b573e09d2
translation-type: tm+mt
source-git-commit: 7b883870bb16284d8070a21547cdb62cc79d7632
workflow-type: tm+mt
source-wordcount: '5490'
ht-degree: 1%

---


# CGI-Parameter{#cgi-parameters}

## CGI-Parameter {#concept_F395999090FE4926B38BC73D5E612800}

## CGI-Parameter suchen {#reference_DA27A8B0728246DA94994885E1353890}

Es wird Suchformularcode bereitgestellt, den Sie kopieren und in den HTML-Code Ihrer Site einfügen können ( **[!UICONTROL Design]** > **[!UICONTROL Auto-Complete]** > **[!UICONTROL Form Source]**).

Siehe [Kopieren des HTML-Codes des Suchformulars in die...](../c-about-auto-complete.md#task_A3A01EA800F24C0AA33902387E0362C7).

Sie können auch die Parameter festlegen, die entweder im Suchformular selbst oder über ein Skript aufgeführt werden. Zusätzlich zu den unten aufgeführten Parametern können Sie auch die Backend-Suchparameter verwenden, um die Suche zu steuern.

Siehe CGI-Parameter für die [Backend-Suche](../c-appendices/c-cgiparameters.md#reference_582E85C3886740C98FE88CA9DF7918E8).

Suchanforderungen bestehen aus einer Basis-URL. Die Basis-URL gibt an, nach welchem Konto der Kunde sucht, und eine Reihe von CGI-Parametern (Schlüssel-Wert-Paare), die angeben, wie die gewünschten Suchergebnisse für das zugehörige Konto zurückgegeben werden.

Die Basis-URL ist mit einem bestimmten Konto und einer gestaffelten oder Live-Umgebung verknüpft. Sie können mehrere Aliase für die Basis-URL von Ihrem Kundenbetreuer anfordern. Beispielsweise kann eine Firma namens Megacorp zwei Basis-URLs mit ihrem Konto verknüpft sein: `https://search.megacorp.com` und `https://stage.megacorp.com`. Die erste URL durchsucht ihren Liveindex und die zweite URL sucht ihren gestaffelten Index.

Es werden drei Formate von CGI-Parametern unterstützt. Standardmäßig ist Ihr Konto so konfiguriert, dass CGI-Parameter wie im folgenden Beispiel mit einem Semikolon getrennt werden:

`https://search.megacorp.com?q=shoes;page=2`

Wenn Sie es vorziehen, können Sie Ihren Kundenbetreuer dazu veranlassen, Ihr Konto so zu konfigurieren, dass zur Trennung der CGI-Parameter ein kaufmännisches kaufmännisches kaufmännisches Und verwendet wird, wie im folgenden Beispiel:

`https://search.megacorp.com?q=shoes&page=2`

Ein drittes Format, das so genannte SEO-Format, wird ebenfalls unterstützt, wenn anstelle des Trennzeichens und Gleichheitszeichens ein Schrägstrich verwendet `/` wird, wie im folgenden Beispiel dargestellt:

`https://search.megacorp.com/q/shoes/page/2`

Jedes Mal, wenn das SEO-Format zum Senden einer Anforderung verwendet wird, werden alle Ausgabelinks im gleichen Format zurückgegeben.

| Parameter für die geführte Suche | Beispiel | Beschreibung |
|--- |--- |--- |
| q | `q=string` | Gibt die Abfrage-Zeichenfolge für die Suche an. Dieser Parameter wird dem `sp_q` Backend-Suchparameter zugeordnet.  Siehe CGI-Parameter für die [Backend-Suche](../c-appendices/c-cgiparameters.md#reference_582E85C3886740C98FE88CA9DF7918E8). |
| q# | `q#=string` | Facting (Suche innerhalb eines bestimmten Felds) erfolgt über nummerierte q- und x-Parameter.  Der Parameter q definiert den Begriff, nach dem Sie in der Facette suchen, wie er durch den entsprechenden Parameter &quot;x&quot;gekennzeichnet ist.<br>Wenn Sie z. B. zwei Facetten haben, die Größe und Farbe heißen, können Sie z. B. q1=small;x1=size;q2=red;x2=color haben.  Dieser Parameter wird den `sp_q_exact_#` Backend-Suchparametern zugeordnet.  <br>Siehe CGI-Parameter für die [Backend-Suche](../c-appendices/c-cgiparameters.md#reference_582E85C3886740C98FE88CA9DF7918E8). |
| x nicht unterstützt# | `q#=string` | Facting (Suche innerhalb eines bestimmten Felds) erfolgt über nummerierte q- und x-Parameter.  Der Parameter q definiert den Begriff, nach dem Sie in der Facette suchen, wie er durch den entsprechenden Parameter &quot;x&quot;gekennzeichnet ist. <br>Wenn Sie z. B. zwei Facetten haben, die Größe und Farbe heißen, können Sie z. B. q1=small;x1=size;q2=red;x2=color haben.  Dieser Parameter wird den `sp_x_#` Backend-Suchparametern zugeordnet.  <br>Siehe CGI-Parameter für die [Backend-Suche](../c-appendices/c-cgiparameters.md#reference_582E85C3886740C98FE88CA9DF7918E8). |
| Erfassung | `collection=string` | Gibt die für die Suche zu verwendende Sammlung an.  Dieser Parameter wird dem `sp_k` Backend-Suchparameter zugeordnet.  Siehe CGI-Parameter für die [Backend-Suche](../c-appendices/c-cgiparameters.md#reference_582E85C3886740C98FE88CA9DF7918E8). |
| count | `count=number` | Gibt die Gesamtanzahl der angezeigten Ergebnisse an.  Die Standardeinstellung ist unter [!UICONTROL Settings ] > [!UICONTROL Searching ] > [!UICONTROL Searches ]. .  Dieser Parameter wird dem `sp_c` Backend-Suchparameter zugeordnet.  Siehe CGI-Parameter für die [Backend-Suche](../c-appendices/c-cgiparameters.md#reference_582E85C3886740C98FE88CA9DF7918E8). |
| Seite | `page=number` | Gibt die Seite der zurückgegebenen Ergebnisse an. |
| rank | `rank=field` | Gibt das Rankenfeld an, das für das statische Rang verwendet werden soll.  Das Feld muss ein Feld vom Typ Rang mit einer Relevanz größer als 0 sein.  Dieser Parameter wird dem `sp_sr` Backend-Parameter zugeordnet.  Siehe CGI-Parameter für die [Backend-Suche](../c-appendices/c-cgiparameters.md#reference_582E85C3886740C98FE88CA9DF7918E8). |
| sortieren | `sort=number` | Gibt die Sortierreihenfolge an.<br>&quot;0&quot;ist der Standardwert und wird nach Relevanzwert sortiert; &quot;1&quot; sortiert nach Datum; &quot;-1&quot;wird nicht sortiert.  Benutzer können einen Feldnamen für den Wert des `sp_s` Parameters angeben.  So werden die Ergebnisse `sp_s=title` nach den Werten sortiert, die im Titelfeld enthalten sind. Wenn ein Feldname für den Wert eines ` sp_s ` Parameters verwendet wird, werden die Ergebnisse nach diesem Feld sortiert und dann nach Relevanz untergeordnet.  To enable this feature, click [!UICONTROL Settings ] > [!UICONTROL Metadata ] > [!UICONTROL Definitions ]. Klicken Sie auf der Seite &quot;Definitionen&quot;auf [!UICONTROL Add New Field ] oder klicken Sie auf [!UICONTROL Edit ] , um einen bestimmten Feldnamen anzuzeigen. Wählen Sie in der [!UICONTROL Sorting ] Dropdown-Liste entweder [!UICONTROL Ascending ] oder [!UICONTROL Descending ]. Dieser Parameter wird dem `sp_s` Backend-Suchparameter zugeordnet. <br>Siehe CGI-Parameter für die [Backend-Suche].(../c-appendices/c-cgiparameters.md#reference_582E85C3886740C98FE88CA9DF7918E8). |

## CGI-Parameter für die Backend-Suche {#reference_582E85C3886740C98FE88CA9DF7918E8}

In der Regel interagieren Kunden mit einer Präsentationsebene namens &quot;Geführte Suche&quot;. Theoretisch ist es jedoch möglich, die Ebene der geführten Suche zu überspringen und mit der Backend-Core-Suche direkt mit den auf dieser Seite beschriebenen CGI-Parametern zu interagieren.

Sie können CGI-Parameter für die Backend-Suche in der folgenden Tabelle auswählen:
<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> </th> 
   <th colname="col2" class="entry"> <p>Unterstützung für einzelne Abfragen </p> </th> 
   <th colname="col03" class="entry"> <p>Unterstützung mehrerer Abfragen </p> </th> 
   <th colname="col3" class="entry"> <p>Beispiele </p> </th> 
   <th colname="col4" class="entry"> <p>Beschreibung </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>1 </p> </td> 
   <td colname="col2"> <p>sp_a </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_a= string </span> </p> </td> 
   <td colname="col4"> <p>Gibt die Kontonummer-Zeichenfolge an. Dieser Parameter ist erforderlich und muss eine gültige Kontonummer-Zeichenfolge sein. Sie finden Ihre Kontonummer unter <span class="uicontrol"> Einstellungen </span> &gt; <span class="uicontrol"> Kontooptionen </span> &gt; <span class="uicontrol"> Kontoeinstellungen </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>2 </p> </td> 
   <td colname="col2"> <p>sp_advanced </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_advanced= 0 oder 1 </span> </p> </td> 
   <td colname="col4"> <p>Wenn <span class="codeph"> sp_advanced=1 mit einer Abfrage gesendet </span> wird, wird der gesamte Code zwischen dem <span class="codeph"> &lt;search-if-advanced&gt; </span> -Tag und dem <span class="codeph"> &lt;/search-if-advanced&gt;- </span> Tag in der Suchvorlage für das Suchformular verwendet. Der gesamte Code zwischen dem Tag <span class="codeph"> &lt;search-if-not-advanced&gt; </span> und dem Tag <span class="codeph"> &lt;/search-if-not-advanced&gt; </span> wird ignoriert. Wenn <span class="codeph"> sp_advanced=0 </span> (oder ein anderer Wert) gesendet wird, wird der Vorlagenblock &lt;search-if-advanced&gt; ignoriert und der Vorlagenblock &lt;search-if-not-advanced&gt; verwendet. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>3 </p> </td> 
   <td colname="col2"> <p>sp_c </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_c= number </span> </p> </td> 
   <td colname="col4"> <p>Gibt die Gesamtanzahl der anzuzeigenden Ergebnisse an. Die Standardeinstellung ist „10“. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>4 </p> </td> 
   <td colname="col2"> <p>sp_context_field </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <code> sp_context_field= <i>field</i> </code> </p> </td> 
   <td colname="col4"> <p>Erfasst Kontextinformationen für das angegebene Feld. Die gesammelten Informationen werden in den Suchergebnissen über das Vorlagen-Tag <span class="codeph"> &lt;search-context&gt; </span> ausgegeben. Die Standardeinstellung ist <span class="codeph">body </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>5 </p> </td> 
   <td colname="col2"> <p>sp_d </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_d= type </span> </p> </td> 
   <td colname="col4"> <p>Gibt den Typ der zu durchsuchenden Datumsbereiche an. Mögliche Werte für den Typ sind vorhanden, d. h. keine Suche nach Datumsbereichen, benutzerspezifisch, was bedeutet, dass der Wert von <span class="codeph"> sp_date_range verwendet werden </span> sollte, um die zu suchenden Daten zu bestimmen, und spezifisch, was bedeutet, dass die Werte in <span class="codeph"> sp_Beginn_day </span>, <span class="codeph"> sp_Beginn_month </span>, <span class="codeph"> sp_Beginn_year </span>, <span class="codeph"> sp_end_day </span><span class="codeph"> </span><span class="codeph"> </span> ,_end_month undsp_end_end_end_end_end_end_end_end_end_end_end Jahr wird zur Bestimmung des zu suchenden Datumsbereichs verwendet. <span class="codeph"> sp_d </span> ist nur erforderlich, wenn Ihr Suchformular die Option enthält, entweder nach einem benutzerdefinierten Bereich (über <span class="codeph"> sp_date_range </span>) oder nach einem bestimmten Beginn- und Enddatumsbereich zu suchen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>6 </p> </td> 
   <td colname="col2"> <p> </p> </td> 
   <td colname="col03"> <p> sp_d_# </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_d_#= type </span> </p> </td> 
   <td colname="col4"> <p>Gibt den Typ der Datumsbereichssuche für die entsprechende <span class="codeph"> sp_q_#- </span> Abfrage an. Das "#"wird durch eine Zahl zwischen 1 und 16 ersetzt (z. B. <span class="codeph"> sp_d_8 </span>, gilt für die nummerierte Abfrage <span class="codeph"> sp_q_8 </span>). </p> <p>Sie können <span class="codeph"> type auf any einstellen, d. h. nicht nach Datumsbereichen suchen, benutzerspezifisch. Dies bedeutet, dass der Wert von </span> sp_date_range_# verwendet <span class="codeph"> wird, um die zu suchenden Daten zu bestimmen, und spezifisch, was bedeutet, dass die Werte in </span> sp_q_min_day_#, <span class="codeph"> sp_q_min_month_# </span>, <span class="codeph"> </span><span class="codeph"> </span><span class="codeph"> </span><span class="codeph"> </span><span class="codeph"> </span> sp_q_year_#, s_q_max_day__q_max_month_# und sp_q_year_# sollten zur Bestimmung des Datumsbereichs verwendet werden. Die Verwendung von <span class="codeph"> sp_d_# </span> ist nur erforderlich, wenn Ihr Suchformular die Option enthält, entweder nach einem benutzerdefinierten Bereich (über <span class="codeph"> </span>sp_date_range_#) oder nach einem bestimmten Beginn- und Enddatumsbereich zu suchen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>7 </p> </td> 
   <td colname="col2"> <p>sp_date_range </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <code> sp_date_range= <i>number</i> </code> </p> </td> 
   <td colname="col4"> <p>Gibt einen vordefinierten Datumsbereich an, der auf die Suche angewendet werden soll. Werte größer gleich null geben die Anzahl der Tage an, die vor dem heutigen Tag gesucht werden sollen — — Beispielsweise gibt der Wert "0"den Wert "today"an, der Wert "1"den Wert "today"und "gestern", der Wert "30"den Wert "within the last 30 days"usw. </p> <p>Werte unter null geben einen benutzerdefinierten Bereich wie folgt an: </p> <p>-1 = "Keine", genau wie bei Angabe eines Datumsbereichs. </p> <p>-2 = "Diese Woche", die von Sonntag bis Samstag der aktuellen Woche durchsucht. </p> <p>-3 = "Letzte Woche", die von Sonntag bis Samstag der Woche vor der aktuellen Woche durchsucht wird. </p> <p>-4 = "Dieser Monat", der Daten innerhalb des aktuellen Monats durchsucht. </p> <p>-5 = "Letzter Monat", der Daten innerhalb des Monats vor dem aktuellen Monat durchsucht. </p> <p>-6 = "Dieses Jahr", das Daten innerhalb des aktuellen Jahres durchsucht. </p> <p>-7 = "Letztes Jahr", das Daten innerhalb des Jahres vor dem aktuellen Jahr durchsucht. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>8 </p> </td> 
   <td colname="col2"> <p> </p> </td> 
   <td colname="col03"> <p>sp_date_range_# </p> </td> 
   <td colname="col3"> <p> <code> sp_date_range_#= <i>number</i> </code> </p> </td> 
   <td colname="col4"> <p>Gibt einen vordefinierten Datumsbereich an, der auf die entsprechende <span class="codeph"> sp_q_#- </span> Abfrage angewendet werden soll. Das "#"wird durch eine Zahl zwischen 1 und 16 ersetzt (z. B. <span class="codeph"> sp_date_range_8 </span>, gilt für die nummerierte Abfrage <span class="codeph"> sp_q_8 </span>). </p> <p>Werte größer als oder gleich null geben die Anzahl der Tage an, die vor dem heutigen Tag gesucht werden sollen. Beispielsweise gibt der Wert 0 heute an; Der Wert 1 gibt heute und gestern an. Der Wert 30 gibt innerhalb der letzten 30 Tage usw. an. </p> <p>Werte unter null geben einen benutzerdefinierten Bereich wie folgt an: </p> <p>-1 = "Keine", genau wie bei Angabe eines Datumsbereichs. </p> <p>-2 = "Diese Woche", die von Sonntag bis Samstag der aktuellen Woche durchsucht. </p> <p>-3 = "Letzte Woche", die von Sonntag bis Samstag der Woche vor der aktuellen Woche durchsucht wird. </p> <p>-4 = "Dieser Monat", der Daten innerhalb des aktuellen Monats durchsucht. </p> <p>-5 = "Letzter Monat", der Daten innerhalb des Monats vor dem aktuellen Monat durchsucht. </p> <p>-6 = "Dieses Jahr", das Daten innerhalb des aktuellen Jahres durchsucht. </p> <p>-7 = "Letztes Jahr", das Daten innerhalb des Jahres vor dem aktuellen Jahr durchsucht. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>9 </p> </td> 
   <td colname="col2"> <p>sp_dedupe_field </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <code> sp_dedupe_field= <i>fieldname</i> </code> </p> </td> 
   <td colname="col4"> <p>Gibt ein einzelnes Feld an, in dem die Suchergebnisse dedupliziert werden sollen. Alle Duplikat-Ergebnisse in diesem Feld werden aus den Suchergebnissen entfernt. Beispiel: Wenn für <span class="codeph"> sp_dedupe_field=title </span>nur das oberste Ergebnis für einen bestimmten Titel in den Suchergebnissen angezeigt wird (keine zwei Ergebnisse haben identischen Titelfeldinhalt). Bei Feldern mit mehreren Werten (Zulassungsliste) wird der gesamte Feldinhalt zum Vergleich verwendet. Es kann nur ein Feld angegeben werden. Ein "table-qualifier"ist im Feldnamen nicht zulässig. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>10 </p> </td> 
   <td colname="col2"> <p>sp_e </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_e= number </span> </p> </td> 
   <td colname="col4"> <p>Gibt an, dass für alle Wörter aus der Abfrage-Zeichenfolge mit mehr als Zeichen eine automatische Platzhaltererweiterung erfolgen soll. Mit anderen Worten, <span class="codeph"> sp_e=5 </span> legt fest, dass Wörter mit 5 oder mehr Zeichen, wie "Abfrage"oder "Nummer", mit dem Platzhalterzeichen "*"erweitert werden sollten, wodurch die Suche einer Suche nach "Abfrage*"oder "Nummer*"entspricht. Wörter mit weniger Zeichen werden nicht erweitert, sodass eine Suche nach "Wort"keine automatische Platzhaltererweiterung hätte. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>11 </p> </td> 
   <td colname="col2"> <p> </p> </td> 
   <td colname="col03"> <p> sp_e_# </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_e_#= number </span> </p> </td> 
   <td colname="col4"> <p>Gibt an, dass die automatische Platzhaltererweiterung für alle Wörter aus der entsprechenden Zeichenfolge <span class="codeph"> sp_q_# </span> Abfrage mit mehr als Zeichen erfolgt. Mit anderen Worten, <span class="codeph"> sp_e_2=5 </span> gibt an, dass Wörter mit fünf oder mehr Zeichen in der <span class="codeph"> Zeichenfolge </span> sp_q_2, wie "Abfrage"oder "Nummer", mit dem Platzhalterzeichen ' <span class="codeph"> * </span>' erweitert werden sollten, sodass die Suche einer Suche nach "Abfrage*"oder "Nummer*"entspricht. Wörter mit weniger Zeichen werden nicht erweitert, sodass eine Suche nach "Wort"in <span class="codeph"> sp_q_2 keine automatische Platzhaltererweiterung </span> hätte. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>12 </p> </td> 
   <td colname="col2"> <p>sp_end_day, sp_end_month, sp_end_year </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <code> sp_end_day= <i>number</i>,sp_end_month= <i>number</i>, sp_end_year= <i>number</i> </code> </p> </td> 
   <td colname="col4"> <p>Dieses Wertetriplet gibt den Enddatumsbereich für die Suche an und muss als Satz angegeben werden. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>13 </p> </td> 
   <td colname="col2"> <p>sp_f </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_f= string </span> </p> </td> 
   <td colname="col4"> <p>Gibt den Zeichensatz der Parameterzeichenfolgen der Abfrage an (z. B. <span class="codeph"> sp_q </span>). Diese Zeichenfolge muss immer mit dem Zeichensatz der Seite übereinstimmen, die das Suchformular enthält. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>14 </p> </td> 
   <td colname="col2"> <p>sp_field_table </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <code> sp_field_ table=table: field,field... </code> </p> </td> 
   <td colname="col4"> <p>Definiert eine logische Datentabelle, die aus den angegebenen Feldern besteht. Beispielsweise würde eine Tabelle mit dem Namen "items"aus den Feldern "color", "size"und "price"wie folgt definiert: </p> <p> <span class="codeph"> sp_field_table=items:color,size,price </span> </p> <p>Logische Tabellen sind besonders hilfreich in Verbindung mit Feldern, in denen "Zulassungslisten"aktiviert ist (unter <span class="uicontrol"> "Einstellungen" </span> &gt; " <span class="uicontrol"> Metadaten" </span> &gt; " <span class="uicontrol"> Definitionen" </span>). Alle CGI-Parameter und Vorlagen-Tags, die einen Feldnamen als Wert annehmen, können optional einen Tabellennamen gefolgt von einem ""angeben. vor dem Feldnamen (z. B. <span class="codeph"> sp_x_1=tablename.fieldname </span>). </p> <p>Wenn Sie beispielsweise nach Dokumenten suchen möchten, die ein oder mehrere rote Elemente in der Größe "groß"enthalten (wobei Elemente als parallele Zeilen mit Metadaten dargestellt werden), können Sie Folgendes verwenden: </p> <p> <code> sp_q_exact_1=red&amp;sp_x_1=items.color&amp; sp_q_exact_2=large&amp;sp_x_2=items.size&amp;sp_field_table=items:color,size,price </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>15 </p> </td> 
   <td colname="col2"> sp_i </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_i= <span class="varname"> Wert </span> </span> </p> </td> 
   <td colname="col4"> <p>Ignoriert die Suche, wenn Sie Berichte erstellen. </p> <p>Verwenden Sie diese Abfrage, um bestimmte Backend-Suchvorgänge zu maskieren, z. B. Suchvorgänge, die Sie generiert haben, oder Suchvorgänge, die ein Administrator im Mitgliedercenter generiert. Da ein Endbenutzer diese Sucharten nicht generiert, werden sie nicht in verschiedenen Search&amp;Promote der Adobe angezeigt. </p> <p>Gültige Werte sind <span class="codeph"> sp_i=1 </span> und <span class="codeph"> sp_i=2 </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>16 </p> </td> 
   <td colname="col2"> <p>sp_k </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_k= string </span> </p> </td> 
   <td colname="col4"> <p> Gibt die für die Suche zu verwendende Sammlung an. Die Standardeinstellung ist keine Sammlung, d. h. die Suche sollte die gesamte Site enthalten. </p> <p>Siehe <a href="../c-appendices/c-searchforms.md#reference_5A079AEEEFB84457892EF0870D0605C3" type="reference" format="dita" scope="local"> Verwenden von Sammlungen in Suchformularen </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>17 </p> </td> 
   <td colname="col2"> <p>sp_l </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_l= string </span> </p> </td> 
   <td colname="col4"> <p>Gibt die Sprache der Parameterzeichenfolgen der Abfrage an (z. B. <span class="codeph"> sp_q </span>). Die <i> Zeichenfolge <span class="codeph"> </span></i> sollte eine Standard-Gebietsschema-ID sein, die einen ISO-639-Sprachcode und optional einen ISO-3166-Ländercode enthält. Beispiel: "en"oder "en_US"für Englisch oder "ja"oder "ja_JP"für Japanisch. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>18 </p> </td> 
   <td colname="col2"> <p>sp_literal </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_literal= 0 oder 1 </span> </p> </td> 
   <td colname="col4"> <p> Wenn Sie <span class="codeph"> sp_literal=1 festlegen, werden </span> vorübergehend alle Funktionen deaktiviert, die die Wörter in der Abfrage interpretieren könnten. Mit diesem Parameter stimmen nur die wörtlichen Wörter der Abfrage mit den Dokumenten überein, unabhängig von Synonymen, alternativen Wortformen und Klangübereinstimmung. </p> <p>Beachten Sie, dass <span class="codeph"> sp_literal=0 keine Bedeutung </span> hat und bei Verwendung ignoriert wird. </p> <p>Siehe <a href="../c-about-linguistics-menu/c-about-dictionaries.md#concept_B8028B71EC8144669614C64578EDB034" type="concept" format="dita" scope="local"> Info zu Wörterbüchern </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>19 </p> </td> 
   <td colname="col2"> <p>sp_m </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_m= number </span> </p> </td> 
   <td colname="col4"> <p> Gibt an, ob Zusammenfassungen angezeigt werden. 1 ist ja, 0 ist nein. Die Standardeinstellung ist „1“. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>20 </p> </td> 
   <td colname="col2"> <p>sp_n </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_n= number </span> </p> </td> 
   <td colname="col4"> <p> Gibt die Anzahl der Ergebnisse an, die die Suchergebnisse Beginn haben. Die Standardeinstellung ist „1“. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>21 </p> </td> 
   <td colname="col2"> <p>sp_not_found_page </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_not_found_page= url </span> </p> </td> 
   <td colname="col4"> <p> Gibt an, ob eine Umleitung zur angegebenen URL erfolgen soll, wenn keine Suchergebnisse vorliegen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>22 </p> </td> 
   <td colname="col2"> <p>sp_p </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_p= any/all/phrase </span> </p> </td> 
   <td colname="col4"> <p> Gibt den Standardtyp der durchzuführenden Suche an. Die Verwendung <span class="codeph"> beliebiger </span> Mittel zur Suche nach Dokumenten, die ein beliebiges Wort aus der Abfrage-Zeichenfolge enthalten. Die Verwendung von <span class="codeph"> all </span> bedeutet, nach Dokumenten zu suchen, die alle Wörter in der Abfrage-Zeichenfolge enthalten. Die Verwendung einer <span class="codeph"> Wortgruppe </span> bedeutet, dass die Zeichenfolge der Abfrage so behandelt wird, als wäre sie eine mit Anführungszeichen versehene Wortgruppe, und alle vom Benutzer eingegebenen Anführungszeichen werden ignoriert. </p> <p>Bei <span class="codeph"> Wortgruppen </span> und <span class="codeph"> allen </span>wird die Angabe von "+"und "-"vor Suchbegriffen deaktiviert und diese Zeichen werden ignoriert. Wenn <span class="codeph"> sp_p nicht vorhanden </span> ist oder auf eine leere Zeichenfolge oder eine beliebige andere festgelegt ist, sind die standardmäßigen Wörterprefixe "+"und "-"zulässig. </p> <p>Weitere Informationen zur Verwendung von Plus ("+") und Minus ("-") bei Suchvorgängen finden Sie in der Beschreibung der Suchtipps. </p> <p>Siehe <a href="../c-about-settings-menu/c-about-searching-menu.md#concept_207105CF26B1448F8A3D223787C56AB8" type="concept" format="dita" scope="local">Info zu Suchen</a> </p> <p>Beispiele zur Verwendung des Parameters <span class="codeph"> sp_p finden Sie im Beispiel für die erweiterte Suche </span> . </p> <p>Siehe <a href="../c-appendices/c-searchforms.md#reference_82E1051918744EBA88A01E9E6AE42C4A" type="reference" format="dita" scope="local"> Beispiel für ein erweitertes Suchformular </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>23 </p> </td> 
   <td colname="col2"> <p> </p> </td> 
   <td colname="col03"> <p> sp_p_# </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_p_#= any/all/Satz </span> </p> </td> 
   <td colname="col4"> <p>Gibt den Standardtyp der Suche an, die mit der entsprechenden <span class="codeph"> sp_q_#- </span> Abfrage durchgeführt werden soll. Das "#"wird durch eine Zahl zwischen 1 und 16 ersetzt ( <span class="codeph"> sp_p_8 </span> gilt beispielsweise für die nummerierte Abfrage <span class="codeph"> sp_q_8 </span>). Die Verwendung <span class="codeph"> beliebiger </span> Mittel gibt Dokumente zurück, die ein beliebiges Wort aus der Abfrage-Zeichenfolge enthalten. Die Verwendung <span class="codeph"> aller </span> Mittel gibt Dokumente zurück, die alle Wörter in der Abfrage-Zeichenfolge enthalten. Die Verwendung von <span class="codeph"> Wortgruppen </span> bedeutet, dass die Zeichenfolge der Abfrage so behandelt wird, als wäre sie eine vollständige Wortgruppe (und alle vom Benutzer eingegebenen Anführungszeichen werden ignoriert). </p> <p>Wenn Sie entweder <span class="codeph"> alle </span> oder <span class="codeph"> Wortgruppe angeben, werden alle Plus- und Minuszeichen vor den Suchbegriffen ignoriert </span>. Wenn <span class="codeph"> sp_p_# ausgelassen </span> wird oder wenn sie auf eine leere Zeichenfolge oder <span class="codeph"> eine beliebige andere festgelegt ist, sind die standardmäßigen Präfixe "+"und "-"zulässig. </span>(s) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>24 </p> </td> 
   <td colname="col2"> <p>sp_pt </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <code> sp_pt= <i>exact/equivalent/compatible</i> </code> </p> </td> 
   <td colname="col4"> <p> Gibt den Typ der anzuwendenden Zielgruppe-Übereinstimmung an. Die Verwendung der <span class="codeph"> exakten </span> bedeutet, dass die Zielgruppe der Ertragsrate nur in Dokumenten übereinstimmt, die exakt mit der Abfrage im Inhalt der Zielgruppe übereinstimmen. Die Verwendung von <span class="codeph"> Entsprechungen </span> ist genau, außer dass die Reihenfolge der Wörter nicht wichtig ist. Durch die Verwendung von <span class="codeph"> kompatiblen Parametern wird der Übereinstimmungstyp der Zielgruppe </span> automatisch auf Grundlage des <span class="codeph"> sp_p- </span> Parameters festgelegt. Die Verwendung der <span class="codeph"> exakten </span> wird verwendet, wenn <span class="codeph"> sp_p </span> vollständig <span class="codeph"> oder </span> Satz ist <span class="codeph"> , ansonsten </span>äquivalent <span class="codeph"> </span> . Der Standardwert von <span class="codeph"> sp_pt </span> ist <span class="codeph"> kompatibel </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>25 </p> </td> 
   <td colname="col2"> <p> </p> </td> 
   <td colname="col03"> <p>sp_pt_# </p> </td> 
   <td colname="col3"> <p> <code> sp_pt_#= <i>exact/equivalent/compatible</i> </code> </p> </td> 
   <td colname="col4"> <p>Gibt den Typ der Zielgruppe-Übereinstimmung an, die mit der entsprechenden <span class="codeph"> sp_q_#- </span> Abfrage angewendet werden soll. Das "#"wird durch eine Zahl zwischen 1 und 16 ersetzt ( <span class="codeph"> sp_p_8 </span> gilt beispielsweise für die nummerierte Abfrage <span class="codeph"> sp_q_8 </span>). Die Verwendung der <span class="codeph"> exakten </span> bedeutet, dass die Zielgruppe der Ertragsrate nur in Dokumenten übereinstimmt, die exakt mit der Abfrage im Inhalt der Zielgruppe übereinstimmen. Die Verwendung von <span class="codeph"> Entsprechungen </span> ist wie <span class="codeph"> exakt </span>, außer dass die Reihenfolge der Wörter nicht wichtig ist. Durch die Verwendung <span class="codeph"> kompatibler Zielgruppen wird der Übereinstimmungstyp </span> automatisch auf Grundlage des entsprechenden <span class="codeph"> sp_p_#- </span> Parameters festgelegt: <span class="codeph"> exakt </span> wird verwendet, wenn <span class="codeph"> sp_p_# vollständig oder Wortgruppe ist, andernfalls </span> entspricht <span class="codeph"> </span> es. Der Standardwert von <span class="codeph"> sp_pt_# </span> ist <span class="codeph"> kompatibel </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>26 </p> </td> 
   <td colname="col2"> <p>sp_q </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_q= string </span> </p> </td> 
   <td colname="col4"> <p> Gibt die Abfrage-Zeichenfolge für die Suche an. Eine leere Zeichenfolge führt dazu, dass keine Ergebnisse angezeigt werden. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>27 </p> </td> 
   <td colname="col2"> <p> </p> </td> 
   <td colname="col03"> <p>sp_q_# </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_q_#= text </span> </p> </td> 
   <td colname="col4"> <p>Dieser Parameter ermöglicht die Erstellung mehrerer Abfragen in Suchformularen. Der <span class="codeph"> Parameter sp_q_# </span> enthält die Abfrage-Zeichenfolge, die in der angegebenen nummerierten Abfrage verwendet wird. Eine Suchanfrage kann auf bis zu 16 verschiedene nummerierte Abfragen verweisen ( <span class="codeph"> sp_q_1 </span> zu <span class="codeph"> sp_q_16 </span>). </p> <p>Wenn Sie beispielsweise das folgende Formular senden, werden alle Dokumente zurückgegeben, die die Wörter "hervorragend"und "books"enthalten. </p> <p> <code class="syntax html"> Search&nbsp;for:&nbsp;&lt;input&nbsp;type="text"&nbsp;name="sp_q"&nbsp;value="great"&gt; 
      Search&nbsp;for:&nbsp;&lt;input&nbsp;type="text"&nbsp;name="sp_q_1"&nbsp;value="books"&gt; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>28 </p> </td> 
   <td colname="col2"> <p>sp_q_day, sp_q_month, sp_q_year </p> </td> 
   <td colname="col03"> <p> sp_q_day_#, sp_q_month_#, sp_q_year_# </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_q_day= integer-Wert </span> </p> <p> <span class="codeph"> sp_q_month= integer-Wert </span> </p> <p> <span class="codeph"> sp_q_year= integer value </span> </p> <p> <span class="codeph"> sp_q_day_#= integer-Wert </span> </p> <p> <span class="codeph"> sp_q_month_#= integer-Wert </span> </p> <p> <span class="codeph"> sp_q_year_#= integer-Wert </span> </p> </td> 
   <td colname="col4"> <p>Mit diesen Parametern wird ein exaktes Datum für eine bestimmte Abfrage angegeben. Die <span class="codeph"> Parameter sp_q_day </span>, <span class="codeph"> sp_q_month </span>und <span class="codeph"> sp_q_year </span> gelten für die Haupt-Abfrage ( <span class="codeph"> sp_q </span>). </p> <p>Der <span class="codeph"> Parameter </span># wird durch eine Zahl zwischen 1 und 16 ersetzt (z. B. <span class="codeph"> sp_q_day_6 </span>, was für die nummerierte Abfrage <span class="codeph"> sp_q_6 gilt </span>). Standardmäßig werden alle Datumsangaben relativ zur Greenwich Mean Time durchsucht. </p> <p>Im folgenden Codeabschnitt können Benutzer nach dem Wort "orange"in Dokumenten vom Typ "Jan."suchen. 1. 2000" in einem benutzerdefinierten Feld mit dem Namen <span class="codeph"> PublishDate </span>: </p> <p> <code class="syntax html"> &lt;input&nbsp;type="hidden"&nbsp;name="sp_x_1"&nbsp;value="PublishDate"&gt; Search&nbsp;for:&nbsp;&lt;input&nbsp;type="text"&nbsp;name="sp_q"&nbsp;value="orange"&gt;On&nbsp;:&nbsp;&lt;input&nbsp;type="text"&nbsp;name="sp_q_day_1"&nbsp;size="2"&nbsp;value="1"&gt;&nbsp;Day&lt;input&nbsp;type="text"&nbsp;name="sp_q_month_1"&nbsp;size="2"&nbsp;value="1"&gt;&nbsp;Month &lt;input&nbsp;type="text"&nbsp;name="sp_q_year_1"&nbsp;size="4"&nbsp;value="2000"&gt;&nbsp;Year&nbsp; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>29 </p> </td> 
   <td colname="col2"> <p>sp_q_location </p> </td> 
   <td colname="col03"> <p>sp_q_location_# </p> </td> 
   <td colname="col3"> <p> <code> sp_q_location=<i>latitude/longitude</i> OR <i>areacode</i> OR <i>zipcode</i> </code> </p> <p> <code> sp_q_location_#= <i>latitude/longitude</i> OR <i>areacode</i> OR <i>zipcode</i> </code> </p> </td> 
   <td colname="col4"> <p>Diese Parameter verbinden einen Ort mit der Haupt- oder nummerierten Abfrage. Die Verwendung von <span class="codeph"> sp_q_location </span> wirkt sich auf die Haupt-Abfrage <span class="codeph"> sp_q_location_# aus </span> (wobei die <span class="codeph"> </span> # durch eine Zahl von 1 bis 16 ersetzt wird), wirkt sich auf die angegebene nummerierte Abfrage aus. Diese Parameter werden verwendet, um eine minimale und/oder maximale Entfernungsabstandssuche mit den Ortsdaten durchzuführen, die für jede Siteseite indiziert sind. Das Format des Werts bestimmt seine Interpretation. </p> <p>Ein Wert in der Form DDD (dreistellige Zahl) wird als ein US-Telefonbereich interpretiert. ein Wert in der Form DDDD oder DDDD-DDDD wird als US-Postleitzahl interpretiert; und ein Wert im Format ±DD.DDDD±DDD.DDDD wird als Breiten-/Längengrad-Paar interpretiert. Die Zeichen sind für jeden Wert erforderlich. Beispielsweise gibt +38.6317+120.5509 den Breitengrad 38.6317, den Längengrad 120.5509 an. </p> <p>Siehe <a href="../c-appendices/r-about-proximity-search.md#reference_45AC6BB50609431ABD31DA46EE65360D" type="reference" format="dita" scope="local"> Info zur Näherungssuche </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>30 </p> </td> 
   <td colname="col2"> <p>sp_q_max_relevant_away </p> </td> 
   <td colname="col03"> <p>sp_q_max_relevant_away _# </p> </td> 
   <td colname="col3"> <p> <code> sp_q_max_relevant_distance= <i>value</i> </code> </p> <p> <code> sp_q_max_relevant_distance_#= <i>value</i> </code> </p> </td> 
   <td colname="col4"> <p>Diese Parameter steuern die Relevanzberechnung, die bei der Suche in der Nähe angewendet wird. Die Verwendung von <span class="codeph"> sp_q_max_relevant_distanziert </span> sich auf die Haupt-Abfrage, <span class="codeph"> sp_q_max_relevant_dist_# </span> (wobei das <span class="codeph"> </span> # durch eine Zahl zwischen 1 und 16 ersetzt wird), wirkt sich auf die angegebene nummerierte Abfrage aus. </p> <p>Der Standardwert von <span class="codeph"> sp_q_max_relevant_away </span> ist 100. </p> <p>Ein perfekter Relevanzwert für die Komponente "Nähe"würde eine Entfernung von 0 darstellen. Ein minimaler Relevanzwert für die Annäherungskomponente würde einen Abstand direkt über dem angegebenen <span class="codeph"> sp_q_max_relevant_distanzwert darstellen </span> . </p> <p>Siehe <a href="../c-appendices/r-about-proximity-search.md#reference_45AC6BB50609431ABD31DA46EE65360D" type="reference" format="dita" scope="local"> Info zur Näherungssuche </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>31 </p> </td> 
   <td colname="col2"> <p>sp_q_min_day, sp_q_min_month, sp_q_min_year </p> <p>sp_q_max_day, sp_q_max_month, sp_q_max_year </p> </td> 
   <td colname="col03"> <p>sp_q_min_day_#, sp_q_min_month_#, sp_q_min_year_# </p> <p> sp_q_max_day_#, sp_q_max_month_#, sp_q_max_year_# </p> </td> 
   <td colname="col3"> <p> <code> sp_q_min_day=<i>integer value</i> </code> </p> <p> <code> sp_q_min_month=<i>integer value</i> </code> </p> <p> <code> sp_q_min_year=<i>integer value</i> </code> </p> <p> <code> sp_q_max_day=<i>integer value</i> </code> </p> <p> <code> sp_q_max_month=<i>integer value</i> </code> </p> <p> <code> sp_q_max_year=<i>integer value</i> </code> </p> <p> <code> sp_q_min_day_#=<i>integer value</i> </code> </p> <p> <code> sp_q_min_month_#=<i>integer value</i> </code> </p> <p> <code> sp_q_min_year_#=<i>integer value</i> </code> </p> <p> <code> sp_q_max_day_#=<i>integer value</i> </code> </p> <p> <code> sp_q_max_month_#=<i>integer value</i> </code> </p> <p> <code> sp_q_max_year_#=<i>integer value</i> </code> </p> </td> 
   <td colname="col4"> <p>Mit diesen Parametern werden Mindest- und Höchstdatumsbereiche für eine bestimmte Abfrage festgelegt. Die <span class="codeph"> Parameter sp_q_min_day </span>, <span class="codeph"> sp_q_min_month </span>, <span class="codeph"> sp_q_min_year, </span>sp_q_max_day <span class="codeph"> , </span>sp_q_max_month <span class="codeph"> </span><i></i> <span class="codeph"> </span>undsp_q_max_year gelten für die Haupt-Abfrage (_q). </p> <p>Das <span class="codeph"> # </span>im Parameternamen wird durch eine Zahl zwischen 1 und 16 ersetzt ( <span class="codeph"> sp_q_min_day_6 </span> gilt beispielsweise für die nummerierte Abfrage <span class="codeph"> sp_q_6 </span>). </p> <p>Es ist zulässig, nur ein Mindestdatum, nur ein Höchstdatum oder sowohl ein Mindest- als auch ein Höchstdatum anzugeben. Für einen bestimmten Mindest- oder Höchstsatz müssen jedoch alle drei Datumsparameter angegeben werden (Tag, Monat und Jahr). Standardmäßig werden alle Datumsangaben relativ zur Greenwich Mean Time durchsucht. </p> <p>Im folgenden Codeabschnitt kann ein Benutzer in Dokumenten mit einem Datum zwischen dem 1. Januar 2000 und dem 31. Dezember 2000 in einem benutzerdefinierten Feld mit dem Namen <span class="codeph"> Veröffentlichungsdatum nach dem Wort "orange"suchen </span>: </p> <p> <code class="syntax html"> &lt;input&nbsp;type="hidden"&nbsp;name="sp_x_1"&nbsp;value="PublishDate"&gt;Search&nbsp;for:&nbsp;&lt;input&nbsp;type="text"&nbsp;name="sp_q"&nbsp;value="orange"&gt;Between:&nbsp;&lt;input&nbsp;type="text"&nbsp;name="sp_q_min_day_1"&nbsp;size="2"&nbsp;value="1"&gt;&nbsp;Start&nbsp;Day&lt;input&nbsp;type="text"&nbsp;name="sp_q_min_month_1"&nbsp;size="2"&nbsp;value="1"&gt;&nbsp;Start&nbsp;Month 
      &lt;input&nbsp;type="text"&nbsp;name="sp_q_min_year_1"&nbsp;size="4"&nbsp;value="2000"&gt;&nbsp;Start&nbsp;Year 
      And:&nbsp;&lt;input&nbsp;type="text"&nbsp;name="sp_q_max_day_1"&nbsp;size="2"&nbsp;value="31"&gt;&nbsp;End&nbsp;Day 
      &lt;input&nbsp;type="text"&nbsp;name="sp_q_max_month_1"&nbsp;size="2"&nbsp;value="12"&gt;&nbsp;End&nbsp;Month 
      &lt;input&nbsp;type="text"&nbsp;name="sp_q_max_year_1"&nbsp;size="4"&nbsp;value="2000"&gt;&nbsp;End&nbsp;Year </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>32 </p> </td> 
   <td colname="col2"> <p>sp_q_min, sp_q_max </p> </td> 
   <td colname="col03"> <p>sp_q_min_#, sp_q_max_#, sp_q_exact_# </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_q_min= Wert </span> </p> <p> <span class="codeph"> sp_q_max= Wert </span> </p> <p> <span class="codeph"> sp_q_min_#= value </span> </p> <p> <span class="codeph"> sp_q_max_#= value </span> </p> <p> <span class="codeph"> sp_q_exact_#=value </span> </p> </td> 
   <td colname="col4"> <p>Diese Parameter geben einen Mindest- (und/oder Maximalwert) an, der auf die Haupt- oder nummerierte Abfrage angewendet werden soll. Die Verwendung von <span class="codeph"> sp_q_min </span>, <span class="codeph"> sp_q_max </span>und <span class="codeph"> sp_q_exact </span> wirkt sich auf die Haupt-Abfrage ( <span class="codeph"> sp_q </span>) aus. </p> <p>Ersetzen Sie <span class="codeph"> # </span>im Parameternamen durch eine Zahl zwischen 1 und 16 ( <span class="codeph"> sp_q_min_8 </span> gilt beispielsweise für die nummerierte Abfrage <span class="codeph"> sp_q_8 </span>). </p> <p>Die Verwendung von <span class="codeph"> sp_q_exact_# </span> ist kurz für die Angabe von <span class="codeph"> sp_q_min_# </span> und <span class="codeph"> sp_q_max_# </span> mit demselben Wert. Wenn <span class="codeph"> sp_q_exact_# angegeben </span> ist, werden alle entsprechenden <span class="codeph"> sp_q_min_#- </span> oder <span class="codeph"> sp_q_max_#- </span> Parameter ignoriert. </p> <p>Die <span class="codeph"> Parameter sp_q_min_# </span>, <span class="codeph"> sp_q_max_# </span> und <span class="codeph"> sp_q_exact_# </span> können optional mehrere "|"-getrennte Werte angeben. So suchen Sie z. B. nach Dokumenten, die den Wert grün oder rot im Feld "Farbe"enthalten: <span class="codeph"> ...&amp;sp_q_exact_1=green|red&amp;sp_x_1=color </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>33 </p> </td> 
   <td colname="col2"> <p>sp_q_nocp </p> </td> 
   <td colname="col03"> <p>sp_q_nocp _# </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_q_nocp= 1 oder 0 </span> </p> <p> <span class="codeph"> sp_q_nocp_#= 1 oder 0 </span> </p> </td> 
   <td colname="col4"> <p>Der Standardwert für den Parameter ist <span class="codeph"> 0, </span> d. h., dass Erweiterungen der allgemeinen Wortgruppe durchgeführt werden. </p> <p>Bei Festlegung auf <span class="codeph"> 1 </span> für die entsprechende Abfrage der Suche werden keine Erweiterungen der allgemeinen Wortgruppen durchgeführt. </p> <p>Die Verwendung von <span class="codeph"> sp_q_nocp </span> wirkt sich auf den Hauptparameter der Abfrage <span class="codeph"> sp_q aus </span>. Um diesen Parameter auf eine nummerierte Abfrage anzuwenden, ersetzen Sie <span class="codeph"> # </span> im Parameternamen durch die entsprechende Nummer. So <span class="codeph"> gilt z. B. </span> sp_q_nocp_8 für die nummerierte Abfrage <span class="codeph"> sp_q_8 </span>. </p> <p> 
     <!--See also <xref href="c_about_common_phrases.xml#concept_4946E53586DF492EAEB1B7F757FD440F" format="dita" scope="local">About Common Phrases</xref>--> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>34 </p> </td> 
   <td colname="col2"> <p>sp_q_required </p> </td> 
   <td colname="col03"> <p>sp_q_required _# </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_q_required= 1 oder 0 oder -1 </span> </p> <p> <span class="codeph"> sp_q_required_#= 1 oder 0 oder -1 </span> </p> </td> 
   <td colname="col4"> <p>Dieser Parameter bestimmt, ob eine Übereinstimmung in der entsprechenden Abfrage auftreten muss (1), darf (0) oder darf (-1), damit ein Dokument auf der Ergebnisseite zurückgegeben wird. </p> <p>Die Verwendung von <span class="codeph"> sp_q_required </span> wirkt sich auf die Haupt-Abfrage ( <span class="codeph"> sp_q </span>) aus. </p> <p>Um eine nummerierte Abfrage zu übernehmen, ersetzen Sie das <span class="codeph"> # </span> im Parameternamen durch die entsprechende Nummer ( <span class="codeph"> sp_q_required_8 </span> gilt beispielsweise für die nummerierte Abfrage <span class="codeph"> sp_q_8 </span>). Der Standardwert des Parameters ist 1 (muss übereinstimmen). </p> <p>Um nach Dokumenten zu suchen, die das Wort "calc"enthalten, aber NICHT "mac", "win"oder "all"im benutzerdefinierten Plattformfeld enthalten, könnte Ihr HTML-Suchformular die folgenden Zeilen enthalten: </p> <p> <code class="syntax html"> &lt;input&nbsp;type="hidden"&nbsp;name="sp_x_1"&nbsp;value="platform"&gt; 
      Search&nbsp;for:&nbsp;&lt;input&nbsp;type="text"&nbsp;name="sp_q"&nbsp;value="calc"&gt; 
      Exclude:&nbsp;&lt;input&nbsp;type="text"&nbsp;name="sp_q_1"&nbsp;value="mac&nbsp;win&nbsp;all"&gt; 
      &lt;input&nbsp;type="hidden"&nbsp;name="sp_q_required_1"&nbsp;value="-1"&gt; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>35 </p> </td> 
   <td colname="col2"> <p>sp_redirect_if_one_result </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <code> sp_redirect_ 
      if_one_result= <i>0 or 1</i> </code> </p> </td> 
   <td colname="col4"> <p>Gibt an, ob zur Suchergebnis-URL umgeleitet werden soll, wenn nur ein Suchergebnis vorhanden ist. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>36 </p> </td> 
   <td colname="col2"> <p>sp_Werber </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_Werber= url </span> </p> </td> 
   <td colname="col4"> <p>Gibt die Werber-URL für die Suche an. Nützlich für die Suche Umschreiben Regeln, bei denen die Suchergebnisse auf dieselbe Site zurückführen wie das Suchformular. </p> <p>Der Standardwert ist der vom Browser bereitgestellte CGI-HTTP_WERBER-Standardwert. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>37 </p> </td> 
   <td colname="col2"> <p>sp_ro </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_ro= <span class="varname"> field </span>: <span class="varname"> Relevanz </span> </span> </p> </td> 
   <td colname="col4"> <p>Ermöglicht die optionale Suchzeit pro Feldname und Relevanzsteuerung. Das <span class="codeph"> oder </span> im Parameternamen steht für "relevant override". Der Parameter akzeptiert einen oder mehrere Feldnamen, gefolgt von einem Doppelpunkt und einem Relevanzwert von 0 bis 10. </p> <p>Wenn Sie beispielsweise den Relevanzwert für den Feldnamen "body"auf 10 festlegen möchten, wird der Parameter zum Zeitpunkt der Suche durch einen Kunden wie folgt angezeigt: </p> <p> <span class="codeph"> sp_ro=body:10 </span> </p> <p>Sie können auch ein Pipe-Trennzeichen verwenden, um mehrere Außerkraftsetzungen der Feldrelevanz in der Parameterzeichenfolge anzugeben. Um beispielsweise den Relevanzwert für die Feldnamen "body"und "title"auf 9 festzulegen, würde der Parameter bei der Durchführung einer Suche wie folgt angezeigt: </p> <p> <span class="codeph"> sp_ro=body:9|title:9 </span> </p> <p> <p>Hinweis:  Die Angabe eines Felds, das nicht an der zugehörigen Suche beteiligt ist, hat keine Auswirkungen. Wenn Sie z. B. <span class="codeph"> sp_ro=title:10 festlegen </span>, der <span class="codeph"> Name des </span> Titelfelds jedoch nicht durchsucht wird, hat der Parameter <span class="codeph"> </span> sp_ro keine Auswirkungen. Mit anderen Worten, wenn Sie einen Feldnamen mit dem Parameter <span class="codeph"> </span> sp_ro angeben, wird dieses Feld nicht automatisch durchsucht. Stattdessen setzt sie die entsprechende Relevanzeinstellung des Felds außer Kraft. </p> </p> <p>Siehe <a href="../c-about-settings-menu/c-about-metadata-menu.md#task_0A7657B63596421BB6DB3ED44F827AB3" type="task" format="dita" scope="local"> Bearbeiten von vordefinierten oder benutzerdefinierten Meta-Tag-Feldern </a>. </p> <p>Siehe <a href="../c-about-rules-menu/c-about-query-cleaning-rules.md#concept_17F3CDDC3C8A4128AF092A82B777B86C" type="concept" format="dita" scope="local"> Grundlagen zu Abfragen-Bereinigungsregeln </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>38 </p> </td> 
   <td colname="col2"> <p>sp_s </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_s= number </span> </p> </td> 
   <td colname="col4"> <p>Gibt die Sortierreihenfolge an. Null (0) ist der Standardwert und Mittel zur Sortierung nach Relevanzwert. Ein (1) bedeutet, nach Datum zu sortieren, und -1 bedeutet, nicht zu sortieren. </p> <p>Sie können einen Feldnamen für den Wert des Parameters <span class="codeph"> "sp_s" </span> angeben. So <span class="codeph"> sortiert </span> sp_s=title die Ergebnisse beispielsweise nach den Werten, die im Titelfeld enthalten sind. Wenn ein Feldname für den Wert eines <span class="codeph"> sp_s- </span> Parameters verwendet wird, werden die Ergebnisse nach diesem Feld sortiert und dann nach Relevanz untergeordnet. </p> <p>Stellen Sie die Sortierung für das referenzierte Feld entweder <span class="uicontrol"> Aufsteigend </span> oder <span class="uicontrol"> Absteigend </span> unter <span class="uicontrol"> Einstellungen </span> &gt; <span class="uicontrol"> Metadaten </span> &gt; <span class="uicontrol"> </span> Definitionen ein, um diese Funktion zu aktivieren. </p> <p>Sie können einer Abfrage auch mehrere Sortierfelder zuweisen, indem Sie den <span class="codeph"> sp_s- </span> Parameter mehrmals im Suchformular festlegen. In den folgenden Vorlagenzeilen werden die Suchergebnisse zunächst nach Künstlernamen, dann nach Albumnamen und dann nach Nachverfolgungsnamen sortiert. </p> <p> <code class="syntax html"> &lt;input&nbsp;type="hidden"&nbsp;name="sp_s"&nbsp;value="artist"&gt; 
      &lt;input&nbsp;type="hidden"&nbsp;name="sp_s"&nbsp;value="album"&gt; 
      &lt;input&nbsp;type="hidden"&nbsp;name="sp_s"&nbsp;value="track"&gt; 
      Search&nbsp;for:&nbsp;&lt;input&nbsp;type="text"&nbsp;name="sp_q"&nbsp;value="Music&nbsp;Search"&gt; </code> </p> <p>Es ist auch möglich, mit der Tabelle übereinstimmende Felddaten zu sortieren, indem Sie vor dem Feldnamen einen Qualifikator für den Tabellennamen angeben, z. B. items.price. Weitere Informationen zur Tabellenzuordnung finden Sie im <span class="codeph"> Parameter </span> sp_field_table. </p> <p>Bei der Suche nach der Nähe können Sie die Ergebnisse nach der Nähe sortieren, indem Sie ein "Feld für die Ausgabe der Nähe" angeben. </p> <p>Siehe <a href="../c-appendices/r-about-proximity-search.md#reference_45AC6BB50609431ABD31DA46EE65360D" type="reference" format="dita" scope="local"> Info zur Näherungssuche </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>39 </p> </td> 
   <td colname="col2"> <p>sp_sr </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_sr= field </span> </p> </td> 
   <td colname="col4"> <p>Gibt das Rankenfeld an, das für das statische Rang verwendet werden soll. Das Feld muss ein Feld vom Typ Rang mit einer Relevanz größer als 0 sein. Wenn für die Abfrage kein <span class="codeph"> sp_sr- </span> Parameter angegeben wurde, wird automatisch ein Feld vom Typ Rank ausgewählt. </p> <p>Um das statische Ranking für eine bestimmte Abfrage zu deaktivieren, fügen Sie einen NULL-Wert für <span class="codeph"> sp_sr ein </span> (z. B. <span class="codeph"> &lt;input type="hidden" name="sp_sr" value=""&gt; </span>). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>40 </p> </td> 
   <td colname="col2"> <p>sp_sfvl_field </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_sfvl_field= string </span> </p> </td> 
   <td colname="col4"> <p>Gibt den Feldnamen an, der in Verbindung mit dem Tag <span class="codeph"> &lt;search-field-value-Liste&gt; </span> in der Suchvorlage verwendet werden soll. </p> <p>Sie können mehrere <span class="codeph"> sp_sfvl_field- </span> Parameter angeben. </p> </td> 
  </tr> 
  <tr>
   <td colname="col1"> <p>41 </p> </td> 
   <td colname="col2"> <p> sp_sfvl_df_count </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_sfvl_df_count= <span class="varname"> &lt;integer_value&gt; </span> </span> </p> </td> 
   <td colname="col4"> <p> Fordert für diese Suche bis zu <span class="codeph"><span class="varname"> &lt;integer_value&gt; </span></span> search-field-value-Liste <span class="codeph"> </span> dynamic-facet-Felder an. </p> <p>Der Standardwert lautet 0. Der maximal zulässige Wert ist die aktuelle Anzahl der dynamischen Facet-Felder, die für einen bestimmten Index definiert sind. Ganzzahlwerte, die kleiner als 0 sind, werden als 0 behandelt. Ganzzahlwerte, die oben angegeben wurden, <span class="codeph"> die Anzahl der dynamischen Facetten-Felder </span> werden bei der <span class="codeph"> Anzahl der dynamischen Facetten-Felder begrenzt </span>. Nicht-ganzzahlige Werte werden ignoriert. werden sie als Standardwert behandelt. </p> <p>Die Suche eines bestimmten Segments wird mit einem maximal zulässigen Wert für <span class="codeph"> sp_sfvl_df_count </span> des <span class="codeph"> Werts für die Anzahl der dynamischen Facetten dieses Segments </span> begrenzt. Beim Zusammenführen von Segmentergebnissen <span class="codeph"> ist der effektive Maximalwert von </span> sp_sfvl_df_count der maximale tatsächliche <span class="codeph"> sp_sfvl_df_count </span> für alle Slices. </p> <p>Siehe <a href="../c-about-design-menu/c-about-dynamic-facets.md#task_D17F484130E448258100BAC1EEC53F39" format="dita" scope="local"> Konfigurieren dynamischer Facets </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>42 </p> </td> 
   <td colname="col2"> <p> sp_sfvl_df_exclude </p> </td> 
   <td colname="col03"> <p> </p> </td>
   <td colname="col3"> <p> </p> <p> <span class="codeph"> sp_sfvl_df_exclude= &lt; <span class="varname"> field_name </span>&gt;[|&lt; <span class="varname"> field_name </span> </span>&gt;|... </p> </td> 
   <td colname="col4"> <p> Gibt eine Liste spezifischer dynamischer Facet-Felder an, die bei dieser Suche nicht berücksichtigt werden sollen. </p> <p>Standardmäßig werden alle dynamischen Facettenfelder berücksichtigt. </p> <p>Siehe <a href="../c-about-design-menu/c-about-dynamic-facets.md#task_D17F484130E448258100BAC1EEC53F39" format="dita" scope="local"> Konfigurieren dynamischer Facets </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>43 </p> </td> 
   <td colname="col2"> <p> sp_sfvl_df_include </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> </p> <p> <span class="codeph"> sp_sfvl_df_include= &lt; <span class="varname"> field_name </span>&gt;[|&lt; <span class="varname"> field_name </span> </span>&gt;|... </p> </td> 
   <td colname="col4"> <p> Gibt eine Liste spezifischer dynamischer Facettenfelder an, die in die Suchergebnisse aufgenommen werden sollen. </p> <p> <p>Hinweis:  Der <span class="codeph"> Parameter </span> sp_sfvl_df_count bestimmt die Gesamtanzahl der zurückzugebenden dynamischen Facet-Felder, einschließlich aller über <span class="codeph"> sp_sfvl_df_include angegebenen Felder </span>. Das heißt, dass die Verwendung von <span class="codeph"> sp_sfvl_df_include </span> nicht zulässt, dass die Gesamtanzahl der zurückgegebenen dynamischen Facet-Felder <span class="codeph"> sp_sfvl_df_count überschreitet </span>. </p> </p> <p>Siehe <a href="../c-about-design-menu/c-about-dynamic-facets.md#task_D17F484130E448258100BAC1EEC53F39" format="dita" scope="local"> Konfigurieren dynamischer Facets </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>44 </p> </td> 
   <td colname="col2"> <p>sp_staged </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_staged= 0 oder 1 </span> </p> </td> 
   <td colname="col4"> <p>Wenn <span class="codeph"> sp_staged=1 mit einer Abfrage gesendet </span> wird, ist die ausgeführte Abfrage eine gestaffelte Suche. </p> <p>Bei einer gestaffelten Suche werden alle Komponenten verwendet, die derzeit gestaffelt sind, einschließlich des Indexes und der Vorlagen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>45 </p> </td> 
   <td colname="col2"> <p>sp_Beginn_day, sp_Beginn_month, sp_Beginn_year </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_Beginn_day= number </span> </p> <p> <span class="codeph"> sp_Beginn_month= number </span> </p> <p> <span class="codeph"> sp_Beginn_year= number </span> </p> </td> 
   <td colname="col4"> <p>Dieses Wertetriplet gibt den Startdatumsbereich für die Suche an und stellt ihn als Satz bereit. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>46 </p> </td> 
   <td colname="col2"> <p> </p> </td> 
   <td colname="col03"> <p>sp_recommendations_q </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_sug_q= number </span> </p> </td> 
   <td colname="col4"> <p>Der Parameter <span class="codeph"> sp_suggerate_q </span> bestimmt, welcher <span class="codeph"> sp_q[_#]- </span> Parameter mit dem Suggest-Dienst verwendet werden soll. </p> <p>Der Standardwert von <span class="codeph"> sp_vorschläge_q </span> ist 0, d. h., die Suchmaschine verwendet den Wert <span class="codeph"> sp_q </span> , um die Vorschläge zu bestimmen. </p> <p>Legen Sie <span class="codeph"> sp_suggerieren_q=1 </span> fest, um den Wert von <span class="codeph"> sp_q_1 </span> zur Bestimmung der Vorschläge usw. zu verwenden. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>47 </p> </td> 
   <td colname="col2"> <p>sp_t </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_t= string </span> </p> </td> 
   <td colname="col4"> <p>Gibt die zu verwendende Transportvorlage an. </p> <p>Dieser Parameter ist nützlich, wenn Sie das Erscheinungsbild der wichtigsten Suchergebnisse über Ihre Website hinweg steuern möchten, indem Sie für jeden Bereich in Ihrem Suchkonto unterschiedliche Suchtransportvorlagen verwenden. </p> <p>Die standardmäßige Transportvorlage lautet "search". </p> <p>Siehe <a href="../c-appendices/c-templates.md#reference_12AAB3B9F4C74C11956F1DBA95714C2F" type="reference" format="dita" scope="local"> Verwalten mehrerer Transportvorlagen für Ihre Website </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>48 </p> </td> 
   <td colname="col2"> <p>sp_trace </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_trace= 0 oder 1 </span> </p> </td> 
   <td colname="col4"> <p>Wenn <span class="codeph"> sp_stage=1 festgelegt </span>, wird die Kernfunktion für die Suchablaufverfolgung in Simulator aktiviert. </p> <p>Siehe <a href="../c-about-simulator.md#concept_020AA6751E32421A96A3455508364C7E" format="dita" scope="local"> Info zu Simulator </a>. </p> <p> <p>Hinweis:  Wenn dieser Parameter nicht angegeben ist, werden bei der Kernsuche keine Nachverfolgungsinformationen erfasst und die zugehörigen Kern-Suchvorlagen-Tags haben keine Ausgabe. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>49 </p> </td> 
   <td colname="col2"> <p>sp_w, sp_w_control </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <code> sp_w= <i>sound-alike-enable</i> </code> </p> <p> <code> sp_w_control=<i>sound-alike-control</i> </code> </p> </td> 
   <td colname="col4"> <p>Legt fest, dass die Klanggleichübereinstimmung für diese Abfrage aktiviert oder deaktiviert werden soll. </p> <p>Das sp_w_control für "Exakt" wird ignoriert. Die Übereinstimmung mit dem Ton ist deaktiviert. </p><p>Das sp_w_control für "Alike" wird ignoriert. Klangähnliche Übereinstimmung ist aktiviert</p><p>sp_w_control für alles andere ist 1. Die Übereinstimmung mit dem Ton ist deaktiviert. </p><p>sp_w_control für alles andere ist alles andere. Die Übereinstimmung mit dem Ton ist aktiviert. </p>Mit dem <span class="codeph"> Parameter sp_w_control </span> können Sie ein Kontrollkästchen mit negativem oder positivem Wortlaut für die Endbenutzer-Kontrolle der Klangalike-Übereinstimmung erstellen. </p> <p>Wenn <span class="codeph"> sp_w_control=0 verwendet </span> wird, wird ein Kontrollkästchen mit negativem Wortlaut verwendet, um den <span class="codeph"> sp_w- </span> Parameter wie im folgenden Beispiel festzulegen: </p> <p> <code class="syntax html"> &lt;input&nbsp;type=hidden&nbsp;name="sp_w_control"&nbsp;value="0"&gt;&lt;input&nbsp;type=checkbox&nbsp;name="sp_w"&nbsp;value="exact"&gt;No&nbsp;Sound-Alike&nbsp;matching </code> </p> <p>Wenn <span class="codeph"> sp_w_control=1 verwendet </span> wird, wird ein Kontrollkästchen mit positivem Wortlaut verwendet, um den <span class="codeph"> sp_w- </span> Parameter wie folgt festzulegen: </p> <p> <code class="syntax html"> &lt;input&nbsp;type=hidden&nbsp;name="sp_w_control"&nbsp;value="1"&gt;&lt;input&nbsp;type=checkbox&nbsp;name="sp_w"&nbsp;value="alike"&gt;Sound-Alike&nbsp;matching </code> </p> <p>Weitere Beispiele zur Verwendung der <span class="codeph"> Parameter sp_w_control </span> und <span class="codeph"> </span> sp_w finden Sie im Beispiel für die erweiterte Suche. </p> <p>Siehe <a href="../c-appendices/c-searchforms.md#reference_82E1051918744EBA88A01E9E6AE42C4A" type="reference" format="dita" scope="local"> Beispiel für ein erweitertes Suchformular </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>50 </p> </td> 
   <td colname="col2"> <p>sp_x </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_x= field </span> </p> </td> 
   <td colname="col4"> <p>Gibt die Felder an, die nach der Abfrage-Zeichenfolge gesucht werden sollen. auf jede Weise alle Felder durchsuchen. title bedeutet nur Suchtitelfelder. desc bedeutet, dass nur Suchfelder mit Dokument-Beschreibungen verwendet werden. Schlüssel bedeutet, dass nur Suchbegriffe des Dokuments verwendet werden. body bedeutet nur Suchtext. alt bedeutet, dass nur alternativer Text gesucht wird. url bedeutet, nur die URL-Werte zu suchen. zielgruppe bedeutet, dass nur Suchbegriffe der Zielgruppe verwendet werden. In diesen Fällen werden die Benutzerspezifikationen der Feldpräfixe "text:", "desc:", "keys:", "body:", "alt:", "url:"und "Zielgruppe:" innerhalb des entsprechenden Parameters <span class="codeph"> "sp_q" </span> ignoriert. Wenn <span class="codeph"> sp_x nicht vorhanden </span> ist oder wenn eine leere Zeichenfolge oder eine beliebige Zeichenfolge festgelegt ist, sind die Standard-Benutzerfeldpräfixe zulässig. Weitere Informationen zu den Feldpräfixen finden Sie in der Beschreibung zu den Suchtipps. </p> <p>Siehe <a href="../c-about-settings-menu/c-about-searching-menu.md#concept_207105CF26B1448F8A3D223787C56AB8" type="concept" format="dita" scope="local">Info zu Suchen</a> </p> <p>Beispiele mit dem Parameter <span class="codeph"> sp_x finden Sie in der Beschreibung des erweiterten Suchformulars </span> . </p> <p>Siehe <a href="../c-appendices/c-searchforms.md#reference_82E1051918744EBA88A01E9E6AE42C4A" type="reference" format="dita" scope="local"> Beispiel für ein erweitertes Suchformular </a>. </p> <p>Sie können Abfragen erstellen, die alle auf " <span class="uicontrol"> Standardmäßig suchen"festgelegten Felder </span> unter <span class="uicontrol"> Optionen </span> &gt; <span class="uicontrol"> Metadaten </span> &gt; <span class="uicontrol"> Definitionen durchsuchen, </span> indem Sie sp_x=any festlegen <span class="codeph"> </span>. Sowohl vordefinierte als auch benutzerdefinierte Felder können als Wert des <span class="codeph"> sp_x- </span> Parameters verwendet werden. </p> <p>Sie können einer Abfrage auch mehrere Felder zuweisen, indem Sie den Parameter <span class="codeph"> sp_x mehrmals einstellen </span> . Mit den folgenden Vorlagenzeilen können Benutzer sowohl die Felder "title"als auch "author"für "Great Books"Abfrage werden. </p> <p> <code class="syntax html"> &lt;input&nbsp;type="hidden"&nbsp;name="sp_x"&nbsp;value="title"&gt;&lt;input&nbsp;type="hidden"&nbsp;name="sp_x"&nbsp;value="author"&gt;Search&nbsp;for:&nbsp;&lt;input&nbsp;type="text"&nbsp;name="sp_q"&nbsp;value="Great&nbsp;Books"&gt; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>51 </p> </td> 
   <td colname="col2"> <p> </p> </td> 
   <td colname="col03"> <p>sp_x_# </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_x_#= field-name </span> </p> </td> 
   <td colname="col4"> <p>Dieser Parameter gibt an, welches Feld in der entsprechenden <span class="codeph"> sp_q_#- </span> Abfrage gesucht werden soll. Die <span class="codeph"> Zahl <span class="codeph"> wird durch eine Zahl zwischen 1 und 16 ersetzt (z. B. </span> sp_x_8 </span> <span class="codeph"> </span>). Der Feldname ist ein beliebiges vordefiniertes oder benutzerdefiniertes Feld. </p> <p>Wenn für eine bestimmte nummerierte Abfrage kein <span class="codeph"> sp_x_#- </span> Parameter angegeben ist, werden alle Felder, die standardmäßig als <span class="uicontrol"> Suche nach </span> den unter <span class="uicontrol"> Einstellung </span> &gt; <span class="uicontrol"> Metadaten </span> &gt; <span class="uicontrol"> Definitionen festgelegten Feldern definiert sind, von dieser Abfrage durchsucht </span> . </p> <p>Wenn Sie beispielsweise das folgende Formular senden, werden alle Dokumente zurückgegeben, die das Wort "hervorragend"enthalten, die auch das Wort "Fitzgerald"im Feld "Autor"enthalten: </p> <p> <code class="syntax html"> Search&nbsp;for:&nbsp;&lt;input&nbsp;type="text"&nbsp;name="sp_q"&nbsp;value="great"&gt;&lt;input&nbsp;type="hidden"&nbsp;name="sp_x_1"&nbsp;value="author"&gt;Search&nbsp;only&nbsp;documents&nbsp;written&nbsp;by:&nbsp;&lt;input&nbsp;type="text"&nbsp;name="sp_q_1"&nbsp;value="Fitzgerald"&gt; </code> </p> <p>Sie können mehrere Feldnamen mit einer bestimmten Abfrage oder nummerierten Abfrage verknüpfen, indem Sie in einer einzigen Suchanfrage mehrere Instanzen desselben Parameters <span class="codeph"> sp_x </span> oder <span class="codeph"> sp_x_# </span> angeben. </p> <p>Wenn Sie z. B. in den Feldern "body"und "keys"nach dem Wort "blume"suchen möchten, können Sie ein Suchformular mit den folgenden Informationen erstellen: </p> <p> <code class="syntax html"> &lt;input&nbsp;type="hidden"&nbsp;name="sp_x_1"&nbsp;value="body"&gt;&lt;input&nbsp;type="hidden"&nbsp;name="sp_x_1"&nbsp;value="keys"&gt;Search&nbsp;for:&nbsp;&lt;input&nbsp;type="text"&nbsp;name="sp_q_1"&nbsp;value="flower"&gt; </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Ein typisches Beispiel für die Verwendung von CGI-Parametern für die Backend-Suche {#section_260012BBC2514CC9A8E02E53DE8B41EE}

Über den folgenden Link wird eine Suche mit &quot;Music&quot;als Abfrage der Suche Beginn und alle Standardparameter verwendet. Beachten Sie, dass die URL zur Lesbarkeit auf zwei Zeilen aufgeteilt ist. In Ihrem HTML-Code sollte sich dieser Link alle in einer Zeile befinden.

```
<a href="https://search.atomz.com/search/?sp_q=Music&sp_a=sp99999999"> 
Testing...</a>
```

Dieselben Funktionen werden typischerweise mit einem Formular definiert:

```
<form action="https://search.atomz.com/search/"> 
<input size=12 name="sp_q" value="Music"><br> 
<input type=hidden name="sp_a" value="sp99999999"> 
<input type=submit value="Search"><br> 
</form>
```

Normalerweise sollten Sie beim Starten einer Suche Standardparameter verwenden. Auf diese Weise wird die erste Seite angezeigt, sortiert nach Relevanz, und der Kunde kann andere Seiten und andere Optionen auswählen. Wenn das Suchformular auf Ihrer Site Optionen für Sammlungen enthält, geben Sie den Sammlungsnamen als Parameter an.

## Ein detailliertes Beispiel für die Verwendung von CGI-Parametern für die Backend-Suche {#section_5FA3C620D5124FB2AB28857F8D8473F6}

Die folgenden Formular-Abfragen zeigen die `25` Ergebnisse, die mit dem Ergebnis beginnen `10`. Zusammenfassungen werden nicht angezeigt, die Sortierreihenfolge ist nach Datum geordnet und die Sammlung mit dem Namen `support` wird verwendet. Es werden nur Dokumente zurückgegeben, die innerhalb der letzten 30 Tage datiert wurden.

```
<form action="https://search.atomz.com/search/"> 
<input size=12 name="sp_q"><br> 
<input type=hidden name="sp_a" value="sp99999999"> 
<input type=submit value="Search"><br> 
<input type=hidden name=sp_n value=10> 
<input type=hidden name=sp_c value=25> 
<input type=hidden name=sp_m value=0> 
<input type=hidden name=sp_s value=1> 
<input type=hidden name=sp_k value="support"> 
<input type=hidden name=sp_date_range value=30> 
</form>
```

