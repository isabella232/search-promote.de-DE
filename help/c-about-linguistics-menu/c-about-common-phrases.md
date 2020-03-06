---
description: Sie können allgemeine Phrasen definieren, die auf Ihrer Website verwendet werden, damit ein Kunde, der eine Suchabfrage aufruft, keine Anführungszeichen zu den von Ihnen definierten Phrasen eingeben muss.
seo-description: Sie können allgemeine Phrasen definieren, die auf Ihrer Website verwendet werden, damit ein Kunde, der eine Suchabfrage aufruft, keine Anführungszeichen zu den von Ihnen definierten Phrasen eingeben muss.
seo-title: Allgemeine Wortgruppen
solution: Target
title: Allgemeine Wortgruppen
topic: Linguistics,Site search and merchandising
uuid: 0f980a22-d826-4476-97de-0e9c14549bc8
translation-type: tm+mt
source-git-commit: 8efa90ac2927b263b7d48ccbf25d4b0e917dac79

---


# Allgemeine Wortgruppen{#about-common-phrases}

Sie können allgemeine Phrasen definieren, die auf Ihrer Website verwendet werden, damit ein Kunde, der eine Suchabfrage aufruft, keine Anführungszeichen zu den von Ihnen definierten Phrasen eingeben muss.

## Verwenden allgemeiner Begriffe {#concept_4946E53586DF492EAEB1B7F757FD440F}

>[!NOTE]
>
>Die Funktion &quot;Gemeinsame Wortgruppe&quot;wird in der Benutzeroberfläche nicht angezeigt, da sie nicht standardmäßig aktiviert ist. Wenden Sie sich an den technischen Support, um diese Funktion für Ihre Verwendung zu aktivieren.

Häufige Wortgruppen sind eine Sammlung von Wortgruppen, die bei der Suche eines Kunden erkannt werden. Es behandelt die Ausdrücke als kombinierte Wortgruppe und nicht als einzelne Wörter. Wenn ein Kunde eine Suchabfrage auf Ihrer Website eingibt, kann er Wortgruppen durch doppelte Anführungszeichen wie &quot;Pazifischer Ozean&quot;identifizieren. Wenn Sie jedoch Gruppen allgemeiner Ausdrücke hinzufügen, werden die Anführungsschritte automatisch für den Kunden ausgeführt, da sie passende Ausdrücke in der Suchabfrage finden.

Angenommen, ein Kunde Ihrer Website gibt die folgende Suchabfrage ein:

`hotels near the pacific ocean`

Ohne die Hinzufügung von Anführungszeichen `pacific ocean`gibt die Suche des Kunden Ergebnisse für Hotels in der Nähe eines Ozeans auf der Welt zurück, was nicht dem Wunsch des Kunden entspricht.

Wenn Sie jedoch den allgemeinen Begriff &quot;Pazifischer Ozean&quot;hinzufügen, wird ihre Suchabfrage automatisch in folgende Suchabfrage konvertiert:

`hotels near the "pacific ocean"`

Die Verwendung von gemeinsamen Wortgruppen schließt nicht aus, dass Ihre Kunden Anführungszeichen um Wortgruppen setzen, sondern fügt einfach Anführungszeichen hinzu, wenn diese definierten Wortgruppen in ihrer Suchabfrage gefunden werden.

Diese Erweiterung der Suchabfrage gilt für CGI-Parameter `sp_q` und - `sp_q_#`Parameter der Backend-Suche.

