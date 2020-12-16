---
description: 'null '
seo-description: 'null '
seo-title: Search&amp;Promote 8.13.0 Versionshinweise (16.04.2014)
solution: Target
title: Search&amp;Promote 8.13.0 Versionshinweise (16.04.2014)
topic: Release Notes,Site search and merchandising
uuid: b3524992-ff00-4a7c-a404-078242456734
translation-type: tm+mt
source-git-commit: 9d5ac055d665b39d09b28063179d74a389d7f830
workflow-type: tm+mt
source-wordcount: '326'
ht-degree: 57%

---


# Search&amp;Promote 8.13.0 Versionshinweise (16.04.2014){#search-promote-release-notes}

| Neue Funktion und Verbesserung | Beschreibung |
|----------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Dynamische Facets mit Unterstützung für vollständigen Tabellenabgleich | Einige Kunden hatten viele Attribute auf SKU-Ebene, die sie mithilfe von dynamischen Facets auswählen und anzeigen wollten. Daher können Sie jetzt optional jedes dynamische Facet-Feld mit bis zu einem Tabellennamen in einer statischen Kontokonfiguration verknüpfen. Diese Tabellenbeziehungen können dann zum Zeitpunkt der Suche für jedes beliebige Facet-Feld, das in die Suche involviert ist, angewendet werden. Siehe [Dynamische Fakten](../c-about-design-menu/c-about-dynamic-facets.md#concept_E65A70C9C2E04804BF24FBE1B3CAD899). |

**Fehlerkorrekturen**

* Das Beschreibungsfeld für die Datenbeschreibung wurde dahingehend geändert, dass das Tag `<search-display-field>` anstelle von `<search-description>` verwendet wird.
* Dem Index Connector wurde eine Funktion hinzugefügt, die zwei oder mehr Felder zu einem primären Schlüssel verkettet.
* Das AttributeLoader-Regen-Enabled-Skript `attributeloader-regen.pl` wurde so geändert, dass es Werte nicht HTML-codiert.
* Bei Abfragen vom Typ „Bereichssuche“ wurde der Umgang mit Leerstellen bei Index- und Suchzeiten abgeglichen.
* Wenn dynamische Facets aktiviert waren, wurde beim Hinzufügen einer Geschäftsregel manchmal ein Fehler verursacht.

   Siehe [Geschäftsregeln](../c-about-rules-menu/c-about-business-rules.md#concept_2A93D76216754D3D8412CDEA00BD26BD).

* Ein JavaScript-Fehler verhinderte das Hinzufügen oder Bearbeiten einer Definition in **Einstellungen** > **SPIN** > **IndexConnector**.
* Nach dem Speichern einer Geschäftsregel schien es, als die Zeit während der Erstellung der Geschäftsregel ausgewählt wurde, standardmäßig auf die GMT-Zeitzone zu setzen. Nach dem Speichern hatte es den Anschein, dass dann die Zeitzone des Kontos übernommen wurde.

   Siehe [Geschäftsregeln](../c-about-rules-menu/c-about-business-rules.md#concept_2A93D76216754D3D8412CDEA00BD26BD).

* Das Sortieren von Geschäftsregeln in Stage funktionierte nicht fehlerfrei.

   Siehe [Geschäftsregeln](../c-about-rules-menu/c-about-business-rules.md#concept_2A93D76216754D3D8412CDEA00BD26BD).

* Die Berichterstellung zur Suchleistung wurde um die Möglichkeit erweitert, Berichte zur Übermittlung per E-Mail einzuplanen.
* Der feste Zeitplan für Geschäftsregeln wurde automatisch auf Sommerzeit umgestellt.

   Siehe [Geschäftsregeln](../c-about-rules-menu/c-about-business-rules.md#concept_2A93D76216754D3D8412CDEA00BD26BD).

* Wenn eine große Anzahl dynamischer Facet-Felder definiert wurde, kam es bei den Benutzern zu langsamen Antwortzeiten bei der Kernsuche.
* Es wurden fälschlicherweise Fehler gemeldet, dass der Index außerhalb des Bereichs liegt.
* Der Zugriff auf Dynamic Media Classic in Rechenzentren außerhalb Nordamerikas wurde unterbrochen.
* Die SPIN XPath-Validierungsfunktion gab einen falsch-positiven Fehler zurück.

* Nach einer SPIN-Aktivierung/Deaktivierung wurde der Benutzer auf die Anmeldeseite des Mitgliederzentrums umgeleitet.

