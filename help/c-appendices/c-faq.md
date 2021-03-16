---
description: Lesen Sie häufig gestellte Fragen zu Search&amp;Promote
solution: Target
title: Häufig gestellte Fragen
topic: Anlagen, Site-Suche und Merchandising
uuid: 4ce454a4-e770-4587-91a0-a25491818ac6
translation-type: tm+mt
source-git-commit: d015154efdccbb4c6a39a56907c0c337ec065c9f
workflow-type: tm+mt
source-wordcount: '8648'
ht-degree: 0%

---


# Häufig gestellte Fragen{#frequently-asked-questions}

## Adobe Flash {#reference_4A25BBDE32214AF5A1A454F38FD51243}

Eine Seite mit häufig gestellten Fragen, die die Unterstützung der Indizierung und Suche von SWF-Dateien auf einer Website behandelt.

Im Folgenden werden häufig gestellte Fragen zu SWF-Dateien behandelt:

* [Wann wird eine SWF-Datei durchsucht und indiziert?](#section_01BB5259140D4D5FB04CCB7A1A63DE99)
* [Was muss ich tun, um eine SWF zu indizieren?](#section_0A6A52CC70D4495BBE14D91906318F95)
* [Wie werden SWF-Dateien erkannt?](#section_B36C0536AB544F509601DC6A11A8E656)
* [Wie werden SWF-Dateien indiziert?](#section_36856058A4B54FA5ABF921344F50410C)
* [Zählt eine SWF-Datei als Seite?](#section_0158D6DE70BC40D78E2374787B9F58AB)
* [Wie vermeide ich die Indizierung einzelner SWF-Dateien...](#section_E38AD37989EF410B97AF5125057BFD22)
* [Wie kann ich verhindern, dass SWF-Dateien in ...](#section_DF2606A50E9A44859CFA0D44D7C5F2E4)
* [Wie kommt es, dass ich die chinesischen, japanischen oder koreanischen SWF-Dateien auf meiner Website nicht durchsuchen kann?](#section_EE1A3A705AE74148BD195A0CE513A5C4)

## Wann wird eine SWF-Datei durchsucht und indiziert? {#section_01BB5259140D4D5FB04CCB7A1A63DE99}

Eine SWF-Datei wird durchsucht und indiziert, wenn sie in einem Einbettungs- oder Objekt-Tag auf einer HTML-Seite enthalten ist, wie im folgenden Beispiel:

```
<embed src="Flash-file-URL">  
 
<object>  
<param name=movie value="Flash-file-URL">  
</object> 
```

Eine SWF-Datei wird auch erkannt, wenn Sie die Datei-URL als Einstiegspunkt Liste haben.

Siehe [Hinzufügen mehrerer URL-Einstiegspunkte, die indiziert werden sollen.](../c-about-settings-menu/c-about-crawling-menu.md#task_2338A47387D74CFDAC4D4EF4A367ED45)

## Was muss ich tun, um eine SWF-Datei zu indizieren? {#section_0A6A52CC70D4495BBE14D91906318F95}

Um SWF-Dateien zu suchen und zu indizieren, wählen Sie den Inhaltstyp **[!UICONTROL Adobe Flash Movies]** ( **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Content Types]**).

Solange auf Ihre Flash-Datei von einem `<embed>`-Tag oder einem `<object>`-Tag in einem HTML-Dokument verwiesen wird, wird der Text indiziert und alle in der Datei aufgelisteten URLs werden durchsucht.

Wenn Ihre Datei nicht über ein `<embed>`-Tag oder ein `<object>`-Tag referenziert wird, können Sie die SWF-Datei in einem `<a href=...>`-Tag in einem HTML-Dokument oder als URL-Einstiegspunkt Liste werden.

Siehe [Hinzufügen mehrerer URL-Einstiegspunkte, die indiziert werden sollen.](../c-about-settings-menu/c-about-crawling-menu.md#task_2338A47387D74CFDAC4D4EF4A367ED45)

## Wie werden SWF-Dateien erkannt? {#section_B36C0536AB544F509601DC6A11A8E656}

SWF-Dateien werden durch den folgenden MIME-Typ identifiziert:

`application/x-shockwave-flash`

SWF-Dateien werden auch mit den MIME-Typen `application/octet-stream`&quot;oder `text/plain` erkannt, vorausgesetzt, die Dateierweiterung lautet .swf.

Ein falsch konfigurierter Server verwendet möglicherweise einen anderen MIME-Typ für SWF-Dateien. Überprüfen Sie unbedingt die Serverkonfiguration, wenn beim Crawling und Indizieren von SWF-Dateien Probleme auftreten.

## Wie werden SWF-Dateien indiziert? {#section_36856058A4B54FA5ABF921344F50410C}

In einer SWF-Datei enthaltener Text wird indiziert, als wäre er `<body>`-Text auf der umschließenden HTML-Seite. Wenn ein Suchergebnis Text findet, der in einer eingebetteten SWF-Datei enthalten ist, wird das Ergebnis tatsächlich mit der einschließenden HTML-Seite und nicht mit der SWF-Datei verknüpft. Auf diese Weise wird die SWF-Datei im richtigen Kontext angezeigt.

Wenn eine SWF-Datei eine URL als Aktion &quot;Film laden&quot;enthält, wird der Text in der referenzierten SWF-Datei als Teil der umschließenden HTML-Seite indiziert.

Wenn eine SWF-Datei eine URL als Aktion &quot;URL abrufen&quot;enthält, wird die URL zu einem späteren Zeitpunkt durchsucht und indiziert, genau wie eine HTML-Referenz `<a href=...>` durchsucht und später indiziert wird.

Wenn eine SWF-Datei als URL-Einstiegspunkt aufgeführt wird, wird der Text der SWF-Datei als eine einzige Seite indiziert. Ein Suchergebnis, das Text von einer Einstiegs-SWF-Verknüpfung direkt zum Film findet, nicht zu einer umschließenden HTML-Seite.

Siehe [Hinzufügen mehrerer URL-Einstiegspunkte, die indiziert werden sollen.](../c-about-settings-menu/c-about-crawling-menu.md#task_2338A47387D74CFDAC4D4EF4A367ED45)

## Zählt eine SWF-Datei als Seite? {#section_0158D6DE70BC40D78E2374787B9F58AB}

Nein. Eine SWF-Datei wird als Teil ihrer umschließenden HTML-Seite betrachtet. Alle in SWF-Dateien enthaltenen &quot;Film laden&quot;-URLs gelten auch als Teil der umschließenden HTML-Seite. Daher zählen SWF-Dateien, auf die von einer HTML-Seite verwiesen wird, nicht als &quot;Seite&quot;für den Gesamtwert der Kontoseite.

Wenn eine SWF-Datei als URL-Einstiegspunkt aufgeführt ist, werden diese SWF-Datei und alle in dieser SWF-Datei aufgelisteten &quot;Film laden&quot;-URLs als eine &quot;Seite&quot;für die Gesamtsumme der Kontoseite gezählt.

## Wie kann ich die Indizierung einzelner SWF-Dateien verhindern? {#section_E38AD37989EF410B97AF5125057BFD22}

Um die Indexierung einer SWF-Datei zu verhindern, können Sie dem umschließenden HTML-Dokument entweder ein robots-Meta-Tag ( `<meta name="ROBOTS" content="NOINDEX">`) oder ein `<noindex>`-Tag hinzufügen. Das heißt, das Dokument, das das `<embed>`- oder `<object>`-Tag enthält.

Sie können auch das Meta-Tag &quot;robots&quot;( `<meta name="ROBOTS" content="NOFOLLOW">`) verwenden, um folgende URLs zu verhindern, die in der SWF-Datei enthalten sind. Wenn das einschließende HTML-Dokument die Option &quot;Folgende&quot;deaktiviert hat, werden die in der SWF-Datei als &quot;URL abrufen&quot;aufgelisteten URLs nicht befolgt.

## Wie kann ich verhindern, dass SWF-Dateien auf meiner Website indiziert werden? {#section_DF2606A50E9A44859CFA0D44D7C5F2E4}

Um die SWF-Indexierung zu deaktivieren, deaktivieren Sie den Inhaltstyp **[!UICONTROL Adobe Flash Movies]** ( **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Content Types]**).

Sie können auch [!DNL URL Masks] verwenden, um die Indizierung von SWF-Dateien zu deaktivieren.

Siehe [Hinzufügen von URL-Masken zum Index oder nicht zum Indexieren von Teilen von...](../c-about-settings-menu/c-about-crawling-menu.md#task_E1AFC17C746048B8843013D979E082C1).

Um die SWF-Indexierung zu deaktivieren, geben Sie eine der folgenden URL-Masken ein:

* `exclude *.swf` (wenn Sie keine regulären Ausdrücke verwenden)
* `exclude regexp ^.*\.swf$` (wenn Sie reguläre Ausdrücke verwenden)

Siehe [Reguläre Ausdruck](../c-appendices/r-regular-expressions.md#reference_B5BA7D61D82E4109A01D2A2D964E3A6A).

## Wie kommt es, dass ich die chinesischen, japanischen oder koreanischen SWF-Dateien auf meiner Website nicht durchsuchen kann? {#section_EE1A3A705AE74148BD195A0CE513A5C4}

Site-Suche/Merchandising ruft UTF-8 aus SWF-Dateien ab, die mit Adobe Flash erstellt wurden. Der UTF-8 enthält keine Angabe der Sprache. Wenn Sie den Inhaltstyp **[!UICONTROL Adobe Flash Movies]** ( **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Content Types]**) ausgewählt haben, müssen Sie mithilfe der Metadaten-Injektionen die Sprache angeben, die von der SWF-Datei verwendet wird.

Siehe [Hinzufügen von Feldinjizierungsdefinitionen](../c-about-settings-menu/c-about-metadata-menu.md#task_E86566FA1FF74CF68115C0ADA05172AE).

Ältere SWF-Dateien geben auch keinen Zeichensatz an. Wenn Sie den SWF-Inhaltstyp **[!UICONTROL Adobe Flash Movies]** ( **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Content Types]**) ausgewählt haben, müssen Sie mithilfe der Metadaten-Injektionen den Zeichensatz angeben, der in der SWF-Datei verwendet wird.

## Allgemeine Suche {#reference_E2C675162789452A9B99C6633B12CBEF}

Eine Seite mit häufig gestellten Fragen, auf der erläutert wird, wie Site-Suche/Merchandising Kunden, die Ihre Website besuchen, dabei unterstützt, das zu finden, wonach sie suchen.

Bei der allgemeinen Suche stellen sich folgende Fragen:

* [Muss ich jede Software installieren, um die Site zu benutzen...](#section_02AB2AFF71984F9DAA3AF2B7C0847A22)
* [Was passiert, wenn meine Site das Seitenlimit überschreitet?](#section_ECA5FA01032D4322BABA4E2C7FE498C1)
* [Wie ändere ich die E-Mail-Adresse, an der die Woche...](#section_AE27F63DD13F425B940C8E7D9ED5C614)
* [Wie sicher sind meine Kundeninformationen bei der Suche/dem Merchandising auf der Site?](#section_5484CB954167412BB7F0480CB0C504B8)
* [Was ist mit der Privatsphäre meiner Kundeninformationen?](#section_8FB493F15E51454BA92A0C83E14C0CC7)
* [Kann ich meine eigenen Banneranzeigen auf der Suche zeigen...](#section_611EB8B32C16418386CB7DC7FB6954B8)

Im Folgenden werden häufig gestellte Fragen zu Suchfunktionen aufgeführt:

* [Kann ich die Suchergebnisse für meine Site anpassen?](#section_A64B3A621B794DF78D35ED06D9C43D0B)
* [Kann ich sehen, was Kunden auf meiner...](#section_73709E1B0E82478DA7B4D15B6C845F33)
* [Wie kann ich steuern, welche Inhaltstypen (PDF, Text, Flash, MP3 und Microsoft Office) indiziert und gesucht werden?](#section_0AB8CB4B6BFA4286AA082055FEBFBE1C)
* [Werden dynamisch generierte Webseiten mit ASP-, JSP-, PHP-, CFM- oder Perl-basierten Inhalten unterstützt?](#section_E279F004F1C542A2B9773B832E7B013F)
* [Wie kann ich Synonyme verwenden, um die Suchergebnisse zu verbessern ...](#section_E6E36E12514F4D7BAB01F8D1AB61D57B)
* [Haben Sie die Kontrolle über die Reihenfolge der Suchergebnisse...](#section_C6361048502745779D9749A842C4C370)
* [Kann ich die Sprache der Suchergebnisseite ändern...](#section_6EE41DA8241247D48BBEB061A50599C5)
* [Kann ich mehr als eine Site auf meiner Adobe haben?](#section_AFA8825182094660A71EEC84B8329D6D)
* [Kann ich mehr als eine Domäne suchen?](#section_BFBB0E9861D942F095B56CF0A8F16596)
* [Kann ich meine Site in separate Abschnitte unterteilen, damit...](#section_52153A9DE9F9493B967A70583848B2A4)
* [Wie schließe ich Teile meiner Website von der...](#section_D452EDE153654EF398F4A87780C6D43B)
* [Welche Zeichensätze werden unterstützt?](#section_A62A6F8F15804F968C77F2DEBDE8F8FD)
* [Was ist, wenn ich meine Website ändere oder aktualisiere?](#section_489050E0EBC14D0594DBBAA0CCF4F6BA)
* [Kann meine Site automatisch indiziert werden?](#section_9C7D41636238488691ECDFEE4D4E5103)
* [Ich verwende Kennwörter auf meiner Website. Kann ich weiterhin Site-Suche/Merchandising verwenden?](#section_4618EB5B66704640B5502D1B5CB4B32E)
* [Unterstützen Sie das Crawling und Indizieren von HTTPS oder...](#section_D5BB8B8FBEA4405583E86B4AEC37151B)
* [Erfüllt Site-Suche/Merchandising die Datei &quot;robots.txt&quot;auf meiner Website?](#section_73BBF6FE93C64C109F45CBC2FA394DB2)
* [Bestimmte Teile meiner Website müssen regelmäßig aktualisiert werden...](#section_6D2FB1DE1B8A49729F9CCAE2A2770AB3)
* [Kann ich Skripten oder Programme verwenden, um eine inkrementelle...](#section_0B6BB039557A42AA876D35D748E17DD0)

## Muss ich irgendeine Software installieren, um Site-Suche/Merchandising zu verwenden? {#section_02AB2AFF71984F9DAA3AF2B7C0847A22}

Nein. Dies ist der Hauptvorteil von Site-Suche/Merchandising. Die Engine ist eine professionelle Anwendung, die komplett auf unseren Hochleistungsservern gehostet und gewartet wird. Dadurch wird die Software einfacher zu verwenden als andere Suchlösungen. Sie müssen nur eine kleine Menge HTML-Code zu Ihren Seiten hinzufügen, damit Kunden Ihrer Website Suchvorgänge eingeben können. Die Site-Suche/Merchandising kümmert sich um den Rest.

## Was passiert, wenn meine Site das Seitenlimit überschreitet? {#section_ECA5FA01032D4322BABA4E2C7FE498C1}

Wir führen weiterhin Suchvorgänge durch, damit Ihre Besucher Ihre Website ohne Unterbrechung durchsuchen können. Überprüfen Sie Ihren vollständigen Indexstatus oder das Live-Protokoll, um festzustellen, ob Ihre Website die Seitenbegrenzung überschreitet.

Siehe [Über vollständigen Index](../c-about-index-menu/c-about-full-index.md#concept_C69BD21863FD4856B49326F35DB570D3).

Siehe [Anzeigen des vollständigen Indexprotokolls einer Live- oder Stage...](../c-about-index-menu/c-about-full-index.md#task_02E5E944C56B4EB19CC1FF321F3221B8).

## Wie ändere ich die E-Mail-Adresse, an die die wöchentlichen Berichte gesendet werden? {#section_AE27F63DD13F425B940C8E7D9ED5C614}

Wöchentliche Berichte werden an den Eigentümer jedes aktiven Kontos gesendet. Sie können die E-Mail-Adresse ändern, indem Sie auf **[!UICONTROL Settings]** > **[!UICONTROL My Profile]** > **[!UICONTROL Personal Information]** klicken. Wenn Sie mehr als ein aktives Suchkonto haben, werden alle Newsletter an die neue Adresse gesendet.

Siehe [Konfigurieren Ihrer persönlichen Benutzerinformationen](../c-about-settings-menu/c-about-my-profile-menu.md#task_A11A3BE2527B4204B896E04303B04AA6).

## Wie sicher sind meine Kundeninformationen bei der Suche/dem Merchandising auf der Site? {#section_5484CB954167412BB7F0480CB0C504B8}

Site-Suche/Merchandising ist sicher, schnell, stabil und einfach zu verwenden. Sie sind nicht gezwungen, Cookies zu verwenden (wenn Sie möchten, können Sie dies aber tun), und vertrauliche Informationen wie Passwörter werden niemals auf einen URL-Link gesetzt, der später von Ihrem Browser abgerufen werden kann.

## Was ist mit der Privatsphäre meiner Kundeninformationen? {#section_8FB493F15E51454BA92A0C83E14C0CC7}

Die Adobe setzt sich dafür ein, die Privatsphäre ihrer Kunden und Besucher zu wahren. Siehe Adobe [Datenschutzzentrum](https://www.adobe.com/privacy.html).

## Kann ich meine eigenen Banneranzeigen auf den Suchergebnisseiten anzeigen? {#section_611EB8B32C16418386CB7DC7FB6954B8}

Ja. Sie steuern das Erscheinungsbild und den Inhalt der Suchergebnisse. In der Suchergebnisvorlage für Ihre Website können Sie Links zu Ihrem eigenen Banneraustauschnetzwerk wie LinkExchange oder SmartClicks erstellen. Alle Treffer Ihrer Besucher werden Ihrem Bannerbörsenkonto gutgeschrieben.

## Kann ich die Suchergebnisse für meine Site anpassen? {#section_A64B3A621B794DF78D35ED06D9C43D0B}

Ja. Dies ist eine exklusive Funktion der Site-Suche/des Merchandisings. Mit unserer fortschrittlichen Vorlagentechnologie und einem wenig Wissen über HTML können Sie genau steuern, wie die Suchergebnisse aussehen.

Siehe [Suchvorlagen-Tags](../c-appendices/c-templates.md#reference_F7AA3FF602314E42842BBC740D2CA1A4).

Die Transition zwischen Ihren eigenen Servern und den Site-Such-/Merchandising-Servern ist für Ihre Kunden völlig nahtlos und unsichtbar. Wenn Sie HTML nicht kennen oder keine Zeit haben, eine benutzerdefinierte Vorlage zu erstellen, können Sie aus einer Reihe von attraktiven, einsatzbereiten Vorlagen wählen, die von einem internen Team professioneller Webentwickler von der Adobe erstellt werden.

## Kann ich sehen, nach welchen Kunden auf meiner Site gesucht wird? {#section_73709E1B0E82478DA7B4D15B6C845F33}

Ja. Wir führen Suchstatistiken für Suchvorgänge durch, die von Besuchern auf Ihrer Website in den letzten zwei Monaten durchgeführt wurden. Sie können diese Statistiken jederzeit unter Berichte im Produktmenü überprüfen. Suchberichte geben Ihnen wichtige Informationen darüber, was Besucher auf Ihrer Website genau suchen. Sie können diese Informationen verwenden, um das Design zu verbessern oder die Site-Suchmaschine/Merchandising-Engine so einzustellen, dass sie Ihren Besuchern besser entspricht.

## Wie kann ich steuern, welche Inhaltstypen (PDF, Text, Flash, MP3 und Microsoft Office) indiziert und gesucht werden? {#section_0AB8CB4B6BFA4286AA082055FEBFBE1C}

Sie können auf einfache Weise Konten konfigurieren, um die Indizierung und Suche von Text in PDF-Dokumenten, Dokumenten mit Normaltext, Flash-, MP3- oder Microsoft Office-Dokumenten zu aktivieren oder zu deaktivieren.

Diese Einstellungen werden auf der Seite [!DNL Staged Content Types] gesteuert.

Siehe [Inhaltstypen](../c-about-settings-menu/c-about-crawling-menu.md#concept_6FEA1355C0374500B4C53090C34A8A07).

## Werden dynamisch generierte Webseiten mit ASP-, JSP-, PHP-, CFM- oder Perl-basierten Inhalten unterstützt? {#section_E279F004F1C542A2B9773B832E7B013F}

Statische oder dynamisch generierte HTML-Webseiten werden indiziert, einschließlich Seiten, die aus Datenbanken erstellt wurden, oder jedes andere Back-End-Verfahren. Da der HTML-Code, den ein Browser sieht, indiziert ist, können Sie Site-Suche/Merchandising auf Websites verwenden, solange diese Back-End-Architekturen HTML-Seiten ergeben.

Der Suchroboter durchsucht Ihre Website, indem er mit der ersten Seite an der in [!DNL Account Settings] angegebenen Website-Adresse beginnt und Links von Seite zu Seite verfolgt.

Siehe [Konfigurieren Ihrer Kontoeinstellungen](../c-about-settings-menu/c-about-account-options-menu.md#task_80A38D0C8E4F453395BD67B81E4B45D9).

Wenn der Suchroboter alle Seiten Ihrer Website durchsucht und indiziert, können Sie die Suchmaschine verwenden, um Ihre Site zu suchen. Mit anderen Worten, wenn dynamisch generierte Dokumente mit Links von anderen Seiten in Ihre Website eingebunden werden, kann der Suchroboter trotzdem durchsuchen und den dynamischen Inhalt indizieren.

Nachdem der Inhalt Ihrer Website durchsucht und indexiert wurde, können Kunden Ihrer Website nach Informationen im indizierten Inhalt suchen.

## Wie kann ich Synonyme verwenden, um die Suchergebnisse für meine Site zu verbessern? {#section_E6E36E12514F4D7BAB01F8D1AB61D57B}

Sie können Synonyme verwenden, wenn Sie möchten, dass Besucher Seiten finden, die mit ihrer Abfrage in Verbindung stehen.

Angenommen, Sie haben eine Seite, die eine Liste von Produkten enthält, die auf Ihrer Site zum Verkauf angeboten werden. Nach der Prüfung der Suchberichte, die durch Site-Suche/Merchandising bereitgestellt werden, stellen Sie jedoch fest, dass Kunden bei ihren Suchvorgängen nach dem Wort &quot;Kosten&quot;, &quot;Kosten&quot;, &quot;Gebühr&quot;oder &quot;Gebühr&quot;suchen. Diese Wörter zeigen Ihre Preisseite nicht in den Suchergebnissen an. Mit der Funktion [!DNL Add Synonyms] in [!DNL Dictionaries] können Sie angeben, dass diese Wörter alle Synonyme sind, und Ihr Kunde kann Ihre Liste finden, unabhängig davon, welchen Suchbegriff er verwendet.

Siehe [Info zu Wörterbüchern](../c-about-linguistics-menu/c-about-dictionaries.md#concept_B8028B71EC8144669614C64578EDB034).

## Habe ich die Kontrolle über die Reihenfolge der Suchergebnisse? {#section_C6361048502745779D9749A842C4C370}

Ja. Mithilfe der Benutzeroberfläche für erweiterte Relevanz können Sie steuern, welche Seiten für eine bestimmte Abfrage zurückgegeben werden. Diese Funktion ist nützlich, wenn Sie sicherstellen möchten, dass Kunden bei der Abfrage bestimmter Wörter eine bestimmte Seite sehen.

Siehe [Hinzufügen eines neuen Meta-Tag-Felds](../c-about-settings-menu/c-about-metadata-menu.md#task_6DF188C0FC7F4831A4444CA9AFA615E5).

## Kann ich die Sprache der Suchergebnisseite ändern? {#section_6EE41DA8241247D48BBEB061A50599C5}

Ja. Die Vorlage für die Site-Suche/das Merchandising ist flexibel, wenn es darum geht, eine Ergebnisseite zu erstellen, die die Sprache Ihrer Wahl verwendet und mit dem Erscheinungsbild Ihrer Website übereinstimmt.

Die Vorlage besteht aus einer Kombination aus Text, Standard-HTML-Tags und speziellen Tags, die zur Anzeige der Suchergebnisse definiert werden. Wenn ein Kunde eine Suche durchführt, liest der Suchroboter die Vorlage, gibt den Text mit standardmäßigen HTML-Tags aus und fügt die Ergebnisverknüpfungen auf der Grundlage der speziellen Vorlagen-Tags ein.

Siehe [Suchvorlagen-Tags](../c-appendices/c-templates.md#reference_F7AA3FF602314E42842BBC740D2CA1A4).

Wenn Sie die Sprache der Ergebnisse ändern möchten, können Sie den englischen Text bearbeiten, der in der Vorlage angezeigt wird.

Siehe [Bearbeiten einer Präsentation oder einer Transportvorlage](../c-about-design-menu/c-about-templates.md#task_800E0E2265C34C028C92FEB5A1243EC3).

## Kann ich mehr als eine Site auf meiner Adobe Kundenanmeldung haben? {#section_AFA8825182094660A71EEC84B8329D6D}

Ja. Mit einer einzigen Adobe Kundenanmeldung können Sie eine andere Suchmaschine für viele verschiedene Websites verwalten. Wählen Sie Konten unter &quot;Konten&quot;aus und verwalten Sie sie.

Siehe [Auswahl eines anderen Kontos, das verwendet werden soll.](../c-about-accounts-menu.md#task_03C0FE918E2D44529CDC3B8DB75D1B26)

## Kann ich mehr als eine Domäne suchen? {#section_BFBB0E9861D942F095B56CF0A8F16596}

Ja. Sie können den Zugriff auf mehrere Domänen mithilfe von [!DNL URL Entrypoints] konfigurieren. Geben Sie URL-Einstiegspunkte für zusätzliche Domänen an, deren Inhaber Sie sind. Denken Sie daran, dass Sie über die Berechtigung zum Indexieren von Domänen verfügen müssen, deren Inhaber Sie nicht sind.

Siehe [Informationen zu URL-Einstiegspunkten](../c-about-settings-menu/c-about-crawling-menu.md#concept_5D857E3B5C124E85BC0B5AE77A509573).

## Kann ich meine Site in separate Abschnitte unterteilen, damit Kunden diese Bereiche einzeln oder die gesamte Site durchsuchen können? {#section_52153A9DE9F9493B967A70583848B2A4}

Ja. Eine Funktion &quot;Sammlungen&quot;ist enthalten, mit der Kunden bestimmte Bereiche Ihrer Website suchen können, um schnell das zu finden, wonach sie suchen.

Siehe [Sammlungen](../c-about-settings-menu/c-about-searching-menu.md#concept_62E42ACE53D54EEE9273433B86259127).

Kunden können beispielsweise eine Sammlung von URLs im Zusammenhang mit Produktverkaufsinformationen oder eine Sammlung von URLs im Zusammenhang mit Supportdiensten suchen. Sie können Sammlungen so einrichten, dass Ihren Kunden eine Dropdown-Liste mit Sammlungen oder eine Gruppe von Kontrollkästchen angezeigt wird.

## Wie kann ich Teile meiner Website von der Suche ausschließen? {#section_D452EDE153654EF398F4A87780C6D43B}

Ja. Geben Sie URL-Masken an, um festzulegen, welche Webseiten in die Indexierung einbezogen oder ausgeschlossen werden sollen. URL-Masken bestimmen, ob Webseiten in den Suchergebnissen angezeigt werden.

Siehe [URL-Masken](../c-about-settings-menu/c-about-crawling-menu.md#concept_8039DFC53FF3410AA494D602F71BA164).

Siehe [Skript &quot;URL-Masken](../c-about-settings-menu/c-about-filtering-menu.md#concept_384F32EA18F84853A7BA99A04009330B)&quot;.

Um zu verhindern, dass Teile einzelner Webseiten durchsucht werden, können Sie Teile einer Seite von der Indexierung ausschließen. Richten Sie den Text mit den Tags `<noindex>` und `</noindex>` ein. Diese Methode ist nützlich, wenn Sie Navigationstext von Suchvorgängen ausschließen möchten.

## Welche Zeichensätze werden unterstützt? {#section_A62A6F8F15804F968C77F2DEBDE8F8FD}

Webseiten geben den Zeichensatz normalerweise mit einem Meta-Tag an, das dem Folgenden ähnelt:

`<META HTTP-EQUIV="Content-Type" CONTENT="text/html; charset=iso-8859-1">`

Die Site-Suchmaschine/Merchandising indiziert Webseiten ordnungsgemäß mit allen gängigen Zeichensätzen, die heute im Internet verwendet werden. Einige der unterstützten Zeichensätze umfassen Folgendes:

<table> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Arabisch (ISO-8859-6) </p> </td> 
   <td colname="col2"> <p>Chinesisch (traditionell) Big5) </p> </td> 
   <td colname="col3"> <p>Japanisch (Shift_JIS) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Arabisch (Windows-1256) </p> </td> 
   <td colname="col2"> <p>Chinesisch (traditionell) EUC-TW) </p> </td> 
   <td colname="col3"> <p>Russisch (KOI8-R) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ostsee (ISO-8859-4) </p> </td> 
   <td colname="col2"> <p>Kyrillisch (ISO-8859-5) </p> </td> 
   <td colname="col3"> <p>Südeuropäisch (ISO-8859-3) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Baltic (Windows-1257) </p> </td> 
   <td colname="col2"> <p>Kyrillisch (Windows-1251) </p> </td> 
   <td colname="col3"> <p>Türkisch (ISO-8859-9) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Mitteleuropäisch (ISO-8859-2) </p> </td> 
   <td colname="col2"> <p>Griechisch (ISO-8859-7) </p> </td> 
   <td colname="col3"> <p>Türkisch (Windows-1254) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Mitteleuropäisch (Windows-1250) </p> </td> 
   <td colname="col2"> <p>Griechisch (Windows-1253) </p> </td> 
   <td colname="col3"> <p>Unicode (UTF-8) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Chinesisch (ISO-2022-CN) </p> </td> 
   <td colname="col2"> <p>Hebräisch (ISO-8859-8) </p> </td> 
   <td colname="col3"> <p>US-ASCII (us-ascii) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Chinesisch (ISO-2022-CN-EXT) </p> </td> 
   <td colname="col2"> <p>Hebräisch (Windows-1255) </p> </td> 
   <td colname="col3"> <p>Westeuropäisch (ISO-8859-1) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Chinesisch (vereinfacht) EUC-CN) </p> </td> 
   <td colname="col2"> <p>Japanisch (EUC-JP) </p> </td> 
   <td colname="col3"> <p>Westeuropäisch (ISO-8859-15) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Chinesisch (vereinfacht) GB2312) </p> </td> 
   <td colname="col2"> <p>Japanisch (ISO-2022-JP) </p> </td> 
   <td colname="col3"> <p>Westeuropäisch (Windows-1252) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Chinesisch (vereinfacht) GBK) </p> </td> 
   <td colname="col2"> <p>Japanisch (ISO-2022-JP-1) </p> </td> 
   <td colname="col3"> <p>Westeuropäisch (x-mac-roman) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Chinesisch (vereinfacht) HZ-GB-2312) </p> </td> 
   <td colname="col2"> <p>Japanisch (ISO-2022-JP-2) </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
 </tbody> 
</table>

Wenden Sie sich an den technischen Support, wenn Sie Fragen zu den oben nicht aufgelisteten Zeichensätzen haben.

## Was ist, wenn ich meine Website ändere oder aktualisiere? {#section_489050E0EBC14D0594DBBAA0CCF4F6BA}

Nachdem Sie den Inhalt Ihrer Website geändert haben, können Sie entweder einen vollständigen oder einen inkrementellen Index durchführen. Die Site-Suche/das Merchandising lädt alle geänderten Website-Inhalte herunter und indiziert diese. Nach Abschluss der Indexierung können Ihre Kunden den neuen Inhalt durchsuchen. Sie können auch eine automatische Indexierung Ihrer Site zu einem bestimmten Zeitpunkt und an einem bestimmten Tag planen.

Siehe [Ausführen eines vollständigen Indexes einer Live- oder Staged-Website...](../c-about-index-menu/c-about-full-index.md#task_F7FE04D8A1654A7787FCCA31B45EB42D).

Siehe [Ausführen eines inkrementellen Indexes einer Live- oder Staged-Website...](../c-about-index-menu/c-about-incremental-index.md#task_9BFB6157F3884B2FAECB7E0E9CA318CB).

Siehe [Einstellen des vollständigen Indexplans für eine Live-Website](../c-about-index-menu/c-about-full-index.md#task_6760F3256D004A228B38968DF15421F0).

Siehe [Einstellen des inkrementellen Indexplans für eine Live-Website](../c-about-index-menu/c-about-incremental-index.md#task_2A46BA189ECC4317A9D5C6E99A336F33).

## Kann meine Site automatisch indiziert werden? {#section_9C7D41636238488691ECDFEE4D4E5103}

Ja. Sie können jeden Tag einen automatischen Index Ihrer Site planen.

Neben der täglichen automatischen Indizierung können Sie festlegen, dass häufig geänderte Teile ihrer Site inkrementell indiziert werden. An Tagen, für die ein automatischer Index geplant ist, können Sie steuern, wann der Index stattfindet. Außerdem können Sie jederzeit manuell einen Site-Index starten, wann immer Sie möchten.

Siehe [Einstellen des vollständigen Indexplans für eine Live-Website](../c-about-index-menu/c-about-full-index.md#task_6760F3256D004A228B38968DF15421F0).

Siehe [Einstellen des inkrementellen Indexplans für eine Live-Website](../c-about-index-menu/c-about-incremental-index.md#task_2A46BA189ECC4317A9D5C6E99A336F33).

## Ich verwende Kennwörter auf meiner Website. Kann ich weiterhin Site-Suche/Merchandising verwenden? {#section_4618EB5B66704640B5502D1B5CB4B32E}

Wenn Sie die HTTP Basic-Authentifizierung zum Schutz bestimmter Bereiche Ihrer Website mit einem Kennwort verwenden, können Sie Bereiche und Kennwörter angeben, mit denen die Site-Suche/Merchandising Ihre Site indizieren kann.

Siehe [Passwörter für den Zugriff auf Bereiche Ihrer Website, die erforderlich sind, hinzufügen...](../c-about-settings-menu/c-about-crawling-menu.md#task_DED19D476FF04B48BB6456D5ECB8628A).

## Unterstützen Sie das Crawling und Indizieren von HTTPS oder sicheren Serverinhalten? {#section_D5BB8B8FBEA4405583E86B4AEC37151B}

Ja. Sie können Inhalte auf sicheren Servern (https) suchen und indizieren.

## Erfüllt Site-Suche/Merchandising die Datei &quot;robots.txt&quot;auf meiner Website? {#section_73BBF6FE93C64C109F45CBC2FA394DB2}

Ja. Das Robots-Ausschlussprotokoll ist konform. Der Suchroboter prüft die Datei &quot;robots.txt&quot;, wenn sie auf Ihrer Website vorhanden ist. Wenn Ihre Datei &quot;robots.txt&quot;alle Roboter vom Crawling Ihrer Site ausschließt, wird auch der Site-Such-/Merchandising-Roboter ausgeschlossen. Damit nur der Site-Such-/Merchandising-Roboter Ihre Site durchsuchen kann, stellen Sie den Inhalt Ihrer Datei &quot;robots.txt&quot;auf Folgendes ein:

```
User-agent: Atomz/1.0 
Disallow:
```

```
User-agent: * 
Disallow: /
```

Weitere Informationen zu Webrobotern und dem Roboter-Ausschlussprotokoll finden Sie unter:

[https://www.robotstxt.org/orig.html](https://www.robotstxt.org/orig.html)

## Bestimmte Teile meiner Website müssen regelmäßig aktualisiert werden, damit meine Kunden die genauesten Suchergebnisse erhalten. Hilft die inkrementelle Indexierung bei diesem Problem? {#section_6D2FB1DE1B8A49729F9CCAE2A2770AB3}

Ja. Dieses Szenario wurde mit der inkrementellen Indexierungsfunktion erstellt, um die Site-Suche/das Merchandising zu erleichtern. Der Hauptvorteil der inkrementellen Indizierung besteht darin, dass Firmen häufig dynamisch verändernde Bereiche ihrer Website indizieren können. Diese Funktion stellt sicher, dass Sie Suchergebnisse mit einer Genauigkeit von &quot;bis zur Minute&quot;anzeigen.

Siehe [Ausführen eines inkrementellen Indexes einer Live- oder Staged-Website...](../c-about-index-menu/c-about-incremental-index.md#task_9BFB6157F3884B2FAECB7E0E9CA318CB).

Siehe [Einstellen des inkrementellen Indexplans für eine Live-Website](../c-about-index-menu/c-about-incremental-index.md#task_2A46BA189ECC4317A9D5C6E99A336F33).

## Werden dynamisch generierte Webseiten von einer Back-End-Datenbank wie Produktkatalogen oder Lagerbestandsverwaltungssystemen unterstützt? {#section_26896C556483457E879785E751583B16}

Statische oder dynamisch erstellte HTML-Webseiten, einschließlich Seiten, die aus Datenbanken erstellt wurden, oder andere Back-End-Prozesse werden indiziert. Da der von einem Browser angezeigte HTML-Code indiziert ist, können Sie die Site-Suche/das Merchandising auf Websites verwenden, solange die Back-End-Datenbankinformationen HTML-Seiten ergeben.

Der Suchroboter durchsucht Ihre Website, indem er mit der ersten Seite an der in [!DNL Account Settings] angegebenen Website-Adresse beginnt und Links von Seite zu Seite verfolgt.

Siehe [Konfigurieren Ihrer Kontoeinstellungen](../c-about-settings-menu/c-about-account-options-menu.md#task_80A38D0C8E4F453395BD67B81E4B45D9).

Wenn der Suchroboter alle Seiten Ihrer Website durchsucht und indiziert, können Sie die Suchmaschine verwenden, um Ihre Site zu suchen. Mit anderen Worten, wenn dynamisch generierte Dokumente mit Links von anderen Seiten in Ihre Website eingebunden werden, kann der Suchroboter weiterhin den dynamischen Datenbankinhalt durchsuchen und indizieren.

Nachdem der Inhalt Ihrer Website durchsucht und indexiert wurde, können Kunden Ihrer Website nach Informationen im indizierten Inhalt suchen.

Sie können auf einfache Weise die Suche nach vollständigem Inhalt oder eine engere themenbasierte Suche aktivieren, die auf Informationen im Titel, die Metadaten-Beschreibung, die Meta-Keywords-Dokument-Tags oder alle drei beschränkt ist. Mithilfe von Metadatendefinitionen können Sie auch benutzerdefinierte Anzeigefelder, z. B. ein Produktbild, in den Suchergebnissen erstellen.

Siehe [Hinzufügen eines neuen Meta-Tag-Felds](../c-about-settings-menu/c-about-metadata-menu.md#task_6DF188C0FC7F4831A4444CA9AFA615E5).

## Kann ich Skripten oder Programme verwenden, um einen inkrementellen Index meiner Site zu initiieren? {#section_0B6BB039557A42AA876D35D748E17DD0}

Ja. Sie können Skripten oder Programm verwenden, um einen inkrementellen Index Ihrer Website zu initiieren und die Server zu pten, um die Site zu indizieren, sobald Inhalte geändert oder aktualisiert werden.

Siehe [Über skriptgesteuerten Index](../c-about-index-menu/c-about-scripted-index.md#concept_34F58D551BC04BFB8ADC294B9DA9199D).

## Funktionsimplementierungen {#reference_2D0C4A80B8D64051BA9694D562DCE663}

Eine Seite mit häufig gestellten Fragen, die verschiedene Funktionsimplementierungen in [!DNL Search&Promote] erläutert.

Die folgenden Fragen stellen sich häufig nach Funktionsimplementierungen in [!DNL Search&Promote] auf einer Website:

* [Warum laufen meine Geschäftsregeln nicht?](#section_7FEB60383D8A4B11A60DFF9067274699)
* [Warum habe ich Probleme bei der Planung der Indexierung, Fehler beim Starten der Indexierung und Probleme beim Starten der Indexierung?](#section_E05758193DF5436784B0145839989F75)
* [Meine Indexgrößenbeschränkung überschreitet meine zulässige Grenze. Warum geschieht dies und wie repariere ich es?](#section_12E7DA979C4C4B1D8A3A6415FC3DDA70)

## Warum laufen meine Geschäftsregeln nicht? {#section_7FEB60383D8A4B11A60DFF9067274699}

Konfigurieren Sie Geschäftsregeln, wenn Banner angezeigt werden, oder entscheiden Sie, welche Ergebnisse in welcher Reihenfolge angezeigt werden. Sie können auch die Position eines Elements in Ihrer Facette und die Vorlage für eine bestimmte Suche konfigurieren.
Ordnen Sie Geschäftsregeln neu an, um die Reihenfolge zu ändern, in der sie auf Präsentationsvorlagen ausgeführt werden. Geschäftsregeln werden in der Reihenfolge ausgeführt, in der sie festgelegt wurden. d. h. je höher die Ordnungsnummer einer Regel ist, desto später wird sie im Prozess ausgeführt, wodurch frühere Regeln übertroffen werden. Sie können Regeln neu anordnen, indem Sie auf der Seite &quot;Geschäftsregeln&quot;in die Spalte &quot;Reihenfolge&quot;der Tabelle eine neue Zahl eingeben.

Siehe [Geschäftsregeln](../c-about-rules-menu/c-about-business-rules.md#concept_2A93D76216754D3D8412CDEA00BD26BD).

## Warum habe ich Probleme bei der Planung der Indexierung, Fehler beim Starten der Indexierung und Probleme beim Starten der Indexierung? {#section_E05758193DF5436784B0145839989F75}

Wenn Sie einen Index generieren, unabhängig davon, ob er vollständig oder inkrementell ist, werden die Informationen zum Index-Crawl-Status in Echtzeit angezeigt. Sie können beispielsweise die Ansicht der Zeitdauer des Beginns, der Zeitdauer und alle während des Indexvorgangs aufgetretenen Fehler durchführen. Informationen zum Status des letzten Index werden ebenfalls angezeigt. Verwenden Sie diese Informationen, um etwaige Indexierungsfehler zu beheben.

Informationen zum Planen eines Indexes finden Sie unter [Einstellen des vollständigen Indexplans für eine Live-Website](../c-about-index-menu/c-about-full-index.md#task_6760F3256D004A228B38968DF15421F0) und [Einstellen des inkrementellen Indexplans für eine Live-Website](../c-about-index-menu/c-about-incremental-index.md#task_2A46BA189ECC4317A9D5C6E99A336F33).

Informationen zum Starten eines gestaffelten Indexes finden Sie unter [Ausführen eines vollständigen Indexes einer Live- oder Staged-Website...](../c-about-index-menu/c-about-full-index.md#task_F7FE04D8A1654A7787FCCA31B45EB42D) oder [Ausführen eines inkrementellen Indexes einer Live- oder Staged-Website...](../c-about-index-menu/c-about-incremental-index.md#task_9BFB6157F3884B2FAECB7E0E9CA318CB).

## Meine Indexgrößenbeschränkung überschreitet meine zulässige Grenze. Warum passiert das und wie repariere ich es? {#section_12E7DA979C4C4B1D8A3A6415FC3DDA70}

Eine Website kann tendenziell wachsen und im Laufe der Zeit Search&amp;Promote &quot;entdeckt&quot; mehr Dokumente und Webseiten hinzugefügt wurden. Eventuell überschreitet Ihr Konto möglicherweise Ihre Indexgrößenbeschränkung. In solchen Fällen können Sie **[!UICONTROL URL Mask]** verwenden. Diese Funktion blendet Dokumente und Webseiten bei Index-Crawling aus, die Sie nicht indizieren möchten oder nicht benötigen, und reduziert so Ihre Indexgröße. Eine andere Möglichkeit könnte darin bestehen, sich an den technischen Support zu wenden, um die Indexierungsgrößenbegrenzung in Ihrem Konto zu erhöhen.

Siehe [URL-Masken](../c-about-settings-menu/c-about-crawling-menu.md#concept_8039DFC53FF3410AA494D602F71BA164).

Wenn Sie sich nicht sicher sind, was Sie tun sollen, wenden Sie sich an den technischen Support. Es kann noch viele andere Variablen geben, die sich auf Ihre Indexgröße auswirken und bei einer Anpassung auch die Rechnungsstellung Ihres Kontos beeinflussen können.

## International {#reference_F017C2968BFB446499EF1D3CE2CAC0FE}

Eine Seite mit häufig gestellten Fragen, die die Unterstützung der Indizierung und Suche in mehr als 19 Sprachen beschreibt, einschließlich Multibyte-asiatischer Sprachen wie Chinesisch (vereinfacht und traditionell), Japanisch und Koreanisch.

Im Folgenden werden häufig gestellte Fragen zu Sprachen und Zeichensätzen behandelt:

* [Was steuert die Zeichensatzkodierung der Abfrage...](#section_DF2E8570AFC2480FA199FD26C941A22F)
* [Werden nur Seiten durchsucht, deren Kodierung mit der Kodierung von...](#section_9E544F3DB7DE41618DC1BC8224B32C5A)
* [Welche Kodierung wird für die Suchergebnisseite verwendet?](#section_DA68670F35D54EAABF7DBB010F4409BF)
* [Kann ich Site-Suche/Merchandising auf Unicode-, UTF-8-, kodierten Seiten verwenden?](#section_130997CB08934A13A5261D85CF88040C)
* [Wie kommt es, dass ich die chinesischen, japanischen oder koreanischen PDF-Dateien auf meiner Website nicht durchsuchen kann?](#section_539AFF482F814D28B5929F683D2F2175)
* [Wie kommt es, dass ich die chinesischen, japanischen oder koreanischen SWF-Dateien auf meiner Website nicht durchsuchen kann?](#section_9C0849528AFF4C10AA97A2C912992638)
* [Wie kommt es, dass ich die chinesischen, japanischen oder koreanischen Microsoft Office-Dateien auf meiner Website nicht durchsuchen kann?](#section_6764BA6863AF492EBA9BE5CCC12CDD1F)
* [Wie kommt es, dass ich die chinesischen, japanischen oder koreanischen MP3-Dateien auf meiner Website nicht durchsuchen kann?](#section_DB6D60CF46F94125BF4E54AF3036DBFC)
* [Muss ich etwas Besonderes tun, um das...](#section_A8BA6DDD3A6048319D3530BCFD6DA1A5)
* [Wie kommt es, dass chinesische, japanische oder koreanische Schriftarten in den Suchergebnissen unter Netscape 4.7 und früher erscheinen?](#section_DF42567063304F918D406AC76529DFB7)

## Was steuert die Zeichensatzkodierung der Abfrage? {#section_DF2E8570AFC2480FA199FD26C941A22F}

Der Abschnitt &quot;Webformulare&quot;Ihres Suchkontos enthält Mustersuchformulare, die Sie verwenden, um Ihrer Website Suchfunktionen hinzuzufügen. Wenn Sie diesen Suchformularcode betrachten, können Sie eine Zeile wie die folgende finden:

`<input type=hidden name="sp_f" value="iso-8859-1">`

Diese Codezeile teilt der Suchmaschine mit, dass die eingehende Abfrage in iso-8859-1 kodiert ist, einer gängigen Kodierung für westeuropäische Sprachen. Sie können diese Einstellung ändern, indem Sie im Produktmenü auf **[!UICONTROL Settings]** > **[!UICONTROL My Profile]** > **[!UICONTROL Personal Information]** klicken. Wählen Sie auf der Seite [!DNL Personal Information] in der Dropdown-Liste **[!UICONTROL Character Encoding]** eine neue Kodierung aus.

Siehe [Konfigurieren Ihrer persönlichen Benutzerinformationen](../c-about-settings-menu/c-about-my-profile-menu.md#task_A11A3BE2527B4204B896E04303B04AA6).

Sie können den Kodierungswert auf Ihren Webseiten auch manuell ändern, indem Sie die Zeile `sp_f` des Suchformulars bearbeiten. Denken Sie daran, dass der Wert des Suchformulars mit der Zeichensatzkodierung der Seite, auf der es angezeigt wird, übereinstimmen muss.`sp_f`

## Werden nur Seiten durchsucht, deren Kodierung mit der Kodierung der Abfrage übereinstimmt? {#section_9E544F3DB7DE41618DC1BC8224B32C5A}

Standardmäßig ist &quot;Nein&quot; eingestellt. Solange Ihre Webseiten die Zeichensatzkodierung richtig identifizieren, werden die erforderlichen Konvertierungen zwischen der Kodierung der Abfrage und der der Seiten vorgenommen, auch wenn die Seiten mehrere Kodierungen verwenden.

## Welche Kodierung wird für die Suchergebnisseite verwendet? {#section_DA68670F35D54EAABF7DBB010F4409BF}

Die Zeichensatzkodierung Ihres Kontos bestimmt die Standardkodierung für Ihre Ergebnisvorlage.

Siehe [Konfigurieren Ihrer persönlichen Benutzerinformationen](../c-about-settings-menu/c-about-my-profile-menu.md#task_A11A3BE2527B4204B896E04303B04AA6).

Weitere Informationen zum Festlegen eines Zeichensatzes in einer HTML-Vorlage erhalten Sie.

Siehe [Suchvorlagen-Tags](../c-appendices/c-templates.md#reference_F7AA3FF602314E42842BBC740D2CA1A4).

## Kann ich Site-Suche/Merchandising auf Unicode-, UTF-8-, kodierten Seiten verwenden? {#section_130997CB08934A13A5261D85CF88040C}

Ja. Unicode-Zeichensätze wie UTF-8 bieten jedoch nicht genügend Informationen, um die Sprache zu bestimmen, in der die Seiten geschrieben werden. Um diese Seiten korrekt zu durchsuchen, müssen Sie die Sprache angeben. Zur Bestimmung der Sprache des Dokuments werden die Informationen in der folgenden Reihenfolge verarbeitet:

* Content-Language HTTP-Header, der vom Server für das Dokument bereitgestellt wird.
* META-Elemente (z. B. `META HTTP-EQUIV="Content-Language" Content="ja_JP"`) im Bereich `<HEAD>` des Dokuments.

* LANG-Attribut des Tags `<HTML>` (z. B. `<HTML LANG="ja_JP">`).

Wenn Ihr Server nicht für die Bereitstellung des Content-Language-HTTP-Headers konfiguriert ist und Ihre Dokumente weder das Sprach-META-Element noch das Sprachattribut für das `<HTML>`-Tag enthalten, können Sie Metadaten-Injektionen verwenden, um die entsprechende Sprache anzugeben.

Siehe [Hinzufügen von Feldinjizierungsdefinitionen](../c-about-settings-menu/c-about-metadata-menu.md#task_E86566FA1FF74CF68115C0ADA05172AE).

## Wie kommt es, dass ich die chinesischen, japanischen oder koreanischen PDF-Dateien auf meiner Website nicht durchsuchen kann? {#section_539AFF482F814D28B5929F683D2F2175}

Site-Suche/Merchandising ruft UTF-8 aus Adobe PDF-Dateien ohne Angabe von Sprache ab. Wenn Sie **[!UICONTROL PDF Documents]** ( **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Content Types]**) ausgewählt haben, müssen Sie mithilfe der Metadaten-Injektionen die Sprache angeben, die in der PDF-Datei verwendet wird.

Siehe [Hinzufügen von Feldinjizierungsdefinitionen](../c-about-settings-menu/c-about-metadata-menu.md#task_E86566FA1FF74CF68115C0ADA05172AE).

## Wie kommt es, dass ich die chinesischen, japanischen oder koreanischen SWF-Dateien auf meiner Website nicht durchsuchen kann? {#section_9C0849528AFF4C10AA97A2C912992638}

Site-Suche/Merchandising ruft UTF-8 aus Adobe-Flash-Filmdateien ab, die mit Adobe Flash ohne Angabe von Sprache erstellt wurden. Wenn Sie den Inhaltstyp **[!UICONTROL Adobe Flash Movies]** ( **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Content Types]**) ausgewählt haben, müssen Sie mithilfe der Metadaten-Injektionen die Sprache angeben, die in der SWF-Datei verwendet wird.

Bei SWF-Dateien der Flash-Version 4 oder älter wird der Zeichensatz der Zeichen in der Datei nicht angegeben. Wenn Sie den Inhaltstyp **[!UICONTROL Adobe Flash Movies]** ( **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Content Types]**) ausgewählt haben, müssen Sie mithilfe von Metadaten-Injektionen den Zeichensatz angeben, der in der SWF-Datei verwendet wird.

Siehe [Hinzufügen von Feldinjizierungsdefinitionen](../c-about-settings-menu/c-about-metadata-menu.md#task_E86566FA1FF74CF68115C0ADA05172AE).

## Wie kommt es, dass ich die chinesischen, japanischen oder koreanischen Microsoft Office-Dateien auf meiner Website nicht durchsuchen kann? {#section_6764BA6863AF492EBA9BE5CCC12CDD1F}

Bei der Site-Suche/beim Merchandising wird UTF-8 aus Microsoft Office-Dateien (Microsoft Word, Microsoft Excel und Microsoft PowerPoint) ohne Angabe der Sprache abgerufen. Wenn Sie den Inhaltstyp **[!UICONTROL Microsoft Office Files]** ( **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Content Types]**) ausgewählt haben, müssen Sie mithilfe der Metadaten-Injektionen die Sprache angeben, die in den Microsoft Office-Dateien verwendet wird.

Siehe [Hinzufügen von Feldinjizierungsdefinitionen](../c-about-settings-menu/c-about-metadata-menu.md#task_E86566FA1FF74CF68115C0ADA05172AE).

## Wie kommt es, dass ich die chinesischen, japanischen oder koreanischen MP3-Dateien auf meiner Website nicht durchsuchen kann? {#section_DB6D60CF46F94125BF4E54AF3036DBFC}

Wenn Sie den Inhaltstyp **[!UICONTROL Text in MP3 Music Files]** ( **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Content Types]**) auswählen, müssen Sie Metadaten-Injektionen verwenden, um den Zeichensatz anzugeben, der zum Kodieren der MP3-Dateien verwendet wird.

Siehe [Hinzufügen von Feldinjizierungsdefinitionen](../c-about-settings-menu/c-about-metadata-menu.md#task_E86566FA1FF74CF68115C0ADA05172AE).

## Muss ich etwas Besonderes tun, um die .txt-Dateien auf meiner Website korrekt zu indizieren? {#section_A8BA6DDD3A6048319D3530BCFD6DA1A5}

Wenn Sie den Inhaltstyp **[!UICONTROL Text Documents]** ( **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Content Types]**) ausgewählt haben, müssen Sie mithilfe von Metadaten-Injektionen den Zeichensatz angeben, der zum Kodieren der .txt-Dateien verwendet wird.

Siehe [Hinzufügen von Feldinjizierungsdefinitionen](../c-about-settings-menu/c-about-metadata-menu.md#task_E86566FA1FF74CF68115C0ADA05172AE).

## Wie kommt es, dass chinesische, japanische oder koreanische Schriftarten in den Suchergebnissen unter Netscape 4.7 und früher erscheinen? {#section_DF42567063304F918D406AC76529DFB7}

Wenn Ihr Konto die Standardvorlage, eine der gebrauchsfertigen Vorlagen oder eine Vorlage verwendet, die auf einer dieser Vorlagen basiert, kann es Schriftart-Tags enthalten, die Arial oder Helvetica als Schriftart angeben. Zum Beispiel `<font face="arial, helvetica" size="+1">`. In Netscape 4.7 und früher werden keine chinesischen, japanischen oder koreanischen Zeichen angezeigt, wenn die Schriftart Arial oder Helvetica verwendet wird. Entfernen Sie das Attribut `face` oder ersetzen Sie die Schriftart durch eine Schrift, die für Chinesisch, Japanisch oder Koreanisch geeigneter ist.

## Niedrige Seitenzahl {#reference_4344E3E3CB2948939860F8C078BD7773}

Eine Seite mit häufig gestellten Fragen, die häufig auftretende Probleme im Zusammenhang mit einer niedrigen Indexierung der Seite behandelt.

Im Folgenden werden häufig gestellte Fragen zu Seitenzahlen mit niedriger Indexierung aufgeführt:

* [Haben Sie Ihr Indexprotokoll geprüft?](#section_D6626536DC3D40DDA4A1224F1CB276BF)
* [Haben Sie Tippfehler in Ihrer URL?](#section_BD2CEABC5D0F4A0DA38F3AD72ABBA676)
* [Hat die Einstiegspunkt-Webseite Links zu anderen Seiten...](#section_1C2D6ED54E7249268B555D9DC33352B3)
* [Sind Links zu anderen Seiten auf Ihrer Website eingebettet in...](#section_EE34A67D60A844EBB0921C03544FF63E)
* [Sind die HTML-Tags auf Ihrer Webseite in einer ...](#section_F31A2F5D2C284AC084158A5BD763DC5D)
* [Haben Sie unsachgemäß formatierte HTML-Kommentar-Tags in Ihrem...](#section_D1C39D79341845CB9C38579AABDF3A24)
* [Enthält Ihre Webseite Links zu anderen Seiten...](#section_F8082759184049AAA8FA6342C1F84389)
* [Verwenden Sie einen virtuellen Domänendienst für Ihre URL...](#section_2861F09EA21A45E6B7E15F032739CDF3)
* [Verwendet Ihre Webseite ein Meta-Aktualisierungs-Tag?](#section_5A2F544C237C49B8B1A7FE0C45371C0D)
* [Verwendet Ihre Webseite ein Meta-Roboter-Tag?](#section_36275A33DDFE4620BABA948F8A63DBD2)
* [Verwendet Ihre Website eine Ausschlussdatei für Roboter?](#section_BF7B663347814F58AD736066C86B7D25)

## Haben Sie Ihr Indexprotokoll geprüft? {#section_D6626536DC3D40DDA4A1224F1CB276BF}

Das Index-Protokoll enthält detaillierte Informationen, die der Site-Such-/Merchandising-Roboter beim Indizieren Ihrer Website erfasst. Das Protokoll enthält eine Liste von durchgekrackten Links und aufgetretenen Fehlern. Die Überprüfung des Indexprotokolls ist der beste Ort, um zu ermitteln, warum nicht alle Seiten auf Ihrer Website indiziert sind.

Siehe [Anzeigen des vollständigen Indexprotokolls einer Live- oder Stage...](../c-about-index-menu/c-about-full-index.md#task_02E5E944C56B4EB19CC1FF321F3221B8).

Siehe [Anzeigen des inkrementellen Indexprotokolls einer Live- oder Stage...](../c-about-index-menu/c-about-incremental-index.md#task_E668E1F1240C476DAA1CA783DC728232).

## Haben Sie Tippfehler in Ihrer URL? {#section_BD2CEABC5D0F4A0DA38F3AD72ABBA676}

Wenn Sie längere URLs in HTML-Formulare eingeben, kann es zu einem oder mehreren Schreibfehlern kommen. Beachten Sie, dass URLs keine Leerzeichen enthalten dürfen. Beachten Sie außerdem, dass bei einigen Webservern die Groß- und Kleinschreibung bei URLs beachtet wird.

Klicken Sie im Produktmenü auf **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL URL Entrypoints]**. Überprüfen Sie auf der Seite [!DNL Staged URL Entrypoints] Folgendes:

* Sie haben keine typografischen Fehler in Ihren URLs.
* Die Zeichen in den URLs verwenden alle das richtige Gehäuse.
* Die URLs enthalten keine Leerzeichen.

Um Ihre URL-Einstiegspunkte zu testen, kopieren Sie eine URL und fügen Sie sie in einen Webbrowser ein, um zu sehen, ob Ihre Website angezeigt wird. Wenn sie nicht angezeigt wird, überprüfen Sie erneut, um sicherzustellen, dass Sie keine Fehler im URL-Pfad gemacht haben.

Siehe [Informationen zu URL-Einstiegspunkten](../c-about-settings-menu/c-about-crawling-menu.md#concept_5D857E3B5C124E85BC0B5AE77A509573).

## Verfügt die Einstiegspunkt-Webseite über Links zu anderen Seiten Ihrer Website? {#section_1C2D6ED54E7249268B555D9DC33352B3}

Der Site-Such-/Merchandising-Roboter durchsucht Ihre Website genau wie Ihr Kunde. durch Befolgen von Links von Seite zu Seite. Links müssen auf der Einstiegsseite vorhanden sein, bevor der Suchroboter andere Seiten auf Ihrer Site finden und indizieren kann.

Siehe [Hinzufügen mehrerer URL-Einstiegspunkte, die indiziert werden sollen.](../c-about-settings-menu/c-about-crawling-menu.md#task_2338A47387D74CFDAC4D4EF4A367ED45)

## Sind Links zu anderen Seiten Ihrer Website in JavaScript eingebettet? {#section_EE34A67D60A844EBB0921C03544FF63E}

Sie können ausgefeilte Navigationstechniken auf Ihrer Website verwenden, z. B. Rollover-Aktionen und Menüs, bei denen JavaScript zur Verknüpfung mit anderen Seiten verwendet wird. Der Site-Such-/Merchandising-Roboter kann jedoch keine in JavaScript eingebetteten Links verfolgen.

Eine Lösung, die Sie zur Behebung dieses Problems verwenden können, besteht darin, versteckte Links zu anderen Seiten im HTML-Code zu platzieren, die das JavaScript enthalten. Obwohl Kunden auf Ihrer Website diese Links nicht sehen, findet und durchsucht der Suchroboter sie immer noch. Sie können verborgene Tags am unteren Rand der Seite direkt vor dem `</body>`-Tag platzieren. Sie können wie folgt aussehen:

```
<a href="/mydir/mypag1.html"></a> 
<a href="/mydir/mypag2.html"></a>
```

Eine andere Lösung besteht darin, die URLs der zusätzlichen Seiten auf Ihrer Website als Einstiegspunkte für Crawl und Index Liste. Beginnen Sie die URLs mit `https://`, wie im Folgenden gezeigt:

```
https://www.mydomain.com/mydir/mypag1.html 
https://www.mydomain.com/mydir/mypag2.html
```

Siehe [Hinzufügen mehrerer URL-Einstiegspunkte, die indiziert werden sollen.](../c-about-settings-menu/c-about-crawling-menu.md#task_2338A47387D74CFDAC4D4EF4A367ED45)

## Sind die HTML-Tags auf Ihrer Webseite in einer ungültigen Reihenfolge? {#section_F31A2F5D2C284AC084158A5BD763DC5D}

Die HTML-Spezifikation erfordert, dass die Tags `<html>`, `<head>` und `<body>` einer bestimmten Sequenz in einem HTML-Dokument folgen. Tags auf allen Webseiten müssen die folgende Reihenfolge aufweisen:

```
<html> 
<head> 
...  
<i>head tags go here</i> ... 
</head> 
<body> 
...  
<i>body tags go here</i> ... 
</body> 
</html>
```

Wenn die HTML-Tags nicht in der richtigen Reihenfolge angeordnet sind, kann der Site-Such-/Merchandising-Roboter Ihre Webseite nicht richtig analysieren und indizieren. Im Folgenden finden Sie ein Beispiel für Tags, die sich nicht in der richtigen Reihenfolge befinden:

```
<body> 
<head> 
...  
<i>head tags are here</i> ... 
</head> 
...  
<i>body tags are here</i> ... 
</body>
```

In diesem Fall platzieren Sie die Tags `<html>`, `<head>` und `<body>` in der richtigen Reihenfolge auf Ihrer Webseite.

## Haben Sie auf Ihrer Webseite falsch formatierte HTML-Kommentar-Tags? {#section_D1C39D79341845CB9C38579AABDF3A24}

Stellen Sie sicher, dass Sie ungültige HTML-Kommentare auf Ihren Webseiten sorgfältig überprüfen und korrigieren.

Die HTML-Spezifikation verlangt, dass ein HTML-Kommentar mit den Zeichen `<!--` und mit den Zeichen `-->` beginnt. Es ist einfach, falsch formatierte Kommentare zu übersehen, die dazu führen, dass der Site-Such-/Merchandising-Roboter die Tags auf Ihrer Webseite falsch analysiert. Ein falsch formatierter Kommentar kann dazu führen, dass der Site-Such-/Merchandising-Roboter andere wichtige Tags verpasst, die analysiert werden müssen. Achten Sie auf Kommentare kurz vor dem `<body>`-Tag in Ihrer Webseite.

Im Folgenden finden Sie ein Beispiel für einen ordnungsgemäß formatierten Kommentar:

`<!-- This HTML comment is OK. -->`

Im Folgenden finden Sie ein Beispiel für fehlerhafte Kommentare:

```
<!- This HTML comment is improperly formed. -> 
<! This HTML comment is also improperly formed. >
```

## Enthält Ihre Webseite Links zu Seiten in einer anderen Domäne? {#section_F8082759184049AAA8FA6342C1F84389}

Oft kann eine Website aus Seiten bestehen, die tatsächlich auf einem Webserver mit einer anderen Domänenadresse vorhanden sind. Wenn Ihre Haupt-Website-Adresse beispielsweise folgende ist:

`https://www.mydomain.com/`

Ihre Website kann auch Seiten in einer anderen Domäne wie der folgenden enthalten:

`https://www.otherdomain.com/`

Standardmäßig folgen die Links des Site-Such-/Merchandising-Roboters nicht auf einer anderen Domäne als der Hauptdomäne. Indem Sie jedoch zusätzliche Einstiegspunkte für Ihr Suchkonto festlegen, können Sie problemlos mehrere Domänen indizieren.

Klicken Sie im Produktmenü auf **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL URL Entrypoints]**. hinzufügen der &quot;Haupt-Website-Einstiegspunkt&quot;-URL Ihrer Site. Fügen Sie dann weitere URL-Einstiegspunkte zu allen anderen Domänen hinzu, die Siteseiten enthalten. Sie würden z. B. Ihren URL-Haupteinstiegspunkt auf Folgendes setzen:

`https://www.mydomain.com/`

und fügen Sie den folgenden zusätzlichen Site-URL-Einstiegspunkt hinzu:

`https://www.otherdomain.com/`

## Verwenden Sie einen virtuellen Domänendienst für Ihre URL? {#section_2861F09EA21A45E6B7E15F032739CDF3}

Möglicherweise verwenden Sie einen virtuellen Domänendienst (manchmal auch als &quot;Domänenumleitungsdienst&quot;bezeichnet), um eine bessere URL für Kunden bereitzustellen, die zu Ihrer Website gelangen. Angenommen, die Adresse Ihrer Website lautet wie folgt:

`https://www.myispdomain.com/~myname/mywebpages/`

Sie verwenden jedoch einen virtuellen Domänendienst, damit Kunden unter folgenden Adressen zu Ihrer Site gelangen können:

`https://myname.adomain.com/`

oder

`https://adomain.com/myname/`

Standardmäßig folgen die Links des Site-Such-/Merchandising-Roboters nicht auf einer anderen Domäne als der Hauptdomäne. Indem Sie jedoch zusätzliche Einstiegspunkte für Ihr Suchkonto festlegen, können Sie problemlos mehrere Domänen indizieren.

Klicken Sie im Produktmenü auf **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL URL Entrypoints]**. hinzufügen der &quot;Haupt-Website-URL-Einstieg&quot; auf den virtuellen Domänennamen Ihrer Site. Fügen Sie dann der Domäne, in der sich Ihre Website befindet, weitere Einstiegspunkte hinzu.

Sie würden z. B. den Haupteinstiegspunkt der URL auf Folgendes setzen:

`https://myname.adomain.com/`

Fügen Sie den folgenden zusätzlichen URL-Einstiegspunkt der Website hinzu:

`https://www.myispdomain.com/~myname/mywebpages/`

## Verwendet Ihre Webseite ein Meta-Aktualisierungs-Tag? {#section_5A2F544C237C49B8B1A7FE0C45371C0D}

Viele Websites haben eine Titelseite, die ein Meta-Aktualisierungs-Tag zwischen den `<head>...</head>`-Tags enthält, ähnlich dem Folgenden:

`<meta http-equiv="Refresh" content="0;URL=https://www.adomain.com/apath/afile.html">`

Unter bestimmten Umständen ist der Site-Suchroboter/Merchandising nicht in der Lage, der Meta-Aktualisierungs-URL zu folgen, um den Inhalt Ihrer Website zu indizieren. Dieses Problem lässt sich einfach umgehen, indem Sie zusätzliche Einstiegspunkte festlegen.

Klicken Sie im Produktmenü auf **[!UICONTROL Settings]** > Crawling > **[!UICONTROL URL Entrypoints]**. hinzufügen einen weiteren Einstiegspunkt zur URL des Meta-Aktualisierungs-Tags.

## Verwendet Ihre Webseite ein Meta-Roboter-Tag? {#section_36275A33DDFE4620BABA948F8A63DBD2}

Manchmal verwenden Webseiten Meta-Robots-Tags, um Webroboter zu steuern, die regelmäßig versuchen, eine Website zu durchsuchen. Meta-Roboter-Tags werden zwischen den `<head>...</head>`-Tags einer Webseite angezeigt und sehen ähnlich wie das folgende Tag aus:

`<meta name="robots" content="noindex, nofollow">`

Da der Site-Such-/Merchandising-Roboter selbst ein Webroboter ist, folgt er den Anweisungen des Meta-Roboter-Tags. Indem Sie andere Roboter auf diese Weise ausschließen, schließen Sie auch den Site-Such-/Merchandising-Roboter aus.

Weitere Informationen zu Webrobotern und dem Roboter-Ausschlussprotokoll finden Sie unter:

[https://www.robotstxt.org/orig.html](https://www.robotstxt.org/orig.html)

Entfernen oder ändern Sie das Meta-Robots-Tag auf den Webseiten, die Sie auf Ihrer Website indizieren möchten.

## Verwendet Ihre Website eine Ausschlussdatei für Roboter? {#section_BF7B663347814F58AD736066C86B7D25}

Manchmal hat eine Website eine Seite namens &quot;robots.txt&quot;, die alle oder bestimmte Roboter vom Crawling ausschließt. Um zu sehen, ob Ihre Website eine Datei &quot;robots.txt&quot;enthält, suchen Sie diese direkt unter der Domäne der obersten Ebene, wie im Folgenden gezeigt:

`https://www.yourdomain.com/robots.txt`

Der Inhalt der Datei &quot;robots.txt&quot;ähnelt dem folgenden Text:

```
User-agent: * 
Disallow: /
```

Da der Site-Such-/Merchandising-Roboter selbst ein Webroboter ist, folgt er den Anweisungen in der Datei &quot;robots.txt&quot;. Er schließt den Site-Such-/Merchandising-Roboter aus. Um dieses Problem zu umgehen, bearbeiten Sie die Ausschlussdatei für Roboter (robots.txt), damit der Site-Such-/Merchandising-Roboter Ihre Website wie folgt durchsuchen und indizieren kann:

```
User-agent: Atomz/1.0 
Disallow: 
 
User-agent: * 
Disallow: /
```

## Microsoft Office {#reference_A85FCC8A96514A7584F4D2A8AC8111D1}

Eine Seite mit häufig gestellten Fragen, die die Unterstützung der Indizierung und Suche von Microsoft® Office-Dateien auf einer Website behandelt.

Im Folgenden werden häufig gestellte Fragen zu Microsoft Office-Dateien aufgeführt:

* [Was wird in einer Microsoft Office-Datei indiziert?](#section_8681DADFCFE24B7787B1FC08D431EE28)
* [Was nicht in einer Microsoft Office-Datei indiziert wird...](#section_BD53BDABFDD94D7EB0E1F55EC18017BB)
* [Wie unterscheiden sich Microsoft Office-Dateien von HTML-Seiten...](#section_C104B44684F340549A6B9EB8F39EDDBB)
* [Wie kann ich verhindern, dass Microsoft Office-Dateien indiziert werden?](#section_FEBA71274CD14CB99731ADF982087F4C)

## Was wird in einer Microsoft Office-Datei indiziert? {#section_8681DADFCFE24B7787B1FC08D431EE28}

Der vollständige Inhalt von Microsoft Word-, Microsoft Excel- und Microsoft PowerPoint-Dateien wird indiziert.

Die folgenden Teile einer Microsoft Word-Datei werden indexiert:

* Titel
* Keywords
* Betreff (Beschreibung)
* Textbasierter Inhalt
* Hyperlinks zu anderen Dokumenten

Die folgenden Teile einer Microsoft Excel-Datei werden indexiert:

* Titel
* Schlüsselwörter
* Betreff (Beschreibung)
* Text in Zellen
* Werte aus numerischen Formeln in Zellen

Die folgenden Teile einer Microsoft PowerPoint-Datei werden indexiert:

* Titel
* Schlüsselwörter
* Betreff (Beschreibung)
* Text auf jeder Folie

## Was wird nicht in einer Microsoft Office-Datei indiziert? {#section_BD53BDABFDD94D7EB0E1F55EC18017BB}

Grafiken, die in Microsoft Office-Dateien enthalten sind, oder Text, der Teil einer enthaltenen Grafik ist, werden nicht indiziert. Benutzerdefinierte Eigenschaftsdefinitionen werden nicht als Metadaten indiziert. Einige Texte in speziellen Feldern, wie Kopf- und Fußzeilen in einer PowerPoint-Datei, werden ebenfalls nicht indiziert.

## Wie unterscheiden sich Microsoft Office-Dateien von HTML-Seiten? {#section_C104B44684F340549A6B9EB8F39EDDBB}

Der Unterschied zwischen der Indizierung von Microsoft Office- und HTML-Dateien durch den Suchroboter besteht darin, dass jede HTML-Datei eine einzelne Seite und eine einzelne Microsoft Office-Datei Hunderte von Seiten darstellen kann. Aus diesem Grund wird jede Seite in einer Microsoft Office-Datei als separate Seite unter Ihrem Suchkonto gezählt.

## Wie kann ich verhindern, dass Microsoft Office-Dateien auf meiner Website indiziert werden? {#section_FEBA71274CD14CB99731ADF982087F4C}

Wenn Sie nicht möchten, dass der Suchroboter Microsoft Office-Dateien durchsucht und indiziert, deaktivieren Sie den Inhaltstyp **[!UICONTROL Microsoft Office Files]** ( **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Content Types]**).

Sie können auch [!DNL URL Masks] verwenden, um die Indizierung von Microsoft Office-Dateien zu deaktivieren.

Geben Sie die folgenden URL-Masken ein:

<table> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Wenn Sie keine regulären Ausdrücke verwenden </p> </td> 
   <td colname="col2"> 
    <ul id="ul_DFEC911DA11C484C8E4671A0F00E1F88"> 
     <li id="li_2E50374E3869426B97353A5A8CBE09EC">exclude *.doc </li> 
     <li id="li_9089D11161524D90849CA88F703772B6">exclude *.xls </li> 
     <li id="li_7F6CFC6212E64C04AAF38E21A667C763">exclude *.ppt </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Wenn Sie reguläre Ausdruck verwenden </p> </td> 
   <td colname="col2"> 
    <ul id="ul_012A45C3EC04460EA09C0ECFB49A8FA9"> 
     <li id="li_0C239F0A536D465F85A98EBF7B6ADF27">exclude regexp ^.*\\.doc$ </li> 
     <li id="li_9F91DA35A2A646ACAFF2BA37F9136E2A">exclude regexp ^.*\\.xls$ </li> 
     <li id="li_9D768D9EA2DB44FBB00A1979E21672E2">exclude regexp ^.*\\.ppt$ </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

Siehe [Hinzufügen von URL-Masken zum Index oder nicht zum Indexieren von Teilen von...](../c-about-settings-menu/c-about-crawling-menu.md#task_E1AFC17C746048B8843013D979E082C1).

Siehe [Reguläre Ausdruck](../c-appendices/r-regular-expressions.md#reference_B5BA7D61D82E4109A01D2A2D964E3A6A).

## MP3 {#reference_7614250EE81C4EEFA43E57A6A74E83D7}

Eine Seite mit häufig gestellten Fragen, die die Unterstützung der Indizierung und Suche von MP3-Musikdateien auf einer Website behandelt.

Im Folgenden finden Sie allgemeine Fragen zu MP3-Dateien.

* [Wann wird eine MP3-Datei durchsucht und indiziert?](#section_538EA1682C9C47E3A62640BB25D84C36)
* [Was muss ich tun, um zu kriechen und zu indizieren?](#section_3CD794446E3545379C14E9F222118665)
* [Wie wird eine MP3-Datei erkannt?](#section_230E7336965A424F96C5CCF1D3C2D103)
* [Was ist in einer MP3-Datei indiziert?](#section_E99D252B27CA4946AED3FCD3ABD8779D)
* [Zählt eine MP3-Datei als Seite?](#section_9910BEB6617D4D2090558CDF6C65D16B)
* [Wie vermeide ich die Indizierung einzelner MP3-Dateien...](#section_C989DC1D3D3841B38F683A462195DC05)
* [Wie kann ich verhindern, dass MP3-Dateien indiziert werden?](#section_305D2B28D1124776B6DC0C62A17827C6)
* [Warum kann ich die chinesischen, japanischen oder koreanischen MP3-Dateien auf meiner Site nicht durchsuchen?](#section_06A48DA3F9E742CC93CC8B5CCD7382FA)

## Wann wird eine MP3-Datei durchsucht und indiziert? {#section_538EA1682C9C47E3A62640BB25D84C36}

MP3-Dateien werden auf zweierlei Weise durchsucht und indiziert. Am häufigsten erfolgt die Eingabe über ein Anker-href-Tag in einer HTML-Datei:

`<a href="MP3-file-URL"></a>`

Eine zweite Möglichkeit besteht darin, die URL der MP3-Datei als URL-Einstiegspunkt einzugeben.

Siehe [Informationen zu URL-Einstiegspunkten](../c-about-settings-menu/c-about-crawling-menu.md#concept_5D857E3B5C124E85BC0B5AE77A509573).

## Was muss ich tun, um die MP3-Dateien auf meiner Site zu durchsuchen und zu indizieren? {#section_3CD794446E3545379C14E9F222118665}

Klicken Sie zum Aktivieren des Crawling und Indizierens von MP3 für Ihr Konto im Produktmenü auf **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Content Types]**. Wählen Sie auf der Seite [!DNL Staged Content Types] **[!UICONTROL Text in MP3 Music Files]** aus.

Siehe [Inhaltstypen](../c-about-settings-menu/c-about-crawling-menu.md#concept_6FEA1355C0374500B4C53090C34A8A07).

## Wie wird eine MP3-Datei erkannt? {#section_230E7336965A424F96C5CCF1D3C2D103}

Eine MP3-Datei wird durch ihren MIME-Typ &quot;audio/mpeg&quot;erkannt.

## Was ist in einer MP3-Datei indiziert? {#section_E99D252B27CA4946AED3FCD3ABD8779D}

MP3-Dateien speichern optional eine kleine Menge an Textinformationen. Diese Informationen können den Namen des Albums, den Namen des Künstlers, den Titel des Liedes, das Musikgenre, das Jahr der Veröffentlichung und einen Kommentar enthalten. Diese Informationen werden am Ende der Datei im so genannten TAG gespeichert. MP3-Dateien, die TAG-Informationen enthalten, werden wie folgt indiziert:

* Der Titel des Liedes wird wie der Titel einer HTML-Seite behandelt.
* Der Kommentar wird wie eine für eine HTML-Seite definierte Beschreibung behandelt.
* Das Genre wird wie ein für eine HTML-Seite definierter Suchbegriff behandelt.
* Der Künstlername, der Albumname und das Veröffentlichungsjahr werden wie der Hauptteil eines HTML-Dokuments behandelt.

## Zählt eine MP3-Datei als Seite? {#section_9910BEB6617D4D2090558CDF6C65D16B}

Ja, jede MP3-Datei, die auf Ihrer Website durchsucht und indiziert wird, wird als eine Seite gezählt.

## Wie kann ich die Indizierung einzelner MP3-Dateien verhindern? {#section_C989DC1D3D3841B38F683A462195DC05}

Umschließen Sie die Anker-Tags, die mit den Tags `<nofollow>` und `</nofollow>` mit den MP3-Dateien verknüpft sind. Der Suchroboter folgt nicht den Verknüpfungen zwischen diesen Tags.

Eine andere Methode besteht darin, die URLs der MP3-Dateien als Ausschlussmasken hinzuzufügen.

Siehe [URL-Masken](../c-about-settings-menu/c-about-crawling-menu.md#concept_8039DFC53FF3410AA494D602F71BA164).

Siehe [Skript &quot;URL-Masken](../c-about-settings-menu/c-about-filtering-menu.md#concept_384F32EA18F84853A7BA99A04009330B)&quot;.

## Wie kann ich verhindern, dass MP3-Dateien indiziert werden? {#section_305D2B28D1124776B6DC0C62A17827C6}

Die einfachste Möglichkeit, die MP3-Indexierung für Ihr Konto zu steuern, ist die Deaktivierung von **[!UICONTROL Text in MP3 Music Files]** auf der [!DNL Staged Content Types]-Seite.

Siehe [Auswählen von Inhaltstypen zum Crawl und Indexieren](../c-about-settings-menu/c-about-crawling-menu.md#task_CCAC5C67C8BF4AB7B79D34A1495D5EE8).

Sie können auch die Funktion &quot;URL-Masken&quot;verwenden, um die MP3-Indexierung nach Dateierweiterung zu deaktivieren. Klicken Sie dazu im Produktmenü auf **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL URL Masks]**. Geben Sie eine der folgenden Masken ein:

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Wenn Ihr Konto... </p> </th> 
   <th colname="col2" class="entry"> <p>Geben Sie die folgende URL-Maske ein </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Verwendet keine regulären Ausdruck </p> </td> 
   <td colname="col2"> <p> <span class="codeph"> exclude *.mp3  </span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Verwendet reguläre Ausdruck </p> </td> 
   <td colname="col2"> <p> <span class="codeph"> exclude regexp ^.*\.mp3$ </span> </p> </td> 
  </tr> 
 </tbody> 
</table>

Siehe [Reguläre Ausdruck](../c-appendices/r-regular-expressions.md#reference_B5BA7D61D82E4109A01D2A2D964E3A6A).

## Warum kann ich die chinesischen, japanischen oder koreanischen MP3-Dateien auf meiner Site nicht durchsuchen? {#section_06A48DA3F9E742CC93CC8B5CCD7382FA}

Um nach chinesischen, japanischen oder koreanischen MP3-Dateien zu suchen, klicken Sie im Produktmenü auf **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Content Types]** > **[!UICONTROL Text in MP3 Music Files]**. Klicken Sie dann auf **[!UICONTROL Settings]** > **[!UICONTROL Metadata]** > **[!UICONTROL Injections]** und geben Sie den Zeichensatz an, der zum Kodieren der MP3-Dateien verwendet wird.

Siehe [Auswählen von Inhaltstypen zum Crawl und Indexieren](../c-about-settings-menu/c-about-crawling-menu.md#task_CCAC5C67C8BF4AB7B79D34A1495D5EE8).

Siehe [Info zu Injektionen](../c-about-settings-menu/c-about-metadata-menu.md#concept_DA091920671948A0A893A26B3A2FAAE5).

## PDF {#reference_F127C4915A0D436DA34E5D75ABFBB21B}

Auf der Seite mit häufig gestellten Fragen wird die Unterstützung der Indizierung und Suche von PDF-Dateien auf einer Website diskutiert.

Im Folgenden werden häufig gestellte Fragen zu PDF-Dateien behandelt:

* [Was wird in einer PDF-Datei indiziert?](#section_62BFCD7158B44F2BB3B1864224B50174)
* [Was wird nicht in einer PDF-Datei indiziert?](#section_A14B353AE503408896BACBBF3F748FA0)
* [Wie werden indizierte PDF-Dateien gezählt?](#section_C35DE36A65D649BD8FF314E9EFD990A6)
* [Können die Suchergebnisse ein PDF-Symbol anzeigen?](#section_829CE82CC3544502A13D27C4DB820189)
* [Können die Suchergebnisse mit einer bestimmten Seite in...](#section_A06E7F7017E6441E98209D288EE57BF6)
* [Wie kann ich verhindern, dass PDF-Dateien indiziert werden...](#section_96671419A822486AAC654D8DAD819940)
* [Wie kommt es, dass ich die chinesischen, japanischen oder koreanischen PDF-Dateien auf meiner Website nicht durchsuchen kann?](#section_D41CA8EFCA0242EA8CF5F8F1924E4CD8)

## Was wird in einer PDF-Datei indiziert? {#section_62BFCD7158B44F2BB3B1864224B50174}

Der gesamte Inhalt von PDF-Dateien wird indiziert. Die folgenden Teile einer PDF-Datei werden indexiert:

* Titel
* Schlüsselwörter
* Betreff (Beschreibung)
* Textbasierter Inhalt

## Was wird nicht in einer PDF-Datei indiziert? {#section_A14B353AE503408896BACBBF3F748FA0}

Das PDF-Inhaltsverzeichnis, Grafiken in der Datei oder Text, der Teil einer enthaltenen Grafik ist, werden nicht indiziert.

## Wie werden indizierte PDF-Dateien gezählt? {#section_C35DE36A65D649BD8FF314E9EFD990A6}

Jede PDF-Datei, einschließlich PDF-Dateien mit mehreren Seiten, wird als ein einziges Dokument gezählt.

## Können die Suchergebnisse ein PDF-Symbol anzeigen? {#section_829CE82CC3544502A13D27C4DB820189}

Ja. Verwenden Sie das `<search-if-link-extension>`-Tag in Ihrer Vorlage, um ein PDF-Symbol oder andere Grafiken oder Text in die Suchergebnisse einzuschließen:

```
<search-results> 
  ... 
  <search-if-link-extension value=".pdf"> 
    <img src="/search/i/pdficon.gif"> 
  </search-if-link-extension> 
  ... 
</search-results>
```

PDF-Symbole helfen Ihren Kunden zu wissen, dass ein Suchergebnis mit einer PDF-Datei verknüpft ist, die sehr groß sein kann. Die Dateigröße kann für Kunden von Bedeutung sein, die über ein Modem oder ein Mobilgerät auf Ihre Website zugreifen.

## Können die Suchergebnisse mit einer bestimmten Seite in einer PDF-Datei verknüpft werden? {#section_A06E7F7017E6441E98209D288EE57BF6}

Ja. Mithilfe des Vorlagen-Tags für intelligente Links ( `<search-smart-link>...</search-smart-link>`) können Kunden auf die erste PDF-Seite klicken, die das Suchergebnis enthält.

Um intelligente Links zu verwenden, ersetzen Sie die Tags `<search-link>...</search-link>` im Suchergebnisbereich Ihrer Vorlage durch `<search-smart-link>...</search-smart-link>`-Tags. Wenn ein Kunde auf einen Link klickt, den die Smart-Link-Tags generieren, wird die erste PDF-Abfrage aufgerufen, die für die Suche relevant ist.

>[!NOTE]
>
>Um diese Funktion nutzen zu können, muss der Kunde eine neuere Version des Adobe Acrobat- oder Adobe Acrobat-Readers verwenden, die das Hervorhebungs-Plug-in und das externe Window Handler (EWH)-Plug-In enthalten muss. Darüber hinaus muss der Webbrowser das Adobe Acrobat-Plugin für Netscape Navigator (Sie können jeden Browser verwenden, der dieses Netscape Navigator-Plug-In akzeptiert) oder das Acrobat ActiveX-Steuerelement für Internet Explorer 4.0 und höher verwenden.

Siehe [Suchvorlagen-Tags](../c-appendices/c-templates.md#reference_F7AA3FF602314E42842BBC740D2CA1A4).

## Wie kann ich verhindern, dass PDF-Dateien auf meiner Website indiziert werden? {#section_96671419A822486AAC654D8DAD819940}

Wenn Sie nicht möchten, dass der Suchroboter PDF-Dateien durchsucht und indiziert, deaktivieren Sie den Inhaltstyp **[!UICONTROL PDF Documents]** ( **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Content Types]**).

Sie können auch [!DNL URL Masks] verwenden, um die PDF-Indexierung zu deaktivieren.

Siehe [Hinzufügen von URL-Masken zum Index oder nicht zum Indexieren von Teilen von...](../c-about-settings-menu/c-about-crawling-menu.md#task_E1AFC17C746048B8843013D979E082C1).

Um die PDF-Indexierung zu deaktivieren, geben Sie eine der folgenden URL-Masken ein:

* `exclude *.pdf` (wenn Sie keine regulären Ausdrücke verwenden)
* `exclude regexp ^.*\.pdf$` (wenn Sie reguläre Ausdrücke verwenden)

Siehe [Reguläre Ausdruck](../c-appendices/r-regular-expressions.md#reference_B5BA7D61D82E4109A01D2A2D964E3A6A).

## Wie kommt es, dass ich die chinesischen, japanischen oder koreanischen PDF-Dateien auf meiner Website nicht durchsuchen kann? {#section_D41CA8EFCA0242EA8CF5F8F1924E4CD8}

Site-Suche/Merchandising ruft UTF-8 aus PDF-Dateien ohne Angabe der Sprache ab. Wenn Sie den Inhaltstyp **[!UICONTROL PDF Documents]** ( **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Content Types]**) ausgewählt haben, müssen Sie mithilfe von Metadaten-Injektionen die Sprache angeben, die in der PDF-Datei verwendet wird.

Siehe [Hinzufügen von Feldinjizierungsdefinitionen](../c-about-settings-menu/c-about-metadata-menu.md#task_E86566FA1FF74CF68115C0ADA05172AE).

## Zu viele Seiten {#reference_48A748BC1ED14844ACAC2735C8388E8A}

Auf der Seite mit häufig gestellten Fragen werden einige Gründe erläutert, warum der Indexer mehr Seiten gezählt hat, als Sie tatsächlich haben, und wie die Lösung in jedem Fall aussieht.

Wenn Sie sicher sind, dass Ihre Website unter Ihrer Seitenbegrenzung liegt, der Indexer Ihnen jedoch mitteilt, dass die Grenze erreicht ist, sollten Sie diese allgemeinen Fragen und Antworten auf mögliche Lösungen überprüfen.

* [Haben Sie Ihre verschiedenen Indexprotokolle geprüft?](#section_C929BF9FDA6B4C9A9078C45AFE80EFE8)
* [Werden CGI-Programm auf Ihrer Website indiziert?](#section_86ED8A641B3841EC80153B4F107548FD)
* [Ist das Durchsuchen von Ordnern auf Ihrem Server aktiviert?](#section_073C88EEE74F4CA0AD2C7145D4810B22)
* [Gibt es Foren oder Newsgruppen auf Ihrer Website?](#section_8DCB94F0850A41B9B2EA885F779E2F84)
* [Sind PDF- oder Microsoft Office-Dateien auf Ihrer Website vorhanden...](#section_455FC5438DF74E68AB9A31D359EAD4D9)
* [Haben Sie mehrere URL-Einstiegspunkte?](#section_8C54AFD7DF56472A9364D516482B534C)
* [Haben Sie die internen Bytes oder Zeitgrenzen von ...](#section_AE1BE61A58864FFE81F0BCEED2EBB15D)

## Haben Sie Ihre verschiedenen Indexprotokolle geprüft? {#section_C929BF9FDA6B4C9A9078C45AFE80EFE8}

Das Index-Protokoll enthält detaillierte Informationen, die vom Site-Such-/Merchandising-Roboter gesammelt wurden, während es Ihre Website indiziert. Das Protokoll enthält eine Liste aller durchgeknackten Links und enthält Fehler. Die Überprüfung des Indexprotokolls ist der beste Ort für Beginn, wenn Sie ermitteln möchten, welche Seiten indiziert werden.

Siehe [Anzeigen des vollständigen Indexprotokolls einer Live- oder Stage...](../c-about-index-menu/c-about-full-index.md#task_02E5E944C56B4EB19CC1FF321F3221B8).

Siehe [Anzeigen des inkrementellen Indexprotokolls einer Live- oder Stage...](../c-about-index-menu/c-about-incremental-index.md#task_E668E1F1240C476DAA1CA783DC728232).

Siehe [Ansicht des skriptgesteuerten inkrementellen Index-Protokolls einer Live- oder...](../c-about-index-menu/c-about-scripted-index.md#task_CBFCE9B9A87B4DF7A2A35A6E83DE93D7).

Siehe [Anzeigen des neu generierten Indexprotokolls einer Live- oder Stage...](../c-about-index-menu/c-about-regenerate-index.md#task_61CE8F9E7BF84BA89A8D482B2106BB15).

Siehe [Anzeigen des neu bewerteten Index-Protokolls einer Live- oder Staged-Website](../c-about-index-menu/c-about-re-rank-index.md#task_3C76107DFAC1495FACD3ABB0A688208D).

## Werden CGI-Programm auf Ihrer Website indiziert? {#section_86ED8A641B3841EC80153B4F107548FD}

CGI-Programm verwenden URL-Parameter, die manchmal dazu führen, dass der Indexer mehrere &quot;gefälschte&quot;URLs durchsucht. Wenn Site-Suche/Merchandising Ihre CGI-Programm liest und URLs mit CGI-Parametern folgt, werden wahrscheinlich mehrere Vielfache Seiten durchsucht und indiziert, die für Ihren Suchindex nicht nützlich sind. Typische CGI-Parameter werden in URLs mit `?`- oder `&`-Zeichen angezeigt.

Mithilfe der Funktion &quot;URL-Masken&quot;können Sie die CGI-Programm von der Indexierung ausschließen. Sie können ein URL-Präfix maskieren oder reguläre Ausdruck verwenden, um Ihre CGI-Skripte zu maskieren.

Siehe [URL-Masken](../c-about-settings-menu/c-about-crawling-menu.md#concept_8039DFC53FF3410AA494D602F71BA164).

Siehe [Skript &quot;URL-Masken](../c-about-settings-menu/c-about-filtering-menu.md#concept_384F32EA18F84853A7BA99A04009330B)&quot;.

Siehe [Reguläre Ausdruck](../c-appendices/r-regular-expressions.md#reference_B5BA7D61D82E4109A01D2A2D964E3A6A).

## Ist das Durchsuchen von Ordnern auf Ihrem Server aktiviert? {#section_073C88EEE74F4CA0AD2C7145D4810B22}

Wenn auf einem Webserver das Durchsuchen von Ordnern aktiviert ist und in einem bestimmten Verzeichnis keine Datei &quot;index.html&quot;vorhanden ist, kann ein Besuch dieses Ordners die Auflistung der Dateien in diesem Verzeichnis anzeigen. Normalerweise befinden sich Links am oberen Seitenrand, mit denen Sie die Liste auf unterschiedliche Weise sortieren können, indem Sie einfach auf **[!UICONTROL Name]**, **[!UICONTROL Last modified]**, **[!UICONTROL Size]** usw. klicken. Normalerweise erscheinen diese im Site-Index-Protokoll für Suche/Merchandising als URLs mit Zeichen wie `?M=A` am Ende. Der Site-Such-/Merchandising-Impulszähler folgt diesen als Links, was dazu führen kann, dass mehrere &quot;gefälschte&quot;URLs indiziert werden.

Normalerweise enthält eine gut konzipierte Website entweder Indexdateien in jedem Verzeichnis, oder das Durchsuchen von Ordnern ist für Ordner ohne Indexdateien deaktiviert. Glücklicherweise gibt es eine einfache Möglichkeit, diese &quot;gefälschten&quot;URLs zu maskieren, wenn Sie Ihre Seiten nicht ändern oder Ordnerauflistungen auf der Serverseite deaktivieren können.

Um diese Aufgabe durchzuführen, klicken Sie auf **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL URL Masks]**. hinzufügen einer Maske, um jede URL zu maskieren, die das Zeichen `?` enthält. Sie können diese Aufgabe ausführen, indem Sie die folgende Maske für regulären Ausdruck eingeben:

`exclude regexp ^.*\?.*$`

Nachdem Sie die Maske erstellt haben, stellen Sie sicher, dass Sie Ihre Website neu indizieren.

Siehe [Ausführen eines vollständigen Indexes einer Live- oder Staged-Website...](../c-about-index-menu/c-about-full-index.md#task_F7FE04D8A1654A7787FCCA31B45EB42D).

Siehe [Ausführen eines inkrementellen Indexes einer Live- oder Staged-Website...](../c-about-index-menu/c-about-incremental-index.md#task_9BFB6157F3884B2FAECB7E0E9CA318CB).

## Gibt es Foren oder Newsgruppen auf Ihrer Website? {#section_8DCB94F0850A41B9B2EA885F779E2F84}

Wenn Foren oder Newsgruppen auf Ihrer Website durchsucht werden, können URLs für verschiedene Anzeigeoptionen oder Sortieroptionen folgen. Dieses Verhalten bedeutet, dass dieselbe Seite mehrmals indiziert wird.

In der Regel verfügen Foren oder Newsgroups über eigene Suchmaschinen. In diesem Fall können Sie [!DNL URL Masks] verwenden, um die Foren von der Site-Suche/Merchandising zu maskieren.

Klicken Sie im Produktmenü auf **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL URL Masks]**. Maskieren Sie auf der Seite [!DNL Staged URL Masks] Ihre Foren, indem Sie ihre URLs als URL-Masken zum Ausschließen eingeben.

Siehe [Hinzufügen von URL-Masken zum Index oder nicht zum Indexieren von Teilen von...](../c-about-settings-menu/c-about-crawling-menu.md#task_E1AFC17C746048B8843013D979E082C1).

Nachdem Sie die Masken erstellt haben, stellen Sie sicher, dass Sie Ihre Website neu indizieren.

Siehe [Ausführen eines vollständigen Indexes einer Live- oder Staged-Website...](../c-about-index-menu/c-about-full-index.md#task_F7FE04D8A1654A7787FCCA31B45EB42D).

Siehe [Ausführen eines inkrementellen Indexes einer Live- oder Staged-Website...](../c-about-index-menu/c-about-incremental-index.md#task_9BFB6157F3884B2FAECB7E0E9CA318CB).

## Gibt es PDF- oder Microsoft Office-Dateien auf Ihrer Website? {#section_455FC5438DF74E68AB9A31D359EAD4D9}

Wenn Sie PDF-Dateien oder [!DNL Microsoft Office]-Dateien auf Ihrer Website haben, werden Sie möglicherweise feststellen, dass die Indexgröße von nur wenigen Dateien viele Seiten zählt. Der Grund dafür, dass mehr Seiten indiziert werden als Dokumente, ist, dass jede Seite in einer PDF- oder Microsoft Office-Datei als separate Seite gezählt wird.

Klicken Sie im Produktmenü auf **[!UICONTROL Index]** > **[!UICONTROL Full Index]** > **[!UICONTROL Live Index]**. Wählen Sie auf der Seite [!DNL Full Index] die Option **[!UICONTROL Count All Pages]** und klicken Sie dann auf **[!UICONTROL Full Index Now]**, um die Gesamtanzahl der Seiten anzuzeigen. Wenn PDF- oder Microsoft Office-Dateien nicht indiziert werden sollen, können Sie diesen Inhaltstyp unter **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Content Types]** deaktivieren.

Siehe [Ausführen eines vollständigen Indexes einer Live- oder Staged-Website...](../c-about-index-menu/c-about-full-index.md#task_F7FE04D8A1654A7787FCCA31B45EB42D).

Siehe [Inhaltstypen](../c-about-settings-menu/c-about-crawling-menu.md#concept_6FEA1355C0374500B4C53090C34A8A07).

## Haben Sie mehrere URL-Einstiegspunkte? {#section_8C54AFD7DF56472A9364D516482B534C}

Der Site-Such-/Merchandising-Roboter beginnt mit dem Crawling an bestimmten URL-Einstiegspunkten und folgt allen gefundenen Links zu allen Inhalten in dieser bestimmten Domäne. Wenn Sie viele URL-Einstiegspunkte angegeben haben, wird möglicherweise eine erhebliche Anzahl von Seiten durchsucht.

Verwenden Sie das `nofollow`-Tag des Robots-Ausschlussprotokolls in den Kopfzeilen der Einstiegspunkte-Dokumente auf den zusätzlichen Domänen wie folgt:

```
<html> 
<head> 
<meta name="robots" content="nofollow"> 
</head>
```

Der obige Code weist den Site-Such-/Merchandising-Roboter an, den Inhalt der Seite zu indizieren, aber nicht den Links zu zusätzlichen Seiten zu folgen.

Weitere Informationen zu Webrobotern und dem Roboter-Ausschlussprotokoll finden Sie unter:

[https://www.robotstxt.org/orig.html](https://www.robotstxt.org/orig.html)

Wenn Sie keinen Zugriff auf die Quelle der Seiten auf zusätzlichen Domänen haben, können Sie die Einstiegspunkte für mehrere URLs entfernen. Auf diese Weise können Sie die Indizierung der Aktivität nur auf Domänen beschränken, deren Inhalte Sie von Kunden durchsuchen können möchten.

Siehe [Informationen zu URL-Einstiegspunkten](../c-about-settings-menu/c-about-crawling-menu.md#concept_5D857E3B5C124E85BC0B5AE77A509573).

## Haben Sie die internen Bytes oder die Zeitbeschränkungen der Site-Suche/Merchandising überschritten? {#section_AE1BE61A58864FFE81F0BCEED2EBB15D}

Überprüfen Sie im Bildschirm &quot;Vollständiger Indexstatus&quot;, ob Ihr Konto seine Grenze erreicht hat. Wenn der Status meldet, dass Ihr Index größer als erlaubt ist oder dass es länger dauerte als erlaubt, wird Ihre Website nicht vollständig indiziert. Sie können diesen Fehler korrigieren, damit Sie eine angemessene Abdeckung und Anzahl der Webseiten erhalten.

Zum Schutz der Site-Such-/Merchandising-Server gibt es interne Beschränkungen für Bytes und Zeit. Nur wenn durchgekrackte Dateien sehr groß sind oder wenn der Server, auf den Site-Suche/Merchandising versucht, langsam erreicht wird, werden diese Beschränkungen erreicht.

Wenn Sie eine Zeitbegrenzung erreicht haben, stellen Sie sicher, dass Ihr Server online ist, und versuchen Sie den Index zu einem späteren Zeitpunkt erneut. Wenn Sie die maximale Anzahl an Bytes erreichen, überprüfen Sie die durchgecrawenen Dateien, indem Sie Ihr Indexprotokoll anzeigen. Sind sie ungewöhnlich groß? Wenden Sie sich an den technischen Support, wenn eine dieser Meldungen angezeigt wird.
