---
description: Search&amp;Promote 8.9.3 Versionshinweise.
solution: Target
title: Search&amp;Promote 8.9.3 Versionshinweise (01.11.2012)
topic-legacy: Release Notes,Site search and merchandising
uuid: 7bc7bcb6-f47f-4e05-94e5-a22a13a187b7
exl-id: 9593a87d-2a84-41e1-b052-644d928f5053
translation-type: tm+mt
source-git-commit: 7559f5f7437d46e3510d4659772308666425ec96
workflow-type: tm+mt
source-wordcount: '283'
ht-degree: 80%

---

# Search&amp;Promote 8.9.3 Versionshinweise (01.11.2012){#search-promote-release-notes}

## Search&amp;Promote 8.9.3 Versionshinweise (01.11.2012) {#concept_85F5B4B4C40C43FEA3AD63E6EA5593CF}

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Neue Funktionen und Erweiterungen </p> </th> 
   <th colname="col2" class="entry"> <p>Beschreibung </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Facet Rail </p> </td> 
   <td colname="col2"> <p> 
     <!--3309390-->Die neue <span class="uicontrol">Facet Rail</span>-Option wurde hinzugefügt, um die Kontrolle über die Bestellung von Facet-Familien und Facet-Namen (nach Anzahl, alphabetisch) zu verbessern. </p> <p>Weitere Informationen finden Sie unter <a href="../c-about-design-menu/c-about-facet-rails.md#concept_1FDC8BCDFFC84A0889DA670F63D5F6DB" format="dita" scope="local">Info zu Facet Rail</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Verschachtelte Facets </p> </td> 
   <td colname="col2"> <p> Es wurde Unterstützung für ein alternatives Sortieren verschachtelter Facets hinzugefügt. </p> <p>Weitere Informationen finden Sie unter <a href="../c-about-design-menu/c-about-facet-rails.md#concept_1FDC8BCDFFC84A0889DA670F63D5F6DB" format="dita" scope="local">Info zu Facet Rail</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Anmerkungen zu den Rangregeln </p> </td> 
   <td colname="col2"> <p> 
     <!--3063772--> Das mehrzeilige Feld <span class="wintitle">Hinweise</span> wurde zu den Dialogfeldern <span class="wintitle">Add Ranking Metric</span> und <span class="wintitle">Edit Ranking Metric</span> für Ranking Rules und Regelgruppendefinitionen hinzugefügt. </p> <p>Hinweise zu Ranking Rules werden auf der Seite <span class="wintitle">Define Ranking Rules</span> angezeigt. Hinweise zu Regelgruppen werden beim Bearbeiten der Definition angezeigt. </p> <p>Siehe <a href="../c-about-rules-menu/c-about-ranking-rules.md#concept_F555C076759B4E81B925441CFE707397" format="dita" scope="local">Info zu Ranking Rules</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Geschäftsregeln </p> </td> 
   <td colname="col2"> <p> 
     <!--3331637--> Die Unterstützung für Einstiegsseiten wurde verbessert, indem kostenlose Ergebnisse mithilfe der neuen Option <span class="uicontrol">Remove All Results</span> aus einer Geschäftsregel entfernt werden. </p> <p>Verwenden Sie diese neue Option zusammen mit anderen Geschäftsregelaktionen, um gespeicherte Einstiegsseiten zu erstellen. Das heißt, der Inhalt einer Seite soll nur mithilfe von Geschäftsregeln erstellt werden, und die kostenlosen Ergebnisse der Suche sollen verworfen werden. </p> <p>Siehe <a href="../c-about-rules-menu/c-about-business-rules.md#task_BD3B31ED48BB4B1B8F1DCD3BFA2528E7" format="dita" scope="local">Hinzufügen einer neuen Geschäftsregel</a> oder <a href="../c-about-rules-menu/c-about-business-rules.md#task_375CFA75D1D94D9E92A35DE1228E5087" format="dita" scope="local">Bearbeiten einer Geschäftsregel</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Banner und Geschäftsregeln </p> </td> 
   <td colname="col2"> <p> Es wurde eine Option hinzugefügt, mit der Sie bedingt festlegen können, dass Banner nicht live geschaltet werden, wenn die Geschäftsregel, die das Banner referenziert, live geschaltet wird. </p> </td> 
  </tr> 
 </tbody> 
</table>

**Fehlerbehebungen**

* Geschäftsregeln funktionierten inkonsistent, wenn ein [!DNL Stage]-Index vorhanden war.
* Automatische Ranking Rules werden jetzt auf gespeicherte Einstiegsseiten angewendet.

   Siehe die Tabelle der Optionen unter [Hinzufügen einer Rangregel](../c-about-rules-menu/c-about-ranking-rules.md#task_A132789FD4E5423DAD090DCDA7311E8A).

* [!DNL promosearch.cgi] keine Werbeaktionen zurückgegeben hat.

   Siehe [Info zu Suchen](../c-about-settings-menu/c-about-searching-menu.md#concept_207105CF26B1448F8A3D223787C56AB8)

* Das Verschieben von Regeln, die sich auf mehrere Banner bezogen, führte in einigen Fällen zu Fehlern.

   Siehe [Info zu Bannern](../c-about-design-menu/c-about-banners.md#concept_5BBE01FEC6134393B43CC917C8CC64DA).

* **[!UICONTROL Did You Mean]** Die Abfrage-Zwischenspeicherung für die Suche ist jetzt deaktiviert.

   Siehe [Info zu „Meinten Sie“](../c-about-linguistics-menu/c-about-did-you-mean.md#concept_7D4F3C29EF184B538B8AE2ECAE0CDC5E).
