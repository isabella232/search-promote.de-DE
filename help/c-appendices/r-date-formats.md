---
description: Sie können die Datumsformate definieren, die beim Analysieren und Indizieren von Feldern mit dem Datentyp "Datum"verwendet werden.
seo-description: Sie können die Datumsformate definieren, die beim Analysieren und Indizieren von Feldern mit dem Datentyp "Datum"verwendet werden.
seo-title: Datumsformate
solution: Target
title: Datumsformate
topic: Appendices,Site search and merchandising
uuid: 148914b5-33ef-41db-8404-67c03f6f0832
translation-type: tm+mt
source-git-commit: ef818327e1cdaad79ac47575a8dfba1de3dc5c2e
workflow-type: tm+mt
source-wordcount: '767'
ht-degree: 3%

---


# Datumsformate{#date-formats}

Sie können die Datumsformate definieren, die beim Analysieren und Indizieren von Feldern mit dem Datentyp &quot;Datum&quot;verwendet werden.

Das Format des Datums und der Uhrzeit wird mit einer Formatzeichenfolge angegeben. Die Formatzeichenfolge besteht aus null oder mehr Konvertierungsspezifikationen (eine Konvertierungsspezifikation besteht aus einem Prozentzeichen und einem anderen Zeichen) und einfachen Zeichen. Für jedes Datumsfeld wird eine standardmäßige Liste der Datumsformat-Zeichenfolgen bereitgestellt.

Sie haben die vollständige Kontrolle über diese Liste und können sie entsprechend den Anforderungen Ihrer Site hinzufügen oder ändern. Die Zeichenfolge des obersten Formats hat Vorrang, und nachfolgende Formatzeichenfolgen werden nur verwendet, wenn beim Analysieren des Inhalts eines bestimmten Metadaten-Tags ein Fehler auftritt.

Angenommen, Sie haben die folgenden Datumsformate angegeben:

<table> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p>%B %d, %Y %T %Z </p> <p>%b %d, %Y %T %Z </p> <p>%A %B %d, %Y %T %Z </p> <p>%A %b %d, %Y %T %Z </p> <p>%a %B %d, %Y %T %Z </p> <p>%a %b %d, %Y %T %Z </p> <p>%d %b %Y %T %Z </p> </td> 
  </tr> 
 </tbody> 
</table>

Das erste Format, &quot;%B %d, %Y %T %Z&quot;, stimmt mit Daten wie dem folgenden &quot;20. September 2014 13:12:00 PDT&quot;überein. Wenn der Metadaten-Tag-Inhalt nicht mit dieser Formatzeichenfolge analysiert werden kann, wird das nächste verfügbare Format &quot;%b %d, %Y %T %Z&quot;versucht. Dieses Format stimmt mit Datumsangaben wie den folgenden überein: &quot;20. September 2014 3:12:00 PDT&quot;. Wenn der Metadaten-Tag-Inhalt nicht mit dieser Formatzeichenfolge analysiert werden kann, wird die Liste der Formatzeichenfolgen nach unten verschoben, bis eine funktionierende Formatzeichenfolge gefunden wird.

