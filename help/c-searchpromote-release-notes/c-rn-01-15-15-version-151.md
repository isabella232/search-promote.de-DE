---
description: Search&amp;Promote 15.1.1 Versionshinweise.
solution: Target
title: Search&amp;Promote 15.1.1 Versionshinweise (15.01.2015)
topic: Versionshinweise, Site-Suche und Merchandising
uuid: 070f9c46-426f-4ca1-80c7-8ca53d40a402
translation-type: tm+mt
source-git-commit: d015154efdccbb4c6a39a56907c0c337ec065c9f
workflow-type: tm+mt
source-wordcount: '241'
ht-degree: 16%

---


# Search&amp;Promote 15.1.1 Versionshinweise (15.01.2015){#search-promote-release-notes}

## Neue Funktion {#section_2A10EF6B40FC4F2CB2381FFA9FFA64BD}

* Bisher wurden in Regeln für die geführte Suche immer linguistische Funktionen wie Wortstämme, Synonyme usw. auf die Keywords angewendet. Nun können Sie diese Erweiterung deaktivieren, damit nur das Keyword wie eingegeben verwendet wird.

   Wenn Sie Geschäftsregeln auf eine Geschäftsregel anwenden möchten, wählen Sie im [!DNL Advanced Rule Builder] nach **[!UICONTROL If any/all of the following conditions are met]** in der ersten Dropdown-Liste **[!UICONTROL keyword]** und dann in der zweiten Dropdown-Liste den neuen Operator **[!UICONTROL equal exact]** aus.

   Siehe [Geschäftsregeln](../c-about-rules-menu/c-about-business-rules.md#concept_2A93D76216754D3D8412CDEA00BD26BD).

## Fehlerbehebungen und Erweiterungen {#section_22D1AFC99F394D569898828A0D3C419D}

* [!DNL Visual Rule Builder] und  [!DNL Advanced Rule Builder] verkürzt den Feldwert des MDI (Merchandising-Dokument-ID) nicht mehr.
* Die RBTA-bezogenen Indizierungsfehler wurden nun behoben.
* Beim Bearbeiten einer vorhandenen Geschäftsregel mit dem Status &quot;genehmigt&quot;wird jetzt der Status &quot;genehmigt&quot;widerrufen. Sie müssen [!DNL Advanced Rule Builder] verwenden, um die Option **[!UICONTROL Approved]** erneut zu aktivieren, und die Regel dann wie gewohnt speichern. Wenn Sie eine bearbeitete Regel nicht erneut genehmigen, wird der Status der Regel automatisch auf der Seite [!DNL Business Rules] auf WIP (Work In Progress) eingestellt.
* Auf der Seite [!DNL Business Rules] steht jetzt eine neue Option **[!UICONTROL Advanced Search]** zur besseren Filterung von Regeln zur Verfügung.
* Die Bedingung **[!UICONTROL contains word]** wurde zu den Regelbedingungen in [!DNL Query Cleaning], [!DNL Pre-Search Rules], [!DNL Post Search Rules] und [!DNL Business Rules] hinzugefügt, damit Sie Wortumbrüche einfach angeben können.
* Verbesserungen, die an Geschäftsregelhinweisen vorgenommen wurden, z. B. beim Ansicht einer Regel, können Sie jetzt den Notizverlauf für diese Regel abrufen. Notizen sind jetzt auch bei **[!UICONTROL Reports]** > **[!UICONTROL Change Log]** angemeldet.
* Abfragen mit einem &lt; 0/>-Wert ungleich null werden nicht mehr durch die [!DNL Adobe Analytics]-Weiterleitung ausgeführt.`sp_i`

   Siehe Zeile 15 in der Tabelle unter [CGI-Parameter für die Backend-Suche](../c-appendices/c-cgiparameters.md#reference_582E85C3886740C98FE88CA9DF7918E8).

