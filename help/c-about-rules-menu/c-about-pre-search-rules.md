---
description: Verwenden Sie Vorab-Suchregeln, um die eingehende Abfrage zu analysieren und zu bestimmen, welche Präsentationsvorlage verwendet werden soll. Vorsuchregeln werden für jede Abfrage nacheinander ausgeführt. Um die Reihenfolge der Regeln zu ändern, können Sie per Drag & Drop die Regeln verschieben. Die tatsächliche Reihenfolge wird erst nach dem Speichern geändert.
solution: Target
title: Vorab-Suchregeln
topic: Regeln, Site-Suche und Merchandising
uuid: e75f9d9e-e8ca-4184-bf79-b1fdadb5c0fe
translation-type: tm+mt
source-git-commit: d015154efdccbb4c6a39a56907c0c337ec065c9f
workflow-type: tm+mt
source-wordcount: '1666'
ht-degree: 1%

---


# Info zu Regeln vor der Suche{#about-pre-search-rules}

Verwenden Sie Vorab-Suchregeln, um die eingehende Abfrage zu analysieren und zu bestimmen, welche Präsentationsvorlage verwendet werden soll. Vorsuchregeln werden für jede Abfrage nacheinander ausgeführt. Um die Reihenfolge der Regeln zu ändern, können Sie per Drag &amp; Drop die Regeln verschieben. Die tatsächliche Reihenfolge wird erst nach dem Speichern geändert.

## Verwenden von Vorsuchregeln {#concept_5BF84BB6FACB4645BA9CB7496A01CD1F}

Vorsuchregeln werden normalerweise verwendet, um auszuwählen, welche Präsentationsvorlage die Ergebnisse basierend auf der eingehenden Abfrage anzeigt. Erweiterte Funktionen können verwendet werden, um die Abfrage zu ändern, die für eine Suche verwendet wird, die für eine Präsentationsvorlage durchgeführt wird. Sie können den Wert der Parameter für die Abfrage nach Bedarf hinzufügen, löschen oder ändern. Für jede eingehende Abfrage untersucht ein Vorsuchverarbeitungsmodul die Vorsuchregeln, um festzustellen, ob die Abfrage geändert wurde und welche Präsentationsvorlage verwendet wird. Jede Vorsuchregel besteht aus zwei Hauptelementen: die Aktionen und optionalen Bedingungen der Regel. Sie können eine unbegrenzte Anzahl von Regeln und Bedingungen angeben. Die Reihenfolge dieser Regeln ist wichtig, da der Regelsatz von Regel zu Regel durchlaufen wird. Wenn die Bedingungen einer Regel übereinstimmen, werden alle zugehörigen Aktionen ausgeführt.

Im Vorsuchverarbeitungsmodul werden alle definierten Vorlagen und die zugehörigen benannten Suchvorgänge instanziiert, wobei jeder Suche eine lokale Kopie der cgi-Parameter zugewiesen wird. Daher können Sie eine Suche anpassen, indem Sie einen der cgi-Parameter, die von der Suche verwendet werden, hinzufügen, löschen oder ändern, ohne eine andere benannte Suche zu ändern, die von der Vorlage verwendet wird oder die andere Vorlagen betrifft. Wenn Sie also über eine Präsentationsvorlage verfügen, die mehr als einen Ergebnissatz anzeigt, können Sie jede Suche einzeln anpassen. Wenn Sie Änderungen an den globalen CGI-Parametern vornehmen möchten, bevor sie für jede Suche nach einer Vorlage kopiert werden, verwenden Sie das Abfrage-Reinigungsmodul.

## Regelbedingungen vor der Suche {#section_B5568ADEB28546A280720309498B045D}

Bedingungen sind optional. Wenn Sie sich dafür entscheiden, Aktionen für jede Abfrage festzulegen, werden die Aktionen immer ausgeführt. Es wird empfohlen, dass die erste Regel für jede Abfrage ausgeführt wird, bei der die Standardvorlage für die Präsentation ausgewählt wird. Auf diese Weise können Sie sicher sein, dass Sie unabhängig von der eingehenden Abfrage eine Präsentationsvorlage für das Worst-Case-Szenario ausgewählt haben. Die Bedingungen können auf allen CGI-Abfragen-, Cookie- oder benutzerspezifischen Variablen basieren, die von einer vorherigen Regel festgelegt wurden, oder auf einer Systemvariablen.

