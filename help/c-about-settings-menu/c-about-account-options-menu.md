---
description: Verwenden Sie das Menü "Kontooptionen", um Ihre Kontoeinstellungen zu aktualisieren, Merchandising-Voreinstellungen festzulegen oder Ihr eigenes Search&amp;Promote-Konto zu entfernen.
solution: Target
subtopic: Account Options
title: Über das Menü "Kontooptionen"
topic-legacy: Settings,Site search and merchandising
uuid: 0f830033-de9e-4197-8d76-906c818662eb
exl-id: 0acaeeed-1649-46bb-af41-20f144400d7c
translation-type: tm+mt
source-git-commit: 7559f5f7437d46e3510d4659772308666425ec96
workflow-type: tm+mt
source-wordcount: '1657'
ht-degree: 2%

---

# Über das Menü &quot;Kontooptionen&quot;{#about-the-account-options-menu}

Über das Menü &quot;Kontooptionen&quot;können Sie Ihre Kontoeinstellungen aktualisieren, Merchandising-Voreinstellungen festlegen oder Ihr eigenes Search&amp;Promote entfernen.

## Konfigurieren der Kontoeinstellungen {#task_80A38D0C8E4F453395BD67B81E4B45D9}

Verwalten Sie Kontoeinstellungen wie den Namen und die Adresse der Website, die Zeitzone und mehr. Oder Ansicht Ihrer Kontonummer.

**So konfigurieren Sie Ihre Kontoeinstellungen**

1. Klicken Sie im Produktmenü auf **[!UICONTROL Settings]** > **[!UICONTROL Account Options]** > **[!UICONTROL Account Settings]**.
1. Legen Sie auf der Seite [!DNL Account Settings] die gewünschten Optionen fest.

   <table> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> <p>Option </p> </th> 
      <th colname="col2" class="entry"> <p>Beschreibung </p> </th> 
      </tr> 
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <p>Website-Name </p> </td> 
      <td colname="col2"> <p>Erforderlich. </p> <p>Ein kurzer Name, der zur Beschreibung Ihrer Website/Ihres Kontos verwendet wird. Diese Option ist nützlich, wenn Sie mehrere Websites haben. </p> <p> <p>Hinweis:  Sie müssen sich an den technischen Support wenden, um einen oder mehrere Namen auszuwählen, die Sie verwenden möchten. </p> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Website-Adresse </p> </td> 
      <td colname="col2"> <p>Erforderlich. </p> <p>Die URL-Adresse Ihrer Website. Die hier angegebene Adresse wird als Einstiegspunkt der Hauptwebsite verwendet. </p> <p>Siehe auch <a href="../c-about-settings-menu/c-about-crawling-menu.md#task_2338A47387D74CFDAC4D4EF4A367ED45" type="task" format="dita" scope="local"> Hinzufügen mehrerer URL-Einstiegspunkte, die indiziert werden sollen </a>. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Zeitzone (für Berichte und Zeitpläne) </p> </td> 
      <td colname="col2"> <p>Die Zeitzone, die für Berichte und Veröffentlichungsvorgänge verwendet wird. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Vorlagen-Tag-Attribute beim Speichern überprüfen </p> </td> 
      <td colname="col2"> <p>Prüft alle Attribute in <span class="codeph"> &lt;guided-*&gt; </span> und <span class="codeph"> &lt;search-*&gt; </span>, wenn Sie eine Vorlage im Staged Template Editor speichern. </p> <p>Siehe <a href="../c-about-design-menu/c-about-templates.md#task_800E0E2265C34C028C92FEB5A1243EC3" type="task" format="dita" scope="local"> Bearbeiten einer Präsentation oder einer Transportvorlage </a>. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Überprüfen von Vorlagenverweisen auf GS-Objekte beim Speichern </p> </td> 
      <td colname="col2"> <p> Überprüft die Existenz von Guided Search-Objekten wie Menüs, Facets, Breadcrumbs, benutzerdefinierten Vars und Vorlagen, die in <span class="codeph"> &lt;guided-*&gt; </span>-Tags referenziert werden. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Strikte Vorlagensyntaxprüfung </p> </td> 
      <td colname="col2"> <p>Macht den Vorlagenvalidator strenger und ermöglicht die Überprüfung von Elementen wie unausgeglichenen Anführungszeichen und &lt;&gt;-Symbolen. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Kontonummer </p> </td> 
      <td colname="col2"> <p>Die Kontonummer kann nicht bearbeitet werden. Es dient nur zur Anzeige. </p> </td> 
      </tr> 
    </tbody> 
    </table>

