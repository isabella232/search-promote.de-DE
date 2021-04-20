---
description: Ein Auffrischungsbericht zur Syntax und den Regeln für das Erstellen von regulären Ausdrücken.
solution: Target
title: Reguläre Ausdrücke
topic: Appendices,Site search and merchandising
uuid: 369b54f6-372a-41de-bb5d-3ae0bd640199
translation-type: tm+mt
source-git-commit: d015154efdccbb4c6a39a56907c0c337ec065c9f
workflow-type: tm+mt
source-wordcount: '1050'
ht-degree: 1%

---


# Reguläre Ausdruck{#regular-expressions}

Ein Auffrischungsbericht zur Syntax und den Regeln für das Erstellen von regulären Ausdrücken.

Siehe auch [Konfigurieren eines inkrementellen Indexes einer gestaffelten Website](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0).

**Syntax regulärer Ausdruck**

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
   <td colname="col3"> <p> Beginn des Zeilenankers. </p> </td> 
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

   * `.` (Punkt),  `*` (Sternchen),  `?` (Fragezeichen),  `+` (Pluszeichen),  `[` (linke eckige Klammer),  `|` (vertikale Linie) und  `\` (umgekehrter Schrägstrich) sind immer Sonderzeichen, es sei denn, sie erscheinen in eckigen Klammern.
   * `^` (Caret oder Zirkumflex) ist besonders am Anfang eines regulären Ausdrucks, oder wenn es sofort folgt links von einem Paar eckiger Klammern.
   * `$` (Dollarzeichen) ist am Ende eines regulären Ausdrucks etwas Besonderes.
   * `.` (period) ist ein regulärer Ausdruck mit einem Zeichen, der mit jedem Zeichen übereinstimmt, einschließlich zusätzlicher Codesatzzeichen mit Ausnahme der neuen Zeile.
   * Eine nicht leere Zeichenfolge in `[ ]` (linke und rechte eckige Klammern) ist ein regulärer Ausdruck mit einem Zeichen, der einem Zeichen, einschließlich zusätzlicher Codesatzzeichen, in dieser Zeichenfolge entspricht.

      Wenn das erste Zeichen der Zeichenfolge jedoch ein `^` (Zirkumflex) ist, stimmt der reguläre Ausdruck mit einem Zeichen mit jedem beliebigen Zeichen überein, einschließlich zusätzlicher Codesatzzeichen, mit Ausnahme von &quot;new-line&quot;und den übrigen Zeichen in der Zeichenfolge.

      Diese besondere Bedeutung hat `^` nur, wenn sie zuerst in der Zeichenfolge vorkommt. Sie können `-` (Minuszeichen) verwenden, um einen Bereich aufeinander folgender Zeichen anzugeben, einschließlich zusätzlicher Codesatzzeichen. Beispiel: [0-9] entspricht [0123456789].

      Zeichen, die den Bereich angeben, müssen aus demselben Codesatz stammen. Wenn die Zeichen aus verschiedenen Codesätzen stammen, wird eines der Zeichen, die den Bereich angeben, zugeordnet. Diese besondere Bedeutung verliert `-`, wenn sie zuerst (nach einer initialen `^`-Anweisung, falls vorhanden) oder zuletzt in der Zeichenfolge auftritt. Die `]` (rechte eckige Klammer) beendet eine solche Zeichenfolge nicht, wenn sie das erste Zeichen darin ist, gegebenenfalls nach einer initialen `^`. `[]a-f]` entspricht beispielsweise entweder einer `]` (rechten eckigen Klammer) oder einem der ASCII-Buchstaben a bis f einschließlich. Die vier oben als Sonderzeichen aufgelisteten Zeichen stehen für sich in einer solchen Zeichenfolge.

**Regeln zum Erstellen regulärer Ausdruck aus regulären Ausdrücken mit einem Zeichen**

Sie können die folgenden Regeln verwenden, um reguläre Ausdruck aus regulären Ausdrücken mit einem Zeichen zu erstellen:

* Ein regulärer Ausdruck mit einem Zeichen ist ein regulärer Ausdruck, der mit dem regulären Ausdruck mit einem Zeichen übereinstimmt.
* Ein regulärer einstelliger Ausdruck gefolgt von einem `*` (Sternchen) ist ein regulärer Ausdruck, der Null oder mehr Vorkommen des regulären einstelligen Ausdrucks entspricht, bei dem es sich möglicherweise um ein zusätzliches Codesatzzeichen handelt. Bei einer beliebigen Option wird die längste Zeichenfolge links gewählt, die eine Übereinstimmung zulässt.
* Ein regulärer einstelliger Ausdruck gefolgt von einem `?` (Fragezeichen) ist ein regulärer Ausdruck, der Null oder ein Vorkommen des regulären einstelligen Ausdrucks entspricht, bei dem es sich möglicherweise um ein zusätzliches Codesatzzeichen handelt. Bei einer beliebigen Option wird die längste Zeichenfolge links gewählt, die eine Übereinstimmung zulässt.
* Ein regulärer Ausdruck mit einem Zeichen gefolgt von einem `+` (Pluszeichen) ist ein regulärer Ausdruck, der einem oder mehreren Vorkommen des regulären einstelligen Ausdrucks entspricht, bei dem es sich möglicherweise um ein zusätzliches Codesatzzeichen handelt. Bei einer beliebigen Option wird die längste Zeichenfolge links gewählt, die eine Übereinstimmung zulässt.
* Ein regulärer Ausdruck mit einem Zeichen gefolgt von `{m}`, `{m,}` oder `{m,n}` ist ein regulärer Ausdruck, der einem Bereich von Vorkommen des regulären Ausdrucks mit einem Zeichen entspricht. Die Werte von m und n müssen nicht negative Ganzzahlen unter 256 sein. `{m}` stimmt genau mit m-Vorkommen überein; `{m,}` entspricht mindestens m Vorkommen; `{m,n}` stimmt mit einer beliebigen Anzahl von Vorkommen zwischen m und n überein. Wenn eine Auswahl vorhanden ist, stimmt der reguläre Ausdruck mit so vielen Vorkommen wie möglich überein.
* Die Verkettung von regulären Ausdrücken ist ein regulärer Ausdruck, der der Verkettung der Zeichenfolgen entspricht, die jeder Komponente des regulären Ausdrucks zugeordnet sind.
* Ein regulärer Ausdruck, der zwischen den Zeichensequenzen ( und ) eingeschlossen ist, ist ein regulärer Ausdruck, der mit dem gleichnamigen regulären Ausdruck übereinstimmt.
* Ein regulärer Ausdruck gefolgt von einem `|` (senkrechten Rohr) gefolgt von einem regulären Ausdruck ist ein regulärer Ausdruck, der entweder dem ersten regulären Ausdruck (vor dem senkrechten Rohr) oder dem zweiten regulären Ausdruck (nach dem senkrechten Rohr) entspricht.

Sie können einen regulären Ausdruck auch so einschränken, dass er nur mit einem Anfangssegment oder finalen Segment einer Zeile oder mit beiden übereinstimmt.

* Ein `^` (Zirkumflex) am Anfang eines regulären Ausdrucks schränkt diesen regulären Ausdruck so ein, dass er mit einem Anfangssegment einer Zeile übereinstimmt.
* Ein `$`-Zeichen (Dollarzeichen) am Ende eines gesamten regulären Ausdrucks schränkt diesen regulären Ausdruck auf Übereinstimmung mit einem endgültigen Liniensegment ein.
* Die Konstruktion &#39;^regulärer Ausdruck$&#39; beschränkt den regulären Ausdruck auf die Übereinstimmung mit der gesamten Zeile.

Es gibt einige vordefinierte Zeichenklassennamen, die Sie anstelle komplexer Ausdruck mit Klammern verwenden können. Eine Ziffer kann beispielsweise durch den einstelligen regulären Ausdruck [0-9] oder durch den einstelligen regulären Ausdruck der Zeichenklasse [[:digit:]] dargestellt werden.

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

Zwei Klassennamen mit Sonderzeichen entsprechen dem Leerzeichen am Beginn und am Wortende. Mit anderen Worten, sie stimmen nicht mit einem tatsächlichen Zeichen überein. Ein Wort gilt als eine beliebige Folge von Buchstaben, Ziffern oder Unterstrichen (_).

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
   <td colname="col2"> <p> Beginn eines Wortes </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> [[:&gt;:]] </p> </td> 
   <td colname="col2"> <p>Wortende </p> </td> 
  </tr> 
 </tbody> 
</table>

