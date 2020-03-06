---
description: Mit Vertikaler Aktualisierung können Sie Teile Ihres Indexes schnell aktualisieren, ohne große Datenmengen verarbeiten zu müssen.
seo-description: Mit Vertikaler Aktualisierung können Sie Teile Ihres Indexes schnell aktualisieren, ohne große Datenmengen verarbeiten zu müssen.
seo-title: Vertikale Aktualisierung
solution: Target
subtopic: Vertical Update
title: Vertikale Aktualisierung
topic: Index,Site search and merchandising
uuid: ded09e89-5a52-4e8c-a6f7-3e25b4191183
translation-type: tm+mt
source-git-commit: f21a3f7fe0aeaab517a5ca36da43594873b3e69a

---


# Vertikale Aktualisierung{#about-vertical-update}

Mit Vertikaler Aktualisierung können Sie Teile Ihres Indexes schnell aktualisieren, ohne große Datenmengen verarbeiten zu müssen.

## Vertikale Aktualisierung verwenden {#concept_E65A70C9C2E04804BF24FBE1B3CAD899}

Ein vertikaler Index dauert nur wenige Sekunden und ist nützlich auf E-Commerce-Websites mit hoher Kapazität, die viele Stunden bis zum vollständigen oder inkrementellen Index dauern können.

Wenn Sie einen vertikalen Index generieren, werden Statusinformationen wie Startzeit, verstrichene Zeit und Fehler während des Indizierungsprozesses angezeigt.

Sie können den vertikalen Indexierungsvorgang jederzeit beenden oder neu starten.

Während der neue vertikale Index Ihre Live-Website aktualisiert, können Kunden weiterhin Ihre Site anhand Ihres aktuellen Indexes suchen.

>[!NOTE]
>
>Diese Funktion ist in [!DNL Adobe Search&Promote]der Standardeinstellung nicht aktiviert. Wenden Sie sich an den technischen Support, um die Funktion für Ihre Verwendung zu aktivieren.

Vertikale Updates sind speziell für eCommerce- [!DNL Adobe Search&Promote] Konten vorgesehen, die IndexConnector verwenden, um den Inhalt für den Suchindex bereitzustellen. Der typische Anwendungsfall ist ein Fall, bei dem der [!DNL Adobe Search&Promote] Index einen durchsuchbaren Produktkatalog darstellt und die Notwendigkeit besteht, häufig veränderte Werte, wie z.B. Inventar-on-hand, Verfügbarkeit und/oder Preis, schnell aktualisieren zu können. Ein vertikales Update ähnelt einem Inkrementalindex, allerdings werden nur Teile der einzelnen Dokumente aktualisiert, während ein Inkrementalindex ganze Dokumente durch neue Versionen ersetzt.

Der Begriff &quot;Vertikale Aktualisierung&quot;bezieht sich auf die Vorstellung, dass ein [!DNL Adobe Search&Promote] Index als Spaltentabelle dargestellt werden kann, wobei jede Spalte einer [!DNL Adobe Search&Promote] Metadatenfelddefinition entspricht und jede Zeile einem Dokument entspricht. Der Vorgang &quot;Vertikale Aktualisierung&quot;ersetzt eine oder mehrere Spalten, ohne dass der Inhalt der anderen Spalten geändert werden muss.

Wenn die Hauptquelle für Inhalte, ein IndexConnector-Feed, alle erforderlichen Datenelemente enthält, um den Index zu erstellen, ist der Vertikale Update-Feed eine Untergruppe des Hauptfeeds, die dasselbe IndexConnector-Schema verwendet, um die Datenelemente zu definieren, die jedoch *nur* die zu aktualisierenden Datenelemente enthalten.

Der vertikale Update-Feed muss mindestens das Element &quot;Primärschlüssel&quot;enthalten (wie mit dem Kontrollkästchen &quot; **Primärschlüssel** &quot;in der IndexConnector-Konfiguration angegeben) und mindestens ein zu aktualisierendes Datenelement.

Ein primärer IndexConnector-Feed könnte z. B. wie folgt aussehen (in der Regel jedoch mit vielen weiteren Datenelementen):

```xml
<?xml version="1.0" encoding="UTF-8"?>
<products>
<product>
  <id><![CDATA[123]]></id>
  <title><![CDATA[Title for product 123]]></title>
  <description><![CDATA[Description for product 123.]]></description>
  <price>3.99</price>
  <link><![CDATA[https://www.somewhere.com/products/123]]></link>
  <image><![CDATA[https://www.somewher.com/images/products/123.jpg]]></image>
  <label><![CDATA[PROD123]]></label>
  <inventory>100</inventory>
  <brand><![CDATA[brand123]]></brand>
  ...
</product>
<product>
...
</product>
</products>
```

