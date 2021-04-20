---
description: Sie können allgemeine Wortgruppen definieren, die auf Ihrer Website verwendet werden, damit ein Kunde bei der Eingabe einer Suchbegriffs-Abfrage keine Anführungszeichen zu den von Ihnen definierten Wortgruppen eingeben muss.
solution: Target
title: Allgemeine Wortgruppen
topic: Linguistics,Site search and merchandising
uuid: 0f980a22-d826-4476-97de-0e9c14549bc8
translation-type: tm+mt
source-git-commit: d015154efdccbb4c6a39a56907c0c337ec065c9f
workflow-type: tm+mt
source-wordcount: '1183'
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

Sie können &quot;Allgemeine Wortgruppen&quot;hinzufügen, um sicherzustellen, dass Abfragen bei der Suche Webseiten, die alle Wörter in der exakten Reihenfolge und in der Nähe enthalten, die vom Kunden eingegeben wurden, korrekt zurückgeben.

Wenn Sie Gruppen mit gemeinsamen Wortgruppen hinzufügen, können Sie die Funktion &quot;Suchen&quot;auf der Hauptseite der Gruppe mit gemeinsamen Wortgruppen verwenden. Mit der Funktion &quot;Suchen&quot;können Sie nach einem vorhandenen Satz suchen und herausfinden, in welcher Gruppe er sich befindet.

