---
description: 'null '
seo-description: 'null '
seo-title: Search&amp;Promote 8.9.4 Versionshinweise (17.01.2013)
solution: Target
title: Search&amp;Promote 8.9.4 Versionshinweise (17.01.2013)
topic: Release Notes,Site search and merchandising
uuid: a9d550f6-0a23-4c71-b123-c31b997e7384
translation-type: tm+mt
source-git-commit: ffdec2cfcb30e733c664a7d1ca23868b7a9a9aa5

---


# Search&amp;Promote 8.9.4 Release Notes (01/17/2013){#search-promote-release-notes}

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Neue Funktionen und Erweiterungen </p> </th> 
   <th colname="col2" class="entry"> <p>Beschreibung </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Regeln </p> </td> 
   <td colname="col2"> <p> Es wurde die Möglichkeit hinzugefügt, beim Erstellen von Regeln zur Bereinigung von Suchanfragen, Vorab-Suchregeln und Regeln nach der Suche Inline-Notizen zu erstellen. Im Notizenfeld können Sie die Regeln dokumentieren und erklären. </p> <p>Siehe <a href="../c-about-rules-menu/c-about-query-cleaning-rules.md#concept_17F3CDDC3C8A4128AF092A82B777B86C" format="dita" scope="local"> Grundlagen zu Abfragen-Bereinigungsregeln</a>. </p> <p>See <a href="../c-about-rules-menu/c-about-pre-search-rules.md#concept_5BF84BB6FACB4645BA9CB7496A01CD1F" format="dita" scope="local"> About Pre-Search Rules</a>. </p> <p>See <a href="../c-about-rules-menu/c-about-post-search-rules.md#concept_AF6ADFCC0ADF4A788003964939917FDE" format="dita" scope="local"> About Post-Search Rules</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Geführte Suche </p> </td> 
   <td colname="col2"> <p> Es wurden Tags für die geführte Suche hinzugefügt, um die Gesamtdauer einer Suche anzugeben. </p> <p> <span class="codeph"> &lt;guided-search-time&gt;</span> - Gibt an, wie lange die Suche dauerte. Der zurückgegebene Suchzeitwert wird in ms angegeben. </p> <p> <span class="codeph"> &lt;guided-fall-through-searches&gt;</span> - Gibt die Anzahl der Kernelsuchvorgänge zurück, die zum Aufbau der Seite der Suchergebnisse verwendet werden. </p> <p> <span class="codeph"> &lt;guided-if-fall-through-search&gt;</span> - Prüft, ob die Anzahl der Hauptsuchvorgänge größer als 1 ist. </p> <p>Siehe auch Verschiedene Sprachen in <a href="../c-appendices/c-templates.md#reference_F1BBF616BCEC4AD7B2548ECD3CA74C64" format="dita" scope="local"> Präsentationsvorlagen-Tags</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

**Fehlerkorrekturen**

* Im Bericht Begriffe wird nun das Sternchensymbol ignoriert.

   Siehe [Anzeigen des Berichts &quot;Begriffe&quot;oder des Berichts &quot;Null-Suchbegriffe&quot;...](../c-about-reports-menu/c-about-reports-menu.md#task_53B7ED1582DD4B0E8376546A7AFC789A).

* Open **[!UICONTROL Reports > Null Search Terms Report]**, select a time slot and then view the report. Klicken Sie auf ein Wort im Bericht, um die Suche zu öffnen, und dann erneut auf Bericht anzeigen. Der Suchlaufzähler für den angeklickten Suchbegriff wurde hierbei früher zweimal erhöht. Dieser Fehler wurde nun behoben.

   Siehe [Anzeigen des Berichts &quot;Begriffe&quot;oder des Berichts &quot;Null-Suchbegriffe&quot;...](../c-about-reports-menu/c-about-reports-menu.md#task_53B7ED1582DD4B0E8376546A7AFC789A).

* Eine Leistungsoptimierung wurde vorgenommen, wenn Sie Geschäftsregeln live schalten.

   See [About Business Rules](../c-about-rules-menu/c-about-business-rules.md#concept_2A93D76216754D3D8412CDEA00BD26BD).

* The ability to remove in [!DNL Breadcrumbs] did not work all the time.

   Siehe [Info zu Breadcrumbs](../c-about-design-menu/c-about-breadcrumbs.md#concept_FB8A943C594A4A1593B118141DA61F03).

* Sofern Sie nicht mit der Neueinstufung verwendet haben, war es mit der Funktion zum Neueinstufen nicht möglich, dass geänderte Rangregeln in den Suchergebnissen wirksam werden.

   Siehe [Info zu Ranking Rules](../c-about-rules-menu/c-about-ranking-rules.md#concept_F555C076759B4E81B925441CFE707397).

   Siehe [Info zu Index](../c-about-index-menu/c-about-re-rank-index.md#concept_147B0A9FCD51451787DA898E06F7C692)neu ordnen.

