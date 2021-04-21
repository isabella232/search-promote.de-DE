---
description: Mit direkten Treffern können Sie einen Kunden zu einer angegebenen URL umleiten, wenn der Kunde nach einem übereinstimmenden Begriff sucht. Mit dieser Funktion können Sie die Navigation der Suche auf Ihrer Website verbessern.
solution: Target
title: Info zu direkten Treffern
topic-legacy: Rules,Site search and merchandising
uuid: 374d63c8-2b82-4165-b543-05b587757baa
exl-id: 251dfa47-f55a-469c-8fca-e187877b7759
translation-type: tm+mt
source-git-commit: 7559f5f7437d46e3510d4659772308666425ec96
workflow-type: tm+mt
source-wordcount: '395'
ht-degree: 1%

---

# Über direkte Treffer{#about-direct-hits}

Mit direkten Treffern können Sie einen Kunden zu einer angegebenen URL umleiten, wenn der Kunde nach einem übereinstimmenden Begriff sucht. Mit dieser Funktion können Sie die Navigation der Suche auf Ihrer Website verbessern.

## Verwenden von direkten Treffern {#concept_C5EE074A19FD4D5B8DD21DB575E35565}

Direkte Treffer bestehen aus zwei Hauptelementen: die URL Ihrer Website und einen oder mehrere durch Kommas getrennte Suchbegriffe. Direkte Treffer werden wie folgt angegeben:

```
    website_URL: term
    website_URL: term, term, term
```

Angenommen, Sie haben eine Firmenwebsite mit einer Seite, auf der alle Ihre Geschäftsbedingungen angegeben sind. Wenn ein Kunde nach Ihren Geschäftsbedingungen sucht, anstatt die Ergebnisse anzuzeigen, können Sie den Kunden zu Ihrer Seite mit Geschäftsbedingungen weiterleiten.

```
    https://www.mycompany.com/policies.asp?article=terms: terms and conditions, terms, conditions, security
    https://www.mycompany.com/press/news.asp: press releases, press
```

Wenn der Begriff &quot;Abfrage&quot;mit keinem direkten Treffer übereinstimmt, werden die Suchergebnisse auf die übliche Weise zurückgegeben.

## Konfigurieren von direkten Treffern {#task_64DFB8C554874C699FCC0C2F26C3669F}

Sie können Suchbegriffe angeben, die einen Webbrowser zu einem URI umleiten, anstatt Suchergebnisse zurückzugeben.

<!-- 

t_configuring_direct_hits.xml

 -->

Leere Zeilen und Kommentarzeilen, die mit einem &quot;#&quot;(Hash) beginnen, sind zulässig.

**So konfigurieren Sie direkte Treffer**

1. Klicken Sie im Produktmenü auf **[!UICONTROL Rules]** > **[!UICONTROL Direct Hits]**.
1. Geben Sie im Feld [!DNL Direct Hits] die URL Ihrer Website sowie einen oder mehrere durch Kommas getrennte Suchbegriffe ein.
1. Klicken **[!UICONTROL Save Changes]**.
1. (Optional) Führen Sie einen der folgenden Schritte aus:

   * Klicken Sie auf **[!UICONTROL History]**, um alle vorgenommenen Änderungen wiederherzustellen.

      Siehe [Verwenden der Option Verlauf](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Klicken **[!UICONTROL Live]**.

      Siehe [Live-Einstellungen anzeigen](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Klicken **[!UICONTROL Push Live]**.

      Siehe [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Testen von direkten Treffern {#task_1E2EA833BF90423AA0DD8C5BBFE77445}

Bevor Sie Regeln für direkte Treffer live übertragen, können Sie direkte Treffer testen, indem Sie einen Begriff eingeben.

<!-- 

t_testing_direct_hits.xml

 -->

Wenn Sie einen Begriff testen, der nicht von einer Direkttrefferregel abgedeckt ist, wird eine Meldung angezeigt, die Sie darüber informiert. In einem solchen Szenario würden die Suchergebnisse wie gewohnt zurückgegeben, wenn die Regel des direkten Treffers auf Ihrer Website live wäre. Wenn Sie einen Begriff testen, der von einer Direkttrefferregel abgedeckt ist, wird eine Meldung angezeigt, die Sie darüber informiert, dass eine Umleitung zur angegebenen URL stattgefunden hat.

**So testen Sie direkte Treffer**

1. Klicken Sie im Produktmenü auf **[!UICONTROL Rules]** > **[!UICONTROL Direct Hits]**.
1. Geben Sie im Feld [!DNL Test Direct Hits] einen Suchbegriff ein und klicken Sie dann auf **[!UICONTROL Test]**.
1. (Optional) Führen Sie einen der folgenden Schritte aus:

   * Klicken Sie auf **[!UICONTROL History]**, um alle vorgenommenen Änderungen wiederherzustellen.

      Siehe [Verwenden der Option Verlauf](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Klicken **[!UICONTROL Live]**.

      Siehe [Live-Einstellungen anzeigen](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Klicken **[!UICONTROL Push Live]**.

      Siehe [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).
