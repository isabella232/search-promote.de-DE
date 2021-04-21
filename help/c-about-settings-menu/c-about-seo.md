---
description: Sie können SEO (Search Engine Optimization) Meta-Tags verwenden, um bestimmte Elemente Ihrer Seiten anzupassen und dadurch die Platzierung der Suchmaschine zu verbessern.
solution: Target
subtopic: SEO
title: Info zu SEO
topic-legacy: Settings,Site search and merchandising
uuid: 5c5d64f5-fe79-4489-85c6-399d1437f2c4
exl-id: 0045455b-cb86-4820-82fa-753475ab6ca6
translation-type: tm+mt
source-git-commit: 7559f5f7437d46e3510d4659772308666425ec96
workflow-type: tm+mt
source-wordcount: '1201'
ht-degree: 1%

---

# Info zu SEO{#about-seo}

Sie können SEO (Search Engine Optimization) Meta-Tags verwenden, um bestimmte Elemente Ihrer Seiten anzupassen und dadurch die Platzierung der Suchmaschine zu verbessern.

## Verwenden von SEO {#concept_C58BFCE720824A2B9B5F5E613CFD4C0B}

Sie können jedes Element als Ausgangstext definieren, gefolgt von einer Liste von Wörtern. Die Liste der Wörter kann Folgendes umfassen:

* Beliebte Suchbegriffe auf Ihrer Site über einen bestimmten Zeitraum (z. B. &quot;letzter Monat&quot;), vorbehaltlich Ihrer benutzerspezifischen Ausnahmen.
* Wertsätze eines oder mehrerer Felder aus der Suche, aus der die Seite stammt.
* Statische Wörter und Wortgruppen, die Sie in einer Liste definieren

Die häufigsten Seitenelemente, die Benutzer für SEO verwenden, sind der Seitentitel und die Meta-Tags &quot;Suchbegriffe&quot;und &quot;Beschreibung&quot;. Sie können Einstellungen für diese drei Seitenelemente definieren. Zusätzlich können Sie die drei folgenden Einstellungen für jeden der drei Seitentypen definieren: Suchergebnisseiten, Durchsuchen-Seiten und Elementinformationsseiten.

Beim Speichern oder Vorschau Ihrer SEO-Einstellungen werden kleine Segmente von Suchvorlagen (Transport) generiert, die Sie mit dem `<search-include>`-Template-Tag in Ihre anderen Suchvorlagen einbeziehen können. Sie können beispielsweise das Feld &quot;Titel der Suchergebnisseiten&quot;in eine andere Vorlage mit folgenden Elementen einschließen:

```
<search-include file="seo/seo_search_title.tpl" />
```

Die neun möglichen Werte für das `file`-Attribut des `<search-include>`-Tags für SEO-Felder lauten wie folgt:

* `seo/seo_search_title.tpl`
* `seo/seo_search_description.tpl`
* `seo/seo_search_keywords.tpl`
* `seo/seo_browse_title.tpl`
* `seo/seo_browse_description.tpl`
* `seo/seo_browse_keywords.tpl`
* `seo/seo_item_title.tpl`
* `seo/seo_item_description.tpl`
* `seo/seo_item_keywords.tpl`

Um SEO-Felder in einer Präsentationsvorlage zu verwenden, führen Sie mehrere Schritte aus.

Zunächst verwenden Sie `<search-include>` wie oben beschrieben, um die gewünschten Felder in eine XML-Suchvorlage innerhalb eines `<general>`-Elements einzuschließen.

Richten Sie anschließend jedes `<search-include>`-Tag mit `<general-field>`- und `</general-field>`-Tags ein und geben Sie die Feldnamen im `name`-Attribut an, wie im folgenden Beispiel:

```
<general> 
    <general-field name="seo_search_title"><search-include file="seo/seo_search_title.tpl" /></general-field> 
    <general-field name="seo_search_description"><search-include file="seo/seo_search_description.tpl" /></general-field> 
    <general-field name="seo_search_keywords"><search-include file="seo/seo_search_keywords.tpl" /></general-field> 
</general>
```

