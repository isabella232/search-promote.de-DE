---
description: Mit Ausgeschlossenen Wörtern können Sie häufig verwendete Ausdrücke und häufig verwendete Wörter wie "a"und "the"angeben, die Sie aus den Suchergebnissen auslassen möchten.
solution: Target
title: Info zu ausgeschlossenen Wörtern
topic-legacy: Linguistics,Site search and merchandising
uuid: 1c879462-1b19-44f6-a3b2-20aa786b3221
exl-id: d553b776-907a-4f4a-8481-b36dc0cb75c9
translation-type: tm+mt
source-git-commit: 7559f5f7437d46e3510d4659772308666425ec96
workflow-type: tm+mt
source-wordcount: '683'
ht-degree: 0%

---

# Info zu ausgeschlossenen Wörtern{#about-excluded-words}

Mit Ausgeschlossenen Wörtern können Sie häufig verwendete Ausdrücke und häufig verwendete Wörter wie &quot;a&quot;und &quot;the&quot;angeben, die Sie aus den Suchergebnissen auslassen möchten.

## Verwenden von ausgeschlossenen Wörtern {#concept_9DB67BD2F0DC43AC88741003D9F39812}

Siehe auch [Suchvorgänge](../c-about-settings-menu/c-about-searching-menu.md#concept_207105CF26B1448F8A3D223787C56AB8).

Ohne ausgeschlossene Wörter können Suchvorgänge, die diese Wörter enthalten, zahlreiche irrelevante Ergebnisse identifizieren. Wenn Sie Wörter und Wortgruppen ausschließen, werden Suchergebnisse weggelassen, die nur mit den von Ihnen angegebenen ausgeschlossenen Begriffen übereinstimmen. Wenn eine Suchbegriffe ein ausgeschlossenes Abfrage enthält, werden nur die nicht ausgeschlossenen Wörter verwendet, um Dokumente zu finden.

Ausgeschlossene Suchbegriffe werden in den Suchergebnissen nicht hervorgehoben. Der Relevanzwert jedes Ergebnisses wird jedoch durch die ausgeschlossenen Wörter beeinflusst. Ausgeschlossene Wörter werden also bei der Suche nach Dokumenten ignoriert, aber sie werden weiterhin verwendet, wenn die Dokumente auf der Suchergebnisseite nach Rang geordnet werden. Bevor die Auswirkungen der Einstellungen für &quot;Ausgeschlossene Wörter&quot;(oder Änderungen an diesen Einstellungen) für Kunden verfügbar sind, müssen Sie Ihren Site-Index neu generieren.

Wenn Sie Wörter eingeben, die aus den Suchergebnissen ausgeschlossen werden sollen, trennen Sie Wörter oder Wortgruppen voneinander durch Kommas. Sie können pro Zeile ein oder mehrere ausgeschlossene Wörter eingeben. Im Folgenden finden Sie ein Beispiel für ausgeschlossene Wörter in separaten Zeilen und dividiert durch Kommas.

![](assets/excluded_words_1.jpg)

Wenn Ihr Kunde anhand der obigen Liste der ausgeschlossenen Wörter nach &quot;USA-Staaten&quot;sucht, werden das Wort &quot;USA&quot;und das Wort &quot;USA&quot;von der Suche ausgeschlossen. Stattdessen findet die Suche alle Seiten, die die Wörter &quot;vereint&quot;, &quot;Bundesstaaten&quot;und &quot;Amerika&quot;enthalten. Seiten, die nur das Wort &quot;of&quot;oder &quot;the&quot;enthalten, werden nicht angezeigt.

Einige Sites enthalten bestimmte Ausdrücke auf den meisten oder allen Seiten. Eine Website zum Thema Tourismus in New York City könnte beispielsweise die Wörter New York im Titel jeder Seite enthalten. Erwägen Sie, diese Wortgruppe und andere ähnliche Begriffe zur Liste zum Ausschließen hinzuzufügen:

![](assets/excluded_words_2.jpg)

Wenn eine Wortgruppe ausgeschlossen wird, werden die einzelnen Wörter, aus denen sie besteht, weiterhin als Suchbegriffe verwendet. Nur wenn ein Besucher in der exakten Reihenfolge eines ausgeschlossenen Satzes nach den genauen Wörtern sucht, wird der Begriff aus den Suchergebnissen ausgeschlossen. Wenn ein Kunde anhand des obigen Beispiels nach dem &quot;neuen York-Ballet&quot;sucht, werden das Wort &quot;the&quot;und der Satz &quot;new york&quot;ausgeschlossen. Nur Seiten, die das Wort &quot;Ballett&quot;enthalten, werden als Suchergebnis zurückgegeben. Auf der anderen Seite findet eine Suche nach &quot;neuen Gebäuden&quot;oder &quot;Herzog von York&quot;immer noch Seiten, die das Wort &quot;neu&quot;bzw. &quot;york&quot;enthalten.

## Konfigurieren von ausgeschlossenen Wörtern {#task_60BF6BB7A66C48479D2BBB32C0F38CDE}

Sie können häufig verwendete Ausdrücke und häufig verwendete Wörter aus Ihren Suchergebnissen ausschließen.

Sie können ein oder mehrere Wörter pro Zeile eingeben. Trennen Sie jedes Wort durch Kommas, wie im folgenden Beispiel:

![](assets/excluded_words_1.jpg)

Sie können auswählen, dass Suchergebnisse angezeigt werden, wenn alle Wörter in der Kundensuche ausgeschlossene Wörter sind. Wenn Sie beispielsweise das Wort &quot;das&quot;ausgeschlossen haben und ein Kunde sich dafür entscheidet, nur nach &quot;dem&quot;zu suchen, zeigen die Suchergebnisse jede Seite an, die das Wort &quot;das&quot;enthält. Dieses Ergebnis ist wahr, auch wenn das Wort &quot;the&quot;ausgeschlossen ist. Wenn Sie diese Option nicht aktivieren, erhält der Kunde keine Suchergebnisse. Diese Einstellung hat keine Auswirkung, wenn die Suche mindestens ein nicht ausgeschlossenes Wort enthält.

**So konfigurieren Sie ausgeschlossene Wörter**

1. Klicken Sie im Produktmenü auf **[!UICONTROL Linguistics]** > **[!UICONTROL Excluded Words]**.
1. Geben Sie auf der Seite [!DNL Excluded Words] im Textfeld **[!UICONTROL Words and Phrases]** die Wörter ein, die Sie aus den Suchergebnissen ausschließen möchten.
1. (Optional) Klicken Sie auf **[!UICONTROL Show results when all words in the query are excluded words]**.

   Wenn alle Wörter in der Kundensuche ausgeschlossen sind, werden alle Wörter zusammen verwendet, um die Suche durchzuführen.
1. Klicken **[!UICONTROL Save Changes]**.
1. Um die Ergebnisse Ihrer Änderungen Vorschau, klicken Sie auf **[!UICONTROL regenerate your staged site index]**, um den Index Ihrer gestaffelten Website neu zu erstellen.

   Siehe [Ausführen eines vollständigen Indexes einer Live- oder Staged-Website...](../c-about-index-menu/c-about-full-index.md#task_F7FE04D8A1654A7787FCCA31B45EB42D).

   Siehe [Ausführen eines inkrementellen Indexes einer Live- oder Staged-Website...](../c-about-index-menu/c-about-incremental-index.md#task_9BFB6157F3884B2FAECB7E0E9CA318CB).
1. (Optional) Klicken Sie im Produktmenü auf **[!UICONTROL Linguistics]** > **[!UICONTROL Excluded Words]** und führen Sie dann einen der folgenden Schritte aus:

   * Klicken Sie auf **[!UICONTROL History]**, um alle vorgenommenen Änderungen wiederherzustellen.

      Siehe [Verwenden der Option Verlauf](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Klicken **[!UICONTROL Live]**.

      Siehe [Live-Einstellungen anzeigen](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Klicken **[!UICONTROL Push Live]**.

      Siehe [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).
