---
description: Sie können den vollständigen Index verwenden, um alle Seiten Ihrer gestaffelten oder Live-Website zu indizieren. Die Indizierung hilft Ihren Kunden, leichter zu finden, was sie suchen oder was sie benötigen, wenn sie eine Suche durchführen.
solution: Target
subtopic: Full Index
title: Info zu vollständigem Index
topic: Index,Site search and merchandising
uuid: dce1eafd-5aea-4945-8305-8f9e7dc392df
translation-type: tm+mt
source-git-commit: d015154efdccbb4c6a39a56907c0c337ec065c9f
workflow-type: tm+mt
source-wordcount: '760'
ht-degree: 1%

---


# Über vollständigen Index{#about-full-index}

Sie können den vollständigen Index verwenden, um alle Seiten Ihrer gestaffelten oder Live-Website zu indizieren. Die Indizierung hilft Ihren Kunden, leichter zu finden, was sie suchen oder was sie benötigen, wenn sie eine Suche durchführen.

## Vollständiger Index {#concept_C69BD21863FD4856B49326F35DB570D3}

Wenn Sie einen vollständigen Index generieren, werden Statusinformationen angezeigt, wie z. B. die Beginn- und die Verfallszeit sowie Fehler während des Indexvorgangs. Informationen zum Status des letzten Index werden ebenfalls angezeigt.

Wenn Sie eine Kontoeinstellung geändert haben, für die eine Indexwiederherstellung erforderlich ist, lautet der Status möglicherweise &quot;Regenerierung&quot;. Während der Regenerierung werden Kontoeinstellungen angewendet, um einen aktualisierten Site-Index zu erstellen.

Sie können den Indexierungsvorgang jederzeit beenden oder neu starten.

Während der neue Index für eine Live-Website erstellt wurde, können Kunden weiterhin Ihre Site anhand Ihres letzten Indexes suchen. Informationen zum Status des letzten Index werden ebenfalls angezeigt.

## Einstellen des vollständigen Indexplans für eine Live-Website {#task_6760F3256D004A228B38968DF15421F0}

Sie können die Uhrzeit und die Tage angeben, an denen die Website durchsucht werden soll, und den Index aktualisieren.

Die von Ihnen ausgewählte Zeit ist lokal gemäß der Zeitzone, die in den Kontoeinstellungen konfiguriert ist.

