---
description: 'null '
seo-description: 'null '
seo-title: Search&amp;Promote 8.16.0 - Versionshinweise (18.09.2014)
solution: Target
title: Search&amp;Promote 8.16.0 - Versionshinweise (18.09.2014)
topic: Release Notes,Site search and merchandising
uuid: 0a59858b-213b-40d6-aea1-d085c4d6d2fa
translation-type: tm+mt
source-git-commit: ffdec2cfcb30e733c664a7d1ca23868b7a9a9aa5

---


# Search&amp;Promote 8.16.0 Release Notes (9/18/2014){#search-promote-release-notes}

## Search&amp;Promote 8.16.0 Release Notes (9/18/2014) {#topic_5BECD3F66C684987828F6AE65E62DA29}

## New features {#section_2A10EF6B40FC4F2CB2381FFA9FFA64BD}

* Zwischenspeichern von Suchergebnissen in der geführten Suche 3 (GS3) - Wenden Sie sich an Ihren technischen Kundenbetreuer von Adobe, wenn Sie diese benutzerdefinierte Funktion einrichten möchten, damit Sie sie in Ihrem Konto verwenden können.
* Vertikale Aktualisierungen für häufig geänderte Felder - Sie können jetzt alle Werte für eine Reihe von Metadatenfeldern schnell aktualisieren, ohne den Inhalt komplett neu indizieren zu müssen.

   Siehe die Option &quot;Feld vertikal aktualisieren&quot;in der Tabelle unter [Hinzufügen eines neuen Meta-Tag-Felds](../c-about-settings-menu/c-about-metadata-menu.md#task_6DF188C0FC7F4831A4444CA9AFA615E5) und [Info zur vertikalen Aktualisierung](../c-about-index-menu/c-about-vertical-updates.md#concept_E65A70C9C2E04804BF24FBE1B3CAD899).

   This feature can only be used on [!DNL Adobe Search&Promote] accounts that use Index Connector. Wenn Sie diese benutzerdefinierte Funktion einrichten möchten, sodass Sie sie für Ihr Konto verwenden können, wenden Sie sich an Ihren technischen Kundenbetreuer von Adobe.

## Fixes and enhancements {#section_22D1AFC99F394D569898828A0D3C419D}

* Corrected the Index Connector parsing of XML feeds that contained `?>` string.
* Index-Connector-SFTP-Feeds wurden behoben, wenn die minimale Dokumentanzahl erzwungen wurde.
* Der Berichtsexport nach Microsoft Excel unterstützt von nun an UTF8.
* Geführte Suche: die Facettenkompilierung war langsam.
* Attribut-Lader: für aggregierte Daten waren doppelte Schlüssel vorhanden.
* Die falsche Ausführungsreihenfolge von Geschäftsregeln beim Aufschalten einer einzelnen Regel wurde korrigiert.
* Von der geführten Suche wurden die falschen Links zum Rückgängigmachen von Facetten generiert.
* Es wurde ein neuer Fernsteuerungsvorgang hinzugefügt (`sp_lines=N`), mit dem Sie den Fortschritt und Status eines momentan ausgeführten Index-Crawls überprüfen können.

   Siehe [Info zur Remote-Steuerung für die Indizierung](../c-about-index-menu/c-about-remote-control-for-indexing.md#concept_C79B322190E84106A434E5C6D4A4118F).

* Beim Abrufen von gelöschten Informationen während des Index-Connector-Inkrements müssen Authentifizierungsinformationen gesendet werden.
* The [!DNL Change Log] report now identifies the user who initiates a manual index operation.

   See [Viewing the Change Log](../c-about-reports-menu/c-about-reports-menu.md#task_166F1156719F4B3D834BEA8E249C8057).

* When you export a [!DNL Terms Report], you are no longer limited to 500 or less items in the report.

   Siehe [Anzeigen des Berichts &quot;Begriffe&quot;oder des Berichts &quot;Null-Suchbegriffe&quot;...](../c-about-reports-menu/c-about-reports-menu.md#task_53B7ED1582DD4B0E8376546A7AFC789A).

* The Index Connector **[!UICONTROL Strip HTML]** setting was always displaying as checked.
* Inconsistent search results were experienced with the **[!UICONTROL Common Phrases]** feature.
* Die Anzeige von Attributnamen war in den Zusammenfassungen der Regelliste abgeschnitten.
* Eine einzelne Geschäftsregel zu aktivieren, hat alle Geschäftsregeln live gedrängt.