## Regelaktionen vor der Suche {#section_3B8E19D287554C1C969F5B8D81226981}

Alle Aktionen innerhalb einer Vorab-Suchregel, die entsprechende Bedingungen aufweisen, werden ausgeführt. Aktionen bestehen in der Regel aus einem Vorgang, den Daten, die für den Vorgang ausgeführt werden sollen, und dem zu verwendenden Wert. Am einfachsten wird festgelegt, welche Präsentationsvorlage verwendet werden soll, wenn die Abfrage den Bedingungen der Vorsuchregel entspricht. Legen Sie dann die gewünschte Vorlage auf den Namen der Präsentationsvorlage fest. Kompliziertere Aktionen können verwendet werden, um die Suche zu ändern, die für eine bestimmte Vorlage verwendet wird, indem eine Operation für den Suchparameter einer Vorlage ausgeführt wird. Bei der Ausführung eines Vorgangs mit dem Suchparameter einer Vorlage geben Sie eine Präsentationsvorlage und eine Suche an.

## Allgemeine Regeln {#section_885ECB9DBF0C4D539C14F82BCAA35B4E}

Beim Ausführen von Vorgängen mit dem Suchparameter einer Vorlage gibt es zwei spezielle Werte: *zielgerichtet und *primär für die Präsentationsvorlage bzw. die benannte Suche. Mit diesen Werten können Sie Regeln basierend auf der primären Suche der aktuellen zielgerichteten Vorlage erstellen. Diese Konstrukte ermöglichen das Erstellen allgemeiner Regeln, bei denen Sie sich keine Gedanken darüber machen müssen, wie die aktuelle zielgerichtete Vorlage oder die primäre Suche genannt wird. Offensichtlich definiert eine vorherige Vorab-Suchregel, was die aktuelle zielgerichtete Vorlage ist. Andernfalls wird eine Vorlage für die erste Präsentation ausgewählt, was unerwünschte Ergebnisse hervorbringt.

## Beispiele {#section_EA153A151987454EA44A4A6862466DF6}

Setzen Sie die Standardvorlage auf &quot;guided.tmpl&quot;, wenn der Benutzer einen cgi-Parameter namens lang eingibt, der auf eine bekannte Sprache eingestellt ist, verwenden Sie die Vorlage dieser Sprache.

```
    On condition: 
      Every Query 
    Perform the following actions: 
      Set targeted template to guided 
 
    On condition: 
      Query lang matches regular expression fr 
    Perform the following actions: 
      Set targeted template to guided_french 
 
    On condition: 
      Query lang matches regular expression de 
    Perform the following actions: 
      Set targeted template to guided_german
```

## Best Practices {#section_31EBAE5E54174DEE8986CBB636746A98}

* Die erste Regel wählt eine Standardvorlage für jede Abfrage aus.
* Die Datenerfassung der Abfrage erfolgt im Rahmen der Abfrage-Reinigungsregeln. Sie können in der Vorsuchverarbeitung darauf verweisen.
* hinzufügen alle neuen benutzerspezifischen Variablen, die Sie in den Vorab-Suchregeln eingeführt haben, zu einer Vorsuchregel, die für jede Abfrage ausgeführt wird, bevor andere Vorab-Suchregeln darauf verweisen.

## Hinzufügen einer neuen Vorsuchregel {#task_182B95918462490D8BDA7F16A81CAC11}

Sie können [!DNL Pre-Search Rules] verwenden, um auszuwählen, welche Präsentationsvorlage verwendet wird, um die Suchergebnisse basierend auf der eingehenden Abfrage anzuzeigen.

**So fügen Sie eine neue Vorsuchregel hinzu**

