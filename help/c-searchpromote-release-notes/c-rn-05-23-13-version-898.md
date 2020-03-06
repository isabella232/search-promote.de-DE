---
description: 'null '
seo-description: 'null '
seo-title: Search&amp;Promote 8.9.8 Versionshinweise (23.05.2013)
solution: Target
title: Search&amp;Promote 8.9.8 Versionshinweise (23.05.2013)
topic: Release Notes,Site search and merchandising
uuid: ff4bfc53-1d0e-4b7d-83ad-54c81d3f9769
translation-type: tm+mt
source-git-commit: ef818327e1cdaad79ac47575a8dfba1de3dc5c2e

---


# Search&amp;Promote 8.9.8 Release Notes (05/23/2013){#search-promote-release-notes}

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Neue Funktion </p> </th> 
   <th colname="col2" class="entry"> <p>Beschreibung </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> Häufige Ausdrücke – Unterstützung für genaue Übereinstimmung </p> </td> 
   <td colname="col2"> <p> Häufige Ausdrücke enthalten Begriffe aus zwei oder mehr Wörtern, die als Ganzes durchsucht werden, wie "Boot-Cut"oder "Tankfüllung"und nicht als separate Teile. Ein häufig verwendeter Ausdruck hat eine eindeutige Bedeutung, die sich von der Bedeutung der einzelnen Bestandteile des Ausdrucks unterscheidet. </p> <p> Sie verwalten ein Wörterbuch häufig verwendeter Ausdrücke, die für Ihren Geschäftsbereich gelten. Wenn ein Kunde eine Suchabfrage ausführt und diese Suchabfrage aus mehreren Wörtern besteht, wird im Wörterbuch eine Suche nach einer genauen Übereinstimmung durchgeführt. </p> <p>Sie können häufig verwendete Ausdrücke hinzufügen, bearbeiten oder löschen. Sie können häufig verwendete Ausdrücke – ähnlich wie Domain-Wörterbucher – auch gruppieren. So können Sie beispielsweise häufig verwendete Ausdrücke nach Bekleidung, Gewebe, Schmuck, Größen, Shopping und Allgemein gruppieren. </p> <p>Siehe <a href="../c-about-linguistics-menu/c-about-common-phrases.md#concept_4946E53586DF492EAEB1B7F757FD440F" format="dita" scope="local"> Allgemeine Wortgruppen </a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

**Fehlerbehebungen und Erweiterungen**

* The backend search CGI parameter `sp_date_range_#` did not work for user-defined fields.

   Siehe CGI-Parameter für die [Backend-Suche](../c-appendices/c-cgiparameters.md#reference_582E85C3886740C98FE88CA9DF7918E8).

* Reverting **[!UICONTROL History]** version did not update the URL entrypoints field content.

   Siehe [Verwenden der Option](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)Verlauf.

   Siehe auch URL- [Einstiegspunkte](../c-about-settings-menu/c-about-crawling-menu.md#concept_5D857E3B5C124E85BC0B5AE77A509573).

* Mit der JSON-Codierung konnten falsch codierte Zeichen nicht verwaltet werden.
* Es wurde eine Unterstützung hinzugefügt, um einen gestaffelten Index remote Online zu stellen.

   Siehe [Info zur Remote-Steuerung für die Indizierung](../c-about-index-menu/c-about-remote-control-for-indexing.md#concept_C79B322190E84106A434E5C6D4A4118F).

