---
description: Search&amp;Promote 8.12.0 Versionshinweise.
solution: Target
title: Search&amp;Promote 8.12.0 Versionshinweise (16.01.2014)
topic: Release Notes,Site search and merchandising
uuid: 4db10eb4-11bf-4483-a7f2-87981d9c7a50
translation-type: tm+mt
source-git-commit: d015154efdccbb4c6a39a56907c0c337ec065c9f
workflow-type: tm+mt
source-wordcount: '257'
ht-degree: 72%

---


# Search&amp;Promote 8.12.0 Versionshinweise (16.01.2014){#search-promote-release-notes}

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Neue Funktionen und Erweiterungen </p> </th> 
   <th colname="col2" class="entry"> <p>Beschreibung </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Stemming-Wörterbücher hinzugefügt </p> </td> 
   <td colname="col2"> <p> </p> <p> Stemming-Wörterbücher für indonesische und türkische Sprachen wurden hinzugefügt. </p> <p>Siehe <a href="../c-about-linguistics-menu/c-about-dictionaries.md#concept_B8028B71EC8144669614C64578EDB034" format="dita" scope="local"> Info zu Wörterbüchern</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Exportberichte </p> </td> 
   <td colname="col2"> <p> 
     <!--3683368-->Sie können jetzt Daten aus den folgenden Berichten in CSV exportieren: 
     <ul id="ul_93B619DBB3444F64BD6D7F9E969AB1E1"> 
      <li id="li_96DDE1A196834845A0FA319903C5934B"> <p>Bericht „Begriffe“ </p> </li> 
      <li id="li_4F1A19DE98C84F8CAD963EEA2B38ED7A"> <p>Null-Suchbegriffbericht </p> </li> 
      <li id="li_A7716C62C4D44CD69D411C3FEE246D96"> <p>Suchanforderungsbericht </p> </li> 
     </ul> </p> <p>Siehe <a href="../c-about-reports-menu/c-about-reports-menu.md#concept_5F901459C7AB461BAB30B305957EB00C" format="dita" scope="local"> Info zum Menü Berichte</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Nicht zuordnen </p> </td> 
   <td colname="col2"> <p>Sie können nun steuern, welche zwei Wörter in den Suchergebnissen einander nicht zugeordnet werden dürfen, beispielsweise „Sweatshirt“ und „Shirt“. </p> <p> <p>Hinweis: Diese Funktion ist standardmäßig nicht aktiviert. Wenden Sie sich an die Adobe-Kundenunterstützung, um die Funktion in Search&amp;Promote für Sie zu aktivieren. </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

**Fehlerkorrekturen**

* Es war nicht möglich, Ergebnisse in einer Empfohlen-Zone hinzuzufügen, die außerhalb der aktuell ausgewählten Facettierungskriterien lagen.
* Es war nicht möglich, ergebnisbasierte Regeln für ein Konto zu speichern, bei dem eine Suche nur über HTTPS möglich war.
* Es hat nicht funktioniert, eine Geschäftsregel für „ist kein Mobiltelefon“ einzurichten.

   Siehe [Geschäftsregeln](../c-about-rules-menu/c-about-business-rules.md#concept_2A93D76216754D3D8412CDEA00BD26BD).

* Bei einer Lagerbestands-Filtersuche wurden keine Ergebnisse ausgegeben.
* Die Facettenreihenfolge von „Größe“ wurde nicht aktualisiert.
* Option für eine benutzerdefinierte Regeldefinition wurde zur Seite „Anfragenbereinigung“ hinzugefügt.

   Siehe [Informationen zu Abfragen-Bereinigungsregeln](../c-about-rules-menu/c-about-query-cleaning-rules.md#concept_17F3CDDC3C8A4128AF092A82B777B86C).

* Im Begriffsbericht wiederholten sich Einträge, wenn nicht genügend Daten zur Verfügung standen.

   Siehe [Anzeigen des Berichts &quot;Begriffe&quot;oder des Berichts &quot;Null-Suchbegriffe&quot;...](../c-about-reports-menu/c-about-reports-menu.md#task_53B7ED1582DD4B0E8376546A7AFC789A).

* Die Aktivierung einer einzelnen Geschäftsregel funktionierte im Staging-Modus, jedoch nicht im Live-Modus.
* Änderungen an Ein- und Ausschlusslisten anhand der automatischen Vervollständigung wurden nicht im Verlauf gespeichert und konnten daher nicht rückgängig gemacht werden.

   Siehe [Info zum automatischen Ausfüllen](../c-about-auto-complete.md#concept_093A9CD754864BA79B456FE4BEB64578).