1. Klicken Sie im Produktmenü auf **[!UICONTROL Rules]** > **[!UICONTROL Pre-Search Rules]**.
1. Klicken Sie auf der Seite [!DNL Pre-Search Rules] auf **[!UICONTROL Add New Rule]**.
1. Geben Sie im Feld [!DNL Name] den Namen der neuen Abfrage-Reinigungsregel ein.
1. Verwenden Sie auf der Seite [!DNL Add Pre-Search Rule] die Dropdown-Listen und Textfelder, um Ihre Abfrage zu erstellen.

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
      <td colname="col2"> <p>Ein HTTP-Cookie. Cookie-Name und -Werte müssen mit der Uniform Resource Identifier-Kodierung versehen sein. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Benutzerdefinierte Variable </p> </td> 
      <td colname="col2"> <p>Eine benutzerdefinierte Variable. hinzufügen, löschen oder legen Sie eine unbegrenzte Anzahl benutzerdefinierter Variablen fest. </p> <p>Sie können auf alle Variablen verweisen, die Sie im Abfragen-Bereinigungsmodul in den Vorab-Suchregeln definiert haben. </p> </td> 
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
        </ul> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Facette </p> </td> 
      <td colname="col2"> <p>Spezielle CGI-Parameter in der globalen Sammlung, die mit einer bestimmten Facette verknüpft sind. Alle CGI-Parameter werden nach der Bereinigung der Abfrage in jede benannte Suche innerhalb einer Vorlage kopiert. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Abfrageparameter </p> </td> 
      <td colname="col2"> <p>CGI-Parameter in der globalen Sammlung. Diese Parameter werden nach der Bereinigung der Abfrage in jede benannte Suche innerhalb einer Vorlage kopiert. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Suchparameter der Vorlage </p> </td> 
      <td colname="col2"> <p>Ein CGI-Parameter, der für eine benannte Suche, die mit einer Präsentationsvorlage verknüpft ist, lokal gültig ist. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Backend-Parameter der Vorlage </p> </td> 
      <td colname="col2"> <p>Eingehende Abfrage-Parameter werden schließlich in Backend-Parameter übersetzt, die zur Durchführung der Suche verwendet werden. </p> <p>Siehe <a href="../c-appendices/c-cgiparameters.md#reference_582E85C3886740C98FE88CA9DF7918E8" type="reference" format="dita" scope="local"> CGI-Parameter für die Backend-Suche </a>. </p> <p>Backend-Parameter werden bei Navigationselementen nicht angezeigt. Daher können Sie zusätzliche Parameter, die Sie auf eine Suche anwenden möchten, von Ihren Kunden ausblenden. Der Parameter ist lokal für eine bestimmte Suche in einer Präsentationsvorlage verfügbar. Aktionen für Backend-Parameter sind verspätet zu binden. d. h. sie werden unmittelbar vor dem Senden der Suche angewendet. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Zielgerichtete Vorlage </p> </td> 
      <td colname="col2"> <p>Eine spezielle Instanz einer systemdefinierten benutzerdefinierten Variablen, die nicht gelöscht werden kann. Diese Variable enthält die aktuelle zielgerichtete Präsentationsvorlage. Sie können diese Variable lesen oder festlegen, indem Sie die benutzerdefinierte Variable "target_template"angeben. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Rang </p> </td> 
      <td colname="col2"> <p>Hier können Sie angeben, welche Rangregel bei der Suche verwendet werden soll. Diese Option wird nur angezeigt, wenn Sie Rangfelder und Rangregeln definiert haben. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Speicher </p> </td> 
      <td colname="col2"> <p>Die Suchmaschine erkennt automatisch, in welchem Speicher sich der Kunde befindet, basierend auf dem Hostnamen oder dem <span class="codeph"> gs_store </span> Abfrage-Parameter, wobei letztere Vorrang haben. Sie können Bedingungen aus dem Store erstellen. Bei der Reinigung der Abfrage können Sie auch eine Aktion verwenden, um den aktuellen Store zu überschreiben. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Letzte Regel </p> </td> 
      <td colname="col2"> <p>Wenn diese Option aktiviert ist, führt das Verarbeitungsmodul vor der Suche nach der Aktion der Übereinstimmungsregel keine weiteren Regeln durch. Diese Aktion ist nützlich, wenn Sie Aktionen festgelegt haben, die dazu führen, dass eine spätere Regel übereinstimmt, die später verwendete Regel jedoch nicht ausgeführt werden soll. </p> </td> 
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

## Bearbeiten einer Vorsuchregel {#task_25F77050C5DA42B29DFD1C9718FB8C64}

Sie können vorhandene Vorsuchregeln bearbeiten, die Sie der Seite [!DNL Pre-Search Rules] hinzugefügt haben.

**So bearbeiten Sie eine Vorsuchregel**