1. Klicken **[!UICONTROL Save Changes]**.

## Integration mit Adobe CQ5 {#task_EA2FC2C24960498DAE01A1AB769D2F14} konfigurieren

Sie können die Integration von Site-Suche/Merchandising mit Adobe CQ5 konfigurieren.

**So konfigurieren Sie die Integration mit Adobe CQ5**

1. Besorgen Sie sich Ihre Mitglieds-ID und Ihre Konto-ID wie folgt:

   * Melden Sie sich bei Ihrem Site-Konto für Suche/Merchandising an.
   * Kopieren Sie im URL-Pfad die Mitglieds-ID und die Konto-ID.

      Wenn beispielsweise der URL-Pfad zu Ihrem Konto `https://searchandpromote.mycompany.com/px/home/?sp_id=00123a4b-sp1234a5b6` lautet, lautet die Mitglieds-ID `00123a4b` und die Konto-ID `sp1234a5b6`.

1. Verwenden Sie in Adobe CQ5 die Registerkarte &quot;Cloud Services&quot;, um Ihre Konfiguration für die Site-Suche/das Merchandising zu erstellen.

   Verwenden Sie die kopierte Mitglieds-ID und die Konto-ID für die entsprechenden Einstellungen.

## Konfigurieren von Merchandising-Voreinstellungen {#task_7AC7B9F5D9F44E10AB5BC0B8CB31C37A}

Verwalten Sie Merchandising-Voreinstellungen wie den standardmäßigen Rule Builder und den standardmäßigen Suchbegriff.

**So konfigurieren Sie Merchandising-Voreinstellungen**

1. Klicken Sie im Produktmenü auf **[!UICONTROL Settings]** > **[!UICONTROL Account Options]** > **[!UICONTROL Merchandising Preferences]**.
1. Legen Sie auf der Seite [!DNL Merchandising Preferences] die gewünschten Optionen fest.

   <table> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> <p>Option </p> </th> 
      <th colname="col2" class="entry"> <p>Beschreibung </p> </th> 
      </tr> 
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <p>Dominanter Schwellenwert für Trigger </p> </td> 
      <td colname="col2"> <p> Der Schwellenwert-Prozentwert, der auf ergebnisbasierte Trigger angewendet wird, die "Kontostandard verwenden"angeben. </p> <p>Eine Änderung dieser Einstellung kann sofort Auswirkungen auf Live-Suchen haben, daher ist Vorsicht geboten. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Gruppendefinition </p> </td> 
      <td colname="col2"> <p>Die Anzahl der Ergebnisse in einer Gruppe für die Merchandising-Konsole. Der Höchstwert ist 50.000. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p> Feld "Merchandising Dokument ID"(MDI) </p> </td> 
      <td colname="col2"> <p> Das von Ihnen angegebene Feld muss die Suchergebnisse, die Sie mithilfe von ergebnisbasierten Triggern und Aktionen mit einem einzigen Ergebnis bearbeiten möchten, "eindeutig kennzeichnen". </p> <p>Die Verwendung des vordefinierten URL-Felds funktioniert in einigen Fällen, wird jedoch nicht empfohlen. Ein benutzerdefiniertes Metadatenfeld mit einer eindeutigen ID für jede Seite (z. B. SKU oder product_id) wäre viel effizienter als das URL-Feld. Wenn Sie "none"angeben, werden ergebnisbasierte Trigger und Aktionen mit einem einzigen Ergebnis im Regelmanager deaktiviert. Eine Änderung dieser Option gilt nur für Regeln, die in Zukunft gespeichert werden. bestehende Regeln verwenden weiterhin das MDI, mit dem sie ursprünglich gespeichert wurden. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Standard-VRB (Visual Rule Builder)-Suchbegriff </p> </td> 
      <td colname="col2"> <p> Hiermit können Sie den anfänglichen Suchbegriff anpassen, der in Visual Rule Builder verwendet wird. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>VRB-Standardsuche </p> </td> 
      <td colname="col2"> <p>Mit dieser Einstellung können Sie festlegen, welche Standardsuche zunächst in Visual Rule Builder ausgewählt wird. </p> <p> Diese Einstellung ist nur für die Implementierung mit mehreren Suchvorgängen relevant. Mit dem VRB können Sie auswählen, für welche Suche der Trigger oder die Aktion, für die die definierte Gruppe gilt, ausgeführt wird. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>VRB/Simulator-Timeout </p> </td> 
      <td colname="col2"> <p>VRB und Simulator senden Suchvorgänge über einen Proxyserver, die langsamer als Ihre Produktionssuche sind. Unter bestimmten Umständen, wie z. B. dem langsamen Laden von Assets, kann der VRB oder Simulator ein Timeout ausführen. Sie können die Anzahl der Sekunden erhöhen oder verringern, die die Benutzeroberfläche warten muss, bevor sie beendet wird. Sie müssen diese Einstellung selten von der Standardeinstellung 60 erhöhen. </p> </td> 
      </tr> 
    </tbody> 
    </table>

