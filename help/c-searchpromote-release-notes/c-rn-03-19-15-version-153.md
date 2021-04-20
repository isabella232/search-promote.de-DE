---
description: Search&amp;Promote 15.3.1 Versionshinweise.
solution: Target
title: Search&amp;Promote 15.3.1 Versionshinweise (24.03.2015)
topic: Release Notes,Site search and merchandising
uuid: f02da5a4-2207-4603-aa05-5cff7be16dd5
translation-type: tm+mt
source-git-commit: d015154efdccbb4c6a39a56907c0c337ec065c9f
workflow-type: tm+mt
source-wordcount: '260'
ht-degree: 1%

---


# Search&amp;Promote 15.3.1 Versionshinweise (24.03.2015){#search-promote-release-notes}

## Neue Funktionen und Verbesserungen {#section_2A10EF6B40FC4F2CB2381FFA9FFA64BD}

* Suche nach Produktmodellnummern - Es wurde eine neue Linguistik-Einstellung hinzugefügt, mit der Sie optional Token auf alphabetisch-numerischen Transitionen teilen können. Diese Funktion ermöglicht flexiblere Freitextübereinstimmungen auf Teil- oder Produktstil-Token.

   Siehe **[!UICONTROL Partial Alphanumeric Matching]** in [Konfigurieren der Übereinstimmung von Suchbegriffen mit Ihrem Webinhalt...](../c-about-linguistics-menu/c-about-words-and-language.md#task_351A9144A51F4B41923BDBACDEF3B616).

* Zusätzliche Möglichkeit zum Exportieren von Daten-Ansichten.

   Siehe [Info zu Data Ansichten](../c-about-reports-menu/c-about-data-views.md#concept_DCA897D074464BC1861AA47B40CC86C3).

* Dynamisch generierte Bereiche für Attribute im Bereich, automatische Facetten-Wert-Sicherungsfunktionen.

   Adobe Systems verlangt derzeit, dass Sie zu diesem Zweck Inhaltswerte bereitstellen, die Bereichswerte identifizieren. Erstellen Sie beispielsweise für einen Preis von 10 eine Bereichszeichenfolge &quot;Zwischen 10 und 20 USD&quot;). Adobe Systems erfordert auch die Verwendung von skriptgesteuerten Filtern. Neue Attribute zu einer Metadatenfelddefinition hinzugefügt, nur für Felder `Type=Number`. Die neuen Optionen verknüpfen das numerische Feld mit einem `Type=Text`-Feld und geben Konfigurationsinformationen an, die beschreiben, wie die Bereichsbeschreibung erstellt wird.

   Siehe [Hinzufügen eines neuen Meta-Tag-Felds](../c-about-settings-menu/c-about-metadata-menu.md#task_6DF188C0FC7F4831A4444CA9AFA615E5).

## Fehlerkorrekturen {#section_22D1AFC99F394D569898828A0D3C419D}

* Das Dialogfeld zum Bearbeiten der Facet-Leiste sollte gestaffelte Facetten enthalten.
* Leere Kernsuchergebnisse für &quot;eingebetteten&quot;Suchmodus, für eine Suche mit japanischen Zeichen.
* Die Tika-Konvertierung von Word .docx-Dateien füllt jetzt das Attribut `title`.
* Fehlerhafte &quot;Duplikat-Banner&quot;-Meldungen im **[!UICONTROL Banner]**-Manager wurden korrigiert.
* [!DNL Dynamic Media Classic] Banner sind jetzt protokollagnostisch.
* Das Feldattribut **[!UICONTROL Table Name]** wurde manchmal ausgeblendet, wenn benutzerdefinierte Felder in der Benutzeroberfläche &quot;Metadaten&quot;bearbeitet wurden, selbst wenn **[!UICONTROL Dynamic Facets]** für das Konto aktiviert war.
* **[!UICONTROL Recent Searches]** nicht mehr mehrfache Kodierungen von Nicht-ASCII-Zeichen.
* MDI-Felder können ausgefüllt werden, ohne auf die skriptgesteuerte Filterung zurückzugreifen.
* Falsche Kodierung in Vorschlägen.
* Der Trigger &quot;andere Facets ausgewählt&quot;funktioniert jetzt korrekt mit komplexen Geschäftsregeln.

