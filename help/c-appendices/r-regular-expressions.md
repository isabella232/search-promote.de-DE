---
description: Ein Auffrischungsbericht zur Syntax und den Regeln zum Erstellen von regulären Ausdrücken.
seo-description: Ein Auffrischungsbericht zur Syntax und den Regeln zum Erstellen von regulären Ausdrücken.
seo-title: Reguläre Ausdrücke
solution: Target
title: Reguläre Ausdrücke
topic: Appendices,Site search and merchandising
uuid: 369b54f6-372a-41de-bb5d-3ae0bd640199
translation-type: tm+mt
source-git-commit: ef818327e1cdaad79ac47575a8dfba1de3dc5c2e

---


# Regular Expressions{#regular-expressions}

Ein Auffrischungsbericht zur Syntax und den Regeln zum Erstellen von regulären Ausdrücken.

Siehe auch [Konfigurieren eines inkrementellen Indexes einer gestaffelten Website](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0).

**Syntax regulärer Ausdrücke**

<table> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Text</b> </p> </td> 
   <td colname="col2"> </td> 
   <td colname="col3"> <p>Beliebiges einzelnes Zeichen </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> </td> 
   <td colname="col2"> <p> [Zeichen] </p> </td> 
   <td colname="col3"> <p> Zeichenklasse: Zeichen </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> </td> 
   <td colname="col2"> <p> [^chars] </p> </td> 
   <td colname="col3"> <p>Zeichenklasse: Keine Zeichen </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> </td> 
   <td colname="col2"> <p> text1|text2 </p> </td> 
   <td colname="col3"> <p> Alternative: text1 oder text2 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Quantifizierer</b> </p> </td> 
   <td colname="col2"> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> </td> 
   <td colname="col2"> <p> ? </p> </td> 
   <td colname="col3"> <p> 0 oder 1 des vorhergehenden Textes </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> </td> 
   <td colname="col2"> <p> * </p> </td> 
   <td colname="col3"> <p> 0 oder N des vorhergehenden Textes (N &gt; 1) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> </td> 
   <td colname="col2"> <p> + </p> </td> 
   <td colname="col3"> <p>1 oder N des vorhergehenden Textes (N &gt; 1) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Gruppierung</b> </p> </td> 
   <td colname="col2"> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> </td> 
   <td colname="col2"> <p> (text) </p> </td> 
   <td colname="col3"> <p> Gruppierung von Text, entweder um die Ränder einer Alternative festzulegen oder um Referenzen wiederherzustellen, bei denen die n. Gruppe auf der RHS einer RewriteRule mit $N verwendet wird) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Anker</b> </p> </td> 
   <td colname="col2"> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> </td> 
   <td colname="col2"> <p> ^ </p> </td> 
   <td colname="col3"> <p> Anfang des Zeilenankers. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> </td> 
   <td colname="col2"> <p> $ </p> </td> 
   <td colname="col3"> <p> Zeilenende-Anker. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Escaping</b> </p> </td> 
   <td colname="col2"> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> </p> </td> 
   <td colname="col2"> <p>\char </p> </td> 
   <td colname="col3"> <p>Entkommen Sie dem bestimmten Zeichen. So geben Sie beispielsweise die Zeichen an ".[]()" und so weiter. </p> </td> 
  </tr> 
 </tbody> 
</table>

**Regeln zu regulären Ausdrücken**