Siehe [Suchen von Gruppen, die bestimmte Wörter in einer Wortgruppe](../c-about-linguistics-menu/c-about-common-phrases.md#task_20714969274740A7BB4DC71E705EA15E) enthalten.

**So fügen Sie eine Gruppe &quot;Common Phrases&quot;hinzu**

1. Klicken Sie im Produktmenü auf **[!UICONTROL Linguistics]** > **[!UICONTROL Common Phrases]**.
1. Klicken Sie auf der Seite [!DNL Common Phrases Groups] auf **Hinzufügen Phrase Group**.
1. Legen Sie auf der Seite [!DNL Add Common Phrase Group] die gewünschten Optionen fest und fügen Sie alle Wortgruppen hinzu, aus denen die Gruppe besteht.

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
      <td colname="col2"> <p>Erforderlich. </p> <p>Der eindeutige Name der Gruppe mit gemeinsamen Phrasen. </p> <p>Wenn Sie später eine Gruppe mit gemeinsamen Wortgruppen bearbeiten, beachten Sie, dass Sie den Gruppennamen nicht ändern können. Um den Gruppennamen zu ändern, verwenden Sie die Funktion <span class="uicontrol"> Umbenennen</span>. </p> <p>Siehe <a href="../c-about-linguistics-menu/c-about-common-phrases.md#task_168E07C59C0F40989D43E7010EFF22EB" format="dita" scope="local"> Umbenennen einer allgemeinen Wortgruppe</a>. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Hinweise </p> </td> 
      <td colname="col2"> <p>Optional. </p> <p>hinzufügen Informationen, die sich auf die Gruppe "Gemeinsame Phrase"beziehen. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Wortgruppen </p> </td> 
      <td colname="col2"> <p>Erforderlich. </p> <p>Hier können Sie einen Satz mit maximal fünf Wörtern angeben. Wenden Sie sich an den technischen Support, um die maximale Worteinstellung anzupassen. </p> <p>Jeder Satz, den Sie eingeben, muss innerhalb einer Common Phrase Group eindeutig sein. </p> <p>Verwenden Sie die Plus- (+) und Minuszeichen (-) in der Spalte Aktion, um die eingegebene Wortgruppe hinzuzufügen oder eine Wortgruppe zu löschen. </p> </td> 
      </tr> 
    </tbody> 
    </table>

1. Klicken Sie auf **Hinzufügen**.
1. (Optional) Führen Sie einen der folgenden Schritte aus:

   * Klicken Sie auf **[!UICONTROL History]**, um alle vorgenommenen Änderungen wiederherzustellen.

      Siehe [Verwenden der Option Verlauf](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Klicken **[!UICONTROL Live]**.

      Siehe [Live-Einstellungen anzeigen](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Klicken **[!UICONTROL Push Live]**.

      Siehe [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Testen eines gemeinsamen Wortes {#task_A0C344E051CA45A9A0588242F9DA675D}

Wenn Sie Metadatenfelder ausgewählt haben, die mit einer Wortgruppe verknüpft werden sollen, können Sie die Erweiterung einer bestimmten Wortgruppe testen.

Wenn Sie die Erweiterung einer Wortgruppe testen, suchen Sie anhand der mit der Wortgruppe verknüpften Metadatenfelder nach einem genauen Satz. Die Wortgruppe wird durchsucht, als hätte sie Anführungszeichen. In allen anderen Metadatenfeldern werden nur die Wörter innerhalb der Wortgruppe ohne Anführungszeichen gesucht. Angenommen, Sie haben die Wortgruppe `audi TT` getestet. Die zurückgegebenen Ergebnisse könnten wie folgt aussehen:

`title|body|field3:"Audi TT" url|desc|keys|target|alt:Audi TT`

**So testen Sie einen gemeinsamen Satz**

1. Klicken Sie im Produktmenü auf **[!UICONTROL Linguistics]** > **[!UICONTROL Common Phrases]**.
1. Geben Sie auf der Seite [!DNL Common Phrases Groups] im Textfeld **Testbegriff, der** enthält, die Wortgruppe ein, deren Metadatenerweiterung Sie testen möchten.
1. Klicken **[!UICONTROL Test]**.

   Die Erweiterungsergebnisse werden im Textfeld angezeigt.
1. (Optional) Ziehen Sie die untere rechte Ecke des Textfelds, um den Anzeigebereich zu erweitern.

## Suchen von Gruppen, die bestimmte Wörter in einem Satz {#task_20714969274740A7BB4DC71E705EA15E} enthalten

Sie können [!DNL Find] verwenden, um nach bestimmten Wörtern in einem Satz unter allen vorhandenen Gruppen zu suchen, die Sie hinzugefügt haben.

Wenn Sie &quot;Suchen&quot;verwenden, wird Folgendes gefunden:

* Wo genau der gleiche Satz unter allen Gruppen gefunden wird.
* Alle Wörter im Satz unter allen Gruppen, unabhängig von der Wortreihenfolge und der Wortnähe im Satz.

Siehe auch [Bearbeiten einer Common Phrase Group](../c-about-linguistics-menu/c-about-common-phrases.md#task_5CAC3A133C5342EEAFE55A7EABCBCD61).

**So suchen Sie Gruppen, die bestimmte Wörter in einer Wortgruppe enthalten**

1. Klicken Sie im Produktmenü auf **[!UICONTROL Linguistics]** > **[!UICONTROL Common Phrases]**.
1. Geben Sie auf der Seite [!DNL Common Phrases Groups] im Textfeld **[!UICONTROL Find groups with phrases that contain]** eine Wortgruppe ein.
1. Klicken **[!UICONTROL Find]**.

   Die Ergebnisse werden im Textfeld angezeigt.
1. (Optional) Führen Sie einen oder mehrere der folgenden Schritte aus:

   * Ziehen Sie die untere rechte Ecke des Textfelds, um den Anzeigebereich zu erweitern.
   * Klicken Sie im Ergebnisfenster auf eine verknüpfte Wortgruppe, um die Seite &quot;Gemeinsame Wortgruppe bearbeiten&quot;der zugehörigen Gruppe zu öffnen.

## Bearbeiten einer gemeinsamen Wortgruppe {#task_5CAC3A133C5342EEAFE55A7EABCBCD61}

Sie können die vorhandenen Felder, Hinweise und Wortgruppen einer von Ihnen hinzugefügten Wortgruppe bearbeiten. Um den Gruppennamen zu bearbeiten, müssen Sie jedoch die Funktion [!DNL Rename] verwenden.

Siehe auch [Umbenennen einer Common Phrase Group](../c-about-linguistics-menu/c-about-common-phrases.md#task_168E07C59C0F40989D43E7010EFF22EB).

**So bearbeiten Sie eine Gruppe mit gemeinsamen Wortgruppen**

1. Klicken Sie im Produktmenü auf **[!UICONTROL Linguistics]** > **[!UICONTROL Common Phrases]**.
1. Klicken Sie auf der Seite [!DNL Common Phrases Groups] rechts neben dem Gruppennamen auf **[!UICONTROL Edit]**.
1. Legen Sie auf der Seite [!DNL Edit Common Phrase Group] die gewünschten Optionen fest.

   Siehe die Tabelle der Optionen unter [Hinzufügen einer gemeinsamen Wortgruppe](../c-about-linguistics-menu/c-about-common-phrases.md#task_35C84FABCD9042C5B48C5C788B752871).
1. Klicken Sie auf **Änderungen speichern**.
1. (Optional) Führen Sie einen der folgenden Schritte aus:

   * Klicken Sie auf **[!UICONTROL History]**, um alle vorgenommenen Änderungen wiederherzustellen.

      Siehe [Verwenden der Option Verlauf](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Klicken **[!UICONTROL Live]**.

      Siehe [Live-Einstellungen anzeigen](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Klicken **[!UICONTROL Push Live]**.

      Siehe [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Umbenennen einer gemeinsamen Wortgruppe {#task_168E07C59C0F40989D43E7010EFF22EB}

Sie können den Namen einer bestehenden Gruppe mit gemeinsamen Phrasen ändern. Wenn Sie jedoch die vorhandenen Felder, Hinweise und Wortgruppen einer Gruppe allgemeiner Wortgruppen ändern möchten, müssen Sie die Funktion [!DNL Edit] verwenden.

Siehe [Bearbeiten einer Common Phrase Group](../c-about-linguistics-menu/c-about-common-phrases.md#task_5CAC3A133C5342EEAFE55A7EABCBCD61) .

**So benennen Sie eine Gruppe mit allgemeinen Wortgruppen um**

1. Klicken Sie im Produktmenü auf **[!UICONTROL Linguistics]** > **[!UICONTROL Common Phrases]**.
1. Klicken Sie auf der Seite [!DNL Common Phrases Groups] rechts neben dem Gruppennamen auf **[!UICONTROL Rename]**.
1. Geben Sie auf der Seite [!DNL Rename Common Phrase Group] im Textfeld **[!UICONTROL Group Name]** den neuen Namen der Gruppe ein.
1. Klicken Sie auf **Umbenennen**.
1. (Optional) Führen Sie einen der folgenden Schritte aus:

   * Klicken Sie auf **[!UICONTROL History]**, um alle vorgenommenen Änderungen wiederherzustellen.

      Siehe [Verwenden der Option Verlauf](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Klicken **[!UICONTROL Live]**.

      Siehe [Live-Einstellungen anzeigen](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Klicken **[!UICONTROL Push Live]**.

      Siehe [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Löschen einer gemeinsamen Wortgruppe {#task_4106D282A2ED4A27B09EE5A8CAAEDA36}

Sie können alle von Ihnen hinzugefügten Common Phrase-Gruppen löschen. Wenn Sie eine Gruppe versehentlich löschen, können Sie [!DNL History] verwenden, um die Gruppe wiederherzustellen.

Siehe [Verwenden der Option Verlauf](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

**So löschen Sie eine Gruppe mit häufigen Wortgruppen**

1. Klicken Sie im Produktmenü auf **[!UICONTROL Linguistics]** > **[!UICONTROL Common Phrases]**.
1. Klicken Sie auf der Seite [!DNL Common Phrases Groups] rechts neben dem Gruppennamen auf **[!UICONTROL Delete]**.
1. Klicken Sie auf der Seite [!DNL Delete Common Phrase Group] auf **[!UICONTROL Delete]**.
1. (Optional) Führen Sie einen der folgenden Schritte aus:

   * Klicken Sie auf **[!UICONTROL History]**, um alle vorgenommenen Änderungen wiederherzustellen.

      Siehe [Verwenden der Option Verlauf](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Klicken **[!UICONTROL Live]**.

      Siehe [Live-Einstellungen anzeigen](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Klicken **[!UICONTROL Push Live]**.

      Siehe [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