Siehe [Konfigurieren Ihrer Kontoeinstellungen](../c-about-settings-menu/c-about-account-options-menu.md#task_80A38D0C8E4F453395BD67B81E4B45D9).

Webserver sollen oft mitten in der Nacht zur Wartung aussteigen. Wenn Ihr Server während einer geplanten Indexzeit ausfällt, schlägt der Indexierungsvorgang fehl. Stellen Sie sicher, dass Sie eine Tageszeit auswählen, zu der der Webserver verfügbar ist.

Der Index-Plan gilt nur für Ihren Live-Index. Sie können keine Stage-Indizes planen.

**So legen Sie den vollständigen Indexzeitplan für eine Live-Website fest**

1. Klicken Sie im Produktmenü auf **[!UICONTROL Index]** > **[!UICONTROL Full Index]** > **[!UICONTROL Live Schedule]**.
1. Wählen Sie in der Dropdown-Liste **[!UICONTROL Time]** die Stunde aus, in der die vollständige Indexierung an Beginn erfolgen soll.
1. Wählen Sie einen oder mehrere Tage aus, an denen die vollständige Indexierung ausgeführt werden soll.
1. Klicken **[!UICONTROL Save Changes]**.

## Ausführen eines vollständigen Indexes einer Live- oder Staged-Website {#task_F7FE04D8A1654A7787FCCA31B45EB42D}

Sie können den vollständigen Index verwenden, um alle Seiten Ihrer gestaffelten oder Live-Website zu indizieren. Die Indizierung hilft Ihren Kunden, leichter zu finden, was sie suchen oder was sie benötigen, wenn sie eine Suche durchführen.

**So führen Sie einen vollständigen Index einer Live- oder einer Stage-Website aus**

1. Führen Sie im Produktmenü einen der folgenden Schritte aus:

   * Klicken Sie auf **[!UICONTROL Index]** > **[!UICONTROL Full Index]** > **[!UICONTROL Live Index]**.

   * Klicken Sie auf **[!UICONTROL Index]** > **[!UICONTROL Full Index]** > **[!UICONTROL Staged Index]**.

1. Legen Sie die gewünschten Indexierungsoptionen fest.

   <table> 
    <thead> 
    <tr> 
    <th colname="col1" class="entry"> <p>Option </p> </th> 
    <th colname="col2" class="entry"> <p>Beschreibung </p> </th> 
    </tr> 
    </thead>
    <tbody> 
    <tr> 
    <td colname="col1"> <p>Index-Cache löschen </p> </td> 
    <td colname="col2"> <p>Entfernt alle Dokumente aus dem Index-Cache. </p> <p>Wenn diese Option aktiviert ist, wird jede Webseite von Ihrem Server heruntergeladen. Wenn diese Einstellung aktiviert und deaktiviert ist, wird Ihr Konto so eingestellt, dass der Cache jedes Mal gelöscht wird, wenn ein vollständiger Index ausgeführt wird. Oder einige zuvor geänderte Kontoeinstellungen erfordern jetzt einen vollständigen Index. </p> <p>Wenn diese Option deaktiviert ist, bleiben alle indizierten Seiten im Index, bis der Webserver erklärt, dass die Seite nicht mehr vorhanden ist. Dies ist auch dann der Fall, wenn Links zu dieser Seite entfernt werden. </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> <p>Ausstehende Elemente wiederherstellen </p> </td> 
    <td colname="col2"> <p>Wählen Sie "Wenn Sie Änderungen an Ihren Kontoeinstellungen vorgenommen haben, die den Inhalt Ihres Indexes wesentlich geändert haben". Wesentliche Änderungen beinhalten Änderungen an Folgendem: 
    <ul id="ul_4EB8FF692FEB47BBB9A64D61299380D1"> 
    <li id="li_7CF8D286512F4210BEA3DB9F0EFA097A">Synonyme </li> 
    <li id="li_8178ABC342BB4365B3927E20433756E3">Sammlungen </li> 
    <li id="li_57C8BD06BFA64AFAA2C9EF2CC59520EF">Metadaten </li> 
    <li id="li_C4B6A7DA023B4A43991D03EC592170C9">Ausgeschlossene Wörter </li> 
    <li id="li_9E0AD4B6DDC24A5A8FB5C2C1CCD5348A">Kontosprache </li> 
    <li id="li_338F107547DF48AAA0EF90F4AD8664A5">Klassifizierung </li> 
    <li id="li_7F49B86D94974E79AAD381A64A1400F2">Umschalten zwischen Groß- und Kleinschreibung </li> 
    <li id="li_E8FE6EE240A840AC826ADF4294AAC6F6">Umschalten zwischen diakritischer Unterstützung </li> 
    <li id="li_51763D482DCB4ED0972966F492B8C0F2">Nummernindizierung umschalten </li> 
    </ul> </p> <p>Bevor ein weiterer Crawl einsetzt, wird ein schneller Durchlauf durch alle Indexdaten durchgeführt, damit diese den neuen Kontoeinstellungen entsprechen. </p> <p>Diese Option ist nur verfügbar, wenn Sie einen vollständigen Index einer gestaffelten Website erstellen. </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> <p>Alle Seiten zählen </p> </td> 
    <td colname="col2"> <p>Ermöglicht das Crawling von Webseiten auch dann fortzusetzen, wenn Sie das Limit Ihrer Kontoseite erreicht haben. </p> <p>Dem Index werden keine weiteren Seiten hinzugefügt, Sie können jedoch die Gesamtanzahl der Dokumente auf Ihrer Website ermitteln. </p> </td> 
    </tr> 
    </tbody> 
    </table>

1. Klicken **[!UICONTROL Full Index Now]**.
1. (Optional) Wenn Indexierungsfehler aufgetreten sind, klicken Sie auf **[!UICONTROL View Errors]**, um das zugehörige Protokoll Ansicht.

## Anzeigen des vollständigen Indexprotokolls einer Live- oder Stage-Website {#task_02E5E944C56B4EB19CC1FF321F3221B8}

Wenn ein vollständiger Index oder ein gestaffelter vollständiger Index abgeschlossen ist, können Sie das zugehörige Protokoll zur Fehlerbehebung für eingetretene Fehler Ansicht haben.

Protokolle können weder exportiert noch gespeichert werden. Das Protokoll bleibt bis zum Auftreten des neuen Indexes zur Ansicht verfügbar.

**So erstellen Sie die Ansicht des vollständigen Indexprotokolls einer Live- oder einer Stage-Website**

1. Führen Sie im Produktmenü einen der folgenden Schritte aus:

   * Klicken Sie auf **[!UICONTROL Index]** > **[!UICONTROL Full Index]** > **[!UICONTROL Live Log]**.

   * Klicken Sie auf **[!UICONTROL Index]** > **[!UICONTROL Full Index]** > **[!UICONTROL Staged Log]**.

1. Führen Sie auf der Protokollseite oben oder unten einen der folgenden Schritte aus:

   * Verwenden Sie die Navigationsoptionen **[!UICONTROL First]**, **[!UICONTROL Prev]**, **[!UICONTROL Next]**, **[!UICONTROL Last]** oder **[!UICONTROL Go to line]**, um durch das Protokoll zu navigieren.

   * Verwenden Sie die Anzeigeoptionen **[!UICONTROL Errors only]**, **[!UICONTROL Wrap line]** oder **[!UICONTROL Show]**, um Ihre Anzeige zu verfeinern.

