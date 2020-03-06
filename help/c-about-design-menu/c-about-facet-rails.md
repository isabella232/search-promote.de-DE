---
description: Mit der Facet Rail können Sie Gruppen von Facetten auf einer Webseite neu anordnen.
seo-description: Mit der Facet Rail können Sie Gruppen von Facetten auf einer Webseite neu anordnen.
seo-title: Über Facet-Leiste
solution: Target
subtopic: Navigation
title: Über Facet-Leiste
topic: Design,Site search and merchandising
uuid: 6da2bd67-8c20-4955-9836-bc8ba88546c5
translation-type: tm+mt
source-git-commit: 6b3aa733b0dfaace956f0ffc25f433fefd21e15f

---


# Über Facet-Leiste{#about-facet-rail}

Mit der Facet Rail können Sie Gruppen von Facetten auf einer Webseite neu anordnen.

## Facet Rail verwenden {#concept_1FDC8BCDFFC84A0889DA670F63D5F6DB}

Eine Facette ist eine Eigenschaft oder ein Merkmal. Es ist eine Möglichkeit, die Suchergebnisse generell zu kategorisieren. Beispielsweise könnten Hersteller, Preis und Farbe als eine Gruppe von Facetten betrachtet werden. Jede Facette kann mehrere Einschränkungen oder Werte aufweisen. Wenn Sie z. B. eine Facette haben, könnten die &quot;Facettenwerte&quot;rot, orange, gelb, grün, blau, indigo und violett sein.