Eine Anforderung besteht darin, schnell nur die `<price>` und `<inventory>` Werte aktualisieren zu können, da sich diese Werte schnell auf der Site des Kunden ändern können. Ein vertikaler Update-Feed könnte dann wie folgt aussehen:

```xml
<?xml version="1.0" encoding="UTF-8"?>
<products>
<product>
  <id><![CDATA[123]]></id>
  <price>3.50</price>
  <inventory>90</inventory>
</product>
<product>
...
</product>
</products>
```

Diese Informationen werden in der Regel in einer separaten Datei auf dem Server des Kunden gespeichert, und die Konfigurationseinstellung &quot;Vertikaler Dateipfad&quot;von IndexConnector verweist auf diese Datei. Der Vorgang &quot;Vertikale Aktualisierung&quot;liest diesen neuen Inhalt und aktualisiert den vorhandenen [!DNL Adobe Search&Promote] Index, wobei nur die Werte für `<price>` und `<inventory>`, in diesem Fall, aktualisiert werden. Bei nachfolgenden Suchen werden die neu aktualisierten Inhalte zurückgegeben.

>[!NOTE]
In diesem Beispiel müssen die Felder `<price>` und `<inventory>` Metadaten mit aktivierter Option &quot; **Vertikales Aktualisierungsfeld** &quot;definiert sein.

Siehe auch [Info zur Remote-Steuerung für Indizierung](../c-about-index-menu/c-about-remote-control-for-indexing.md#concept_C79B322190E84106A434E5C6D4A4118F) und [Hinzufügen eines neuen Meta-Tag-Felds](../c-about-settings-menu/c-about-metadata-menu.md#task_6DF188C0FC7F4831A4444CA9AFA615E5).

## Konfigurieren eines vertikalen Updates einer gestaffelten Website {#task_46A367B0786C4C90BFFA5D3F95FD86C0}

Sie können konfigurieren, welche Index Connector-Quellen Sie in Ihre vertikale Aktualisierung aufnehmen möchten, indem Sie URLs angeben.

**So konfigurieren Sie ein vertikales Update einer gestaffelten Website**

1. Klicken Sie im Produktmenü auf **[!UICONTROL Index]** > **[!UICONTROL Vertical Update]** > **[!UICONTROL Configuration]**.
1. Geben Sie auf der **[!UICONTROL Vertical Update Configuration]** Seite im Feld URLs aktualisieren die URLs der Seiten an, die Sie indizieren möchten.

   Der Suchroboter aktualisiert nur die Dokumente, die in den angegebenen Index Connector-Quellen identifiziert werden.

   Dieses Feld darf nur die Index Connector-URLs enthalten, wie im folgenden Beispiel gezeigt:

   `index:product_catalog`.
1. Klicken **[!UICONTROL Save Changes]**.
1. (Optional) Führen Sie einen der folgenden Schritte aus:

   * Klicken Sie auf **[!UICONTROL History]** , um alle vorgenommenen Änderungen wiederherzustellen.

      Siehe [Verwenden der Option](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)Verlauf.

   * Klicken **[!UICONTROL Live]**.

      Siehe [Live-Einstellungen](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)anzeigen.

   * Klicken **[!UICONTROL Push Live]**.

      Siehe [Pushing-Einstellungen](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Anzeigen des Protokolls &quot;Vertikale Aktualisierung&quot;einer Live- oder Stage-Website {#task_E668E1F1240C476DAA1CA783DC728232}

Wenn ein vertikales Live-Update oder ein gestaffeltes vertikales Update abgeschlossen ist, können Sie das zugehörige Protokoll anzeigen, um Fehler zu beheben, die möglicherweise aufgetreten sind.

Sie können keine Protokolldateien mit vertikaler Aktualisierung exportieren und auch nicht speichern. Die Protokolldatei bleibt bis zum nächsten Index verfügbar.

**So zeigen Sie das Protokoll &quot;Vertikale Aktualisierung&quot;einer Live- oder Stage-Website an**

1. Führen Sie im Produktmenü einen der folgenden Schritte aus:

   * Klicken Sie auf **[!UICONTROL Index]** > **[!UICONTROL Vertical Update]** > **[!UICONTROL Live Log]**.

   * Klicken Sie auf **[!UICONTROL Index]** > **[!UICONTROL Vertical Update]** > **[!UICONTROL Staged Log]**.

1. Führen Sie auf der Protokollseite oben oder unten einen der folgenden Schritte aus:

   * Verwenden Sie die Navigationsoptionen **[!UICONTROL First]**, **[!UICONTROL Prev]**, **[!UICONTROL Next]**, **[!UICONTROL Last]** oder **[!UICONTROL Go to line]** , um durch das Protokoll zu navigieren.

   * Verwenden Sie die Anzeigeoptionen **[!UICONTROL Errors only]**, **[!UICONTROL Wrap line]** oder **[!UICONTROL Show]** , um Ihre Anzeige zu verfeinern.

