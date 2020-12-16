---
description: Sie können Regeln nach der Suche verwenden, um die Ergebnisse einer Suche zu untersuchen und festzustellen, wie sich die Suche auf den angezeigten Inhalt auswirkt.
seo-description: Sie können Regeln nach der Suche verwenden, um die Ergebnisse einer Suche zu untersuchen und festzustellen, wie sich die Suche auf den angezeigten Inhalt auswirkt.
seo-title: Über Regeln nach der Suche
solution: Target
title: Über Regeln nach der Suche
topic: Rules,Site search and merchandising
uuid: 312d1e4a-f5b6-4629-8645-17e6f6c09fc4
translation-type: tm+mt
source-git-commit: d07cdc2c88f93eed4cecb0ee8818f7fdea06ee9d
workflow-type: tm+mt
source-wordcount: '2121'
ht-degree: 1%

---


# Über Regeln nach der Suche{#about-post-search-rules}

Sie können Regeln nach der Suche verwenden, um die Ergebnisse einer Suche zu untersuchen und festzustellen, wie sich die Suche auf den angezeigten Inhalt auswirkt.

## Verwenden von Regeln nach der Suche {#concept_AF6ADFCC0ADF4A788003964939917FDE}

Wenn eine Suche keine Ergebnisse enthält, kann eine Regel nach der Suche nach einem ähnlichen Element suchen. Alternativ kann eine Webseite angezeigt werden, auf der Kunden, die nach dem nicht gefundenen Artikel suchen, andere Artikel empfohlen werden.

Jede Regel nach der Suche besteht aus zwei Hauptelementen: die Aktionen der Regel und ihre optionalen Bedingungen. Sie können eine unbegrenzte Anzahl von Regeln und Bedingungen angeben. Die Reihenfolge dieser Regeln ist wichtig, da der Regelsatz in einer Schleife von Regel zu Regel ausgeführt wird. Wenn die Bedingungen einer Regel übereinstimmen, werden alle zugehörigen Aktionen ausgeführt.

Sie können die Suchergebnisse für maximal drei Suchrunden verfeinern. Danach wird das, was aktuell verfügbar ist, verwendet. Diese Beschränkung verhindert unendliche Schleifen und stellt sicher, dass der Kunde eine effiziente Antwort erhält. Je häufiger Sie eine Suche wiederholen, desto länger dauert es, bis Ihre Suchergebnisse zurückgegeben werden. Wenn keine der passenden Regeln eine der Suchen nach der aktuell verwendeten Präsentationsvorlage ändert oder die Vorlage wechselt, gilt der Satz der Suchergebnisse als abgeschlossen und die Ausstiege nach der Suche.

Die Verarbeitung nach der Suche baut auf den früheren Verarbeitungsmodulen Abfrage Clearing und Pre-Search auf. Daher stehen alle in diesen Modulen festgelegten benutzerspezifischen Variablen zur Verwendung in den Verarbeitungsregeln für die Nachsuche zur Verfügung. Ebenso hat die Vorsuchverarbeitung alle Vorlagen instanziiert, bei denen jede benannte Suche, die der Präsentationsvorlage zugeordnet ist, eine eigene lokale Kopie der CGI-Parameter hat. Sie können jede Suche einzeln anpassen.

