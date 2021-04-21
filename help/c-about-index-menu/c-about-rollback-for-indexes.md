---
description: Sie können Rollback verwenden, um von Ihnen erstellte Website-Indizes zu sichern und zu archivieren. Sie können die Sicherung eines Indexes auch jederzeit wiederherstellen.
solution: Target
subtopic: Rollback
title: Grundlagen zur Datenwiederherstellung für Indizes
topic-legacy: Index,Site search and merchandising
uuid: abed878a-71b3-4122-9822-7410f4427a9a
exl-id: bc75f6ba-d919-4dff-8ee2-e17568892626
translation-type: tm+mt
source-git-commit: 7559f5f7437d46e3510d4659772308666425ec96
workflow-type: tm+mt
source-wordcount: '835'
ht-degree: 0%

---

# Info zur Datenrückgängigmachung für Indizes{#about-rollback-for-indexes}

Sie können [!DNL Rollback] verwenden, um von Ihnen erstellte Website-Indizes zu sichern und zu archivieren. Sie können die Sicherung eines Indexes auch jederzeit wiederherstellen.

## Verwenden von Datenrückläufen für Indizes {#concept_0BC4BC975DB045A986C3607CF32705D8}

Das Archiv enthält vier Indizes: den aktuellen Site-Index und drei vorherige Site-Indizes, die der Suchroboter automatisch anhand der Rollback-Konfigurationseinstellungen archiviert. Bei jeder Indexierung Ihrer Website wird das Archiv aktualisiert. Neuere Indizes ersetzen vorhandene archivierte Indizes, sodass das Archiv immer aktuell bleibt.

Jeder archivierte Index wird mit den folgenden Informationen im Archiv aufgeführt:

* Datum und Uhrzeit der Fertigstellung des Indexes
* Indexalter.
* Anzahl der indizierten Dokumente.
* Indizierung des Operationstyps (vollständig, inkrementell usw.)
* Indexstatus, z. B. ob der Index aktuell aktiv ist und ob er nach dem nächsten Index beibehalten oder entfernt wird.

Bei jeder Indexierung Ihrer Website wird der neue Index dem Archiv hinzugefügt und ein vorhandener archivierter Index wird entfernt. Beachten Sie jedoch, dass der älteste Index nicht unbedingt derjenige ist, der entfernt wird. Wenn dem Archiv ein neuer Index hinzugefügt wird, wird für jeden archivierten Index ein Altersvergleich mit den in den Einstellungen für die Rollback-Konfiguration angegebenen Seiten durchgeführt. Der am weitesten vom gewünschten Zeitplan entfernte Index wird entfernt. Angenommen, die Konfigurationseinstellung beträgt 24,48,72 und die Altersgruppe der gespeicherten Indizes beträgt 5, 23, 47 und 71. Der letzte Index (fünf Stunden alt) wird entfernt, wenn dem Archiv ein neuer Index hinzugefügt wird, weil das Alter am weitesten von den Einstellungen entfernt ist. Der Einfachheit halber wird im Archiv angegeben, welcher Index entfernt wird, wenn die Site erneut indiziert wird.

Sie können während der Aktivierung eines Indexes zu anderen Bereichen in der Benutzeroberfläche navigieren. Eine Statusanzeige verfolgt den Fortschritt der Aktivierung und ist verfügbar, wenn Sie die Ansicht der [!DNL Rollback]-Seite durchführen. Wenn ein archivierter Index wiederhergestellt wird, werden Benutzer über die Seiten &quot;Vollständiger Index&quot;, &quot;Inkrementeller Index&quot;, &quot;Skriptindex&quot;und &quot;Regenerieren&quot;benachrichtigt. Während der Wiederherstellung eines Indexes kann es zu keinem Indexierungsvorgang kommen. Wenn ein Rollback-Vorgang mit einem geplanten Site-Index kollidiert, wird die geplante Indexierung aufgeschoben, bis der Rollback abgeschlossen ist. Wenn ein Index bereits ausgeführt wird, wird er abgebrochen, sofern der Benutzer bestätigt, dass die Rollback-Priorität erhalten wird.

Um die Integrität des Archivs zu wahren, aktualisiert der Suchroboter das Datenrücklaufarchiv nicht, wenn während eines Crawls Fehler auftreten. Es gibt auch keine Aktualisierung, wenn ein Benutzer einen Indexierungsvorgang abbricht. Wenn ein Indexierungsvorgang die maximale Zeit, Byte, Seiten oder Dokumente überschreitet, schließt der Crawler den Index ab und fügt ihn dem Archiv hinzu. Wenn die Mindestanzahl von Seiten bei einem Indexierungsvorgang nicht erreicht wird, bricht der Crawler den Index ab und der vorherige Index bleibt aktiv.