Anschließend können Sie in Ihrer Präsentationsvorlage die benannten Felder mit den Tags `<guided-general-field>` an den gewünschten Stellen einfügen, wie im folgenden Beispiel dargestellt:

```
<title><guided-general-field gsname="default" field="seo_search_title"></title> 
<meta name="description" content="<guided-general-field gsname="default" field="seo_search_description">"/> 
<meta name="keywords" content="<guided-general-field gsname="default" field="seo_search_keywords">"/>
```

Beachten Sie die Verwendung des Attributs `gsname`, um in diesem Fall die Standardsuche anzugeben.

Insgesamt können Sie neun verschiedene SEO-Felder definieren, die Sie auf Ihren Webseiten verwenden können. Dazu gehören:

* Suchergebnisseiten - Titel, Beschreibung und Suchbegriffe
* Durchsuchen-Seiten - Titel, Beschreibung und Suchbegriffe
* Artikeldetailseiten - Titel, Beschreibung und Suchbegriffe

Alle neun Felder sind mit ähnlichen Einstellungen definiert. Tatsächlich sind die Namen der neun Felder, wie z.B. das Feld &quot;Titel&quot;in &quot;Suchergebnisseiten&quot;, nur Vorschläge, wie Sie sie verwenden könnten. Sie können beliebige Felder in jedem Kontext in Ihren Präsentationsvorlagen und Suchvorlagen verwenden.

