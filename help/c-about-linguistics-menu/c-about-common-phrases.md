---
description: Sie können allgemeine Wortgruppen definieren, die auf Ihrer Website verwendet werden, damit ein Kunde bei der Eingabe einer Suchbegriffs-Abfrage keine Anführungszeichen zu den von Ihnen definierten Wortgruppen eingeben muss.
seo-description: Sie können allgemeine Wortgruppen definieren, die auf Ihrer Website verwendet werden, damit ein Kunde bei der Eingabe einer Suchbegriffs-Abfrage keine Anführungszeichen zu den von Ihnen definierten Wortgruppen eingeben muss.
seo-title: Allgemeine Wortgruppen
solution: Target
title: Allgemeine Wortgruppen
topic: Linguistics,Site search and merchandising
uuid: 0f980a22-d826-4476-97de-0e9c14549bc8
translation-type: tm+mt
source-git-commit: 8efa90ac2927b263b7d48ccbf25d4b0e917dac79
workflow-type: tm+mt
source-wordcount: '1216'
ht-degree: 1%

---


# Allgemeine Phrasen{#about-common-phrases}

Sie können allgemeine Wortgruppen definieren, die auf Ihrer Website verwendet werden, damit ein Kunde bei der Eingabe einer Suchbegriffs-Abfrage keine Anführungszeichen zu den von Ihnen definierten Wortgruppen eingeben muss.

## Verwenden von allgemeinen Wortgruppen {#concept_4946E53586DF492EAEB1B7F757FD440F}

>[!NOTE]
>
>Die Funktion &quot;Gemeinsame Wortgruppe&quot;wird in der Benutzeroberfläche nicht angezeigt, da sie nicht standardmäßig aktiviert ist. Wenden Sie sich an den technischen Support, um diese Funktion für Ihre Verwendung zu aktivieren.

Häufige Wortgruppen sind eine Sammlung von Wortgruppen, die bei der Suche eines Kunden erkannt werden. Es behandelt die Ausdrücke als kombinierte Wortgruppe und nicht als einzelne Wörter. Wenn ein Kunde eine Abfrage zur Suche auf Ihrer Website aufruft, kann er Sätze identifizieren, indem er die Begriffe mit Dubletten-Anführungszeichen wie &quot;Pazifischer Ozean&quot;umschließt. Wenn Sie jedoch Gruppen allgemeiner Ausdrücke hinzufügen, werden die Anführungsschritte automatisch für den Kunden ausgeführt, da passende Ausdrücke in der Abfrage gefunden werden.

Angenommen, ein Kunde Ihrer Website gibt die folgende Abfrage ein:

`hotels near the pacific ocean`

Ohne das Hinzufügen von Anführungszeichen um `pacific ocean` gibt die Suche des Kunden Ergebnisse für Hotels in der Nähe eines Ozeans auf der Welt zurück, was nicht dem Wunsch des Kunden entspricht.

Wenn Sie jedoch den allgemeinen Begriff &quot;Pazifischer Ozean&quot;hinzufügen, wird die Abfrage der Suche automatisch in folgende Elemente konvertiert:

`hotels near the "pacific ocean"`

Die Verwendung von gemeinsamen Wortgruppen schließt nicht aus, dass Ihre Kunden Anführungszeichen um Wortgruppen herum verwenden, sondern fügt einfach Anführungszeichen hinzu, wenn diese definierten Wortgruppen in ihrer Abfrage gefunden werden.

Diese Erweiterung der Abfrage für die Suche nach Backend-CGI-Parametern `sp_q` und `sp_q_#`,

