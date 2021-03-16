---
description: Search&amp;Promote 8.11.0 Versionshinweise.
solution: Target
title: Search&amp;Promote 8.11.0 Versionshinweise (29.10.2013)
topic: Versionshinweise, Site-Suche und Merchandising
uuid: 973f9608-a5c7-4571-ae2b-6f1fa05bc862
translation-type: tm+mt
source-git-commit: d015154efdccbb4c6a39a56907c0c337ec065c9f
workflow-type: tm+mt
source-wordcount: '301'
ht-degree: 57%

---


# Search&amp;Promote 8.11.0 Versionshinweise (29.10.2013){#search-promote-release-notes}

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Neue Funktion </p> </th> 
   <th colname="col2" class="entry"> <p>Beschreibung </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> DE-Compounder für Dänisch </p> </td> 
   <td colname="col2"> <p> Es wird nun ein Mechanismus bereitgestellt, mit dem die Search&amp;Promote <span class="keyword"> der Adobe</span> auf die Spracherkennung (Dänisch), Zerlegung, Stemmung und Segmentierung zugreifen kann, die von der Adobe bereitgestellt werden. </p> </td> 
  </tr> 
 </tbody> 
</table>

**Erweiterungen und Fehlerbehebungen**

* Die vorhandenen [!DNL Search&Promote]-Tabellenabgleichungsfunktionen wurden verbessert. Die Erweiterungen bieten eine bessere Unterstützung der Kundenanforderungen in Bezug auf zunehmend komplexere Beziehungen zwischen SKU und Produktdaten.

   >[!NOTE]
   >
   >Diese Funktion ist standardmäßig nicht aktiviert. Wenden Sie sich an die Adobe-Kundenunterstützung, um die Funktion in Search&amp;Promote für Sie zu aktivieren.

* Es wurde eine Option hinzugefügt, bei der die geführte Suche Facets mithilfe der Spracheinstellung des Kontos sortiert.

   >[!NOTE]
   Diese Funktion ist standardmäßig nicht aktiviert. Wenden Sie sich an die Adobe-Kundenunterstützung, um die Funktion in Search&amp;Promote für Sie zu aktivieren.

* Es wurde eine Option hinzugefügt, mit der die Anzahl der Facetwerte erhöht wurde, die ein Benutzer für Mehrfachauswahlfacets angeben kann.

   >[!NOTE]
   Diese Funktion ist standardmäßig nicht aktiviert. Wenden Sie sich an die Adobe-Kundenunterstützung, um die Funktion in Search&amp;Promote für Sie zu aktivieren.

* Das Kontrollkästchen **[!UICONTROL Only allow searches that use HTTPS]** wurde zu **[!UICONTROL Settings]** > **[!UICONTROL Searching]** > **[!UICONTROL Restrictions]** hinzugefügt.

   Siehe [Über Einschränkungen](../c-about-settings-menu/c-about-searching-menu.md#concept_B5B527E04EBF4E9AB5956EEF881DDBF1).

* Es wurde eine Option zu **[!UICONTROL Settings]** > **[!UICONTROL Searching]** > **[!UICONTROL Feeds]** > **[!UICONTROL Create Feed]** > **[!UICONTROL Generic Feed]** hinzugefügt, um Tabstoppzeichen im [!DNL File Submission]-Bedienfeld des Assistenten beizubehalten.

   Siehe [Erstellen eines Feeds](../c-about-settings-menu/c-about-searching-menu.md#task_63179C1FC359497483CD6CE13FD1C250).

* Es wurde die in jedem der oberen und unteren Felder für das neue Facet-Definitionsformular zulässige Datengröße von 80 auf 1.000 Zeichen erhöht.

   Siehe [Über Facets](../c-about-design-menu/c-about-facets.md#concept_FA912B3B41EE493DB2F492D188457FF5).

* Debugging-Parameter für die geführte Suche melden nun korrekte Geschäftsregelnummern.
* Geschäftsregeln werden nun auf die Live-Umgebung angewendet.
* Die unscharfe Suche funktioniert nun auch dann, wenn eine Suche nach Längen-/Breitengrad für Konten mit der konfigurierten Sprache „Dänisch (Dänemark)“ vorgenommen wird.
* Ergebnisbasierte Auslöser ohne zugewiesenen Plan werden nun ausgelöst.
* Bei Verwendung der Option **[!UICONTROL Ignore Apostrophes]** in **[!UICONTROL Linguistics]** > **[!UICONTROL Words & Language]** werden nun konsistente Ergebnisse gemeldet.

   Siehe [Info zu Wörtern und Sprachen](../c-about-linguistics-menu/c-about-words-and-language.md#concept_CEB4B9576F3C4E2EB87B352EEC738D79).

* Die Benutzeroberfläche mit der Wörterliste für die automatische Vervollständigung funktioniert nun für eine große Anzahl an Facets.

