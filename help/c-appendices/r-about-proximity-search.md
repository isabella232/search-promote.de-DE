---
description: Mit der Nahtesuche können Sie eine eindeutige Position mit einer beliebigen Seite Ihrer Website verbinden und dann die Ergebnisse nach Entfernung (Entfernung) zu einer bestimmten Position suchen und sortieren.
seo-description: Mit der Nahtesuche können Sie eine eindeutige Position mit einer beliebigen Seite Ihrer Website verbinden und dann die Ergebnisse nach Entfernung (Entfernung) zu einer bestimmten Position suchen und sortieren.
seo-title: Info zur Bereichssuche
solution: Target
title: Info zur Bereichssuche
topic: Appendices,Site search and merchandising
uuid: 24fc9265-3400-46a7-b6e0-4de5b049a39a
translation-type: tm+mt
source-git-commit: ef818327e1cdaad79ac47575a8dfba1de3dc5c2e
workflow-type: tm+mt
source-wordcount: '779'
ht-degree: 0%

---


# Info zur Suche nach der Nähe{#about-proximity-search}

Mit der Nahtesuche können Sie eine eindeutige Position mit einer beliebigen Seite Ihrer Website verbinden und dann die Ergebnisse nach Entfernung (Entfernung) zu einer bestimmten Position suchen und sortieren.

Angenommen, Sie haben Seiten auf Ihrer Website mit Postleitzahl-Metadaten wie den folgenden in den USA aufgefüllt:

```
<meta name="zipcode" content="84057">
```

Anschließend konfigurieren Sie Ihr Konto, um Ihre ZIP-Code-Metadaten zu indizieren. Auf der Seite **[!UICONTROL Settings]** > **[!UICONTROL Metadata]** > **[!UICONTROL Definitions]** > **[!UICONTROL Add New Field]** legen Sie die folgenden Optionen fest:[!DNL Add Field]

* Feldname: `zip`
* Meta-Tag-Name(n): `zipcode`
* Datentyp: **[!UICONTROL Location]**
* Sortieren: **[!UICONTROL Ascending]**
* Standardeinheiten: **[!UICONTROL Miles]**

Nach der Indexierung Ihrer Site führen Sie die folgende Suche durch:

```
...&sp_q_location_1=84057&sp_x_1=zip&sp_q_max_1=100&sp_s=zip_proximity
```

Die Ergebnismenge enthält alle Dokumente, die sich innerhalb von 100 Meilen von der Postleitzahl 84057 befinden und in aufsteigender Reihenfolge von dieser Postleitzahl sortiert werden.

Sie können auch Telefongebietscodes für Standorte in den USA verwenden. Sie können auch Breiten-/Längengradpaare verwenden, um Positionen in den Metadaten Ihrer Site und in Ihren Suchkriterien anzugeben. Der Standorttyp wird automatisch anhand der bereitgestellten Daten bestimmt.

Drei-stellige Ortswerte (&quot;DDD&quot;, wobei jedes &quot;D&quot;eine Dezimalzahl von 0-9 darstellt) werden als Telefongebietscode der Vereinigten Staaten behandelt.

Fünf- oder vierstellige Werte für den Standort (&quot;DDDD&quot;oder &quot;DDDDD-DDDD&quot;) werden als Postleitzahl der Vereinigten Staaten behandelt.

Positionswerte in exakter Form von &quot;±DD.DDD±DDD.DDDD&quot;werden als Breiten-/Längengrad-Paar behandelt. Der erste signierte numerische Wert gibt den Breitengrad und der zweite signierte numerische Wert den Längengrad an.

**Wichtig**: Wenn Sie einen positiven Breitenwert oder einen positiven Längengradwert oder beides angeben, muss das Zeichen &quot;+&quot;in der URL als  `%2b` kodiert werden. Andernfalls wird das &quot;+&quot;als Leerzeichen interpretiert und der Wert wird nicht als gültiger Ort erkannt. Angenommen, Sie hatten einen Breitenwert +49.2394 und einen Längengradwert von -123.1892. Der Positionsteil der URL mit &quot;+&quot;-kodiert würde wie folgt aussehen:

```
...&sp_q_location_1=%2b49.2394-123.1892...
```

* Positive Breitenwerte stellen Grad nördlich des Äquators dar.
* Negative Breitenwerte stellen Grade südlich des Äquators dar.
* Positive Längengradwerte stellen Grade östlich von Prime Meridian dar.
* Negative Längengradwerte stellen Grade westlich von Prime Meridian dar.