Siehe auch [Vorlagen](../c-about-design-menu/c-about-templates.md#concept_06EB481B14864E18A8AE2BCD1D6EF0B5).

Siehe auch [Präsentationsvorlagen-Tags](../c-appendices/c-templates.md#reference_F1BBF616BCEC4AD7B2548ECD3CA74C64).

Siehe auch [Suchvorlagen-Tags](../c-appendices/c-templates.md#reference_F7AA3FF602314E42842BBC740D2CA1A4).

Siehe auch [Konfigurieren einer Liste des Suchergebnisses](../c-about-settings-menu/c-about-seo.md#task_A459A3734EC04042BA52C81184251DD4).

## Konfigurieren einer Liste für Suchergebnisse {#task_A459A3734EC04042BA52C81184251DD4}

Sie können die Liste von Suchergebnisbegriffen und -begriffen konfigurieren, die in Seitentiteln, Beschreibungen und Suchbegriffen enthalten sind.

**So konfigurieren Sie eine Liste mit Suchergebnissen**

1. Klicken Sie im Produktmenü auf **[!UICONTROL Settings]** > **[!UICONTROL SEO]** > **[!UICONTROL Search Result Pages]**.
1. Legen Sie auf der Seite [!DNL SEO Browse Pages Word List] in den entsprechenden Gruppen [!DNL Title], [!DNL Description] und [!DNL Keywords] die gewünschten Optionen fest.

   <table> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> <p>Option </p> </th> 
      <th colname="col2" class="entry"> <p>Beschreibung </p> </th> 
      </tr> 
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <p>Titel | Beschreibung | Suchbegriffe Beginn mit </p> </td> 
      <td colname="col2"> <p>Der Text, der vor dem Wort Liste angezeigt werden soll. </p> <p>Sie möchten beispielsweise, dass die Liste "Suchbegriffe"mit dem Wort "Marken"beginnt. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Beliebte Suchvorgänge einschließen während </p> </td> 
      <td colname="col2"> <p>Der Zeitraum, für den Suchvorgänge eingeschlossen werden. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Maximale Suchanzahl </p> </td> 
      <td colname="col2"> <p>Die maximale Anzahl der Suchvorgänge, die eingeschlossen werden. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Feldwerte einschließen </p> </td> 
      <td colname="col2"> <p>Die Feldwerte, die in der Liste des Ergebnisworts enthalten sind. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>hinzufügen </p> </td> 
      <td colname="col2"> <p>Liste der Wörter, die Sie dem Seitentitel der Suchergebnisse, dem Titel der Durchsuchen-Seite oder dem Titel der Artikeldetails hinzufügen möchten. </p> <p>Klicken Sie auf <b>Bearbeiten</b>, um der Liste Wörter hinzuzufügen. </p> <p>Sie können ein Wort oder eine Wortgruppe pro Zeile hinzufügen. Wenn Sie fertig sind, klicken Sie auf <b>Änderungen speichern</b> und schließen Sie dann die Seite, um zur SEO-Hauptseite zurückzukehren. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Entfernen Sie diese Wörter und Wortgruppen (mit Ausnahme der eingeschlossenen Feldwerte) </p> </td> 
      <td colname="col2"> <p>Liste der Wörter, die Sie aus dem Seitentitel der Suchergebnisse, dem Titel der Durchsuchen-Seite oder dem Titel der Artikeldetails entfernen möchten. </p> <p>Klicken Sie auf <b>Bearbeiten</b>, um der Liste zum Entfernen Wörter hinzuzufügen. </p> <p>Sie können ein Wort oder eine Wortgruppe pro Zeile hinzufügen. Wenn Sie fertig sind, klicken Sie auf <b>Änderungen speichern</b> und schließen Sie dann die Seite, um zur SEO-Hauptseite zurückzukehren. </p> </td> 
      </tr> 
    </tbody> 
    </table>

1. (Optional) Klicken Sie auf **Beispielausgabe für Vorschauen**, um die Ergebniswerte für die von Ihnen festgelegten SEO-Felder Vorschau.

   Siehe [Vorschau der von Ihnen konfigurierten SEO-Meta-Tags](../c-about-settings-menu/c-about-seo.md#task_3F97949E193C4F92A104AD117FE49621).
1. Klicken Sie auf **Änderungen speichern**.
1. (Optional) Erstellen Sie Ihren Stage-Site-Index neu, wenn Sie die Vorschauen durchführen möchten.

   Siehe [Konfigurieren eines inkrementellen Indexes einer gestaffelten Website](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0).
1. (Optional) Führen Sie auf der Seite [!DNL SEO Search Results Word List] einen der folgenden Schritte aus:

   * Klicken Sie auf **[!UICONTROL History]**, um alle vorgenommenen Änderungen wiederherzustellen.

      Siehe [Verwenden der Option Verlauf](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Klicken **[!UICONTROL Live]**.

      Siehe [Live-Einstellungen anzeigen](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Klicken **[!UICONTROL Push Live]**.

      Siehe [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Konfigurieren einer Liste für Durchsuchen-Seiten {#task_D7A1D765A92A4D6C94E672B3A86ECB5A}

Sie können die Liste der Suchseitenbegriffe und -ausdrücke konfigurieren, die in Seitentiteln, Beschreibungen und Suchbegriffen enthalten sind.

**So konfigurieren Sie eine Liste mit Suchseiten**

1. Klicken Sie im Produktmenü auf **[!UICONTROL Settings]** > **[!UICONTROL SEO]** > **[!UICONTROL Browse Pages]**.
1. Legen Sie auf der Seite [!DNL SEO Browse Pages Word List] in den entsprechenden Gruppen [!DNL Title], [!DNL Description] und [!DNL Keywords] die gewünschten Optionen fest.

   Siehe die Tabelle der Optionen unter [Konfigurieren einer Liste für Suchergebnisse](../c-about-settings-menu/c-about-seo.md#task_A459A3734EC04042BA52C81184251DD4).
1. (Optional) Klicken Sie auf **Beispielausgabe für Vorschauen**, um die Ergebniswerte für die von Ihnen festgelegten SEO-Felder Vorschau.

   Siehe [Vorschau der von Ihnen konfigurierten SEO-Meta-Tags](../c-about-settings-menu/c-about-seo.md#task_3F97949E193C4F92A104AD117FE49621).
1. Klicken Sie auf **Änderungen speichern**.
1. (Optional) Erstellen Sie Ihren Stage-Site-Index neu, wenn Sie die Vorschauen durchführen möchten.

   Siehe [Konfigurieren eines inkrementellen Indexes einer gestaffelten Website](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0).
1. (Optional) Führen Sie auf der Seite [!DNL SEO Browse Pages Word List] einen der folgenden Schritte aus:

   * Klicken Sie auf **[!UICONTROL History]**, um alle vorgenommenen Änderungen wiederherzustellen.

      Siehe [Verwenden der Option Verlauf](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Klicken **[!UICONTROL Live]**.

      Siehe [Live-Einstellungen anzeigen](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Klicken **[!UICONTROL Push Live]**.

      Siehe [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Konfigurieren eines Elementdetail-Worts Liste {#task_761538C519B34164BE189F13C39B2495}

Sie können die Liste der Wörter und Ausdrücke von Elementdetails konfigurieren, die in Seitentiteln, Beschreibungen und Suchbegriffen enthalten sind.

**So konfigurieren Sie eine Liste mit Elementdetails**

1. Klicken Sie im Produktmenü auf **[!UICONTROL Settings]** > **[!UICONTROL SEO]** > **[!UICONTROL Item Detail Pages]**.
1. Legen Sie auf der Seite [!DNL SEO Item Detail Word List] in den entsprechenden Gruppen [!DNL Title], [!DNL Description] und [!DNL Keywords] die gewünschten Optionen fest.

   Siehe die Tabelle der Optionen unter [Konfigurieren einer Liste für Suchergebnisse](../c-about-settings-menu/c-about-seo.md#task_A459A3734EC04042BA52C81184251DD4).
1. (Optional) Klicken Sie auf **Beispielausgabe für Vorschauen**, um die Ergebniswerte für die von Ihnen festgelegten SEO-Felder Vorschau.

   Siehe [Vorschau der von Ihnen konfigurierten SEO-Meta-Tags](../c-about-settings-menu/c-about-seo.md#task_3F97949E193C4F92A104AD117FE49621).
1. Klicken Sie auf **Änderungen speichern**.
1. (Optional) Erstellen Sie Ihren Stage-Site-Index neu, wenn Sie die Vorschauen durchführen möchten.

   Siehe [Konfigurieren eines inkrementellen Indexes einer gestaffelten Website](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0).
1. (Optional) Führen Sie auf der Seite [!DNL SEO Item Detail Word List] einen der folgenden Schritte aus:

   * Klicken Sie auf **[!UICONTROL History]**, um alle vorgenommenen Änderungen wiederherzustellen.

      Siehe [Verwenden der Option Verlauf](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Klicken **[!UICONTROL Live]**.

      Siehe [Live-Einstellungen anzeigen](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Klicken **[!UICONTROL Push Live]**.

      Siehe [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Vorschau der SEO-Meta-Tags, die Sie konfiguriert haben {#task_3F97949E193C4F92A104AD117FE49621}

Sie können die resultierenden Werte für die SEO-Felder, die Sie einstellen, Vorschau haben, um zu sehen, was dort eingefügt wird, wo Sie sie verwenden.

SEO-Felder können eingeschlossene Feldwerte enthalten, sodass die Suchergebnisse von der von Ihnen angegebenen Abfrage der Suche abhängen können.

**Zur Vorschau der von Ihnen konfigurierten SEO-Meta-Tags**

1. Klicken Sie im Produktmenü auf **[!UICONTROL Settings]** > **[!UICONTROL SEO]** > **[!UICONTROL Search Result Pages]**.
1. Klicken Sie auf der SEO-Seite auf **Vorschau Sample Output**.
1. Geben Sie auf der Seite [!DNL SEO Preview] im Feld [!DNL Enter sample query] den Begriff Abfrage ein, nach dem Sie suchen möchten.
1. Klicken Sie auf **Suchen**.

   Die sich ergebenden Felder &quot;Titel&quot;, &quot;Beschreibung&quot;und &quot;Suchbegriffe&quot;zeigen den Inhalt, der auf der soeben eingegebenen Abfrage in eine Seite eingefügt wird.
1. Klicken Sie auf **Schließen**, um zur Haupt-SEO-Seite zurückzukehren.