Die folgende Tabelle beschreibt die verfügbaren Datumsformat-Zeichenfolgen:

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Datenformat </p> </th> 
   <th colname="col2" class="entry"> <p>Beschreibung </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>%A </p> </td> 
   <td colname="col2"> <p>Entspricht der nationalen Darstellung des vollständigen Wochentagsnamens, z. B. "Montag". Die nationale Vertretung wird anhand der Einstellung "Sprache"bei der Option "Wörter und Sprachen"bestimmt </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%a </p> </td> 
   <td colname="col2"> <p> entspricht der nationalen Darstellung des abgekürzten Wochentagsnamens, wobei die Abkürzung die ersten drei Zeichen, z. "Mo." Die nationale Vertretung wird anhand der Einstellung "Sprache"bei der Option "Wörter und Sprachen"bestimmt </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%B </p> </td> 
   <td colname="col2"> <p> entspricht der nationalen Vertretung des vollen Monatsnamens, z. "Juni." Die nationale Vertretung wird anhand der Einstellung "Sprache"bei der Option "Wörter und Sprachen"bestimmt </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%b </p> </td> 
   <td colname="col2"> <p> entspricht der nationalen Darstellung des abgekürzten Monatsnamens, wobei die Abkürzung die ersten drei Zeichen, z. "Jun." Die nationale Vertretung wird anhand der Einstellung "Sprache"bei der Option "Wörter und Sprachen"bestimmt </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%D </p> </td> 
   <td colname="col2"> <p> entspricht "%m/%d/%y", z. B. "06.06.01" </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%d </p> </td> 
   <td colname="col2"> <p> entspricht dem Tag des Monats als Dezimalzahl (01-31) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%e </p> </td> 
   <td colname="col2"> <p> entspricht dem Tag des Monats als Dezimalzahl (1-31); einstellige Ziffern werden durch ein Leerzeichen vorangestellt </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%H </p> </td> 
   <td colname="col2"> <p> entspricht der Stunde (24-Stunden-Uhr) als Dezimalzahl (00-23) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%h </p> </td> 
   <td colname="col2"> <p> entspricht der nationalen Darstellung des abgekürzten Monatsnamens, wobei die Abkürzung die ersten drei Zeichen, z. "Jun"(entspricht %b) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%I </p> </td> 
   <td colname="col2"> <p> entspricht der Stunde (12-Stunden-Uhr) als Dezimalzahl (01-12) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%j </p> </td> 
   <td colname="col2"> <p> entspricht dem Tag des Jahres als Dezimalzahl (001-366) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%k </p> </td> 
   <td colname="col2"> <p> entspricht der Stunde (24-Stunden-Uhr) als Dezimalzahl (0-23); einstellige Ziffern werden durch ein Leerzeichen vorangestellt </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%l </p> </td> 
   <td colname="col2"> <p> entspricht der Stunde (12-Stunden-Uhr) als Dezimalzahl (1-12); einstellige Ziffern werden durch ein Leerzeichen vorangestellt </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%M </p> </td> 
   <td colname="col2"> <p> entspricht der Minute als Dezimalzahl (00-59) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%m </p> </td> 
   <td colname="col2"> <p> entspricht dem Monat als Dezimalzahl (01-12) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%p </p> </td> 
   <td colname="col2"> <p> Entspricht der nationalen Vertretung von "ante meridiem" oder "post meridiem", z. B. "PM." Die nationale Vertretung wird anhand der Einstellung "Sprache"bei der Option "Wörter und Sprachen"bestimmt </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%R </p> </td> 
   <td colname="col2"> <p> entspricht "%H:%M", z. B. "13:23" </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%r </p> </td> 
   <td colname="col2"> <p> entspricht "%I:%M:%S %p", z. B. 01:23:45 PM" </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%S </p> </td> 
   <td colname="col2"> <p> entspricht der zweiten als Dezimalzahl (00-60) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%T </p> </td> 
   <td colname="col2"> <p> entspricht "%H:%M:%S", z. B. "13:26:47" </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%U </p> </td> 
   <td colname="col2"> <p> entspricht der Wochenzahl des Jahres (Sonntag als erster Wochentag) als Dezimalzahl (00-53) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%v </p> </td> 
   <td colname="col2"> <p> entspricht "%e-%b-%Y", z. B. "6-Juni-2001" </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%Y </p> </td> 
   <td colname="col2"> <p> entspricht dem Jahr mit dem Jahrhundert als Dezimalzahl, z. "2001" </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%y </p> </td> 
   <td colname="col2"> <p> entspricht dem Jahr ohne Jahrhundert als Dezimalzahl (00-99) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%Z </p> </td> 
   <td colname="col2"> <p> stimmt mit dem Zeitzonennamen überein </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%% </p> </td> 
   <td colname="col2"> <p> Stimmt überein "%" </p> </td> 
  </tr> 
 </tbody> 
</table>

**Standardformatierungszeichenfolgen**

Die folgenden Standardformat-Zeichenfolgen werden von Vorlagen verwendet. Sie können diese Liste nach Bedarf erweitern oder bearbeiten.

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Standardformat-Zeichenfolge </p> </th> 
   <th colname="col2" class="entry"> <p>Ergebnisbeispiel </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>%B %d, %Y %T %Z </p> </td> 
   <td colname="col2"> <p> 5. September 1999 13:12:00 PDT </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%b %d, %Y %T %Z </p> </td> 
   <td colname="col2"> <p> 05.09.13:12:00 PDT </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%A %B %d, %Y %T %Z </p> </td> 
   <td colname="col2"> <p> Sonntag, 5. September 1999 13:12:00 PDT </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%A %b %d, %Y %T %Z </p> </td> 
   <td colname="col2"> <p> Sonntag, 5. September 1999 13:12:00 PDT </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%a %B %d, %Y %T %Z </p> </td> 
   <td colname="col2"> <p> Sun 5. September 1999 13:12:00 PDT </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%a %b %d, %Y %T %Z </p> </td> 
   <td colname="col2"> <p> Sun Sep 5, 1999 13:12:00 PDT </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%d %b %Y %T %Z </p> </td> 
   <td colname="col2"> <p> 5 September 1999 13:12:00 PDT </p> </td> 
  </tr> 
 </tbody> 
</table>