## Konfigurieren des Wiederherstellungs-Archivierungsplans für Indizes {#task_CD403B9AE2244B13A6B3861B5F9B055C}

Sie können [!DNL Configure] verwenden, um zu ermitteln, welche Indexdateien im Datenrücklaufarchiv gespeichert werden sollen. Das Archiv kann den aktuellen Index und drei Sicherungsindizes speichern.

Das Feld **[!UICONTROL Schedule]** enthält drei kommagetrennte Werte, die Stunden von der Gegenwart repräsentieren. Die Zeitplanwerte 24,48,72 geben beispielsweise 24 Stunden ab der Gegenwart oder gestern, 48 Stunden ab der Gegenwart oder vor zwei Tagen und 72 Stunden ab der Gegenwart oder vor drei Tagen an.

Die Suche archiviert kontinuierlich die Site-Indizes, die einem Tag, zwei Tagen und drei Tagen am nächsten liegen. Die tatsächlichen Zeiten und Daten der archivierten Indizes können je nach Indizierungszeitplan Ihrer Website variieren.

**So konfigurieren Sie den Zeitplan für die Archivierung der Datenrückkopien von Indizes**

1. Klicken Sie im Produktmenü auf **[!UICONTROL Index]** > **[!UICONTROL Rollback]** > **[!UICONTROL Configure]**.
1. Geben Sie auf der Seite [!DNL Rollback Configuration] im Feld **[!UICONTROL Schedule]** eine kommagetrennte Liste von drei Indexseiten in Stunden ein. Die Indizes, die diesen Seiten am nächsten kommen, werden gespeichert.
1. Klicken **[!UICONTROL Save Changes]**.

## Aktivieren eines archivierten Indexes {#task_5DCE3D660F6F4197993E92AA59227332}

Sie können die Funktion &quot;Datenrücklauf&quot;verwenden, um einen archivierten Index zu aktivieren.

Wenn Sie auf **[!UICONTROL Activate]** klicken, um einen Index zurückzufahren, wird der derzeit aktive Index in das Archiv verschoben.

Nach der Aktivierung des archivierten Indexes werden Sie zur Seite [!DNL Activate Index] zurückgeleitet. Informationen zum Index-Rollback werden angezeigt. Die Spalte [!DNL Activate] in der Tabelle [!DNL Available Indexes] gibt außerdem den Index für die zurückgerollte Anzeige mit dem Status &quot;Active Index&quot;an.

1. Klicken Sie im Produktmenü auf **[!UICONTROL Index]** > **[!UICONTROL Rollback]** > **[!UICONTROL Rollback]**.
1. Klicken Sie auf der Seite [!DNL Activate Index] in der Tabelle [!DNL Available Indexes] für den verknüpften archivierten Indextyp, den Sie aktivieren möchten, auf **[!UICONTROL Activate]**.

   Verwenden Sie die Spalten &quot;Datum&quot;, &quot;Alter&quot;, &quot;Seiten&quot;und &quot;Vorgang&quot;, um festzustellen, welcher Index aktiviert werden soll.
1. Überprüfen Sie auf der Seite [!DNL Verify Rollback] die Indexinformationen, um sicherzustellen, dass Sie den richtigen Index ausgewählt haben, und klicken Sie dann auf **[!UICONTROL Activate Now]**.

## Anzeigen des Protokolls aller Index-Rückflüsse {#task_D2D9AA7203F0465FB5AE0D49212AC41C}

Ansicht des Datums und der Uhrzeit aller rollback-bezogenen Vorgänge

**So Ansicht Sie das Protokoll aller Index-Rückflüsse**

1. Führen Sie im Produktmenü einen der folgenden Schritte aus:

   * Klicken Sie auf **[!UICONTROL Index]** > **[!UICONTROL Re-Rank Index]** > **[!UICONTROL Live Log]**.

   * Klicken Sie auf **[!UICONTROL Index]** > **[!UICONTROL Re-Rank Index]** > **[!UICONTROL Staged Log]**.

1. Führen Sie auf der Protokollseite oben oder unten einen der folgenden Schritte aus:

   * Verwenden Sie die Navigationsoptionen **[!UICONTROL First]**, **[!UICONTROL Prev]**, **[!UICONTROL Next]**, **[!UICONTROL Last]** oder **[!UICONTROL Go to line]**, um durch das Protokoll zu navigieren.

   * Verwenden Sie die Anzeigeoptionen **[!UICONTROL Errors only]**, **[!UICONTROL Wrap line]** oder **[!UICONTROL Show]**, um Ihre Anzeige zu verfeinern.
