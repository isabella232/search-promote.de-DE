---
description: Verwenden Sie die Abfrage-Bereinigungsregeln, um die eingehende Abfrage zu analysieren und zu ändern.
solution: Target
title: Grundlagen zu Abfragen-Bereinigungsregeln
topic-legacy: Rules,Site search and merchandising
uuid: 683af81f-f7c0-45f8-9212-e5e7cb82ccca
exl-id: 22ebca58-7687-4c8c-9ac1-bacb321065f3
translation-type: tm+mt
source-git-commit: 7559f5f7437d46e3510d4659772308666425ec96
workflow-type: tm+mt
source-wordcount: '1596'
ht-degree: 1%

---

# Info zu Abfragen-Bereinigungsregeln{#about-query-cleaning-rules}

Verwenden Sie die Abfrage-Bereinigungsregeln, um die eingehende Abfrage zu analysieren und zu ändern.

## Verwenden von Abfrage-Bereinigungsregeln {#concept_17F3CDDC3C8A4128AF092A82B777B86C}

Diese Funktion wird häufig verwendet, wenn Sie das Verhalten der Site-Suche/des Merchandising ändern möchten. Sie können beispielsweise eine leere Suche in einen beliebten Suchbegriff statt in eine &quot;*&quot;-Suche ändern und so ein beliebtes Produkt bewerben. Sie können auch Abfragen-Reinigungsregeln verwenden, um einen direkten Treffer auszuführen, bei dem Sie zu einer URL umleiten. Dies kann besonders nützlich sein, wenn Sie feststellen, dass jemand nach einer Produkt-SKU sucht und Sie die Suche überspringen und zu der Produktseite umleiten möchten. Die Abfrage-Bereinigung kann auch die Abfrage mindern und benutzerdefinierte Variablen festlegen, die in späteren Verarbeitungsablaufschritten verwendet werden können. Abfrage-Reinigungsregeln werden für jede Abfrage nacheinander ausgeführt. Um die Reihenfolge der Regeln zu ändern, können Sie per Drag &amp; Drop die Regeln verschieben. Die tatsächliche Bestellung wird erst nach dem Speichern geändert.

Die Abfrage-Reinigungsregeln in einem Abfrage-Reinigungsmodul werden geprüft, um festzustellen, ob ein Parameter der Abfrage geändert werden muss oder ob benutzerspezifische Variablen festgelegt werden müssen. Jede Abfrage-Reinigungsregel besteht aus zwei Hauptelementen: die Aktionen und optionalen Bedingungen der Regel. Es kann eine unbegrenzte Anzahl von Regeln und Bedingungen angegeben werden. Die Reihenfolge dieser Regeln ist wichtig, da Site-Suche/Merchandising die Regel für Regel durchlaufen. Wenn die Bedingungen einer Regel übereinstimmen, werden alle zugehörigen Aktionen ausgeführt.

Nach Abschluss der Abfrage-Reinigung werden die resultierenden CGI-Parameter verwendet. Alle benutzerspezifischen Variablen, die festgelegt wurden, stehen für spätere Phasen des Verarbeitungsablaufs zur Verfügung. Standardmäßig entfernt das System automatisch den Leerraum am Anfang und am Ende der Abfrage.

## Informationen zu Abfragen-Bereinigungsbedingungen {#section_BF6F25F94FED4DDEA8600D921EA43A66}

Bedingungen sind optional. Wenn Sie entscheiden, dass Aktionen für jede Abfrage festgelegt werden, werden die Aktionen immer ausgeführt. Die Bedingungen können auf einem beliebigen CGI-Abfrage-Parameter, einem vorhandenen Cookie oder einer benutzerspezifischen Variablen basieren, die eine vorherige Regel festgelegt hat. Es gilt als &quot;Best Practice&quot;, wenn die erste Abfrage-Bereinigungsregel für jede Abfrage ausgeführt wird, in der alle benutzerspezifischen Variablen, die Sie verwenden möchten, definiert und initialisiert werden.