1. Klicken Sie im Produktmenü auf **[!UICONTROL Rules]** > **[!UICONTROL Pre-Search Rules]**.
1. Klicken Sie auf der Seite [!DNL Pre-Search Rules] unter der Spalte **[!UICONTROL Actions]** der Tabelle für die zugehörige Regel, die Sie bearbeiten möchten, auf **[!UICONTROL Edit]**.
1. Verwenden Sie auf der Seite [!DNL Edit Pre-Search Rule] die Dropdown-Listen und Textfelder, um Ihre Abfrage zu erstellen.

   Siehe die Tabelle der Optionen unter [Hinzufügen einer neuen Vorsuchregel](../c-about-rules-menu/c-about-pre-search-rules.md#task_182B95918462490D8BDA7F16A81CAC11).
1. Klicken **[!UICONTROL Save Changes]**.
1. (Optional) Führen Sie einen der folgenden Schritte aus:

   * Klicken Sie auf **[!UICONTROL History]**, um alle vorgenommenen Änderungen wiederherzustellen.

      Siehe [Verwenden der Option Verlauf](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Klicken **[!UICONTROL Live]**.

      Siehe [Live-Einstellungen anzeigen](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Klicken **[!UICONTROL Push Live]**.

      Siehe [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Löschen einer Vorsuchregel {#task_128B6A79CA6C451C991AEDAD58F51743}

Sie können Vorsuchregeln löschen, die Sie nicht mehr benötigen oder verwenden.

Wenn Sie eine Regel löschen, wird die Reihenfolge, in der die verbleibenden Regeln ausgeführt werden, automatisch angepasst, um den Löschvorgang zu berücksichtigen.

**So löschen Sie eine Vorsuchregel**

1. Klicken Sie im Produktmenü auf **[!UICONTROL Rules]** > **[!UICONTROL Pre-Search Rules]**.
1. Klicken Sie auf der Seite [!DNL Pre-Search Rules] unter der Spalte **[!UICONTROL Actions]** der Tabelle für die zugehörige Regel, die Sie löschen möchten, auf **[!UICONTROL Delete]**.
1. Klicken Sie im Dialogfeld [!DNL Confirmation] auf **[!UICONTROL OK]**.
1. (Optional) Führen Sie einen der folgenden Schritte aus:

   * Klicken Sie auf **[!UICONTROL History]**, um alle vorgenommenen Änderungen wiederherzustellen.

      Siehe [Verwenden der Option Verlauf](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Klicken **[!UICONTROL Live]**.

      Siehe [Live-Einstellungen anzeigen](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Klicken **[!UICONTROL Push Live]**.

      Siehe [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Ändern der Reihenfolge, in der Vorsuchregeln ausgeführt werden{#task_C18817276A3C459089C97448076365D1}

Sie können die Vorsuchregeln neu anordnen, um die Reihenfolge zu ändern, in der sie in Präsentationsvorlagen ausgeführt werden.

Vorsuchregeln werden in der Reihenfolge ausgeführt, in der sie definiert wurden. Je höher die Ordnungsnummer einer Regel ist, desto später wird sie im Prozess ausgeführt, wodurch frühere Regeln übertroffen werden. Sie können Regeln neu anordnen, indem Sie auf der Seite [!DNL Pre-Search Rules] in die Spalte Reihenfolge der Tabelle eine neue Zahl eingeben. Sie können die Ausführungsreihenfolge auch per Drag &amp; Drop ändern.

**So ändern Sie die Reihenfolge, in der Vorsuchregeln ausgeführt werden**

1. Klicken Sie im Produktmenü auf **[!UICONTROL Rules]** > **[!UICONTROL Pre-Search Rules]**.
1. Führen Sie auf der Seite [!DNL Pre-Search Rules] einen der folgenden Schritte aus:

   * Klicken Sie auf die Spaltenüberschrift **[!UICONTROL Order]**, um die Regeln in auf- oder absteigender Reihenfolge zu sortieren.
   * Geben Sie in der Spalte **[!UICONTROL Order]** im Textfeld links neben dem Namen einer Vorsuchregel die laufende Nummer der Reihenfolge ein, in der die Regel ausgeführt werden soll.
   * Ziehen Sie eine Tabellenzeile an die gewünschte Position. Alle Bestellnummern werden aktualisiert, um die neue Reihenfolge zu widerspiegeln, in der die Regeln ausgeführt werden.

1. Klicken **[!UICONTROL Save Changes]**.
1. (Optional) Führen Sie einen der folgenden Schritte aus:

   * Klicken Sie auf **[!UICONTROL History]**, um alle vorgenommenen Änderungen wiederherzustellen.

      Siehe [Verwenden der Option Verlauf](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Klicken **[!UICONTROL Live]**.

      Siehe [Live-Einstellungen anzeigen](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Klicken **[!UICONTROL Push Live]**.

      Siehe [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

