---
description: Erfahren Sie, wie Sie verschiedene CGI-Parameter verwenden.
solution: Target
title: CGI-Parameter
topic-legacy: Appendices,Site search and merchandising
uuid: a5f43547-bc15-44aa-ba23-6b8b573e09d2
exl-id: 9f24aebf-5fa3-433e-b66d-4129bdd3f7f6
translation-type: tm+mt
source-git-commit: 7559f5f7437d46e3510d4659772308666425ec96
workflow-type: tm+mt
source-wordcount: '1938'
ht-degree: 1%

---

# CGI-Parameter{#cgi-parameters}

## CGI-Parameter {#concept_F395999090FE4926B38BC73D5E612800}

## CGI-Parameter suchen {#reference_DA27A8B0728246DA94994885E1353890}

Es wird der Suchformularcode bereitgestellt, mit dem Sie die HTML Ihrer Site kopieren und einfügen können ( **[!UICONTROL Design]** > **[!UICONTROL Auto-Complete]** > **[!UICONTROL Form Source]**).

Siehe [Kopieren des HTML-Codes des Suchformulars in die...](../c-about-auto-complete.md#task_A3A01EA800F24C0AA33902387E0362C7).

Sie können auch die Parameter festlegen, die entweder im Suchformular selbst oder über ein Skript aufgeführt werden. Zusätzlich zu den unten aufgeführten Parametern können Sie auch die Backend-Suchparameter verwenden, um die Suche zu steuern.

Siehe [CGI-Parameter für die Backend-Suche](../c-appendices/c-cgiparameters.md#reference_582E85C3886740C98FE88CA9DF7918E8).

Suchanforderungen bestehen aus einer Basis-URL. Die Basis-URL gibt an, nach welchem Konto der Kunde sucht, und eine Reihe von CGI-Parametern (Schlüssel-Wert-Paare), die angeben, wie die gewünschten Suchergebnisse für das zugehörige Konto zurückgegeben werden.

Die Basis-URL ist mit einem bestimmten Konto und einer gestaffelten oder Live-Umgebung verknüpft. Sie können mehrere Aliase für die Basis-URL von Ihrem Kundenbetreuer anfordern. Beispielsweise kann eine Firma namens Megacorp zwei Basis-URLs mit ihrem Konto verknüpft sein: `https://search.megacorp.com` und `https://stage.megacorp.com`. Die erste URL durchsucht ihren Liveindex und die zweite URL sucht ihren gestaffelten Index.

Es werden drei Formate von CGI-Parametern unterstützt. Standardmäßig ist Ihr Konto so konfiguriert, dass CGI-Parameter wie im folgenden Beispiel mit einem Semikolon getrennt werden:

`https://search.megacorp.com?q=shoes;page=2`

Wenn Sie es vorziehen, können Sie Ihren Kundenbetreuer dazu veranlassen, Ihr Konto so zu konfigurieren, dass zur Trennung der CGI-Parameter ein kaufmännisches kaufmännisches kaufmännisches Und verwendet wird, wie im folgenden Beispiel:

`https://search.megacorp.com?q=shoes&page=2`

Ein drittes Format, das so genannte SEO-Format, wird ebenfalls unterstützt, wenn anstelle des Trennzeichens und Gleichheitszeichens ein Schrägstrich `/` verwendet wird, wie im folgenden Beispiel:

`https://search.megacorp.com/q/shoes/page/2`

Jedes Mal, wenn das SEO-Format zum Senden einer Anforderung verwendet wird, werden alle Ausgabelinks im gleichen Format zurückgegeben.

| Parameter für die geführte Suche | Beispiel | Beschreibung |
|--- |--- |--- |
| q | `q=string` | Gibt die Abfrage-Zeichenfolge für die Suche an. Dieser Parameter wird dem Backend-Suchparameter `sp_q` zugeordnet.  Siehe [CGI-Parameter für die Backend-Suche](../c-appendices/c-cgiparameters.md#reference_582E85C3886740C98FE88CA9DF7918E8). |
| q# | `q#=string` | Facting (Suche innerhalb eines bestimmten Felds) erfolgt über nummerierte q- und x-Parameter.  Der Parameter q definiert den Begriff, nach dem Sie in der Facette suchen, wie er durch den entsprechenden Parameter &quot;x&quot;gekennzeichnet ist.<br>Wenn Sie z. B. zwei Facetten haben, die Größe und Farbe heißen, können Sie z. B. q1=small;x1=size;q2=red;x2=color haben.  Dieser Parameter wird den Backend-Suchparametern `sp_q_exact_#` zugeordnet.  <br>Siehe CGI-Parameter für die  [Backend-Suche](../c-appendices/c-cgiparameters.md#reference_582E85C3886740C98FE88CA9DF7918E8). |
| x nicht unterstützt# | `q#=string` | Facting (Suche innerhalb eines bestimmten Felds) erfolgt über nummerierte q- und x-Parameter.  Der Parameter q definiert den Begriff, nach dem Sie in der Facette suchen, wie er durch den entsprechenden Parameter &quot;x&quot;gekennzeichnet ist. <br>Wenn Sie z. B. zwei Facetten haben, die Größe und Farbe heißen, können Sie z. B. q1=small;x1=size;q2=red;x2=color haben.  Dieser Parameter wird den Backend-Suchparametern `sp_x_#` zugeordnet.  <br>Siehe CGI-Parameter für die  [Backend-Suche](../c-appendices/c-cgiparameters.md#reference_582E85C3886740C98FE88CA9DF7918E8). |
| Erfassung | `collection=string` | Gibt die für die Suche zu verwendende Sammlung an.  Dieser Parameter wird dem Backend-Suchparameter `sp_k` zugeordnet.  Siehe [CGI-Parameter für die Backend-Suche](../c-appendices/c-cgiparameters.md#reference_582E85C3886740C98FE88CA9DF7918E8). |
| count | `count=number` | Gibt die Gesamtanzahl der angezeigten Ergebnisse an.  Die Standardeinstellung ist in [!UICONTROL Settings ] > [!UICONTROL Searching ] > [!UICONTROL Searches ] definiert. .  Dieser Parameter wird dem Backend-Suchparameter `sp_c` zugeordnet.  Siehe [CGI-Parameter für die Backend-Suche](../c-appendices/c-cgiparameters.md#reference_582E85C3886740C98FE88CA9DF7918E8). |
| Seite | `page=number` | Gibt die Seite der zurückgegebenen Ergebnisse an. |
| rank | `rank=field` | Gibt das Rankenfeld an, das für das statische Rang verwendet werden soll.  Das Feld muss ein Feld vom Typ Rang mit einer Relevanz größer als 0 sein.  Dieser Parameter wird dem Backend-Parameter `sp_sr` zugeordnet.  Siehe [CGI-Parameter für die Backend-Suche](../c-appendices/c-cgiparameters.md#reference_582E85C3886740C98FE88CA9DF7918E8). |
| sortieren | `sort=number` | Gibt die Sortierreihenfolge an.<br>&quot;0&quot;ist der Standardwert und wird nach Relevanzwert sortiert; &quot;1&quot; sortiert nach Datum; &quot;-1&quot;wird nicht sortiert.  Benutzer können einen Feldnamen für den Wert des Parameters `sp_s` angeben.  Beispielsweise sortiert `sp_s=title` die Ergebnisse nach den Werten, die im Titelfeld enthalten sind. Wenn ein Feldname für den Wert eines Parameters ` sp_s ` verwendet wird, werden die Ergebnisse nach diesem Feld sortiert und dann nach Relevanz untergeordnet.  Um diese Funktion zu aktivieren, klicken Sie auf [!UICONTROL Settings ] > [!UICONTROL Metadata ] > [!UICONTROL Definitions ]. Klicken Sie auf der Seite &quot;Definitionen&quot;auf [!UICONTROL Add New Field ] oder klicken Sie für einen bestimmten Feldnamen auf [!UICONTROL Edit ]. Wählen Sie in der Dropdown-Liste [!UICONTROL Sorting ] entweder [!UICONTROL Ascending ] oder [!UICONTROL Descending ] aus. Dieser Parameter wird dem Backend-Suchparameter `sp_s` zugeordnet. <br>Siehe CGI-Parameter für die  [Backend-Suche].(../c-appendices/c-cgiparameters.md#reference_582E85C3886740C98FE88CA9DF7918E8). |

## CGI-Parameter für die Backend-Suche {#reference_582E85C3886740C98FE88CA9DF7918E8}

Kunden interagieren in der Regel mit einer Präsentationsebene, der so genannten &quot;geführten Suche&quot;. Theoretisch ist es jedoch möglich, die Ebene der geführten Suche zu überspringen und mit der Backend-Core-Suche direkt mit den auf dieser Seite beschriebenen CGI-Parametern zu interagieren.

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
   <td colname="col3"> <p> <code>sp_a= string </code> </p> </td> 
   <td colname="col4"> <p>Gibt die Kontonummer-Zeichenfolge an. Dieser Parameter ist erforderlich und muss eine gültige Kontonummer-Zeichenfolge sein. Sie finden die Zeichenfolge Ihrer Kontonummer unter <span class="uicontrol"> Einstellungen </span> &gt; <span class="uicontrol"> Kontooptionen </span> &gt; <span class="uicontrol"> Kontoeinstellungen </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>2 </p> </td> 
   <td colname="col2"> <p>sp_advanced </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <code>sp_advanced= 0 or 1 </code> </p> </td> 
   <td colname="col4"> <p>Wenn <code>sp_advanced=1 </code> mit einer Abfrage gesendet wird, wird der gesamte Code zwischen dem <code>&lt;search-if-advanced&gt; </code>-Tag und dem <code>&lt;/search-if-advanced&gt; </code>-Tag in der Suchvorlage für das Suchformular verwendet. Der gesamte Code zwischen dem Tag <code>&lt;search-if-not-advanced&gt; </code> und dem Tag <code>&lt;/search-if-not-advanced&gt; </code> wird ignoriert. Wenn <code>sp_advanced=0 </code> (oder ein anderer Wert) gesendet wird, wird der Vorlagenblock &lt;search-if-advanced&gt; ignoriert und der Vorlagenblock &lt;search-if-not-advanced&gt; verwendet. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>3 </p> </td> 
   <td colname="col2"> <p>sp_c </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <code>sp_c= number </code> </p> </td> 
   <td colname="col4"> <p>Gibt die Gesamtanzahl der anzuzeigenden Ergebnisse an. Die Standardeinstellung ist „10“. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>4 </p> </td> 
   <td colname="col2"> <p>sp_context_field </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <code> sp_context_field= <i>field</i> </code> </p> </td> 
   <td colname="col4"> <p>Erfasst Kontextinformationen für das angegebene Feld. Die erfassten Informationen werden in den Suchergebnissen mithilfe des Vorlagentags <code>&lt;search-context&gt; </code> ausgegeben. Der Standardwert lautet <code>body </code>.  </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>5 </p> </td> 
   <td colname="col2"> <p>sp_d </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <code>sp_d= type </code> </p> </td> 
   <td colname="col4"> <p>Gibt den Typ der zu durchsuchenden Datumsbereiche an. Mögliche Werte für den Typ sind vorhanden, d. h., keine Suche nach Datumsbereichen, benutzerspezifisch. Dies bedeutet, dass der Wert von <code>sp_date_range </code> zur Bestimmung der zu suchenden Daten und spezifisch verwendet werden sollte. Dies bedeutet, dass die Werte in <code>sp_start_day </code>, <code>sp_start_month </code>, <code>sp_start_year </code>, <code>sp_end_day </code>, <code>sp_end_month </code> und <code>sp_end_year </code> zur Bestimmung des zu suchenden Datumsbereichs verwendet werden. <code>sp_d </code> ist nur erforderlich, wenn Ihr Suchformular die Option zur Suche entweder nach einem benutzerdefinierten Bereich (als  <code>sp_date_range </code>benutzerspezifischen Bereich) oder nach einem bestimmten Beginn- und Enddatumsbereich enthält. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>6 </p> </td> 
   <td colname="col2"> <p> </p> </td> 
   <td colname="col03"> <p> sp_d_# </p> </td> 
   <td colname="col3"> <p> <code>sp_d_#= type </code> </p> </td> 
   <td colname="col4"> <p>Gibt den Typ der Datumsbereichssuche für die entsprechende <code>sp_q_# </code>-Abfrage an. Das "#"wird durch eine Zahl zwischen 1 und 16 ersetzt (z. B. gilt <code>sp_d_8 </code> für die nummerierte Abfrage <code>sp_q_8 </code>). </p> <p>Sie können <code>type </code> auf beliebige Werte einstellen. Dies bedeutet, dass keine Suche nach Datumsbereichen durchgeführt wird, benutzerspezifisch. Dies weist darauf hin, dass der Wert von <code>sp_date_range_# </code> zur Bestimmung der zu suchenden Daten verwendet wird. Spezifische Werte geben an, dass die Werte in <code>sp_q_min_day_# </code>, <code>sp_q_min_month_# </code>, <code>sp_q_min_year_# </code>, <code>sp_q_max_day_# </code>, <code>sp_q_max_month_# </code> und <code>sp_q_max_year_# </code> zur Bestimmung des Datumsbereichs verwendet werden sollten. Die Verwendung von <code>sp_d_# </code> ist nur erforderlich, wenn Ihr Suchformular die Möglichkeit enthält, entweder nach einem benutzerdefinierten Bereich (über <code>sp_date_range_# </code>) oder nach einem bestimmten Beginn und einem bestimmten Enddatumsbereich zu suchen. </p> </td> 
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
   <td colname="col4"> <p>Gibt einen vordefinierten Datumsbereich an, der auf die entsprechende <code>sp_q_# </code>-Abfrage angewendet werden soll. Das "#"wird durch eine Zahl zwischen 1 und 16 ersetzt (z. B. gilt <code>sp_date_range_8 </code> für die nummerierte Abfrage <code>sp_q_8 </code>). </p> <p>Werte größer als oder gleich null geben die Anzahl der Tage an, die vor dem heutigen Tag gesucht werden sollen. Beispielsweise gibt der Wert 0 heute an; Der Wert 1 gibt heute und gestern an. Der Wert 30 gibt innerhalb der letzten 30 Tage usw. an. </p> <p>Werte unter null geben einen benutzerdefinierten Bereich wie folgt an: </p> <p>-1 = "Keine", genau wie bei Angabe eines Datumsbereichs. </p> <p>-2 = "Diese Woche", die von Sonntag bis Samstag der aktuellen Woche durchsucht. </p> <p>-3 = "Letzte Woche", die von Sonntag bis Samstag der Woche vor der aktuellen Woche durchsucht wird. </p> <p>-4 = "Dieser Monat", der Daten innerhalb des aktuellen Monats durchsucht. </p> <p>-5 = "Letzter Monat", der Daten innerhalb des Monats vor dem aktuellen Monat durchsucht. </p> <p>-6 = "Dieses Jahr", das Daten innerhalb des aktuellen Jahres durchsucht. </p> <p>-7 = "Letztes Jahr", das Daten innerhalb des Jahres vor dem aktuellen Jahr durchsucht. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>9 </p> </td> 
   <td colname="col2"> <p>sp_dedupe_field </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <code> sp_dedupe_field= <i>fieldname</i> </code> </p> </td> 
   <td colname="col4"> <p>Gibt ein einzelnes Feld an, in dem die Suchergebnisse dedupliziert werden sollen. Alle Duplikat-Ergebnisse in diesem Feld werden aus den Suchergebnissen entfernt. Beispiel: Wenn für <code>sp_dedupe_field=title </code> nur das oberste Ergebnis für einen bestimmten Titel in den Suchergebnissen angezeigt wird (keine zwei Ergebnisse haben identischen Inhalt im Titelfeld). Bei Feldern mit mehreren Werten (Zulassungsliste) wird der gesamte Feldinhalt zum Vergleich verwendet. Es kann nur ein Feld angegeben werden. Ein "table-qualifier"ist im Feldnamen nicht zulässig. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>10 </p> </td> 
   <td colname="col2"> <p>sp_e </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <code>sp_e= number </code> </p> </td> 
   <td colname="col4"> <p>Gibt an, dass für alle Wörter aus der Abfrage-Zeichenfolge mit mehr als Zeichen eine automatische Platzhaltererweiterung erfolgen soll. Mit anderen Worten, <code>sp_e=5 </code> gibt an, dass Wörter mit 5 oder mehr Zeichen, wie "Abfrage"oder "Nummer", mit dem Platzhalterzeichen "*"erweitert werden sollten, wodurch die Suche einer Suche nach "Abfrage*"oder "Nummer*"entspricht. Wörter mit weniger Zeichen werden nicht erweitert, sodass eine Suche nach "Wort"keine automatische Platzhaltererweiterung hätte. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>11 </p> </td> 
   <td colname="col2"> <p> </p> </td> 
   <td colname="col03"> <p> sp_e_# </p> </td> 
   <td colname="col3"> <p> <code>sp_e_#= number </code> </p> </td> 
   <td colname="col4"> <p>Gibt an, dass die automatische Platzhaltererweiterung für alle Wörter aus der entsprechenden Abfrage-Zeichenfolge <code>sp_q_# </code> mit mehr als Zeichen erfolgt. Mit anderen Worten, <code>sp_e_2=5 </code> gibt an, dass Wörter mit fünf oder mehr Zeichen in der <code>sp_q_2 </code>-Abfrage-Zeichenfolge, wie "Abfrage"oder "Zahl", mit dem Platzhalterzeichen "<code>* </code>"erweitert werden sollten, sodass die Suche einer Suche nach "Abfrage*"oder "Nummer*"entspricht. Wörter mit weniger Zeichen werden nicht erweitert, sodass eine Suche nach "Wort"in <code>sp_q_2 </code> keine automatische Platzhaltererweiterung hätte. </p> </td> 
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
   <td colname="col3"> <p> <code>sp_f= string </code> </p> </td> 
   <td colname="col4"> <p>Gibt den Zeichensatz der Parameterzeichenfolgen der Abfrage an (z. B. <code>sp_q </code>). Diese Zeichenfolge muss immer mit dem Zeichensatz der Seite übereinstimmen, die das Suchformular enthält. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>14 </p> </td> 
   <td colname="col2"> <p>sp_field_table </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <code> sp_field_ table=table: field,field... </code> </p> </td> 
   <td colname="col4"> <p>Definiert eine logische Datentabelle, die aus den angegebenen Feldern besteht. Beispielsweise würde eine Tabelle mit dem Namen "items"aus den Feldern "color", "size"und "price"wie folgt definiert: </p> <p> <code>sp_field_table=items:color,size,price </code> </p> <p>Logische Tabellen sind besonders hilfreich in Verbindung mit Feldern, in denen "Zulassungslisten" markiert ist (unter <span class="uicontrol"> Einstellungen </span> &gt; <span class="uicontrol"> Metadaten </span> &gt; <span class="uicontrol"> Definitionen </span>). Alle CGI-Parameter und Vorlagen-Tags, die einen Feldnamen als Wert annehmen, können optional einen Tabellennamen gefolgt von einem ""angeben. vor dem Feldnamen (z. B. <code>sp_x_1=tablename.fieldname </code>). </p> <p>Wenn Sie beispielsweise nach Dokumenten suchen möchten, die ein oder mehrere rote Elemente in der Größe "groß"enthalten (wobei Elemente als parallele Zeilen mit Metadaten dargestellt werden), können Sie Folgendes verwenden: </p> <p> <code> sp_q_exact_1=red&amp;sp_x_1=items.color&amp; sp_q_exact_2=large&amp;sp_x_2=items.size&amp;sp_field_table=items:color,size,price </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>15 </p> </td> 
   <td colname="col2"> sp_i </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> </p></td><td colname="col4"><p></p><p></p><p><code>sp_i=1 </code><code>sp_i=2 </code></p></td></tr><tr><td colname="col1"><p></p></td><td colname="col2"><p></p></td><td colname="col03"><p></p></td><td colname="col3"><p><code>sp_k= string </code></p></td><td colname="col4"><p></p><p></p></td></tr><tr><td colname="col1"><p></p></td><td colname="col2"><p></p></td><td colname="col03"><p></p></td><td colname="col3"><p><code>sp_l= string </code></p></td><td colname="col4"><p><code>sp_q </code><code>string </code></p></td></tr><tr><td colname="col1"><p></p></td><td colname="col2"><p></p></td><td colname="col03"><p></p></td><td colname="col3"><p><code>sp_literal= 0 or 1 </code></p></td><td colname="col4"><p><code>sp_literal=1 </code></p><p><code>sp_literal=0 </code></p><p></p></td></tr><tr><td colname="col1"><p></p></td><td colname="col2"><p></p></td><td colname="col03"><p></p></td><td colname="col3"><p><code>sp_m= number </code></p></td><td colname="col4"><p></p></td></tr><tr><td colname="col1"><p></p></td><td colname="col2"><p></p></td><td colname="col03"><p></p></td><td colname="col3"><p><code>sp_n= number </code></p></td><td colname="col4"><p></p></td></tr><tr><td colname="col1"><p></p></td><td colname="col2"><p></p></td><td colname="col03"><p></p></td><td colname="col3"><p><code>sp_not_found_page= url </code></p></td><td colname="col4"><p></p></td></tr><tr><td colname="col1"><p></p></td><td colname="col2"><p></p></td><td colname="col03"><p></p></td><td colname="col3"><p><code>sp_p= any/all/phrase </code></p></td><td colname="col4"><p><code>any </code><code>all </code><code>phrase </code></p><p><code>phrase </code><code>all </code><code>sp_p </code></p><p></p><p></p><p><code>sp_p </code></p><p></p></td></tr><tr><td colname="col1"><p></p></td><td colname="col2"><p></p></td><td colname="col03"><p></p></td><td colname="col3"><p><code>sp_p_#= any/all/phrase </code></p></td><td colname="col4"><p><code>sp_q_# </code><code>sp_p_8 </code><code>sp_q_8 </code><code>any </code><code>all </code><code>phrase </code></p><p><code>all </code><code>phrase </code><code>sp_p_# </code><code>any </code></p></td></tr><tr><td colname="col1"><p></p></td><td colname="col2"><p></p></td><td colname="col03"><p></p></td><td colname="col3"><p><code> sp_pt= <i>exact/equivalent/compatible</i> </code></p></td><td colname="col4"><p><code>exact </code><code>equivalent </code><code>compatible </code><code>sp_p </code><code>exact </code><code>sp_p </code><code>all </code><code>phrase </code><code>equivalent </code><code>sp_pt </code><code>compatible </code></p></td></tr><tr><td colname="col1"><p></p></td><td colname="col2"><p></p></td><td colname="col03"><p></p></td><td colname="col3"><p><code> sp_pt_#= <i>exact/equivalent/compatible</i> </code></p></td><td colname="col4"><p><code>sp_q_# </code><code>sp_p_8 </code><code>sp_q_8 </code><code>exact </code><code>equivalent </code><code>exact </code><code>compatible </code><code>sp_p_# </code><code>exact </code><code>sp_p_# </code><code>equivalent </code><code>sp_pt_# </code><code>compatible </code></p></td></tr><tr><td colname="col1"><p></p></td><td colname="col2"><p></p></td><td colname="col03"><p></p></td><td colname="col3"><p><code>sp_q= string </code></p></td><td colname="col4"><p></p></td></tr><tr><td colname="col1"><p></p></td><td colname="col2"><p></p></td><td colname="col03"><p></p></td><td colname="col3"><p><code>sp_q_#= text </code></p></td><td colname="col4"><p><code>sp_q_# </code><code>sp_q_1 </code><code>sp_q_16 </code></p><p></p><p><code class="syntax html"> Search&nbsp;for:&nbsp;&lt;input&nbsp;type="text"&nbsp;name="sp_q"&nbsp;value="great"&gt; 
      Search&nbsp;for:&nbsp;&lt;input&nbsp;type="text"&nbsp;name="sp_q_1"&nbsp;value="books"&gt; </code></p></td></tr><tr><td colname="col1"><p></p></td><td colname="col2"><p></p></td><td colname="col03"><p></p></td><td colname="col3"><p><code>sp_q_day= integer value </code></p><p><code>sp_q_month= integer value </code></p><p><code>sp_q_year= integer value </code></p><p><code>sp_q_day_#= integer value </code></p><p><code>sp_q_month_#= integer value </code></p><p><code>sp_q_year_#= integer value </code></p></td><td colname="col4"><p><code>sp_q_day </code><code>sp_q_month </code><code>sp_q_year </code><code>sp_q </code></p><p><code># </code><code>sp_q_day_6 </code><code>sp_q_6 </code></p><p><code>PublishDate </code></p><p><code class="syntax html"> &lt;input&nbsp;type="hidden"&nbsp;name="sp_x_1"&nbsp;value="PublishDate"&gt; Search&nbsp;for:&nbsp;&lt;input&nbsp;type="text"&nbsp;name="sp_q"&nbsp;value="orange"&gt;On&nbsp;:&nbsp;&lt;input&nbsp;type="text"&nbsp;name="sp_q_day_1"&nbsp;size="2"&nbsp;value="1"&gt;&nbsp;Day&lt;input&nbsp;type="text"&nbsp;name="sp_q_month_1"&nbsp;size="2"&nbsp;value="1"&gt;&nbsp;Month &lt;input&nbsp;type="text"&nbsp;name="sp_q_year_1"&nbsp;size="4"&nbsp;value="2000"&gt;&nbsp;Year&nbsp; </code></p></td></tr><tr><td colname="col1"><p></p></td><td colname="col2"><p></p></td><td colname="col03"><p></p></td><td colname="col3"><p><code> sp_q_location=<i>latitude/longitude</i> OR <i>areacode</i> OR <i>zipcode</i> </code></p><p><code> sp_q_location_#= <i>latitude/longitude</i> OR <i>areacode</i> OR <i>zipcode</i> </code></p></td><td colname="col4"><p><code>sp_q_location </code><code>sp_q_location_# </code><code># </code></p><p></p><p></p></td></tr><tr><td colname="col1"><p></p></td><td colname="col2"><p></p></td><td colname="col03"><p></p></td><td colname="col3"><p><code> sp_q_max_relevant_distance= <i>value</i> </code></p><p><code> sp_q_max_relevant_distance_#= <i>value</i> </code></p></td><td colname="col4"><p><code>sp_q_max_relevant_distance </code><code>sp_q_max_relevant_distance_# </code><code># </code></p><p><code>sp_q_max_relevant_distance </code></p><p><code>sp_q_max_relevant_distance_# </code></p><p></p></td></tr><tr><td colname="col1"><p></p></td><td colname="col2"><p></p><p></p></td><td colname="col03"><p></p><p></p></td><td colname="col3"><p><code> sp_q_min_day=<i>integer value</i> </code></p><p><code> sp_q_min_month=<i>integer value</i> </code></p><p><code> sp_q_min_year=<i>integer value</i> </code></p><p><code> sp_q_max_day=<i>integer value</i> </code></p><p><code> sp_q_max_month=<i>integer value</i> </code></p><p><code> sp_q_max_year=<i>integer value</i> </code></p><p><code> sp_q_min_day_#=<i>integer value</i> </code></p><p><code> sp_q_min_month_#=<i>integer value</i> </code></p><p><code> sp_q_min_year_#=<i>integer value</i> </code></p><p><code> sp_q_max_day_#=<i>integer value</i> </code></p><p><code> sp_q_max_month_#=<i>integer value</i> </code></p><p><code> sp_q_max_year_#=<i>integer value</i> </code></p></td><td colname="col4"><p><code>sp_q_min_day </code><code>sp_q_min_month </code><code>sp_q_min_year </code><code>sp_q_max_day </code><code>sp_q_max_month </code><code>sp_q </code></p><p><code># </code><code>sp_q_min_day_6 </code><code>sp_q_6 </code></p><p></p><p><code>PublishDate </code></p><p><code class="syntax html"> &lt;input&nbsp;type="hidden"&nbsp;name="sp_x_1"&nbsp;value="PublishDate"&gt;Search&nbsp;for:&nbsp;&lt;input&nbsp;type="text"&nbsp;name="sp_q"&nbsp;value="orange"&gt;Between:&nbsp;&lt;input&nbsp;type="text"&nbsp;name="sp_q_min_day_1"&nbsp;size="2"&nbsp;value="1"&gt;&nbsp;Start&nbsp;Day&lt;input&nbsp;type="text"&nbsp;name="sp_q_min_month_1"&nbsp;size="2"&nbsp;value="1"&gt;&nbsp;Start&nbsp;Month 
      &lt;input&nbsp;type="text"&nbsp;name="sp_q_min_year_1"&nbsp;size="4"&nbsp;value="2000"&gt;&nbsp;Start&nbsp;Year 
      And:&nbsp;&lt;input&nbsp;type="text"&nbsp;name="sp_q_max_day_1"&nbsp;size="2"&nbsp;value="31"&gt;&nbsp;End&nbsp;Day 
      &lt;input&nbsp;type="text"&nbsp;name="sp_q_max_month_1"&nbsp;size="2"&nbsp;value="12"&gt;&nbsp;End&nbsp;Month 
      &lt;input&nbsp;type="text"&nbsp;name="sp_q_max_year_1"&nbsp;size="4"&nbsp;value="2000"&gt;&nbsp;End&nbsp;Year </code></p></td></tr><tr><td colname="col1"><p></p></td><td colname="col2"><p></p></td><td colname="col03"><p></p></td><td colname="col3"><p><code>sp_q_min= value </code></p><p><code>sp_q_max= value </code></p><p><code>sp_q_min_#= value </code></p><p><code>sp_q_max_#= value </code></p><p><code>sp_q_exact_#=value </code></p></td><td colname="col4"><p><code>sp_q_min </code><code>sp_q_max </code><code>sp_q_exact </code><code>sp_q </code></p><p><code># </code><code>sp_q_min_8 </code><code>sp_q_8 </code></p><p><code>sp_q_exact_# </code><code>sp_q_min_# </code><code>sp_q_max_# </code><code>sp_q_exact_# </code><code>sp_q_min_# </code><code>sp_q_max_# </code></p><p><code>sp_q_min_# </code><code>sp_q_max_# </code><code>sp_q_exact_# </code><code>...&amp;sp_q_exact_1=green|red&amp;sp_x_1=color </code></p></td></tr><tr><td colname="col1"><p></p></td><td colname="col2"><p></p></td><td colname="col03"><p></p></td><td colname="col3"><p><code>sp_q_nocp= 1 or 0 </code></p><p><code>sp_q_nocp_#= 1 or 0 </code></p></td><td colname="col4"><p><code>0 </code></p><p><code>1 </code></p><p><code>sp_q_nocp </code><code>sp_q </code><code># </code><code>sp_q_nocp_8 </code><code>sp_q_8 </code></p><p></p></td></tr><tr><td colname="col1"><p></p></td><td colname="col2"><p></p></td><td colname="col03"><p></p></td><td colname="col3"><p><code>sp_q_required= 1 or 0 or -1 </code></p><p><code>sp_q_required_#= 1 or 0 or -1 </code></p></td><td colname="col4"><p></p><p><code>sp_q_required </code><code>sp_q </code></p><p><code># </code><code>sp_q_required_8 </code><code>sp_q_8 </code></p><p></p><p><code class="syntax html"> &lt;input&nbsp;type="hidden"&nbsp;name="sp_x_1"&nbsp;value="platform"&gt; 
      Search&nbsp;for:&nbsp;&lt;input&nbsp;type="text"&nbsp;name="sp_q"&nbsp;value="calc"&gt; 
      Exclude:&nbsp;&lt;input&nbsp;type="text"&nbsp;name="sp_q_1"&nbsp;value="mac&nbsp;win&nbsp;all"&gt; 
      &lt;input&nbsp;type="hidden"&nbsp;name="sp_q_required_1"&nbsp;value="-1"&gt; </code></p></td></tr><tr><td colname="col1"><p></p></td><td colname="col2"><p></p></td><td colname="col03"><p></p></td><td colname="col3"><p><code> sp_redirect_ 
      if_one_result= <i>0 or 1</i> </code></p></td><td colname="col4"><p></p></td></tr><tr><td colname="col1"><p></p></td><td colname="col2"><p></p></td><td colname="col03"><p></p></td><td colname="col3"><p><code>sp_referrer= url </code></p></td><td colname="col4"><p></p><p></p></td></tr><tr><td colname="col1"><p></p></td><td colname="col2"><p></p></td><td colname="col03"><p></p></td><td colname="col3"><p></p></td><td colname="col4"><p><code>ro </code></p><p></p><p><code>sp_ro=body:10 </code></p><p></p><p><code>sp_ro=body:9|title:9 </code></p><p><p><code>sp_ro=title:10 </code><code>title </code><code>sp_ro </code><code>sp_ro </code></p></p><p></p><p></p></td></tr><tr><td colname="col1"><p></p></td><td colname="col2"><p></p></td><td colname="col03"><p></p></td><td colname="col3"><p><code>sp_s= number </code></p></td><td colname="col4"><p></p><p><code>sp_s </code><code>sp_s=title </code><code>sp_s </code></p><p></p><p><code>sp_s </code></p><p><code class="syntax html"> &lt;input&nbsp;type="hidden"&nbsp;name="sp_s"&nbsp;value="artist"&gt; 
      &lt;input&nbsp;type="hidden"&nbsp;name="sp_s"&nbsp;value="album"&gt; 
      &lt;input&nbsp;type="hidden"&nbsp;name="sp_s"&nbsp;value="track"&gt; 
      Search&nbsp;for:&nbsp;&lt;input&nbsp;type="text"&nbsp;name="sp_q"&nbsp;value="Music&nbsp;Search"&gt; </code></p><p><code>sp_field_table </code></p><p></p><p></p></td></tr><tr><td colname="col1"><p></p></td><td colname="col2"><p></p></td><td colname="col03"><p></p></td><td colname="col3"><p><code>sp_sr= field </code></p></td><td colname="col4"><p><code>sp_sr </code></p><p><code>sp_sr </code><code>&lt;input type="hidden" name="sp_sr" value=""&gt; </code></p></td></tr><tr><td colname="col1"><p></p></td><td colname="col2"><p></p></td><td colname="col03"><p></p></td><td colname="col3"><p><code>sp_sfvl_field= string </code></p></td><td colname="col4"><p><code>search-field-value-list</code></p><p><code>sp_sfvl_field </code></p></td></tr><tr><td colname="col1"><p></p></td><td colname="col2"><p></p></td><td colname="col03"><p></p></td><td colname="col3"><p></p></td><td colname="col4"><p><code>search-field-value-list </code></p><p><code>dynamic-facet-field-count </code><code>dynamic-facet-field-count </code></p><p><code>sp_sfvl_df_count </code><code>dynamic-facet-field-count </code><code>sp_sfvl_df_count </code><code>sp_sfvl_df_count </code></p><p></p></td></tr><tr><td colname="col1"><p></p></td><td colname="col2"><p></p></td><td colname="col03"><p></p></td><td colname="col3"><p></p><p></p></td><td colname="col4"><p></p><p></p><p></p></td></tr><tr><td colname="col1"><p></p></td><td colname="col2"><p></p></td><td colname="col03"><p></p></td><td colname="col3"><p></p><p></p></td><td colname="col4"><p></p><p><p><code>sp_sfvl_df_count </code><code>sp_sfvl_df_include </code><code>sp_sfvl_df_include </code><code>sp_sfvl_df_count </code></p></p><p></p></td></tr><tr><td colname="col1"><p></p></td><td colname="col2"><p></p></td><td colname="col03"><p></p></td><td colname="col3"><p><code>sp_staged= 0 or 1 </code></p></td><td colname="col4"><p><code>sp_staged=1 </code></p><p></p></td></tr><tr><td colname="col1"><p></p></td><td colname="col2"><p></p></td><td colname="col03"><p></p></td><td colname="col3"><p><code>sp_start_day= number </code></p><p><code>sp_start_month= number </code></p><p><code>sp_start_year= number </code></p></td><td colname="col4"><p></p></td></tr><tr><td colname="col1"><p></p></td><td colname="col2"><p></p></td><td colname="col03"><p></p></td><td colname="col3"><p><code>sp_suggest_q= number </code></p></td><td colname="col4"><p><code>sp_suggest_q </code><code>sp_q[_#] </code></p><p><code>sp_suggest_q </code><code>sp_q </code></p><p><code>sp_suggest_q=1 </code><code>sp_q_1 </code></p></td></tr><tr><td colname="col1"><p></p></td><td colname="col2"><p></p></td><td colname="col03"><p></p></td><td colname="col3"><p><code>sp_t= string </code></p></td><td colname="col4"><p></p><p></p><p></p><p></p></td></tr><tr><td colname="col1"><p></p></td><td colname="col2"><p></p></td><td colname="col03"><p></p></td><td colname="col3"><p><code>sp_trace= 0 or 1 </code></p></td><td colname="col4"><p><code>sp_stage=1 </code></p><p></p><p><p></p></p></td></tr><tr><td colname="col1"><p></p></td><td colname="col2"><p></p></td><td colname="col03"><p></p></td><td colname="col3"><p><code> sp_w= <i>sound-alike-enable</i> </code></p><p><code> sp_w_control=<i>sound-alike-control</i> </code></p></td><td colname="col4"><p></p><p></p><p></p><p></p><p></p><code>sp_w_control </code></p><p><code>sp_w_control=0 </code><code>sp_w </code></p><p><code class="syntax html"> &lt;input&nbsp;type=hidden&nbsp;name="sp_w_control"&nbsp;value="0"&gt;&lt;input&nbsp;type=checkbox&nbsp;name="sp_w"&nbsp;value="exact"&gt;No&nbsp;Sound-Alike&nbsp;matching </code></p><p><code>sp_w_control=1 </code><code>sp_w </code></p><p><code class="syntax html"> &lt;input&nbsp;type=hidden&nbsp;name="sp_w_control"&nbsp;value="1"&gt;&lt;input&nbsp;type=checkbox&nbsp;name="sp_w"&nbsp;value="alike"&gt;Sound-Alike&nbsp;matching </code></p><p><code>sp_w_control </code><code>sp_w </code></p><p></p></td></tr><tr><td colname="col1"><p></p></td><td colname="col2"><p></p></td><td colname="col03"><p></p></td><td colname="col3"><p><code>sp_x= field </code></p></td><td colname="col4"><p><code>sp_q </code><code>sp_x </code></p><p></p><p><code>sp_x </code></p><p></p><p><code>sp_x=any </code><code>sp_x </code></p><p><code>sp_x </code></p><p><code class="syntax html"> &lt;input&nbsp;type="hidden"&nbsp;name="sp_x"&nbsp;value="title"&gt;&lt;input&nbsp;type="hidden"&nbsp;name="sp_x"&nbsp;value="author"&gt;Search&nbsp;for:&nbsp;&lt;input&nbsp;type="text"&nbsp;name="sp_q"&nbsp;value="Great&nbsp;Books"&gt; </code></p></td></tr><tr><td colname="col1"><p></p></td><td colname="col2"><p></p></td><td colname="col03"><p></p></td><td colname="col3"><p><code>sp_x_#= field-name </code></p></td><td colname="col4"><p><code>sp_q_# </code><code> # </code><code>sp_x_8 </code></p><p><code>sp_x_# </code></p><p></p><p><code class="syntax html"> Search&nbsp;for:&nbsp;&lt;input&nbsp;type="text"&nbsp;name="sp_q"&nbsp;value="great"&gt;&lt;input&nbsp;type="hidden"&nbsp;name="sp_x_1"&nbsp;value="author"&gt;Search&nbsp;only&nbsp;documents&nbsp;written&nbsp;by:&nbsp;&lt;input&nbsp;type="text"&nbsp;name="sp_q_1"&nbsp;value="Fitzgerald"&gt; </code></p><p><code>sp_x </code><code>sp_x_# </code></p><p></p><p><code class="syntax html"> &lt;input&nbsp;type="hidden"&nbsp;name="sp_x_1"&nbsp;value="body"&gt;&lt;input&nbsp;type="hidden"&nbsp;name="sp_x_1"&nbsp;value="keys"&gt;Search&nbsp;for:&nbsp;&lt;input&nbsp;type="text"&nbsp;name="sp_q_1"&nbsp;value="flower"&gt; </code></p></td></tr></tbody></table>

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

Die folgenden Formular-Abfragen zeigen `25` Ergebnisse an, die mit dem Ergebnis `10` beginnen. Zusammenfassungen werden nicht angezeigt, die Sortierreihenfolge ist nach Datum geordnet und die Sammlung mit dem Namen `support` wird verwendet. Es werden nur Dokumente zurückgegeben, die innerhalb der letzten 30 Tage datiert wurden.

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