## Informationen zu Abfragen-Bereinigungsaktionen {#section_78F74A9B48DE484191CDA95F5B4E7154}

Alle Aktionen innerhalb einer Abfrage-Bereinigungsregel, für die entsprechende Bedingungen gelten, werden ausgeführt. Aktionen bestehen in der Regel aus einem Vorgang, den Daten, auf denen der Vorgang ausgeführt werden soll, und dem zu verwendenden Wert.

Siehe die Tabelle der Optionen unter [Hinzufügen einer Abfrage-Reinigungsregel](../c-about-rules-menu/c-about-query-cleaning-rules.md#task_47F43988D3D9485F8AE1DFDA7E00BF54).

## Über Umleitungen {#section_597481E6194440C0A7B9E6FC901A81C0}

Auf der Oberfläche &quot;Direct-Hits&quot;können Sie einen Satz von Weiterleitungen definieren, die auf dem Begriff der eingehenden Abfrage basieren. Umleitungen innerhalb der Abfrage-Reinigung erweitern diese Idee. Bei Umleitungen erhalten Sie jedoch eine genauere Granularität bei Umleitungen, indem Sie Bedingungen festlegen, und können zu einer dynamischen URL statt zu einer statischen URL umgeleitet werden. Wenn Sie die Umleitungsaktion auswählen, wird die Zeile aktualisiert und enthält ein Textfeld, in dem Sie die URL angeben, zu der Sie umleiten möchten. In der URL können Sie Variablen oder Parameter angeben, die Sie ersetzen möchten, indem Sie sie in geschweifte Klammern der Dublette einschließen. Benutzerspezifische Variablen haben bei der Substitution eine höhere Priorität als CGI-Parameter.

## Beispiele {#section_DB5047CC38FB4A57B15CAAF9848073E3}

Angenommen, Sie haben einen Bekleidungseinzelhandel mit einer Website. Wenn der Benutzer ohne Suchbegriffe auf Suchen klickt, möchten Sie eine Suche nach Jeans zurückgeben, denn dafür sind Sie international bekannt. Sie möchten den Begriff &quot;Abfrage&quot;auch nach Geschlecht analysieren, damit Sie später eine Vorsuchregel erstellen können, die auf der benutzerspezifischen Variablen basiert, die für jedes Geschlecht eine andere Präsentationsvorlage verwendet.

```
On condition: 
  query q equal 
Perform the following actions: 
  Set query parameter q to value jeans 
 
On condition: 
  Query q matches regular expression wom[e|a]n[s]|girl[s] 
Perform the following actions: 
  Add custom variable gender 
  Set custom variable gender to value female 
 
On condition: 
  Query q matches regular expression men[s]|boy[s] 
Perform the following actions: 
  Add custom variable gender 
  Set custom variable gender to value male
```

MegaElectronic ist ein großer Elektronikladen. MegaElectronic hat bei der Analyse ihrer Suchdaten festgestellt, dass viele ihrer versierten Kunden oft nach einem Produkt suchen, das die SKU des Produkts verwendet, anstatt ein Suchergebnis für das einzelne Produkt zurückzugeben, möchte MegaElectronic zu der mit dieser SKU verbundenen Webseite umleiten.

```
On condition: 
  query q matches regular expression ^\D\D\D-\d\d\d\d$ 
Perform the following actions: 
  redirect to https://www.megaelectronic.com/?sku={{q}}
```

## Hinzufügen einer Abfrage-Reinigungsregel {#task_47F43988D3D9485F8AE1DFDA7E00BF54}

Sie können Regeln definieren, die die eingehende Abfrage eines Kunden bereinigen oder bearbeiten.

Sie können nur Vorlagen auswählen, die derzeit vorhanden sind. Wenn Sie keine Vorlagen haben, müssen Sie diese zunächst definieren.

Siehe [Vorlagen](../c-about-design-menu/c-about-templates.md#concept_06EB481B14864E18A8AE2BCD1D6EF0B5).

**So fügen Sie eine Abfrage-Reinigungsregel hinzu**

1. Klicken Sie im Produktmenü auf **[!UICONTROL Rules]** > **[!UICONTROL Query Cleaning]**.
1. Klicken Sie auf der Seite [!DNL Query Cleaning Rules] auf **[!UICONTROL Add New Rule]**.
1. Geben Sie im Feld [!DNL Name] den Namen der neuen Abfrage-Reinigungsregel ein.
1. Verwenden Sie auf der Seite [!DNL Add Query Cleaning Rule] die Dropdown-Listen und Textfelder, um Ihre Abfrage zu erstellen.

   <table> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> <p>Option </p> </th> 
      <th colname="col2" class="entry"> <p>Beschreibung </p> </th> 
      </tr> 
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <p>Cookie </p> </td> 
      <td colname="col2"> <p>Ein HTTP-Cookie. Sie können Bedingungen auf der Grundlage von Cookies definieren, die Ihrer Domäne zugeordnet sind. Oder Sie können ein Cookie setzen, das mit ausgehenden Suchergebnissen geschrieben wird. Cookie-Name und -Werte müssen mit der Uniform Resource Identifier-Kodierung versehen sein. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Benutzerdefinierte Variable </p> </td> 
      <td colname="col2"> <p>Eine benutzerdefinierte Variable. hinzufügen, löschen oder legen Sie eine unbegrenzte Anzahl benutzerdefinierter Variablen fest. Sie können hier auf alle benutzerdefinierten Variablen in den Regeln vor der Suche und nach der Suche verweisen. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Systemvariable </p> </td> 
      <td colname="col2"> <p>Schreibgeschützte Variablen, die vom internen System festgelegt wurden, das Sie überprüfen können. Die folgenden Systemvariablen werden unterstützt: </p> <p> 
        <ul id="ul_BC17F1637F27424CA4E8F530C28A3245"> 
          <li id="li_C7DF96EFD7AA4A449D00F7EACCAA0EB1"> <span class="uicontrol"> hostname </span> <p>Der Name des Serverhosts. </p> </li> 
          <li id="li_F85AB1D2B9374A859657D12B8ED6674B"> <span class="uicontrol"> URI </span> <p>Die angeforderte URL ohne Abfrage-Zeichenfolge. </p> </li> 
          <li id="li_440149C9EC6E4805B77BBC97BE41542A"> <span class="uicontrol"> args  </span> <p>Die gesamte Abfrage-Zeichenfolge. </p> </li> 
          <li id="li_F583FC4B0E404858BB3522B33A6F7A0A"> <span class="uicontrol"> Umgebung </span> <p>"Stage"oder "live"hängt davon ab, ob die eingehende Abfrage an Ihre inszenierte oder Live-Umgebung gesendet wurde. </p> </li> 
          <li id="li_15902AA49B144D42A5E95D7E8B0FB1E1"> <span class="uicontrol"> referrer </span> <p>Die URL, von der der Kunde kam. </p> </li> 
          <li id="li_6FEE352DB7A842FCB2EBE1398AD03666"> <span class="uicontrol"> user agent  </span> <p>Die Zeichenfolge "user-agent"im Browser des Kunden. </p> </li> 
        </ul> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Abfrageparameter </p> </td> 
      <td colname="col2"> <p>An die Abfrage übergebene CGI-Parameter. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Backend-Parameter </p> </td> 
      <td colname="col2"> <p>Eingehende Abfrage-Parameter werden schließlich in Backend-Parameter übersetzt, die zur Durchführung der Suche verwendet werden. </p> <p>Siehe <a href="../c-appendices/c-cgiparameters.md#reference_582E85C3886740C98FE88CA9DF7918E8" type="reference" format="dita" scope="local"> CGI-Parameter für die Backend-Suche </a>. </p> <p>Backend-Parameter werden bei Navigationselementen nicht angezeigt. Daher können Sie zusätzliche Parameter, die Sie auf eine Suche anwenden möchten, von Ihren Kunden ausblenden. Aktionen für Backend-Parameter sind verspätet zu binden. d. h. sie werden unmittelbar vor dem Senden der Suche angewendet. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Facette </p> </td> 
      <td colname="col2"> <p>Spezielle CGI-Parameter, die mit einer bestimmten Facette verknüpft sind. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Rang </p> </td> 
      <td colname="col2"> <p>Hier können Sie angeben, welche Rangregel bei der Suche verwendet werden soll. Diese Option wird nur angezeigt, wenn Sie bestimmte Rangfelder und Rangregeln definiert haben. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Speicher </p> </td> 
      <td colname="col2"> <p>Die Suchmaschine erkennt automatisch, in welchem Speicher sich der Benutzer befindet, basierend auf dem Hostnamen oder dem <span class="codeph"> gs_store </span> Abfrage-Parameter, wobei letztere Vorrang haben. Sie können Bedingungen aus dem Store erstellen. Bei der Reinigung der Abfrage können Sie auch eine Aktion verwenden, um den aktuellen Store zu überschreiben. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Letzte Regel </p> </td> 
      <td colname="col2"> <p>Wenn die Bedingungen für eine Regel erfüllt sind, für die der letzte Regelsatz festgelegt wurde, führt das Verarbeitungsmodul für die Abfrage-Bereinigung nach der Aktion der Übereinstimmungsregel keine weiteren  durch. Dies ist nützlich, wenn Sie Aktionen festgelegt haben, die dazu führen, dass eine spätere Regel übereinstimmt, die später verwendete Regel jedoch nicht ausgelöst werden soll. Beachten Sie, dass die Umleitung, wenn die Aktion einer Regel eine Umleitung durchführen soll, sofort erfolgt, sodass sie im Wesentlichen so wirkt, als ob die letzte Regel festgelegt wäre. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Aussetzen </p> </td> 
      <td colname="col2"> <p>Deaktiviert die Ausführung der Regel, löscht jedoch nicht die Regel. </p> </td> 
      </tr> 
    </tbody> 
    </table>

1. Klicken **[!UICONTROL Add]**.
1. (Optional) Führen Sie einen der folgenden Schritte aus:

   * Klicken Sie auf **[!UICONTROL History]**, um alle vorgenommenen Änderungen wiederherzustellen.

      Siehe [Verwenden der Option Verlauf](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Klicken **[!UICONTROL Live]**.

      Siehe [Live-Einstellungen anzeigen](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Klicken **[!UICONTROL Push Live]**.

      Siehe [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Bearbeiten einer Abfrage-Reinigungsregel {#task_FA2FF1A7E2634350AD703485CBC27CB3}

Sie können vorhandene Abfragen-Reinigungsregeln bearbeiten, die Sie der Seite &quot;Abfrage-Reinigungsregeln&quot;hinzugefügt haben.

**So bearbeiten Sie eine Abfragen-Reinigungsregel**

1. Klicken Sie im Produktmenü auf **[!UICONTROL Rules]** > **[!UICONTROL Query Cleaning]**.
1. Klicken Sie auf der Seite [!DNL Query Cleaning Rules] unter der Spalte **[!UICONTROL Actions]** der Tabelle für die zugehörige Regel, die Sie bearbeiten möchten, auf **[!UICONTROL Edit]**.
1. Verwenden Sie auf der Seite [!DNL Edit Query Cleaning Rule] die Dropdown-Listen und Textfelder, um Ihre Abfrage zu erstellen.

   Siehe die Tabelle der Optionen unter [Hinzufügen einer Abfrage-Reinigungsregel](../c-about-rules-menu/c-about-query-cleaning-rules.md#task_47F43988D3D9485F8AE1DFDA7E00BF54).
1. Klicken **[!UICONTROL Save Changes]**.
1. (Optional) Führen Sie einen der folgenden Schritte aus:

   * Klicken Sie auf **[!UICONTROL History]**, um alle vorgenommenen Änderungen wiederherzustellen.

      Siehe [Verwenden der Option Verlauf](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Klicken **[!UICONTROL Live]**.

      Siehe [Live-Einstellungen anzeigen](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Klicken **[!UICONTROL Push Live]**.

      Siehe [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Löschen einer Abfrage-Reinigungsregel {#task_C52D17226B824590B087CAB6970CBB01}

Sie können Abfragen löschen, die Sie nicht mehr benötigen oder verwenden.

Wenn Sie eine Regel löschen, wird die Reihenfolge, in der die verbleibenden Regeln ausgeführt werden, automatisch angepasst, um den Löschvorgang zu berücksichtigen.

**So löschen Sie eine Abfragen-Reinigungsregel**

1. Klicken Sie im Produktmenü auf **[!UICONTROL Rules]** > **[!UICONTROL Query Cleaning]**.
1. Klicken Sie auf der Seite [!DNL Query Cleaning Rules] unter der Spalte **[!UICONTROL Actions]** der Tabelle für die zugehörige Regel, die Sie löschen möchten, auf **[!UICONTROL Delete]**.
1. Klicken Sie im Dialogfeld [!DNL Confirmation] auf **[!UICONTROL OK]**.
1. (Optional) Führen Sie einen der folgenden Schritte aus:

   * Klicken Sie auf **[!UICONTROL History]**, um alle vorgenommenen Änderungen wiederherzustellen.

      Siehe [Verwenden der Option Verlauf](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Klicken **[!UICONTROL Live]**.

      Siehe [Live-Einstellungen anzeigen](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Klicken **[!UICONTROL Push Live]**.

      Siehe [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Ändern der Reihenfolge, in der Abfrage-Reinigungsregeln ausgeführt werden{#task_C24012C45A4445468A7FD998017388CA}

Sie können die Abfragen-Reinigungsregeln neu anordnen, um die Reihenfolge zu ändern, in der sie in Präsentationsvorlagen ausgeführt werden.

Abfragen-Reinigungsregeln werden in der Reihenfolge ausgeführt, in der sie definiert wurden. Je höher die Ordnungsnummer einer Regel ist, desto später wird sie im Prozess ausgeführt, wodurch frühere Regeln übertroffen werden. Sie können Regeln neu anordnen, indem Sie auf der Seite [!DNL Query Cleaning Rules] in die Spalte Reihenfolge der Tabelle eine neue Zahl eingeben. Sie können die Ausführungsreihenfolge auch per Drag &amp; Drop ändern.

**So ändern Sie die Reihenfolge, in der Abfrage-Reinigungsregeln ausgeführt werden**

1. Klicken Sie im Produktmenü auf **[!UICONTROL Rules]** > **[!UICONTROL Query Cleaning]**.
1. Führen Sie auf der Seite [!DNL Query Cleaning Rules] einen der folgenden Schritte aus:

   * Klicken Sie auf die Spaltenüberschrift [!DNL Order], um die Regeln in auf- oder absteigender Reihenfolge zu sortieren.
   * Geben Sie in der Spalte [!DNL Order] im Textfeld links neben dem Regelnamen für die Abfrage die Ordnungsnummer ein, die ausgeführt werden soll.
   * Ziehen Sie eine Tabellenzeile an die gewünschte Position. Alle Bestellnummern werden aktualisiert, um die neue Reihenfolge zu widerspiegeln, in der die Regeln ausgeführt werden.

1. Klicken **[!UICONTROL Save Changes]**.
1. (Optional) Führen Sie einen der folgenden Schritte aus:

   * Klicken Sie auf **[!UICONTROL History]**, um alle vorgenommenen Änderungen wiederherzustellen.

      Siehe [Verwenden der Option Verlauf](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Klicken **[!UICONTROL Live]**.

      Siehe [Live-Einstellungen anzeigen](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Klicken **[!UICONTROL Push Live]**.

      Siehe [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).
