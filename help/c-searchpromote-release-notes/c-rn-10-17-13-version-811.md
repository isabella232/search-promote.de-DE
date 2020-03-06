---
description: 'null '
seo-description: 'null '
seo-title: Search&amp;Promote 8.11.0 Versionshinweise (29.10.2013)
solution: Target
title: Search&amp;Promote 8.11.0 Versionshinweise (29.10.2013)
topic: Release Notes,Site search and merchandising
uuid: 973f9608-a5c7-4571-ae2b-6f1fa05bc862
translation-type: tm+mt
source-git-commit: ef818327e1cdaad79ac47575a8dfba1de3dc5c2e

---


# Search&amp;Promote 8.11.0 Release Notes (10/29/2013){#search-promote-release-notes}

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
   <td colname="col2"> <p> A mechanism is now provided to allow <span class="keyword"> Adobe Search&amp;Promote</span> to access the language (Danish) detection, decompounding, stemming and segmentor services provided by Adobe. </p> </td> 
  </tr> 
 </tbody> 
</table>

**Erweiterungen und Fehlerbehebungen**

* Enhancements made to the existing [!DNL Search&Promote] table matching capabilities. Die Erweiterungen bieten eine bessere Unterstützung der Kundenanforderungen in Bezug auf zunehmend komplexere Beziehungen zwischen SKU und Produktdaten.

   >[!NOTE]
   >
   >Diese Funktion ist standardmäßig nicht aktiviert. Wenden Sie sich an die Adobe-Kundenunterstützung, um die Funktion in Search&amp;Promote für Sie zu aktivieren.

* Es wurde eine Option hinzugefügt, bei der die geführte Suche Facets mithilfe der Spracheinstellung des Kontos sortiert.

   >[!NOTE]
   Diese Funktion ist standardmäßig nicht aktiviert. Wenden Sie sich an die Adobe-Kundenunterstützung, um die Funktion in Search&amp;Promote für Sie zu aktivieren.

* Es wurde eine Option hinzugefügt, mit der die Anzahl der Facetwerte erhöht wurde, die ein Benutzer für Mehrfachauswahlfacets angeben kann.

   >[!NOTE]
   Diese Funktion ist standardmäßig nicht aktiviert. Wenden Sie sich an die Adobe-Kundenunterstützung, um die Funktion in Search&amp;Promote für Sie zu aktivieren.

* Kontrollkästchen **[!UICONTROL Only allow searches that use HTTPS]** zu **[!UICONTROL Settings]** > **[!UICONTROL Searching]** > **[!UICONTROL Restrictions]**.

   Siehe [Informationen zu Einschränkungen](../c-about-settings-menu/c-about-searching-menu.md#concept_B5B527E04EBF4E9AB5956EEF881DDBF1).

* Es wurde eine Option zu **[!UICONTROL Settings]** > **[!UICONTROL Searching]** > **[!UICONTROL Feeds]** > **[!UICONTROL Create Feed]** > hinzugefügt, um Tabstoppzeichen im **[!UICONTROL Generic Feed]** [!DNL File Submission] Bedienfeld des Assistenten beizubehalten.

   Siehe [Erstellen eines Feeds](../c-about-settings-menu/c-about-searching-menu.md#task_63179C1FC359497483CD6CE13FD1C250).

* Es wurde die in jedem der oberen und unteren Felder für das neue Facet-Definitionsformular zulässige Datengröße von 80 auf 1.000 Zeichen erhöht.

   Siehe [Grundlagen](../c-about-design-menu/c-about-facets.md#concept_FA912B3B41EE493DB2F492D188457FF5).

* Debugging-Parameter für die geführte Suche melden nun korrekte Geschäftsregelnummern.
* Geschäftsregeln werden nun auf die Live-Umgebung angewendet.
* Die unscharfe Suche funktioniert nun auch dann, wenn eine Suche nach Längen-/Breitengrad für Konten mit der konfigurierten Sprache „Dänisch (Dänemark)“ vorgenommen wird.
* Ergebnisbasierte Auslöser ohne zugewiesenen Plan werden nun ausgelöst.
* Konsistente Ergebnisse werden jetzt bei Verwendung der **[!UICONTROL Ignore Apostrophes]** Option unter **[!UICONTROL Linguistics]** > **[!UICONTROL Words & Language]** gemeldet.

   Siehe [Info zu Wörtern und Sprachen](../c-about-linguistics-menu/c-about-words-and-language.md#concept_CEB4B9576F3C4E2EB87B352EEC738D79).

* Die Benutzeroberfläche mit der Wörterliste für die automatische Vervollständigung funktioniert nun für eine große Anzahl an Facets.