Der Wert &quot;+48.8577+002.2950&quot;entspricht beispielsweise 48.8577 Grad nördlich des Äquators, 2.295 Grad östlich des Premierministers, der exakten Position des Eiffelturms in Paris, Frankreich. Die numerischen Zeichen und jede Ziffer sind erforderlich, auch die führenden und nachfolgenden Nullen. Beispielsweise sind die drei Werte &quot;48.8577+2.2950&quot;, &quot;+48.8577+2.2950&quot;und &quot;+48.8577+02.295&quot;keine Orte. Beim ersten Wert fehlt das vorangestellte Zeichen auf der Breitenfläche. Beim zweiten Wert fehlen die beiden führenden Nullen auf der Länge. Beim dritten Wert fehlt die nachgestellte Null auf dem Längengrad. Achten Sie darauf, dass Sie Ihr Indexprotokoll sorgfältig auf standortbezogene Probleme prüfen.

Wenn Sie nach der Nähe suchen, wird ein spezielles &quot;Proximity Output Field&quot; für diese Suche erstellt. Das Feld wird mit dem relativen Abstand zwischen der in den Suchkriterien angegebenen Position und der Position gefüllt, die mit den einzelnen Suchergebnissen verknüpft ist. Dieses spezielle Feld wird nach dem Ortsnamen-Feld benannt, das in den Suchkriterien verwendet wird, wobei am Ende &quot;_ximity&quot;hinzugefügt wird.

In der obigen Beispielsuche werden die Ergebnisse in aufsteigender Reihenfolge nach &quot;zip_ximity&quot;sortiert. Das heißt, der Abstand zwischen der angegebenen Postleitzahl (84057) und der Position des Postfachs der einzelnen Ergebnisse. Sie können dieses spezielle &quot;Proximity Output Field&quot;auch verwenden, um die relative Entfernung für jedes Suchergebnis in Kilometern oder Meilen anzuzeigen, indem Sie das `<Search-Display-Field>` Search template-Tag verwenden.

Siehe [Suchvorlagen-Tags](../c-appendices/c-templates.md#reference_F7AA3FF602314E42842BBC740D2CA1A4).

Sie können auch ohne die Option sp_s suchen. In diesem Fall werden die Ergebnisse nach dem Ergebnis sortiert (sp_s=0, was der Standardwert ist). Das Ergebnis wird durch den relativen Abstand der einzelnen Ergebnisse von dem Ort der Suche nach der Nähe beeinflusst, der durch den Parameter sp_q_location[_#] angegeben wird. Es wird ein neuer cgi-Parameter sp_q_max_relevant_distanziert[#] hinzugefügt, um optional die Relevanzberechnung zu steuern, die bei der Suche nach der Nähe angewendet wird.

Im Folgenden finden Sie ein Suchbeispiel zur räumlichen Nähe:

```
...&sp_q_location_1=84057&sp_x_1=zip&sp_q_max_1=100&sp_q_2=shirt&sp_x_2=title&sp_q_max_relevant_distance_2=50
```

Die Ergebnismenge enthält alle Dokumente, die sich innerhalb von 100 Meilen von der Postleitzahl 84057 befinden und das Wort &quot;Shirt&quot;im Titelfeld enthalten, sortiert nach Scoring, das durch die Näherungsrelevanz-Bewertung beeinflusst wird. Ein perfekter Relevanzwert für die Komponente &quot;Nähe&quot;würde eine Entfernung von 0 darstellen. Ein Mindestwert für die Relevanz der Komponente &quot;Nähe&quot;würde eine Entfernung von etwas mehr als 50 Meilen darstellen.

Weitere Informationen zur Suche nach räumlicher Nähe finden Sie unter `sp_location`, `sp_location_#`, `sp_q_min`, `sp_q_min_#`, `sp_q_max`, `sp_q_max_#` und `sp_s` im Referenzthema &quot;Search CGI Parameters&quot;.

Siehe [CGI-Parameter suchen](../c-appendices/c-cgiparameters.md#reference_DA27A8B0728246DA94994885E1353890).

Siehe [Hinzufügen eines neuen Meta-Tag-Felds](../c-about-settings-menu/c-about-metadata-menu.md#task_6DF188C0FC7F4831A4444CA9AFA615E5).