Siehe [Grundlagen](../c-about-design-menu/c-about-facets.md#concept_FA912B3B41EE493DB2F492D188457FF5).

Mit der Facet Rail können Sie diese Facettengruppen auf einer Webseite neu anordnen. Angenommen, Sie haben auf der linken Seite einer Webseite einen Suchergebnisabschnitt. Der Abschnitt aufgelistet, von oben nach unten, eine Kategorie-Facette, eine Markenfacette, eine Preis-Facette und eine beliebteste Facette. Mithilfe einer Facettenleiste können Sie beispielsweise festlegen, dass die Facette &quot;Am meisten bevorzugte&quot;über oder unter der Facette &quot;Kategorie&quot;angezeigt wird.

Die Gruppe von Facetten, die Sie zusammen neu anordnen möchten, gehört zu einem Facettenschienen-Tag. Eine Facette kann nur zu einer Facettenleiste gehören. Die Facettenleiste ist ein Präsentationsvorlage-Tag und umfasst eine einzelne Darstellung einer Facette. Alle Facetten, die zu dieser Leiste gehören, weisen dieselbe Facet-Darstellung auf.

Siehe [Grundlagen zu Vorlagen](../c-about-design-menu/c-about-templates.md#concept_06EB481B14864E18A8AE2BCD1D6EF0B5) und Facets in [Präsentationsvorlagen-Tags](../c-appendices/c-templates.md#reference_F1BBF616BCEC4AD7B2548ECD3CA74C64).

## Konfigurieren einer Facettenleiste {#task_561A8FF1CAD1402B9DD33E276BBC6A0E}

Sie können eine Facettenleiste hinzufügen, um Ihre Präsentationsebene anzupassen. Facet-Rails bieten Ihren Kunden eine geführte Suche, mit der sie anhand der Reihenfolge der Facetten Ihrer Webseite einen Drilldown in ihren Suchergebnissen durchführen können.

<!-- 

t_configuring_facet_rail.xml

-->

Änderungen, die Sie an Facettenschienen vornehmen, können mithilfe der Funktion Verlauf zurückgesetzt werden.

**So konfigurieren Sie eine Facettenleiste**

1. Bevor Sie eine Facettenleiste konfigurieren können, stellen Sie sicher, dass Sie bereits eine Facette hinzugefügt und als Teil dieser Aufgabe einen Facettenschienennamen angegeben haben.

   Siehe [Hinzufügen einer neuen Facette](../c-about-design-menu/c-about-facets.md#task_FC07BFFA62CA4B718D6CBF4F2855C89B).
1. Klicken Sie im Produktmenü auf **[!UICONTROL Design]** > **[!UICONTROL Navigation]** > **[!UICONTROL Facet Rail.]**
1. Wählen Sie auf der [!DNL Facet Rail] Seite die Facetten aus, die Sie in die Facettenleiste aufnehmen möchten, und stellen Sie dann die **[!UICONTROL Sort Facets Method]** Option aus der Dropdownliste ein.

   <!-- 
   r_facet_rail_options.xml
   -->

   | Funktion/Option | Beschreibung |
   |--- |--- |
   | Facet Rail Name | Identifiziert den Namen der Facettenleiste.  Sie erstellen den Namen der Facettenleiste zum Zeitpunkt des Hinzufügens der Facette.  Siehe [Hinzufügen einer neuen Facette](../c-about-design-menu/c-about-facets.md#task_FC07BFFA62CA4B718D6CBF4F2855C89B) |
   | Einbezogene Facets | Eine Liste möglicher Facetten, die Sie zur Facettenleiste hinzufügen können.  Wenn Sie Facets mit `Custom`der Reihenfolge sortieren, in der Sie die Facetten hier auswählen, bestimmt die Reihenfolge, in der sie im `Custom Facet Order` Textfeld angezeigt werden. |
   | Facet-Sortiermethode | Wählen Sie aus einer der folgenden drei Optionen in der Dropdownliste:<ul><li>`Alpha` Die Facetten werden in alphabetischer Reihenfolge in Bezug auf ihre Namen sortiert, einschließlich Interpunktionszeichen.</li><li>`Alpha (not case sensitive)` Die Facetten werden in alphabetischer Reihenfolge nach Namen sortiert, wobei die Groß-/Kleinschreibung von Buchstaben ignoriert wird und Interpunktionszeichen enthalten sind. </li><li>`Alpha (alphanumeric only)` Die Facetten werden in alphabetischer Reihenfolge nach Namen sortiert, wobei Interpunktionszeichen ignoriert werden. </li><li>`Alpha (not case sensitive, alphanumeric only)` Die Facetten sind in Bezug auf ihre Namen in alphabetischer Reihenfolge sortiert, wobei die Groß-/Kleinschreibung von Buchstaben ignoriert und Interpunktionszeichen ignoriert werden. </li><li>`Count` Die Facetten werden nach Anzahl sortiert. </li><li>`Custom` Öffnet das `Custom Facet Order` Textfeld, in dem Sie die Reihenfolge der Facetten durch Eingabe des genauen Namens der einzelnen Facetten festlegen können. Alle ausgeklammerten Facettenbeschriftungen werden aus der `Custom Facet Order` Liste entfernt.</li></ul> |
   | Benutzerdefinierte Facet-Reihenfolge | Diese Option ist nur verfügbar, wenn Sie `Custom` aus der `Sort Facets Method` Dropdownliste ausgewählt haben.  Ermöglicht die Auflistung von Facettennamen, entweder pro Zeile oder alle in einer Zeile und kommagetrennt. Wenn Facettenbeschriftungen definiert sind, werden sie in der `Facets Included` Liste in Klammern angezeigt.  Fügen Sie keine Facettenbeschriftungen in das `Custom Facet Order` Textfeld ein.  Wenn Sie in der `Facets Included` Liste Facetten auswählen oder deren Auswahl aufheben, wird das `Custom Facet Order` Textfeld automatisch aktualisiert. |

1. Klicken **[!UICONTROL Save Changes]**.
1. (Optional) Führen Sie auf der [!DNL Facet Rail] Seite einen der folgenden Schritte aus:

   * Klicken Sie auf **[!UICONTROL History]** , um alle vorgenommenen Änderungen wiederherzustellen.

      Siehe [Verwenden der Option](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)Verlauf.

   * Klicken **[!UICONTROL Live]**.

      Siehe [Live-Einstellungen](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)anzeigen.

   * Klicken **[!UICONTROL Push Live]**.

      Siehe [Pushing-Einstellungen](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

1. Bearbeiten Sie die Präsentationsvorlage wie folgt:

   * Erstellen Sie eine &quot;Facettenvorlage&quot;in der Präsentationsvorlage.
   * Umschließen Sie die &quot;Facettenvorlage&quot;mit den `<guided-facet-rail>` Tags.

      Siehe Facets in [Präsentationsvorlagen-Tags](../c-appendices/c-templates.md#reference_F1BBF616BCEC4AD7B2548ECD3CA74C64).

      Beispiel:

      ```
      <guided-facet-rail>
        <guided-facet>
          <guided-facet-display-name/>
          ...
          </guided-facet>
        </guided-facet-rail>
      ```

      Diese Tags schneiden einen Abschnitt der Präsentationsvorlage aus, um zu einem wiederholbaren Muster für jede Facette in der Facettenleiste zu werden. Jede Facette, die zur Facettenleiste gehört, verwendet diesen ausgeschnittenen Abschnitt, um ihre Ausgabe zu bewerten. Nur ein `<guided-facet-rail>` Tag kann in der endgültigen Präsentationsvorlage angezeigt werden.

      Die folgenden Tags benötigen das `gsname` Attribut in diesem Attribut nicht, `<guided-facet-rail>` da der Wert zum Suchzeitpunkt dynamisch bestimmt wird und korrekt ersetzt wird:

      `<guided-facet>`
      `<guided-facet-display-name>`
      `<guided-facet-total-count>`
      `<guided-facet-undo-link>`
      `<guided-facet-undo-path>`
      `<guided-facet-behavior>`

   * Speichern Sie die Präsentationsvorlage und veröffentlichen Sie sie live.

      Siehe [Bearbeiten einer Präsentation oder einer Transportvorlage](../c-about-design-menu/c-about-templates.md#task_800E0E2265C34C028C92FEB5A1243EC3).
