---
description: Search&amp;Promote 8.16.0 Versionshinweise.
solution: Target
title: Search&amp;Promote 8.16.0 - Versionshinweise (18.09.2014)
topic-legacy: Release Notes,Site search and merchandising
uuid: 0a59858b-213b-40d6-aea1-d085c4d6d2fa
exl-id: 929d6f97-4939-4e37-aded-6a746757b960
translation-type: tm+mt
source-git-commit: 7559f5f7437d46e3510d4659772308666425ec96
workflow-type: tm+mt
source-wordcount: '332'
ht-degree: 37%

---

# Search&amp;Promote 8.16.0 Versionshinweise (18.09.2014){#search-promote-release-notes}

## Search&amp;Promote 8.16.0 Versionshinweise (18.09.2014) {#topic_5BECD3F66C684987828F6AE65E62DA29}

## Neue Funktionen {#section_2A10EF6B40FC4F2CB2381FFA9FFA64BD}

* Zwischenspeichern von Suchergebnissen in der geführten Suche 3 (GS3) - Wenden Sie sich an Ihren technischen Kundenbetreuer, wenn Sie diese benutzerdefinierte Funktion einrichten möchten, damit Sie sie in Ihrem Konto verwenden können.
* Vertikale Aktualisierungen für häufig geänderte Felder - Sie können jetzt alle Werte für eine Reihe von Metadatenfeldern schnell aktualisieren, ohne den Inhalt komplett neu indizieren zu müssen.

   Siehe Option Feld für vertikale Aktualisierung in der Tabelle unter [Hinzufügen eines neuen Meta-Tag-Felds](../c-about-settings-menu/c-about-metadata-menu.md#task_6DF188C0FC7F4831A4444CA9AFA615E5) und [Über Vertikale Aktualisierung](../c-about-index-menu/c-about-vertical-updates.md#concept_E65A70C9C2E04804BF24FBE1B3CAD899).

   Diese Funktion kann nur für [!DNL Adobe Search&Promote]-Konten verwendet werden, die Index Connector verwenden. Wenn Sie diese benutzerdefinierte Funktion einrichten möchten, sodass Sie sie für Ihr Konto verwenden können, wenden Sie sich an Ihren technischen Kundenbetreuer von Adobe.

## Fehlerbehebungen und Erweiterungen {#section_22D1AFC99F394D569898828A0D3C419D}

* Korrektur des Index Connector-Parsens von XML-Feeds, die die Zeichenfolge `?>` enthielten.
* Index-Connector-SFTP-Feeds wurden behoben, wenn die minimale Dokumentanzahl erzwungen wurde.
* Der Berichtsexport nach Microsoft Excel unterstützt von nun an UTF8.
* Geführte Suche: die Facettenkompilierung war langsam.
* Attribut-Lader: für aggregierte Daten waren doppelte Schlüssel vorhanden.
* Die falsche Ausführungsreihenfolge von Geschäftsregeln beim Aufschalten einer einzelnen Regel wurde korrigiert.
* Von der geführten Suche wurden die falschen Links zum Rückgängigmachen von Facetten generiert.
* Es wurde ein neuer Fernsteuerungsvorgang hinzugefügt (`sp_lines=N`), mit dem Sie den Fortschritt und Status eines momentan ausgeführten Index-Crawls überprüfen können.

   Siehe [Info zur Remote-Steuerung für Indizierung](../c-about-index-menu/c-about-remote-control-for-indexing.md#concept_C79B322190E84106A434E5C6D4A4118F).

* Beim Abrufen von gelöschten Informationen während des Index-Connector-Inkrements müssen Authentifizierungsinformationen gesendet werden.
* Der Bericht [!DNL Change Log] identifiziert nun den Benutzer, der einen manuellen Indexvorgang initiiert.

   Siehe [Anzeigen des Änderungsprotokolls](../c-about-reports-menu/c-about-reports-menu.md#task_166F1156719F4B3D834BEA8E249C8057).

* Wenn Sie ein [!DNL Terms Report] exportieren, sind Sie nicht mehr auf 500 oder weniger Elemente im Bericht beschränkt.

   Siehe [Anzeigen des Berichts &quot;Begriffe&quot;oder des Berichts &quot;Null-Suchbegriffe&quot;...](../c-about-reports-menu/c-about-reports-menu.md#task_53B7ED1582DD4B0E8376546A7AFC789A).

* Die Einstellung Index-Connector **[!UICONTROL Strip HTML]** wurde immer als aktiviert angezeigt.
* Mit der Funktion **[!UICONTROL Common Phrases]** wurden inkonsistente Suchergebnisse festgestellt.
* Die Anzeige von Attributnamen war in den Zusammenfassungen der Regelliste abgeschnitten.
* Eine einzelne Geschäftsregel zu aktivieren, hat alle Geschäftsregeln live gedrängt.
