---
description: Search&amp;Promote 8.8 Versionshinweise.
solution: Target
title: Search&amp;Promote 8.8 Versionshinweise (26.04.2012)
topic-legacy: Release Notes,Site search and merchandising
uuid: ddb9f1af-92a4-4f85-be8f-a36f34d31add
exl-id: 3bd9b6af-99a2-4631-b7a7-0a792122c157
translation-type: tm+mt
source-git-commit: 7559f5f7437d46e3510d4659772308666425ec96
workflow-type: tm+mt
source-wordcount: '322'
ht-degree: 70%

---

# Search&amp;Promote 8.8 Versionshinweise (26.04.2012){#search-promote-release-notes}

**Neue Funktionen**

* Dynamische facettierte Suche

   Die Fähigkeit zur dynamischen facettierten Suche für freie Attributsätze, die jeder Seite des Site-Inhalts zugeordnet sind und sich potenziell von Index zu Index ändern können (neue Attribute werden hinzugefügt, alte entfernt oder umbenannt). Die dynamische facettierte Suche weist die Slot-Facetten automatisch den echten Facetten zu. Die Ebene zur Geführten Suche hilft, diese Funktion mit Geschäftsregeln zu nutzen.
* Benutzeroberfläche von Adobe Search&amp;Promote

   Die Benutzeroberfläche der Adobe wurde für alle Webseiten der Adobe-Search&amp;Promote implementiert.
* Engere Integration mit dem Anmeldeportal der Adobe

   Adobe-Search&amp;Promote können ausschließlich das Adobe-Login-Portal nutzen. Aktuelle [!DNL Adobe Publish]-, Adobe SiteSearch- und Atomz-Kunden verwenden weiterhin die Legacy-Anmeldung.
* Neuer morphologischer Analyzer für Chinesisch und Japanisch

   Der morphologische Analyzer, der auf Index und Suchzeit angewandt wird, unterstützt Chinesisch und Japanisch.
* Unterstützung neuer Dokumenttypen, z. B. Microsoft Office 2010

   Search kann verschiedene Dokumenttypen, z. B. .doc, .docx, .pdf und .mp3 in HTML konvertieren, bevor sie an den Indexer weitergegeben werden.
* Neues Onlinehilfesystem für Adobe Search&amp;Promote

   Das Onlinehilfesystem verfügt über eine neue Benutzeroberfläche und ist nun aufgabenbasiert.

**Korrekturen und Erweiterungen**

* Es wurde ein Fehler behoben, der dazu führte, dass ein Banner mit dem Stage Manager live geschaltet wurde, wodurch die Funktionen im Zusammenhang mit Dynamic Media Classic nicht funktionierten.
* Es wurde ein Problem behoben, bei dem die Bearbeitung einer Regel mit dem Auslöser „Query Parameter does not exist“ (Abfrageparameter existiert nicht) fälschlicherweise übersetzt wurde in „Keyword contains“ (Suchbegriff enthält).
* Es wurde ein Problem behoben, bei dem Sie Parameter nicht mehr bearbeiten konnten.
* Es wurde ein Problem mit Index Connector behoben, bei dem zwei oder mehr Zuordnungsdefinitionen nicht auf denselben Metadaten-/Feldwert verweisen können.
* Es wurden Probleme beim Crawling einiger PDF-Dokumente behoben. Das Upgrade auf Version 3.03 behebt die jüngsten Absturzprobleme.
* Es können nun kürzere Geschäftsregelbeschreibungen genutzt werden (z. B., dass field_table nicht im Manager angezeigt wird).
* Das Navigationsmenü zur Geführten Suche umfasste maximal neun Elemente. Jetzt liegt die Obergrenze bei 20.
* An Index Connector wurden Leistungsverbesserungen vorgenommen.