Siehe [Informationen zu Abfragen-Bereinigungsregeln](../c-about-rules-menu/c-about-query-cleaning-rules.md#concept_17F3CDDC3C8A4128AF092A82B777B86C).

Siehe [Info zu Vorsuchregeln](../c-about-rules-menu/c-about-pre-search-rules.md#concept_5BF84BB6FACB4645BA9CB7496A01CD1F).

## Grundlagen zu Regelbedingungen nach der Suche {#section_C43EB77CC0AC43B8B9D38569264BF1B5}

Bedingungen sind optional. Wenn Sie angeben, dass Aktionen für jede Abfrage angegeben werden, werden die Aktionen immer ausgeführt. Sie können Bedingungen auf allen CGI-Abfragen-Parametern, Cookies, Suchergebnissen oder benutzerspezifischen Variablen basieren, die von einer vorherigen Regel festgelegt wurden. Sie können sie auch auf einer Systembedingung wie der derzeit ausgewählten Vorlage oder der letzten Suche basieren. Wenn Sie eine Bedingung auf Grundlage der Ergebnisse einer Suche oder eines CGI-Parameters erstellen, geben Sie die Vorlage und den Namen der Suche an.

## Über Aktionen nach der Suche nach Regeln {#section_0E15FE683A894ECAAA386267EEC7F7C5}

Alle Aktionen in einer Regel nach der Suche, die Übereinstimmungsbedingungen aufweisen, werden ausgeführt. Aktionen bestehen in der Regel aus einem Vorgang, den Daten, die für den Vorgang ausgeführt werden sollen, und dem zu verwendenden Wert. Die einfachste Aktion besteht darin, basierend auf den Bedingungen der Regel nach der Suche zu entscheiden, welche Präsentationsvorlage verwendet werden soll. Sie können erweiterte Aktionen verwenden, um die Parameter für eine Suche zu ändern, die dazu führt, dass die Suche erneut ausgeführt wird. Geben Sie beim Durchführen eines Vorgangs für den Suchparameter einer Vorlage eine Präsentationsvorlage an und suchen Sie danach.

## Allgemeine Regeln {#section_AEE923988CC748FF9DEF2233FBF333B5}

Bei der Ausführung von Vorgängen mit dem Suchparameter einer Vorlage gibt es zwei spezielle Werte: *target und *primary für die Präsentationsvorlage bzw. die benannte Suche. Verwenden Sie diese Werte, um Regeln basierend auf der primären Suche der aktuellen zielgerichteten Vorlage zu erstellen. Mit diesen Konstrukten können Sie allgemeine Regeln erstellen, bei denen Sie sich keine Gedanken darüber machen müssen, wie die aktuelle zielgerichtete Vorlage oder die primäre Suche heißen soll. Wenn dieser Durchgang der erste Durchgang der Nachsuchverarbeitung ist, wird die Vorlage, auf die die Vorsuchverarbeitung eingestellt ist, als Zielvorlage verwendet.

## Umleitungen {#section_E5669A2F13C240F2968E31C75591CD6A}

Mit direkten Treffern und Umleitungen innerhalb der Bereinigung von Abfragen können Sie zu einer URL umleiten, die auf den eingehenden Suchbegriffen basiert. Umleitungen innerhalb von Regeln nach der Suche erweitern diese Idee, allerdings können Sie damit überprüfen, wie viele Ergebnisse die Suche zurückgegeben hat, bevor Sie entscheiden, ob eine Umleitung durchgeführt werden soll. Mit Regeln nach der Suche können Sie zu einer URL umleiten, in der Sie benutzerdefinierte Variablen oder Abfragen ersetzen können. Oder Sie können zu einem Feld innerhalb des ersten Ergebnisses umleiten. Wenn Sie zu einem Ergebnisfeld umleiten, definieren Sie das Feld in der Transportvorlage. Es muss eine gültige, explizite URL enthalten, andernfalls wird die Umleitung übersprungen.

Wenn Sie den Umleitungsmechanismus in Regeln nach der Suche verwenden, können Sie erkennen, wann eine Suche ein einzelnes Ergebnis zurückgibt. Anstatt ein solches Ergebnis zurückzugeben, können Sie zu der mit dem Ergebnis verknüpften Webseite umleiten.

Ein Beispiel für die Verwendung von Weiterleitungen mit Regeln nach der Suche finden Sie im nachstehenden Beispiel.

## Letzte Regel {#section_FC1E0050C9324278B171038E98F6C335}

Wenn die Bedingungen für eine Regel erfüllt sind, für die die Option **[!UICONTROL Last Rule]** festgelegt ist, führt das Verarbeitungsmodul für die Nachsuchverarbeitung nach der Aktion der Übereinstimmungsregel keine weiteren Regeln durch. Diese Situation ist nützlich, wenn Sie Aktionen festgelegt haben, die dazu führen, dass eine spätere Regel übereinstimmt, die Verarbeitung jedoch beendet werden soll. Und damit diese spätere Regel nach der nächsten Suchrunde möglicherweise übereinstimmt.

## Beispiele {#section_DDB98383690941F9B44AD00FBA55BB56}

Im folgenden Beispiel nehmen Sie an, dass Sie über zwei Präsentationsvorlagen verfügen. Eine Vorlage wird verwendet, um viele Suchergebnisse anzuzeigen, und die andere Vorlage wird verwendet, um ein einzelnes Ergebnis und eine zusätzliche Suche nach Zubehör, das mit der Hauptsuche verbunden ist, anzuzeigen. Sie möchten erkennen, wann Sie ein einzelnes Ergebnis haben, und zu Ihrer anderen Präsentationsvorlage wechseln. Für diese Aufgabe können Sie die folgenden Regeln verwenden:

```
On condition: 
  targeted template is default 
  targeted template primary results equal 1 
  not last search 
Perform the following actions: 
  Set targeted template to product_spotlight
```

MegaElectronic ist ein großer Elektronikladen. Nach der Analyse ihrer Suchdaten bemerkt MegaElectronic, dass viele ihrer Kunden eine Produktsuche mit der Teilenummer eines Produkts durchführen. In solchen Fällen möchte MegaElectronic zu der mit dem Produkt verbundenen Webseite umleiten, wenn der Kunde direkt danach gesucht hat und nur ein einziges Produkt gefunden wurde.

Um dieses Ergebnis zu erzielen, können Sie eine einzelne Regel mit drei Bedingungen verwenden. Die erste Bedingung prüft, ob die zurückgegebene Suche nur ein einziges Ergebnis hat. Die zweite Bedingung stellt sicher, dass der Begriff Abfrage mit dem Teilenumleitungsformat von MegaElectronic übereinstimmt. Die dritte Bedingung stellt sicher, dass der Kunde keine Facetten zum Drilldown zu einem Ergebnis verwendet hat, da es sich bei der Teilenummer möglicherweise um eine Teilteilnummer handelt und mehr als ein Ergebnis zurückgegeben wird. Die Aktion führt eine Weiterleitung zu einem Feld im Ergebnis durch.

```
On condition: 
  targeted template's primary results equal 1 
  query q matches regular expression ^\D\D\D-\d+ 
  no facet selected ^\D\D\D-\d+ 
Perform the following actions: 
  redirect to result field "loc" in template *targeted for search *primary
```

## Best Practices {#section_1BF7DE1BD5664B3BAEC26AA829FDB0BA}

* Alle Regelsätze, die eine neue Suchrunde auslösen, sollten immer über eine bedingte Klausel verfügen, um zu überprüfen, ob dies nicht der letzte Durchgang durch das Modul ist. Wenn Sie bereits die maximale Anzahl von Suchvorgängen durchgeführt haben, können Sie keine Suchvorgänge wiederholen.
* Wenn Sie das Modul zuletzt durchlaufen und die Ergebnisse immer noch schlecht sind, können Sie zu einer Vorlage &quot;Keine Ergebnisse&quot;wechseln.
* Sie sollten die Änderung einer Präsentationsvorlage auf Grundlage des Ergebnisses einer Suche mit möglicherweise anderen Parametern vornehmen. Wenn Sie eine Vorlage auswählen möchten, die nur auf der eingehenden Abfrage basiert, ist eine Vorsuchregel effizienter.
* Die Datenerfassung der Abfrage erfolgt im Abfrage-Reinigungsmodul. Sie können in der Nachsuchverarbeitung auf die benutzerspezifischen Variablen verweisen.
* Wenn Sie eine Umleitung durchführen, überprüfen Sie immer, ob der Kunde keine Facetten ausgewählt hat. Der Grund dafür liegt darin, dass es unpraktisch ist, wenn ein Kunde in eine Facette bohrt und plötzlich aus den Suchergebnissen entfernt wird. Der Kunde möchte die Auswahl der Facette möglicherweise aufheben, wenn er feststellt, dass das Ergebnis nicht gewünscht ist, dass er danach gesucht hat.

## Hinzufügen einer neuen Regel nach der Suche {#task_52F6F9AAD65B45B5ACA1FF245DFFADD9}

Sie können [!DNL Post-Search Rules] verwenden, um auszuwählen, welche Präsentationsvorlage verwendet wird, um die Suchergebnisse basierend auf der eingehenden Abfrage anzuzeigen.

**So fügen Sie eine neue Regel nach der Suche hinzu**

1. Klicken Sie im Produktmenü auf **[!UICONTROL Rules]** > **[!UICONTROL Post-Search Rules]**.
1. Klicken Sie auf der Seite [!DNL Post-Search Rules] auf **[!UICONTROL Add New Rule]**.
1. Geben Sie im Feld [!DNL Name] den Namen der neuen Abfrage-Reinigungsregel ein.
1. Verwenden Sie auf der Seite [!DNL Add Post-Search Rule] die Dropdown-Listen und Textfelder, um Ihre Abfrage zu erstellen.

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
      <td colname="col2"> <p>Ein HTTP-Cookie. Cookie-Namen und -Werte müssen mit dem Uniform Resource Identifier kodiert sein. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Benutzerdefinierte Variable </p> </td> 
      <td colname="col2"> <p>Eine benutzerdefinierte Variable. Sie können eine unbegrenzte Anzahl benutzerdefinierter Variablen hinzufügen, löschen oder festlegen. </p> <p>Sie können auf alle benutzerspezifischen Variablen verweisen, die Sie in den Abfragen-Bereinigung- und Vorab-Suchregelmodulen in den Regeln nach der Suche definiert haben. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Systemvariable </p> </td> 
      <td colname="col2"> <p>Schreibgeschützte Variablen, die vom internen System festgelegt wurden, das Sie überprüfen können. Die folgenden Systemvariablen werden unterstützt: </p> <p> 
        <ul id="ul_BC17F1637F27424CA4E8F530C28A3245"> 
          <li id="li_C7DF96EFD7AA4A449D00F7EACCAA0EB1"> <span class="uicontrol"> hostname </span> <p>Der Name des Serverhosts. </p> </li> 
          <li id="li_F85AB1D2B9374A859657D12B8ED6674B"> <span class="uicontrol"> URI </span> <p>Die angeforderte Uniform Resource Identifier ohne die Abfrage-Zeichenfolge. </p> </li> 
          <li id="li_440149C9EC6E4805B77BBC97BE41542A"> <span class="uicontrol"> args  </span> <p>Die gesamte Abfrage-Zeichenfolge. </p> </li> 
          <li id="li_F583FC4B0E404858BB3522B33A6F7A0A"> <span class="uicontrol"> Umgebung </span> <p>"Stage"oder "live"hängt davon ab, ob die eingehende Abfrage an Ihre inszenierte Umgebung oder Ihre Live-Umgebung gesendet wurde. </p> </li> 
          <li id="li_15902AA49B144D42A5E95D7E8B0FB1E1"> <span class="uicontrol"> referrer </span> <p>Die Uniform Resource Locator, von der der Kunde kam. </p> </li> 
        </ul> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Systemvariable </p> </td> 
      <td colname="col2"> <p>Schreibgeschützte Variablen, die Sie unter Bedingungen zur Bestimmung des aktuellen Status verwenden können. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Suchfacette der Vorlage </p> </td> 
      <td colname="col2"> <p>Eine Facette, die lokal zu einer benannten Suche gehört, die mit einer Präsentationsvorlage verknüpft ist. Eine Facette sind im Wesentlichen spezielle CGI-Parameter, mit denen angegeben wird, welcher Wert in einer Facette vom Kunden ausgewählt wurde. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Suchparameter der Vorlage </p> </td> 
      <td colname="col2"> <p>Ein CGI-Parameter, der für eine benannte Suche, die mit einer Präsentationsvorlage verknüpft ist, lokal gültig ist. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Backend-Parameter der Vorlage </p> </td> 
      <td colname="col2"> <p>Eingehende Abfrage-Parameter werden schließlich in Backend-Parameter übersetzt, die zur Durchführung der Suche verwendet werden. </p> <p>Siehe <a href="../c-appendices/c-cgiparameters.md#reference_582E85C3886740C98FE88CA9DF7918E8" type="reference" format="dita" scope="local"> CGI-Parameter für die Backend-Suche </a>. </p> <p>Backend-Parameter werden bei Navigationselementen nicht angezeigt. Daher können Sie zusätzliche Parameter, die Sie auf eine Suche anwenden möchten, von Ihren Kunden ausblenden. </p> <p>Der Parameter ist lokal für eine bestimmte Suche in einer Präsentationsvorlage verfügbar. Aktionen für Backend-Parameter sind verspätet zu binden. d. h. sie werden unmittelbar vor dem Senden der Suche angewendet. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Zielgerichtete Vorlage </p> </td> 
      <td colname="col2"> <p>Eine spezielle Instanz einer systemdefinierten benutzerdefinierten Variablen, die nicht gelöscht werden kann. Diese Variable enthält die aktuelle zielgerichtete Präsentationsvorlage. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Rang </p> </td> 
      <td colname="col2"> <p>Hier können Sie angeben, welche Rangregel bei der Suche verwendet werden soll. Diese Option wird nur angezeigt, wenn Sie Rangfelder und Rangregeln definiert haben. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Letzte Regel </p> </td> 
      <td colname="col2"> <p>Wenn diese Option aktiviert ist, führt das Verarbeitungsmodul nach der Suche nach der passenden Regel keine weiteren Regeln durch. Diese Aktion ist nützlich, wenn Sie Aktionen festgelegt haben, die dazu führen, dass eine spätere Regel übereinstimmt, die später verwendete Regel jedoch nicht ausgeführt werden soll. </p> </td> 
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

## Bearbeiten einer Regel {#task_ECB00334C0A74C87AF857DB3EB372119} nach der Suche

Sie können vorhandene Regeln nach der Suche bearbeiten, die Sie der Seite [!DNL Post-Search Rules] hinzugefügt haben.

**So bearbeiten Sie eine Regel nach der Suche**

1. Klicken Sie im Produktmenü auf **[!UICONTROL Rules]** > **[!UICONTROL Pre-Search Rules]**.
1. Klicken Sie auf der Seite [!DNL Post-Search Rules] unter der Spalte **[!UICONTROL Actions]** der Tabelle für die zugehörige Regel, die Sie bearbeiten möchten, auf **[!UICONTROL Edit]**.
1. Verwenden Sie auf der Seite [!DNL Edit Post-Search Rule] die Dropdown-Listen und Textfelder, um Ihre Abfrage zu erstellen.

   Siehe die Tabelle der Optionen unter [Hinzufügen einer neuen Regel nach der Suche](../c-about-rules-menu/c-about-post-search-rules.md#task_52F6F9AAD65B45B5ACA1FF245DFFADD9).
1. Klicken **[!UICONTROL Save Changes]**.
1. (Optional) Führen Sie einen der folgenden Schritte aus:

   * Klicken Sie auf **[!UICONTROL History]**, um alle vorgenommenen Änderungen wiederherzustellen.

      Siehe [Verwenden der Option Verlauf](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Klicken **[!UICONTROL Live]**.

      Siehe [Live-Einstellungen anzeigen](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Klicken **[!UICONTROL Push Live]**.

      Siehe [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Löschen einer Regel {#task_0F4653AB20D54B769A4FA8D1491AB4CF} nach der Suche

Sie können Regeln nach der Suche löschen, die Sie nicht mehr benötigen oder verwenden.

Wenn Sie eine Regel löschen, wird die Reihenfolge, in der die verbleibenden Regeln ausgeführt werden, automatisch angepasst, um den Löschvorgang zu berücksichtigen.

**So löschen Sie eine Regel nach der Suche**

1. Klicken Sie im Produktmenü auf **[!UICONTROL Rules]** > **[!UICONTROL Post-Search Rules]**.
1. Klicken Sie auf der Seite [!DNL Post-Search Rules] unter der Spalte **[!UICONTROL Actions]** der Tabelle für die zugehörige Regel, die Sie löschen möchten, auf **[!UICONTROL Delete]**.
1. Klicken Sie im Dialogfeld [!DNL Confirmation] auf **[!UICONTROL OK]**.
1. (Optional) Führen Sie einen der folgenden Schritte aus:

   * Klicken Sie auf **[!UICONTROL History]**, um alle vorgenommenen Änderungen wiederherzustellen.

      Siehe [Verwenden der Option Verlauf](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Klicken **[!UICONTROL Live]**.

      Siehe [Live-Einstellungen anzeigen](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Klicken **[!UICONTROL Push Live]**.

      Siehe [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Ändern der Reihenfolge, in der die Regeln nach der Suche ausgeführt werden{#task_40542FCD32234BBF881A81BF5477F78F}

Sie können Regeln nach der Suche neu anordnen, um die Reihenfolge zu ändern, in der sie in Präsentationsvorlagen ausgeführt werden.

Regeln nach der Suche werden in der Reihenfolge ausgeführt, in der sie definiert wurden. Je höher die Ordnungsnummer einer Regel ist, desto später wird sie im Prozess ausgeführt, wodurch frühere Regeln übertroffen werden. Sie können Regeln neu anordnen, indem Sie auf der Seite [!DNL Post-Search Rules] in die Spalte Reihenfolge der Tabelle eine neue Zahl eingeben. Sie können auch per Drag &amp; Drop Regeln verwenden, um ihre Ausführungsreihenfolge zu ändern.

**So ändern Sie die Reihenfolge, in der Regeln nach der Suche ausgeführt werden**

1. Klicken Sie im Produktmenü auf **[!UICONTROL Rules]** > **[!UICONTROL Post-Search Rules]**.
1. Führen Sie auf der Seite [!DNL Post-Search Rules] einen der folgenden Schritte aus:

   * Klicken Sie auf die Spaltenüberschrift **[!UICONTROL Order]**, um die Regeln in auf- oder absteigender Reihenfolge zu sortieren.
   * Geben Sie in der Spalte [!DNL Order] im Textfeld links neben dem Namen einer Vorsuchregel die laufende Nummer der Reihenfolge ein, in der die Regel ausgeführt werden soll.
   * Ziehen Sie eine Tabellenzeile an die gewünschte Position. Alle Bestellnummern werden aktualisiert, um die neue Reihenfolge zu widerspiegeln, in der die Regeln ausgeführt werden.

1. Klicken **[!UICONTROL Save Changes]**.
1. (Optional) Führen Sie einen der folgenden Schritte aus:

   * Klicken Sie auf **[!UICONTROL History]**, um alle vorgenommenen Änderungen wiederherzustellen.

      Siehe [Verwenden der Option Verlauf](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Klicken **[!UICONTROL Live]**.

      Siehe [Live-Einstellungen anzeigen](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Klicken **[!UICONTROL Push Live]**.

      Siehe [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).
