---
description: Mit Staging können Sie Änderungen an Ihren Einstellungen und Konfigurationen testen und in einer Vorschau anzeigen, ohne dass sich dies auf Ihren Live-Index auswirkt.
seo-description: Mit Staging können Sie Änderungen an Ihren Einstellungen und Konfigurationen testen und in einer Vorschau anzeigen, ohne dass sich dies auf Ihren Live-Index auswirkt.
seo-title: Staging
solution: Target
title: Staging
topic: Staging,Site search and merchandising
uuid: 2e5889a6-2e9c-4ac7-9d6e-d35e7cafda5b
translation-type: tm+mt
source-git-commit: ef818327e1cdaad79ac47575a8dfba1de3dc5c2e

---


# Staging{#about-staging}

Mit Staging können Sie Änderungen an Ihren Einstellungen und Konfigurationen testen und in einer Vorschau anzeigen, ohne dass sich dies auf Ihren Live-Index auswirkt.

## Staging {#concept_08B8F3CA1F4241108F14BA7FC7806CA7}

Mit Staging können Sie Änderungen an Ihren Einstellungen und Konfigurationen testen und in einer Vorschau anzeigen, ohne dass sich dies auf Ihren Live-Index auswirkt.

Siehe auch [Element-ID :context_A5783D07C72042EC8886F300FFF62C50](c-about-simulator.md#context_A5783D07C72042EC8886F300FFF62C50).

Jede Seite mit den Staging-Optionen **[!UICONTROL Push All Live]** oder **[!UICONTROL View Live Settings]** bedeutet, dass alle Einstellungen auf dieser Seite gestaffelt werden können. Ausnahmen sind die Webseiten in Index. Die Seiten in diesem Bereich gelten entweder explizit für den gestaffelten Index oder den Live-Index, damit Sie die beiden Indizes unabhängig voneinander steuern können.

Sie können fast alles anzeigen, einschließlich Ihres Indexes. Einige Ausnahmen beinhalten kontospezifische Einstellungen, die sich sowohl auf Ihre staged als auch auf die Live-Umgebung gleichzeitig auswirken, sowie die Planung von Indizierungsvorgängen. Wenn Sie Änderungen an einer Einstellung speichern, die gestaffelt werden kann, wird diese automatisch gestaffelt.

Wenn die **[!UICONTROL Push All Live]** oder die **[!UICONTROL View Lives Settings]** Optionen nicht aktiviert (abgeblendet) sind, bedeutet dies, dass die gestaffelten Einstellungen auf dieser Seite mit den Live-Einstellungen identisch sind.

Beachten Sie bei einem gestaffelten Element, dass die Live-Version der Einstellungen schreibgeschützt ist. Sie kann nur durch Live-Schaltung der inszenierten Einstellungen manipuliert werden.

## Verlauf auf Stage-Seiten {#section_5BE780AFF26A450A9EFF4000DE53531B}

Die meisten gestaffelten Einstellungen haben eine [!DNL History] Option oben rechts auf der Seite. Wenn Sie auf klicken, können Sie alle Änderungen wiederherstellen, die Sie kürzlich an der von Ihnen geöffneten gestaffelten Seite vorgenommen haben. **[!UICONTROL History]**

Sie können das Änderungsprotokoll auch für eine alternative Ansicht des Verlaufs anzeigen. Bei jeder Anwendung einer Änderung wird eine Sicherungsversion der zugrunde liegenden Datendatei erstellt. Das Änderungsprotokoll zeigt jede dieser Revisionen mit der Versionsnummer, der E-Mail-Adresse des Benutzers, der die Änderungen vorgenommen hat, und dem Datum, an dem die Sicherung durchgeführt wurde. Der Eintrag mit einem fett gedruckten Versionswert stellt die aktuelle Version dar.

See [Viewing the Change Log](c-about-reports-menu/c-about-reports-menu.md#task_166F1156719F4B3D834BEA8E249C8057).

## Die Seite &quot;Live-Einstellungen verwalten&quot; {#section_E72B8CAF516345A5B6B6783CF6E512EE}

Neben dem direkten Angebot der Optionen **[!UICONTROL Push All Live]** und **[!UICONTROL View Live Settings]** Optionen innerhalb einer bestimmten Seite können Sie auch die **[!UICONTROL Manage Stage-Live Settings]** Seite verwenden, um dasselbe zu tun. Die **[!UICONTROL Manage Stage-Live Settings]** Seite, die im Hauptmenü des Produkts verfügbar ist, ist eine zentrale Stelle, die Ihnen alle derzeit gestaffelten Einstellungen in Ihrem Konto anzeigt. Sie können alle Einstellungen live schalten, nur ausgewählte Einstellungen live schalten oder Einstellungen löschen. Als Best Practice sollten Sie jedoch alle gestaffelten Elemente immer live schalten, um Probleme mit der wechselseitigen Abhängigkeit zu vermeiden.

Die Einstellungen auf der Seite sind in Kategorien unterteilt. Sie können jede Kategorie erweitern, um anzuzeigen, welche Seiteneinstellungen gestaffelt werden. Derzeit werden Abhängigkeiten nicht im Stage Manager nachverfolgt. Es wird daher empfohlen, alle Elemente mit Ausnahme des Indexes gleichzeitig zu veröffentlichen.

Sie können einen gestaffelten Index live übertragen. Vergewissern Sie sich, dass Sie zuerst überprüfen, ob der gestaffelte Index nicht stabil oder beschädigt ist. Wenn Sie einen Fehler machen und den gestaffelten Index live schalten, können Sie einen alten Live-Index wiederherstellen. Die Liveschaltung eines gestaffelten Indexes dauert in der Regel weniger als 30 Sekunden.

## Testen einer gestaffelten Einstellung oder eines Indexes {#section_6800E52D20854A779946EAB600801F12}

Auf Seiten, die ein Teststeuerelement unterstützen, können Sie diese mit den Einstellungen für die Stage- oder Live-Wiedergabe testen. Wenn Sie die gestaffelten Einstellungen anzeigen, wird die gestaffelte Einstellung für den Test verwendet. Ebenso verwendet der Test beim Anzeigen der Live-Einstellung die Live-Einstellungen. Im Abschnitt &quot;Vorlagen&quot;werden alle Tests mit der gestaffelten Version des Indexes durchgeführt. Um einen gestaffelten Index zu suchen, legen Sie den `sp_staged` CGI-Parameter gleich 1 fest. Dies bedeutet wiederum, dass Sie den gestaffelten Index verwenden möchten. Wenn kein gestaffelter Index vorhanden ist, wird Ihr Liveindex durchsucht und die Einstellungen für die gestaffelte Suchzeit werden entsprechend angewendet.

Siehe auch CGI-Parameter für die [Backend-Suche](c-appendices/c-cgiparameters.md#reference_582E85C3886740C98FE88CA9DF7918E8).

## Live-Einstellungen anzeigen {#task_401A0EBDB5DB4D4CA933CBA7BECDC10F}

Sie können die Live-Version der Einstellungen von jeder gestaffelten Seite aus überprüfen.

<!-- 

t_viewing_live_settings.xml

 -->

Wenn die **[!UICONTROL View Live Settings]** Option nicht aktiviert (abgeblendet) ist, bedeutet dies, dass die Anzeigeeinstellungen für diese Seite und die Live-Einstellungen bereits synchronisiert sind.

**So zeigen Sie Live-Einstellungen an**

1. Klicken Sie auf einer Seite mit Stage-Einstellungen auf **[!UICONTROL View Live Settings]** , um die Live-Version der Einstellungen anzuzeigen.
1. Optional können Sie einen der folgenden Schritte ausführen:

   * Klicken Sie auf **[!UICONTROL View]** , um die aktuellen Optionen anzuzeigen, die für die Einstellung &quot;Gestaffelt&quot;ausgewählt wurden.
   * Klicken Sie **[!UICONTROL View Stage Settings]** auf , um zur gestaffelten Einstellung zurückzukehren, in der Sie die Einstellung bearbeiten oder löschen können.

## Push-Einstellungen live {#task_44306783B4C0408AAA58B471DAF2D9A4}

Sie können die Einstellungen von jeder gestaffelten Seitenansicht oder von der zentralen **[!UICONTROL Manage Stage-Live Settings]** Seite live übertragen.

<!-- 

t_pushing_live_settings_live.xml

 -->

Wenn die **[!UICONTROL Push Live]** Option auf einer Seite aktiviert (nicht abgeblendet) ist, bedeutet dies, dass eine gestaffelte Einstellung vorhanden ist. Oder es bedeutet, dass eine Einstellung bearbeitet wird und die Einstellung beim Speichern gestaffelt wird. Wenn Sie auf diese Option klicken, werden alle nicht gespeicherten Änderungen im gestaffelten Bereich gespeichert. Wenn keine Bearbeitung aussteht, werden die Einstellungen der Seite sofort live geschaltet.

**So übertragen Sie Stage-Einstellungen live**

1. Führen Sie einen der folgenden Schritte aus:

   * Klicken Sie auf jeder Seite, für die &quot;Staged&quot;als Ansicht ausgewählt ist, auf **[!UICONTROL Push Live]**.
   * Klicken Sie im Produktmenü auf **[!UICONTROL Staging]**. Führen Sie auf der **[!UICONTROL Manage Stage-Live Settings]** Seite einen der folgenden Schritte aus:

   * Überprüfen Sie in der Einstellungsstruktur nur die Einstellungen, die Sie live übertragen möchten, und klicken Sie dann auf **[!UICONTROL Push Selected Live]**.
   * Klicken **[!UICONTROL Push All Live]**.

## Löschen der Einstellungen für die Stage-Live-Wiedergabe von einem zentralen Speicherort {#task_B72BEA9269704B1399600A9CA273369B}

Wenn Sie viele Einstellungen löschen müssen, können Sie die Einstellungen auf der **[!UICONTROL Manage Stage-Live Settings]** Seite an einem zentralen Speicherort löschen.

<!-- 

t_deleting_staged_settings_from_a_central_location.xml

 -->

**Warnung**: Wenn Sie auf klicken **[!UICONTROL Delete Selected]**, werden alle aktivierten Einstellungen sofort gelöscht. Es gibt kein Bestätigungsdialogfeld, um zu überprüfen, ob Sie die ausgewählten Einstellungen wirklich löschen möchten. Außerdem gibt es keine Verlaufsfunktion, die mit der Seite verknüpft ist. Daher können Sie den Löschvorgang nicht rückgängig machen.

**So löschen Sie die Stage-Live-Einstellungen von einem zentralen Speicherort**

1. Klicken Sie im Produktmenü auf **[!UICONTROL Staging]**.
1. Verwenden Sie auf der **[!UICONTROL Manage Stage-Live Settings]** Seite die Einstellungsstruktur, um nur die Einstellungen zu überprüfen, die Sie löschen möchten.
1. Klicken **[!UICONTROL Delete Selected]**.