* Ein gewöhnliches Zeichen - nicht eines der unten beschriebenen Sonderzeichen - ist ein regulärer Ausdruck mit einem Zeichen, der sich selbst entspricht.
* Ein umgekehrter Schrägstrich (\) gefolgt von einem Sonderzeichen ist ein regulärer Ausdruck mit einem Zeichen, der dem Sonderzeichen selbst entspricht. Sonderzeichen sind:

   * `.` (Punkt), `*` (Sternchen), `?` (Fragezeichen), `+` (Pluszeichen), `[` (eckige Klammer links), `|` (vertikale Linie) und `\` (umgekehrter Schrägstrich) sind immer Sonderzeichen, es sei denn, sie erscheinen in eckigen Klammern.
   * `^` (Caret oder Zirkumflex) ist besonders am Anfang eines regulären Ausdrucks, oder wenn es unmittelbar folgt links von einem Paar eckiger Klammern.
   * `$` (Dollarzeichen) ist ein Sonderzeichen am Ende eines regulären Ausdrucks.
   * `.` (period) ist ein einstelliger regulärer Ausdruck, der mit jedem Zeichen übereinstimmt, einschließlich ergänzender Codesatzzeichen mit Ausnahme von new-line.
   * Eine nicht leere Zeichenfolge aus Zeichen, die in `[ ]` (eckige Klammern links und rechts) eingeschlossen ist, ist ein regulärer Ausdruck mit einem Zeichen, einschließlich ergänzender Codesatzzeichen, in dieser Zeichenfolge.

      Wenn das erste Zeichen der Zeichenfolge jedoch ein `^` (Zirkumflex) ist, stimmt der reguläre Ausdruck mit einem Zeichen mit jedem beliebigen Zeichen überein, einschließlich ergänzender Codesatzzeichen, mit Ausnahme der neuen Zeile und der restlichen Zeichen in der Zeichenfolge.

      Diese besondere Bedeutung `^` hat nur dann eine Bedeutung, wenn sie zuerst in der Zeichenfolge vorkommt. Sie können `-` (Minuszeichen) verwenden, um einen Bereich aufeinander folgender Zeichen anzugeben, einschließlich zusätzlicher Codesatzzeichen. Beispiel: [0-9] entspricht [0123456789].

      Zeichen, die den Bereich angeben, müssen aus demselben Codesatz stammen. Wenn die Zeichen aus verschiedenen Codesätzen stammen, wird eines der Zeichen, die den Bereich angeben, zugeordnet. Diese besondere Bedeutung `-` verliert sie, wenn sie zuerst (nach einer Initial- `^`oder gegebenenfalls letzten) im String auftritt. Die `]` (rechte eckige Klammer) beendet eine solche Zeichenfolge nicht, wenn es sich um das erste Zeichen innerhalb der Zeichenfolge handelt, nach einer ersten `^`Angabe (sofern vorhanden). Beispielsweise entspricht []a-f entweder einer `]` (rechten eckigen Klammer) oder einem der ASCII-Buchstaben a bis f. Die vier oben als Sonderzeichen aufgelisteten Zeichen stehen für sich in einer solchen Zeichenfolge.

**Regeln zum Erstellen regulärer Ausdrücke aus regulären Ausdrücken mit einem Zeichen**

Sie können die folgenden Regeln verwenden, um reguläre Ausdrücke aus regulären Ausdrücken mit einem Zeichen zu erstellen:

* Ein regulärer Ausdruck mit einem Zeichen ist ein regulärer Ausdruck, der dem entspricht, was der reguläre Ausdruck mit einem Zeichen enthält.
* Ein einstelliger regulärer Ausdruck gefolgt von einem `*` (Sternchen) ist ein regulärer Ausdruck, der null oder mehr Vorkommen des einstelligen regulären Ausdrucks entspricht, bei dem es sich möglicherweise um ein zusätzliches Codesatzzeichen handelt. Bei einer beliebigen Option wird die längste Zeichenfolge links gewählt, die eine Übereinstimmung zulässt.
* Ein einstelliger regulärer Ausdruck gefolgt von einem `?` (Fragezeichen) ist ein regulärer Ausdruck, der null oder ein Vorkommen des einstelligen regulären Ausdrucks entspricht, bei dem es sich möglicherweise um ein zusätzliches Codesatzzeichen handeln kann. Bei einer beliebigen Option wird die längste Zeichenfolge links gewählt, die eine Übereinstimmung zulässt.
* Ein einstelliger regulärer Ausdruck gefolgt von einem `+` (Pluszeichen) ist ein regulärer Ausdruck, der einem oder mehreren Vorkommen des einstelligen regulären Ausdrucks entspricht, bei dem es sich möglicherweise um ein zusätzliches Codesatzzeichen handelt. Bei einer beliebigen Option wird die längste Zeichenfolge links gewählt, die eine Übereinstimmung zulässt.
* Ein regulärer Ausdruck mit einem Zeichen gefolgt von `{m}`, `{m,}`oder `{m,n}` ist ein regulärer Ausdruck, der einem Bereich von Vorkommen des regulären Ausdrucks mit einem Zeichen entspricht. Die Werte von m und n müssen nicht negative Ganzzahlen unter 256 sein. exakt `{m}` m-Vorkommen entspricht; mindestens m Vorkommen `{m,}` ; Entspricht einer beliebigen Anzahl von Vorfällen zwischen m und n einschließlich. `{m,n}` Wenn eine Auswahl vorhanden ist, stimmt der reguläre Ausdruck mit so vielen Vorkommen wie möglich überein.
* Die Verkettung regulärer Ausdrücke ist ein regulärer Ausdruck, der mit der Verkettung der Zeichenfolgen übereinstimmt, die mit jeder Komponente des regulären Ausdrucks übereinstimmen.
* Ein regulärer Ausdruck, der zwischen den Zeichensequenzen ( und ) eingeschlossen ist, ist ein regulärer Ausdruck, der mit dem Inhalt des nicht formatierten regulären Ausdrucks übereinstimmt.
* Ein regulärer Ausdruck, gefolgt von einem `|` (senkrechten Strich), gefolgt von einem regulären Ausdruck ist ein regulärer Ausdruck, der entweder dem ersten regulären Ausdruck (vor dem vertikalen Strich) oder dem zweiten regulären Ausdruck (nach dem vertikalen Strich) entspricht.

Sie können einen regulären Ausdruck auch so einschränken, dass er nur mit einem Anfangssegment oder finalen Segment einer Zeile oder mit beiden übereinstimmt.

* Ein `^` (Zirkumflex) am Anfang eines regulären Ausdrucks schränkt diesen regulären Ausdruck so ein, dass er mit einem anfänglichen Segment einer Zeile übereinstimmt.
* Ein `$` (Dollarzeichen) am Ende eines gesamten regulären Ausdrucks schränkt diesen regulären Ausdruck so ein, dass er mit dem endgültigen Segment einer Zeile übereinstimmt.
* Die Konstruktion &#39;^regulärer Ausdruck$&#39; beschränkt den regulären Ausdruck auf die Übereinstimmung mit der gesamten Zeile.

Es gibt einige vordefinierte Zeichenklassennamen, die Sie anstelle komplexer, mit Klammern versehener regulärer Ausdrücke verwenden können. Eine Ziffer kann beispielsweise durch den einstelligen regulären Ausdruck [0-9] oder durch den einstelligen regulären Ausdruck [[:digit:]] der Zeichenklasse dargestellt werden.

Die vordefinierten Zeichenklassen und ihre Bedeutung lauten wie folgt:

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Character-Klasse </p> </th> 
   <th colname="col2" class="entry"> <p>Beschreibung </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> [[:alnum:]] </p> </td> 
   <td colname="col2"> <p> Ein alphabetisches Zeichen oder eine Ziffer. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> [[:alpha:]] </p> </td> 
   <td colname="col2"> <p>Ein alphabetisches Zeichen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> [[:leer gelassen:]] </p> </td> 
   <td colname="col2"> <p>Ein Leerzeichen oder eine Registerkarte. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> [[:cntrl:]] </p> </td> 
   <td colname="col2"> <p> ein Kontrollcode; nicht druckbares Zeichen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> [[:digit:]] </p> </td> 
   <td colname="col2"> <p>Eine Ziffer. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> [[:graph:]] </p> </td> 
   <td colname="col2"> <p> Beliebiges Druckzeichen außer Leerzeichen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> [[:lower:]] </p> </td> 
   <td colname="col2"> <p>Ein alphabetisches Kleinbuchstaben. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> [[:print:]] </p> </td> 
   <td colname="col2"> <p> Beliebiges Druckzeichen einschließlich Leerzeichen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> [[:punct:]] </p> </td> 
   <td colname="col2"> <p> Interpunktion. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> [[:Leerzeichen:]] </p> </td> 
   <td colname="col2"> <p> Leerzeichen wie Leerzeichen, Tabulatoren oder Zeilenende. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> [[:top:]] </p> </td> 
   <td colname="col2"> <p> Ein alphabetisches Großbuchstaben. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> [[:xdigit:]] </p> </td> 
   <td colname="col2"> <p> Eine hexadezimale Zahl, Groß- oder Kleinschreibung. </p> </td> 
  </tr> 
 </tbody> 
</table>

Zwei Klassennamen mit Sonderzeichen entsprechen dem Leerzeichen am Anfang und am Ende eines Wortes. Mit anderen Worten, sie stimmen nicht mit einem tatsächlichen Zeichen überein. Ein Wort gilt als eine beliebige Folge von Buchstaben, Ziffern oder Unterstrichen (_).

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Character-Klasse </p> </th> 
   <th colname="col2" class="entry"> <p>Beschreibung </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> [[:&lt;:]] </p> </td> 
   <td colname="col2"> <p> Wortbeginn </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> [[:&gt;:]] </p> </td> 
   <td colname="col2"> <p>Wortende </p> </td> 
  </tr> 
 </tbody> 
</table>