Siehe Tabellenzeilen 25, 26 und 32 in CGI- [Suchparametern](../c-appendices/c-cgiparameters.md#reference_582E85C3886740C98FE88CA9DF7918E8)für die Backend-Suche.

## Hinzufügen einer gemeinsamen Wortgruppe {#task_35C84FABCD9042C5B48C5C788B752871}

Sie können &quot;Common Phrase Groups&quot;hinzufügen, um sicherzustellen, dass bei Suchabfragen Webseiten, die alle Wörter in exakter Reihenfolge und Nähe enthalten, die vom Kunden eingegeben wurden, korrekt zurückgegeben werden.

Wenn Sie Gruppen mit gemeinsamen Wortgruppen hinzufügen, können Sie die Funktion &quot;Suchen&quot;auf der Hauptseite der Gruppe mit gemeinsamen Wortgruppen verwenden. Mit der Funktion &quot;Suchen&quot;können Sie nach einem vorhandenen Satz suchen und herausfinden, in welcher Gruppe er sich befindet.

Siehe [Suchen von Gruppen, die bestimmte Wörter in einer Wortgruppe](../c-about-linguistics-menu/c-about-common-phrases.md#task_20714969274740A7BB4DC71E705EA15E)enthalten.

**So fügen Sie eine Gruppe &quot;Common Phrases&quot;hinzu**

1. Klicken Sie im Produktmenü auf **[!UICONTROL Linguistics]** > **[!UICONTROL Common Phrases]**.
1. Klicken Sie auf der [!DNL Common Phrases Groups] Seite auf **Wortgruppe** hinzufügen.
1. Legen Sie auf der [!DNL Add Common Phrase Group] Seite die gewünschten Optionen fest und fügen Sie alle Wortgruppen hinzu, aus denen die Gruppe besteht.

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
      <td colname="col2"> <p>Erforderlich. </p> <p>Der eindeutige Name der Gruppe mit gemeinsamen Phrasen. </p> <p>Wenn Sie später eine Gruppe mit gemeinsamen Wortgruppen bearbeiten, beachten Sie, dass Sie den Gruppennamen nicht ändern können. Um den Gruppennamen zu ändern, verwenden Sie die Funktion <span class="uicontrol"> Umbenennen</span> . </p> <p>Siehe <a href="../c-about-linguistics-menu/c-about-common-phrases.md#task_168E07C59C0F40989D43E7010EFF22EB" format="dita" scope="local"> Umbenennen einer gemeinsamen Wortgruppe</a>. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Hinweise </p> </td> 
      <td colname="col2"> <p>Optional. </p> <p>Fügen Sie Informationen hinzu, die sich auf die Gruppe Gemeinsame Phrase beziehen. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Wortgruppen </p> </td> 
      <td colname="col2"> <p>Erforderlich. </p> <p>Hier können Sie einen Satz mit maximal fünf Wörtern angeben. Wenden Sie sich an den technischen Support, um die maximale Worteinstellung anzupassen. </p> <p>Jeder Satz, den Sie eingeben, muss innerhalb einer Common Phrase Group eindeutig sein. </p> <p>Verwenden Sie die Plus- (+) und Minuszeichen (-) in der Spalte Aktion, um die eingegebene Wortgruppe hinzuzufügen oder eine Wortgruppe zu löschen. </p> </td> 
      </tr> 
    </tbody> 
    </table>

1. Klicken Sie auf **Hinzufügen**.
1. (Optional) Führen Sie einen der folgenden Schritte aus:

   * Klicken Sie auf **[!UICONTROL History]** , um alle vorgenommenen Änderungen wiederherzustellen.

      Siehe [Verwenden der Option](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)Verlauf.

   * Klicken **[!UICONTROL Live]**.

      Siehe [Live-Einstellungen](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)anzeigen.

   * Klicken **[!UICONTROL Push Live]**.

      Siehe [Pushing-Einstellungen](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Testen einer allgemeinen Wortgruppe {#task_A0C344E051CA45A9A0588242F9DA675D}

Wenn Sie Metadatenfelder ausgewählt haben, die mit einer Wortgruppe verknüpft werden sollen, können Sie die Erweiterung einer bestimmten Wortgruppe testen.

Wenn Sie die Erweiterung einer Wortgruppe testen, suchen Sie anhand der mit der Wortgruppe verknüpften Metadatenfelder nach einem genauen Satz. Die Wortgruppe wird durchsucht, als hätte sie Anführungszeichen. In allen anderen Metadatenfeldern werden nur die Wörter innerhalb der Wortgruppe ohne Anführungszeichen gesucht. Angenommen, Sie haben die Wortgruppe getestet `audi TT`. Die zurückgegebenen Ergebnisse könnten wie folgt aussehen:

`title|body|field3:"Audi TT" url|desc|keys|target|alt:Audi TT`

**So testen Sie einen gemeinsamen Satz**

1. Klicken Sie im Produktmenü auf **[!UICONTROL Linguistics]** > **[!UICONTROL Common Phrases]**.
1. Geben Sie auf der [!DNL Common Phrases Groups] Seite in den **Satz Test, der das Textfeld enthält** , die Wortgruppe ein, deren Metadatenerweiterung Sie testen möchten.
1. Klicken **[!UICONTROL Test]**.

   Die Erweiterungsergebnisse werden im Textfeld angezeigt.
1. (Optional) Ziehen Sie die untere rechte Ecke des Textfelds, um den Anzeigebereich zu erweitern.

## Suchen von Gruppen, die bestimmte Wörter in einer Wortgruppe enthalten {#task_20714969274740A7BB4DC71E705EA15E}

Sie können [!DNL Find] zur Suche nach bestimmten Wörtern in einem Satz unter allen vorhandenen Gruppen, die Sie hinzugefügt haben, verwendet werden.

Wenn Sie &quot;Suchen&quot;verwenden, wird Folgendes gefunden:

* Wo genau der gleiche Satz unter allen Gruppen gefunden wird.
* Alle Wörter im Satz unter allen Gruppen, unabhängig von der Wortreihenfolge und der Wortnähe im Satz.

Siehe auch [Bearbeiten einer gemeinsamen Wortgruppe](../c-about-linguistics-menu/c-about-common-phrases.md#task_5CAC3A133C5342EEAFE55A7EABCBCD61).

**So suchen Sie Gruppen, die bestimmte Wörter in einer Wortgruppe enthalten**

1. Klicken Sie im Produktmenü auf **[!UICONTROL Linguistics]** > **[!UICONTROL Common Phrases]**.
1. Geben Sie auf der [!DNL Common Phrases Groups] Seite im **[!UICONTROL Find groups with phrases that contain]** Textfeld eine Wortgruppe ein.
1. Klicken **[!UICONTROL Find]**.

   Die Ergebnisse werden im Textfeld angezeigt.
1. (Optional) Führen Sie einen oder mehrere der folgenden Schritte aus:

   * Ziehen Sie die untere rechte Ecke des Textfelds, um den Anzeigebereich zu erweitern.
   * Klicken Sie im Ergebnisfenster auf eine verknüpfte Wortgruppe, um die Seite &quot;Gemeinsame Wortgruppe bearbeiten&quot;der zugehörigen Gruppe zu öffnen.

## Bearbeiten einer gemeinsamen Wortgruppe {#task_5CAC3A133C5342EEAFE55A7EABCBCD61}

Sie können die vorhandenen Felder, Hinweise und Wortgruppen einer von Ihnen hinzugefügten Wortgruppe bearbeiten. Um den Gruppennamen zu bearbeiten, müssen Sie jedoch die [!DNL Rename] Funktion verwenden.

Siehe auch [Umbenennen einer Gruppe](../c-about-linguistics-menu/c-about-common-phrases.md#task_168E07C59C0F40989D43E7010EFF22EB)mit gemeinsamen Wortgruppen.

**So bearbeiten Sie eine Gruppe mit gemeinsamen Wortgruppen**

1. Klicken Sie im Produktmenü auf **[!UICONTROL Linguistics]** > **[!UICONTROL Common Phrases]**.
1. Klicken Sie auf der [!DNL Common Phrases Groups] Seite rechts neben dem Gruppennamen **[!UICONTROL Edit]** auf .
1. Legen Sie auf der [!DNL Edit Common Phrase Group] Seite die gewünschten Optionen fest.

   Siehe die Tabelle der Optionen unter [Hinzufügen einer gemeinsamen Wortgruppe](../c-about-linguistics-menu/c-about-common-phrases.md#task_35C84FABCD9042C5B48C5C788B752871).
1. Klicken Sie auf **Änderungen speichern**.
1. (Optional) Führen Sie einen der folgenden Schritte aus:

   * Klicken Sie auf **[!UICONTROL History]** , um alle vorgenommenen Änderungen wiederherzustellen.

      Siehe [Verwenden der Option](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)Verlauf.

   * Klicken **[!UICONTROL Live]**.

      Siehe [Live-Einstellungen](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)anzeigen.

   * Klicken **[!UICONTROL Push Live]**.

      Siehe [Pushing-Einstellungen](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Umbenennen einer gemeinsamen Wortgruppe {#task_168E07C59C0F40989D43E7010EFF22EB}

Sie können den Namen einer bestehenden Gruppe mit gemeinsamen Phrasen ändern. Wenn Sie jedoch die vorhandenen Felder, Hinweise und Wortgruppen einer Gruppe allgemeiner Wortgruppen ändern möchten, müssen Sie die [!DNL Edit] Funktion verwenden.

Siehe [Bearbeiten einer gemeinsamen Wortgruppe](../c-about-linguistics-menu/c-about-common-phrases.md#task_5CAC3A133C5342EEAFE55A7EABCBCD61) .

**So benennen Sie eine Gruppe mit allgemeinen Wortgruppen um**

1. Klicken Sie im Produktmenü auf **[!UICONTROL Linguistics]** > **[!UICONTROL Common Phrases]**.
1. Klicken Sie auf der [!DNL Common Phrases Groups] Seite rechts neben dem Gruppennamen **[!UICONTROL Rename]** auf .
1. Geben Sie auf der [!DNL Rename Common Phrase Group] Seite im **[!UICONTROL Group Name]** Textfeld den neuen Namen der Gruppe ein.
1. Klicken Sie auf **Umbenennen**.
1. (Optional) Führen Sie einen der folgenden Schritte aus:

   * Klicken Sie auf **[!UICONTROL History]** , um alle vorgenommenen Änderungen wiederherzustellen.

      Siehe [Verwenden der Option](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)Verlauf.

   * Klicken **[!UICONTROL Live]**.

      Siehe [Live-Einstellungen](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)anzeigen.

   * Klicken **[!UICONTROL Push Live]**.

      Siehe [Pushing-Einstellungen](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Löschen einer gemeinsamen Wortgruppe {#task_4106D282A2ED4A27B09EE5A8CAAEDA36}

Sie können alle von Ihnen hinzugefügten Common Phrase-Gruppen löschen. Wenn Sie eine Gruppe versehentlich löschen, können Sie die Gruppe [!DNL History] wiederherstellen.

Siehe [Verwenden der Option](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)Verlauf.

**So löschen Sie eine Gruppe mit häufigen Wortgruppen**

1. Klicken Sie im Produktmenü auf **[!UICONTROL Linguistics]** > **[!UICONTROL Common Phrases]**.
1. Klicken Sie auf der [!DNL Common Phrases Groups] Seite rechts neben dem Gruppennamen **[!UICONTROL Delete]** auf .
1. Klicken Sie auf der [!DNL Delete Common Phrase Group] Seite auf **[!UICONTROL Delete]**.
1. (Optional) Führen Sie einen der folgenden Schritte aus:

   * Klicken Sie auf **[!UICONTROL History]** , um alle vorgenommenen Änderungen wiederherzustellen.

      Siehe [Verwenden der Option](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)Verlauf.

   * Klicken **[!UICONTROL Live]**.

      Siehe [Live-Einstellungen](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)anzeigen.

   * Klicken **[!UICONTROL Push Live]**.

      Siehe [Pushing-Einstellungen](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