Siehe die Tabellenzeilen 25, 26 und 32 in [CGI-Parameter für die Backend-Suche](../c-appendices/c-cgiparameters.md#reference_582E85C3886740C98FE88CA9DF7918E8).

## Hinzufügen einer gemeinsamen Wortgruppe {#task_35C84FABCD9042C5B48C5C788B752871}

Sie können gemeinsame Ausdrucksgruppen hinzufügen, um sicherzustellen, dass Suchabfragen Webseiten exakt zurückgeben, die alle Wörter in der exakten Reihenfolge und Nähe enthalten, die ein Kunde eingegeben hat.

Beim Hinzufügen von allgemeinen Ausdrucksgruppen können Sie die Funktion &quot;Suchen&quot;auf der Hauptseite der allgemeinen Ausdrucksgruppe verwenden. Mit der Suchfunktion können Sie nach einem vorhandenen Ausdruck suchen und herausfinden, in welcher Gruppe er sich befindet.

Siehe [Suchen von Gruppen, die bestimmte Wörter in einem Ausdruck enthalten](../c-about-linguistics-menu/c-about-common-phrases.md#task_20714969274740A7BB4DC71E705EA15E).

**So fügen Sie eine Gruppe für allgemeine Ausdrücke hinzu**

1. Klicken Sie im Produktmenü auf **[!UICONTROL Linguistics]** > **[!UICONTROL Common Phrases]**.
1. Klicken Sie auf der Seite [!DNL Common Phrases Groups] auf **Phrase-Gruppe hinzufügen**.
1. Legen Sie auf der Seite [!DNL Add Common Phrase Group] die gewünschten Optionen fest und fügen Sie alle Sätze hinzu, aus denen die Gruppe besteht.

   <table> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> <p>Option </p> </th> 
      <th colname="col2" class="entry"> <p>Beschreibung </p> </th> 
      </tr> 
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <p>Gruppenname </p> </td> 
      <td colname="col2"> <p>Erforderlich. </p> <p>Eindeutiger Name der Gruppe der gemeinsamen Ausdrücke. </p> <p>Wenn Sie später eine Gruppe allgemeiner Ausdrücke bearbeiten, können Sie den Gruppennamen nicht ändern. Um den Gruppennamen zu ändern, verwenden Sie die Funktion <span class="uicontrol"> Umbenennen</span>. </p> <p>Siehe <a href="../c-about-linguistics-menu/c-about-common-phrases.md#task_168E07C59C0F40989D43E7010EFF22EB" format="dita" scope="local"> Umbenennen einer allgemeinen Ausdrucksgruppe</a>. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Hinweise </p> </td> 
      <td colname="col2"> <p>Optional. </p> <p>Fügen Sie Informationen hinzu, die sich auf die Gruppe "Gemeinsame Ausdrücke"beziehen. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Ausdrücke </p> </td> 
      <td colname="col2"> <p>Erforderlich. </p> <p>Ermöglicht die Angabe einer Wortgruppe mit maximal fünf Wörtern. Wenden Sie sich an den technischen Support, um die maximale Worteinstellung anzupassen. </p> <p>Jeder Ausdruck, den Sie eingeben, muss innerhalb einer gemeinsamen Ausdrucksgruppe eindeutig sein. </p> <p>Verwenden Sie die Plus-Symbole (+) und Minus-Symbole (-) in der Spalte "Aktion", um den eingegebenen Ausdruck hinzuzufügen oder einen Ausdruck zu löschen. </p> </td> 
      </tr> 
    </tbody> 
    </table>

1. Klicken Sie auf **Hinzufügen**.
1. (Optional) Führen Sie einen der folgenden Schritte aus:

   * Klicken Sie auf **[!UICONTROL History]**, um die vorgenommenen Änderungen wiederherzustellen.

      Siehe [Verwenden der Option Verlauf](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Klicken **[!UICONTROL Live]**.

      Siehe [Live-Einstellungen anzeigen](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Klicken **[!UICONTROL Push Live]**.

      Siehe [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Testen eines allgemeinen Ausdrucks {#task_A0C344E051CA45A9A0588242F9DA675D}

Wenn Sie Metadatenfelder ausgewählt haben, die mit einer Ausdrucksgruppe verknüpft werden sollen, können Sie die Erweiterung eines bestimmten Ausdrucks testen.

Wenn Sie die Erweiterung eines Ausdrucks testen, suchen Sie nach einem genauen Ausdruck für die Metadatenfelder, die Sie mit der Ausdrucksgruppe verknüpft haben. Der Ausdruck wird durchsucht, als ob er Anführungszeichen um ihn herum hätte. In allen anderen Metadatenfeldern werden nur die Wörter innerhalb des Ausdrucks ohne Anführungszeichen gesucht. Beispiel: Sie haben den Ausdruck `audi TT` getestet. Die zurückgegebenen Ergebnisse könnten wie folgt angezeigt werden:

`title|body|field3:"Audi TT" url|desc|keys|target|alt:Audi TT`

**So testen Sie einen allgemeinen Ausdruck**

1. Klicken Sie im Produktmenü auf **[!UICONTROL Linguistics]** > **[!UICONTROL Common Phrases]**.
1. Geben Sie auf der Seite [!DNL Common Phrases Groups] im Textfeld **Ausdruck testen, der** enthält, den Ausdruck ein, dessen Metadatenerweiterung Sie testen möchten.
1. Klicken **[!UICONTROL Test]**.

   Die Erweiterungsergebnisse werden im Textfeld angezeigt.
1. (Optional) Ziehen Sie die untere rechte Ecke des Textfelds, um den Anzeigebereich zu erweitern.

## Suchen von Gruppen, die bestimmte Wörter in einem Ausdruck {#task_20714969274740A7BB4DC71E705EA15E} enthalten

Sie können [!DNL Find] verwenden, um nach bestimmten Wörtern in einem Ausdruck unter allen vorhandenen Gruppen zu suchen, die Sie hinzugefügt haben.

Wenn Sie &quot;Suchen&quot;verwenden, wird Folgendes gefunden:

* Wo genau der gleiche Satz unter allen Gruppen gefunden wird.
* Alle Wörter in der Phrase unter allen Gruppen, unabhängig von der Wortfolge und der Nähe in der Phrase.

Siehe auch [Bearbeiten einer allgemeinen Ausdrucksgruppe](../c-about-linguistics-menu/c-about-common-phrases.md#task_5CAC3A133C5342EEAFE55A7EABCBCD61).

**So suchen Sie nach Gruppen, die bestimmte Wörter in einem Ausdruck enthalten**

1. Klicken Sie im Produktmenü auf **[!UICONTROL Linguistics]** > **[!UICONTROL Common Phrases]**.
1. Geben Sie auf der Seite [!DNL Common Phrases Groups] im Textfeld **[!UICONTROL Find groups with phrases that contain]** einen Ausdruck ein.
1. Klicken **[!UICONTROL Find]**.

   Die Ergebnisse werden im Textfeld angezeigt.
1. (Optional) Führen Sie einen oder mehrere der folgenden Schritte aus:

   * Ziehen Sie die untere rechte Ecke des Textfelds, um den Anzeigebereich zu erweitern.
   * Klicken Sie im Ergebnisfenster auf einen Hyperlink, um die Seite &quot;Allgemeine Phrase-Gruppe bearbeiten&quot;der zugeordneten Gruppe zu öffnen.

## Bearbeiten einer gemeinsamen Ausdrucksgruppe {#task_5CAC3A133C5342EEAFE55A7EABCBCD61}

Sie können die vorhandenen Felder, Hinweise und Ausdrücke einer gemeinsamen Ausdrucksgruppe bearbeiten, die Sie hinzugefügt haben. Um jedoch den Gruppennamen zu bearbeiten, müssen Sie die [!DNL Rename]-Funktion verwenden.

Siehe auch [Umbenennen einer allgemeinen Ausdrucksgruppe](../c-about-linguistics-menu/c-about-common-phrases.md#task_168E07C59C0F40989D43E7010EFF22EB).

**Bearbeiten einer Gruppe allgemeiner Ausdrücke**

1. Klicken Sie im Produktmenü auf **[!UICONTROL Linguistics]** > **[!UICONTROL Common Phrases]**.
1. Klicken Sie auf der Seite [!DNL Common Phrases Groups] auf **[!UICONTROL Edit]** ganz rechts neben einem Gruppennamen.
1. Legen Sie auf der Seite [!DNL Edit Common Phrase Group] die gewünschten Optionen fest.

   Siehe die Tabelle der Optionen unter [Hinzufügen einer gemeinsamen Ausdrucksgruppe](../c-about-linguistics-menu/c-about-common-phrases.md#task_35C84FABCD9042C5B48C5C788B752871).
1. Klicken Sie auf **Änderungen speichern**.
1. (Optional) Führen Sie einen der folgenden Schritte aus:

   * Klicken Sie auf **[!UICONTROL History]**, um die vorgenommenen Änderungen wiederherzustellen.

      Siehe [Verwenden der Option Verlauf](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Klicken **[!UICONTROL Live]**.

      Siehe [Live-Einstellungen anzeigen](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Klicken **[!UICONTROL Push Live]**.

      Siehe [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Umbenennen einer gemeinsamen Ausdrucksgruppe {#task_168E07C59C0F40989D43E7010EFF22EB}

Sie können den Namen einer vorhandenen gemeinsamen Ausdrucksgruppe ändern. Wenn Sie jedoch die vorhandenen Felder, Hinweise und Ausdrücke einer gemeinsamen Ausdrucksgruppe ändern möchten, müssen Sie die [!DNL Edit]-Funktion verwenden.

Siehe [Bearbeiten einer gemeinsamen Ausdrucksgruppe](../c-about-linguistics-menu/c-about-common-phrases.md#task_5CAC3A133C5342EEAFE55A7EABCBCD61) .

**Umbenennen einer Gruppe allgemeiner Ausdrücke**

1. Klicken Sie im Produktmenü auf **[!UICONTROL Linguistics]** > **[!UICONTROL Common Phrases]**.
1. Klicken Sie auf der Seite [!DNL Common Phrases Groups] auf **[!UICONTROL Rename]** ganz rechts neben einem Gruppennamen.
1. Geben Sie auf der Seite [!DNL Rename Common Phrase Group] im Textfeld **[!UICONTROL Group Name]** den neuen Namen der Gruppe ein.
1. Klicken Sie auf **Umbenennen**.
1. (Optional) Führen Sie einen der folgenden Schritte aus:

   * Klicken Sie auf **[!UICONTROL History]**, um die vorgenommenen Änderungen wiederherzustellen.

      Siehe [Verwenden der Option Verlauf](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Klicken **[!UICONTROL Live]**.

      Siehe [Live-Einstellungen anzeigen](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Klicken **[!UICONTROL Push Live]**.

      Siehe [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Löschen einer gemeinsamen Ausdrucksgruppe {#task_4106D282A2ED4A27B09EE5A8CAAEDA36}

Sie können alle von Ihnen hinzugefügten allgemeinen Phrase-Gruppen löschen. Wenn Sie eine Gruppe versehentlich löschen, können Sie [!DNL History] verwenden, um die Gruppe wiederherzustellen.

Siehe [Verwenden der Option Verlauf](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

**Löschen einer Gruppe allgemeiner Ausdrücke**

1. Klicken Sie im Produktmenü auf **[!UICONTROL Linguistics]** > **[!UICONTROL Common Phrases]**.
1. Klicken Sie auf der Seite [!DNL Common Phrases Groups] auf **[!UICONTROL Delete]** ganz rechts neben einem Gruppennamen.
1. Klicken Sie auf der Seite [!DNL Delete Common Phrase Group] auf **[!UICONTROL Delete]**.
1. (Optional) Führen Sie einen der folgenden Schritte aus:

   * Klicken Sie auf **[!UICONTROL History]**, um die vorgenommenen Änderungen wiederherzustellen.

      Siehe [Verwenden der Option Verlauf](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Klicken **[!UICONTROL Live]**.

      Siehe [Live-Einstellungen anzeigen](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Klicken **[!UICONTROL Push Live]**.

      Siehe [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