1. Klicken **[!UICONTROL Save Changes]**.

## Zugriff auf Ihr Dynamic Media Classic-Konto für die Adobe {#task_CEFF88C2033D41D0B2FE86C435EDAC6D} konfigurieren

Verknüpfen Sie Ihr Site-Such-/Merchandising-Konto mit der Adobe Dynamic Media Classic, damit Sie mit hochgeladenen digitalen Assets aus Adobe Scene7 einfach Banneranzeigen zu Ihrer Website hinzufügen können.

Siehe [Info zu Bannern](../c-about-design-menu/c-about-banners.md#concept_5BBE01FEC6134393B43CC917C8CC64DA).

Siehe [Hinzufügen eines Banners mit der Adobe Dynamic Media Classic](../c-about-design-menu/c-about-banners.md#task_AD1E0C00A9E04B1FA819EB93288786B3).

**So konfigurieren Sie den Zugriff auf Ihr Adobe Dynamic Media Classic-Konto**

1. Klicken Sie im Produktmenü auf **[!UICONTROL Settings]** > **[!UICONTROL Account Options]** > **[!UICONTROL Scene7 Configuration]**.
1. Legen Sie auf der Seite [!DNL Scene7 Configuration] die gewünschten Optionen fest.

   <table> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> <p>Option </p> </th> 
      <th colname="col2" class="entry"> <p>Beschreibung </p> </th> 
      </tr> 
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <p>Region </p> </td> 
      <td colname="col2"> <p>Erforderlich. Identifiziert die Region, in der Ihr Dynamic Media Classic-Konto auf die verschiedenen Dynamic Media Classic-Server zugreift. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Standardmäßige Firma </p> </td> 
      <td colname="col2"> <p>Identifiziert den Namen der Firma, die mit Ihrem Dynamic Media Classic-Konto verknüpft ist. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p> E-Mail </p> </td> 
      <td colname="col2"> <p>Erforderlich. Identifiziert Ihre E-Mail-Adresse, die für die Anmeldung und Kommunikation bei Dynamic Media Classic verwendet wird. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Passwort </p> </td> 
      <td colname="col2"> <p>Erforderlich. Ihr Dynamic Media Classic-Anmeldekennwort. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Aktiviert </p> </td> 
      <td colname="col2"> <p>Aktiviert alle Dynamic Media Classic-Steuerelemente in Site-Suche/Merchandising. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Test </p> </td> 
      <td colname="col2"> <p>Vergewissert sich, dass der Name, die E-Mail-Adresse und das Kennwort für Ihre Dynamic Media Classic-Region korrekt sind. </p> </td> 
      </tr> 
    </tbody> 
    </table>

1. (Optional) Klicken Sie auf **[!UICONTROL Test]**, um sicherzustellen, dass Ihr Dynamic Media Classic-Regionenname, Ihre E-Mail-Adresse und Ihr Kennwort korrekt sind.
1. Klicken **[!UICONTROL Save Changes]**.

## Adobe Analytics-Weiterleitung konfigurieren {#task_2C9DE333FD7246E4A460FC0F55204160}

Wenn Sie [!DNL Adobe Analytics] zur Verfolgung von Site-Besuchern verwenden, können Sie [!DNL Adobe Analytics Redirector] in Site-Suche/Merchandising verwenden, um alle HTTP-Umleitungen mit [!DNL Adobe Analytics] zu verfolgen.

**So konfigurieren Sie die Adobe Analytics-Weiterleitung**

1. Klicken Sie im Produktmenü auf **[!UICONTROL Settings]** > **[!UICONTROL Account Options]** > **[!UICONTROL Adobe Analytics Redirector]**.
1. Legen Sie auf der Seite [!DNL Adobe Analytics Redirector] die gewünschten Optionen fest.

   <table> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> <p>Option </p> </th> 
      <th colname="col2" class="entry"> <p>Beschreibung </p> </th> 
      </tr> 
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <p>Adobe Analytics-Weiterleitungsfunktion aktivieren </p> </td> 
      <td colname="col2"> <p>Aktiviert die Verfolgung von HTTP-Weiterleitungen mit Adobe Analytics. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Tracking-Server </p> </td> 
      <td colname="col2"> <p> Identifiziert den Namen Ihres Adobe Analytics-Tracking-Servers. </p> <p>Um den Namen des Tracking-Servers herauszufinden, </p> <p> 
      <ol id="ol_D17B77E81F8D40D0948415CD60839BE3"> 
      <li id="li_BE58DBA104D44F0DB6C64AD3F12CEA97"> Klicken Sie in Adobe Analytics auf <span class="uicontrol"> Admin </span> &gt; <span class="uicontrol"> Admin Console </span> &gt; <span class="uicontrol"> Code-Manager </span>. </li> 
      <li id="li_67A93D17C3A14874928C6DC4FF2D4784"> Wählen Sie im Gruppenfeld <span class="wintitle"> Optionen </span> eine Report Suite aus der entsprechenden Dropdown-Liste aus. </li> 
      <li id="li_5AAB004AC58441DBB0F813BDE30EFFD4"> Klicken Sie auf <span class="uicontrol">„Code generieren“</span>.  </li> 
      <li id="li_E80368993F4D4DD69E37509FF4348B36"> Klicken Sie auf der Seite <span class="wintitle"> Code-Manager </span> auf die Registerkarte <span class="uicontrol"> Core-JavaScript-Datei </span>. </li> 
      <li id="li_991BDCDDA41A445F85CEEAAE9A46A304"> Suchen Sie in <span class="wintitle"> Config Section </span> die Zeile, die wie folgt aussieht: <p> <code> s.trackingServer="yourcompany.122.2o7.net" </code> </p> <p>Der Name des Tracking-Servers lautet in diesem Fall <span class="codeph"> "yourcompany.122.2o7.net" </span> </p> </li> 
      </ol> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Report Suite-ID </p> </td> 
      <td colname="col2"> <p> Identifiziert Ihre Report Suite-ID. </p> <p>Um Ihre Report Suite-ID herauszufinden, </p> <p> 
      <ol id="ol_4FD7B2459358486DBDB130426131D16A"> 
      <li id="li_9AF624CEB128453C808892EEE385D5D1"> Klicken Sie in Adobe Analytics auf <span class="uicontrol"> Admin </span> &gt; <span class="uicontrol"> Admin Console </span> &gt; <span class="uicontrol"> Report Suites </span>. </li> 
      <li id="li_AAC47EAA04144A67BDCB5C7B8D8098E9"> Suchen Sie in der Tabelle nach der ID in der Spalte <span class="wintitle"> Report Suite-ID </span>. </li> 
      </ol> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Benutzerdefinierte Parameter </p> </td> 
      <td colname="col2"> <p>Ermöglicht das Hinzufügen benutzerdefinierter Parameter zur Adobe Analytics-Umleitungs-URL. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Legen Sie die Groß-/Kleinschreibung für alle benutzerdefinierten Werte fest auf </p> </td> 
      <td colname="col2"> <p>Ermöglicht die Standardisierung auf das Gehäuse, das für benutzerdefinierte Parameterwerte verwendet wird, die Sie oben angegeben haben. Adobe Analytics unterscheidet zwischen Groß- und Kleinschreibung, sodass es einen Grund gibt, die Groß- und Kleinschreibung von Werten zu vereinheitlichen. </p> </td> 
      </tr> 
    </tbody> 
    </table>

1. Klicken **[!UICONTROL Save Changes]**.
1. (Optional) Erstellen Sie Ihren Stage-Site-Index neu, wenn Sie die Vorschauen durchführen möchten.

   Siehe [Konfigurieren eines inkrementellen Indexes einer gestaffelten Website](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0).
1. (Optional) Führen Sie auf der Seite [!DNL Adobe Analytics Redirector] einen der folgenden Schritte aus:

   * Klicken **[!UICONTROL Live]**.

      Siehe [Live-Einstellungen anzeigen](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Klicken **[!UICONTROL Push Live]**.

      Siehe [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Konfigurieren von Stammdateien {#task_5F175C8743FB49A2A003813CBF7C56BF}

Verwalten Sie Stammdateien im Stammordner Ihrer Website.

**So konfigurieren Sie Stammdateien**

1. Klicken Sie im Produktmenü auf **[!UICONTROL Settings]** > **[!UICONTROL Account Options]** > **[!UICONTROL Root Files]**.
1. Navigieren Sie auf der Seite [!DNL Root Files] zu den Stammdateien, die Sie hochladen möchten.

   <table> 
    <thead> 
    <tr> 
      <th colname="col1" class="entry"> <p>Stammdatei </p> </th> 
      <th colname="col2" class="entry"> <p>Beschreibung </p> </th> 
    </tr> 
    </thead>
    <tbody> 
    <tr> 
      <td colname="col1"> <p>favicon.ico </p> </td> 
      <td colname="col2"> <p> Das Symbol der Site. Normalerweise wird sie in der Adressleiste des Browsers des Kunden angezeigt. </p> </td> 
    </tr> 
    <tr> 
      <td colname="col1"> <p>robots.txt </p> </td> 
      <td colname="col2"> <p>Ermöglicht oder deaktiviert den Zugriff von Bots auf bestimmte Teile der Website. </p> </td> 
    </tr> 
    <tr> 
      <td colname="col1"> <p>sitemap.xml </p> </td> 
      <td colname="col2"> <p>Die XML-Datei mit einer Liste aller auf der Website verfügbaren Seiten. </p> </td> 
    </tr> 
    <tr> 
      <td colname="col1"> <p>crossdomain.xml </p> </td> 
      <td colname="col2"> <p>Ermöglicht oder deaktiviert Flash Playern den domänenübergreifenden Zugriff auf Dateien. </p> </td> 
    </tr> 
    </tbody> 
    </table>

1. Klicken **[!UICONTROL Save Changes]**.
1. (Optional) Erstellen Sie Ihren Stage-Site-Index neu, wenn Sie die Vorschauen durchführen möchten.

   Siehe [Konfigurieren eines inkrementellen Indexes einer gestaffelten Website](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0).
1. (Optional) Führen Sie auf der Seite [!DNL Root Files] einen der folgenden Schritte aus:

   * Klicken **[!UICONTROL Live]**.

      Siehe [Live-Einstellungen anzeigen](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Klicken **[!UICONTROL Push Live]**.

      Siehe [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Übertragung des Kontoeigentums an einen anderen Kontobenutzer {#task_47E3C66CC6374274830DA10171E0CF17}

Wenn Sie als Kontoinhaber Ihre Anmeldung stornieren möchten, müssen Sie zunächst das Eigentum an einen anderen aktiven Kontobenutzer übertragen. Sie können [!DNL Transfer Ownership] verwenden, um diese Aufgabe durchzuführen.

Sie können die Eigentumsrechte an einem vorhandenen Site-Konto für Suche/Merchandising-Benutzer übertragen.

Nach Abschluss der Eigentumsübertragung erhält der neue Kontoinhaber eine E-Mail-Benachrichtigung und der ehemalige Eigentümer wird von den Beschränkungen und Verantwortlichkeiten dieser Position befreit.

Es kann nur einen Inhaber pro Konto geben. Wenn Sie Ihr Eigentum an einen anderen Benutzer übertragen, haben Sie keine Eigentumsrechte mehr.

Siehe [Anmeldung abbrechen](../c-about-settings-menu/c-about-my-profile-menu.md#task_D57701BB726243B08CEA14EEC86C3087).

Siehe [Entfernen eines Kontos](../c-about-settings-menu/c-about-account-options-menu.md#task_975178D5B9444BF8B52D72B897A49C32).

Siehe [Selbstentnahme aus einem Konto](../c-about-settings-menu/c-about-account-options-menu.md#task_C56F5AB87B664BAAAC2FD2F15003E73F).

**So übertragen Sie das Kontoeigentum auf ein anderes Konto**

1. Klicken Sie im Produktmenü auf **[!UICONTROL Settings]** > **[!UICONTROL Account Options]** > **[!UICONTROL Transfer Ownership]**.
1. Klicken Sie auf der Seite [!DNL Transfer Ownership] auf den Benutzer, für den Sie das Eigentum an Ihrem Konto übernehmen möchten.
1. Klicken **[!UICONTROL Transfer]**.

## Entfernen eines Kontos {#task_975178D5B9444BF8B52D72B897A49C32}

Sie können ein Konto vollständig aus der Site-Suche/dem Merchandising entfernen. Wenn Sie dies tun, haben Sie und andere Benutzer Ihres Kontos keinen Zugriff mehr darauf.

Wenn Sie Ihr Konto entfernen, kann es nicht mehr zur Indexierung oder Suche Ihrer Live-Site verwendet werden. Außerdem

Damit andere Benutzer dieses Konto weiterhin verwenden können, können Sie das Eigentum an einen anderen Benutzer übertragen und sich dann selbst als Benutzer des Kontos entfernen.

Siehe [Übertragen des Kontoeigentums an einen anderen Kontobenutzer](../c-about-settings-menu/c-about-account-options-menu.md#task_47E3C66CC6374274830DA10171E0CF17).

Wenn Sie andere Konten haben, werden Sie nach dem Entfernen des aktuellen Kontos zum ersten Konto geleitet, das in Ihrer Anmeldung aufgeführt ist.

Siehe [Selbstentnahme aus einem Konto](../c-about-settings-menu/c-about-account-options-menu.md#task_C56F5AB87B664BAAAC2FD2F15003E73F).

Siehe [Anmeldung abbrechen](../c-about-settings-menu/c-about-my-profile-menu.md#task_D57701BB726243B08CEA14EEC86C3087).

**So entfernen Sie ein Konto**

1. Klicken Sie im Produktmenü auf **[!UICONTROL Settings]** > **[!UICONTROL Account Options]** > **[!UICONTROL Remove Account]**.
1. (Optional) Geben Sie im Feld [!DNL Reason for Removal] einen Grund für die Kontoentfernung ein.
1. Klicken **[!UICONTROL Remove Account]**.

## Entfernen Sie sich selbst aus einem Konto {#task_C56F5AB87B664BAAAC2FD2F15003E73F}

Sie können sich selbst aus einem Site-Such-/Merchandising-Konto entfernen.

Wenn Sie sich selbst aus einem Konto entfernen, können Sie nicht mehr darauf zugreifen, und Sie können Ihre Kontoeinstellungen nicht bearbeiten oder Ihre Site damit indizieren.

Um wieder Zugriff auf das Konto zu erhalten, bitten Sie einen aktuellen Kontobenutzer, Sie erneut zu installieren.

Siehe [Anmeldung abbrechen](../c-about-settings-menu/c-about-my-profile-menu.md#task_D57701BB726243B08CEA14EEC86C3087).

Siehe [Entfernen eines Kontos](../c-about-settings-menu/c-about-account-options-menu.md#task_975178D5B9444BF8B52D72B897A49C32).

Siehe [Übertragen des Kontoeigentums an einen anderen Kontobenutzer](../c-about-settings-menu/c-about-account-options-menu.md#task_47E3C66CC6374274830DA10171E0CF17).

**So entfernen Sie sich aus einem Konto**

1. Klicken Sie im Produktmenü auf **[!UICONTROL Settings]** > **[!UICONTROL Account Options]** > **[!UICONTROL Remove Yourself]**.
1. Klicken **[!UICONTROL Remove Yourself]**.
