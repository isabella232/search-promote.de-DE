---
description: Sie können "Meinten Sie" so konfigurieren, dass Kunden Vorschläge für gültige Suchbegriffe gegeben werden, wenn sie fehlgeschlagene Suchen ausprobiert haben. Vorschläge werden erstellt, indem nach Rechtschreibkorrekturen gesucht und die Suchbegriffe eingegeben werden, die zu einer gültigen Suche führen.
solution: Target
title: Meinten Sie
topic: Linguistics,Site search and merchandising
uuid: c5973541-3d6b-4fc9-bad4-66d4d3559fe8
translation-type: tm+mt
source-git-commit: d015154efdccbb4c6a39a56907c0c337ec065c9f
workflow-type: tm+mt
source-wordcount: '733'
ht-degree: 2%

---


# Meinten Sie {#about-did-you-mean}

Sie können &quot;Meinten Sie&quot; so konfigurieren, dass Kunden Vorschläge für gültige Suchbegriffe gegeben werden, wenn sie fehlgeschlagene Suchen ausprobiert haben. Vorschläge werden erstellt, indem nach Rechtschreibkorrekturen gesucht und die Suchbegriffe eingegeben werden, die zu einer gültigen Suche führen.

## Konfigurieren bedeutete {#task_B539D6A0043547EFB1CA19B67E762371}

Sie können festlegen, wie [!DNL site search/merchandising] Suchvorschläge macht, wenn die Abfrage des Kunden keine oder nur minimale Suchergebnisse zurückgibt.

<!-- 

t_configuring_did_you_mean.xml

 -->

**Zur Konfiguration von**

1. Klicken Sie im Produktmenü auf **[!UICONTROL Linguistics]** > **[!UICONTROL Did You Mean]**.
1. Geben Sie auf der Seite [!DNL Did You Mean] im Textfeld **Entfernen Sie diese Wörter aus Empfehlungen** Leerzeichen oder durch Zeilen getrennte Wörter ein, um unerwünschte Vorschläge zu filtern.

   Dies sind Wörter in Ihrem Suchindex, die nicht als empfohlene alternative Suchbegriffe angezeigt werden. Sie können alle Wörter, die einem Muster entsprechen, mithilfe von regulären Ausdrücken ausschließen. Andernfalls wird nur das genaue Wort entfernt.

1. Legen Sie die gewünschten Optionen für **Hat Sie &lt;** festgelegt.

   <!-- 
   
   r_did_you_mean_options.xml
   
   -->

   <table> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> <p>Option </p> </th> 
      <th colname="col2" class="entry"> <p>Beschreibung </p> </th> 
      </tr> 
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <p>Empfehlungsalgorithmus </p> </td> 
      <td colname="col2"> <p>Stellt fest, wie weit die Software geht, um Vorschläge zu finden. Wenn ein Benutzer einen Fehler aus einem Buchstaben macht, erhalten alle Algorithmen dieselben Vorschläge. Der Grund dafür ist, dass es nur eine Bearbeitung braucht, um einen funktionierenden Vorschlag zu erhalten, und alle Algorithmen finden Wörter, die dem Original nahe sind. Wenn die ursprünglichen Suchbegriffe jedoch nicht den vorhandenen Begriffen im Index ähnlich sind, suchen die <b>Deep</b>- und <b>Bad Spellers</b>-Empfehlungsalgorithmen weiterhin nach möglichen Vorschlägen. Dieses Szenario ist nützlich, wenn ein Kunde einen eigenen Namen versucht, der schwer einzugeben ist, und die Namen ausgelesen werden. Wenn Sie jedoch nur ähnliche Vorschläge anzeigen möchten, können Sie den Algorithmus <b>Quick</b> wählen. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Standardanzahl der anzuzeigenden Vorschläge </p> </td> 
      <td colname="col2"> <p>Gibt die Anzahl der "Meinten Sie"-Vorschläge (0-20) an, die angezeigt werden sollen, wenn die Suche eines Kunden keine Ergebnisse zurückgibt. Die Standardeinstellung ist „3“. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Minimale Wortlänge des Vorschlags </p> </td> 
      <td colname="col2"> <p>Prunes Haben Sie Begriffe gemeint, indem Sie die Mindestanzahl von Buchstaben für ein vorgeschlagenes Wort angeben. </p> <p>Wenn Sie den Wert beispielsweise auf 4 setzen, schlägt die Software kein Wort mit einer Länge von 1, 2 oder 3 Zeichen vor. Wenn Sie den Wert 0 angeben, werden keine kurzen Wörter aus den Begriffsvorschlägen entfernt. Wenn Sie einen hohen Wert angeben, führt dies in der Regel zu keinen Begriffsvorschlägen. Der Standardwert lautet 3. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Mindestindex-Frequenz </p> </td> 
      <td colname="col2"> <p> Gibt an, wie oft ein Wort mindestens im Index angezeigt werden muss, bevor es im Wörterbuch "Meinten Sie"enthalten ist. </p> <p>Sie können keine negative Zahl im Feld angeben. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Suchen Sie nach einem vorgeschlagenen Begriff, wenn keine Ergebnisse vorliegen </p> </td> 
      <td colname="col2"> <p>Sucht automatisch nach dem ersten vorgeschlagenen Begriff, wenn die Suche eines Kunden keine Ergebnisse liefert und es mindestens einen "Meinten Sie"-Begriff-Vorschlag gibt. </p> <p>Sie können die folgenden Tags in Ihrer Präsentationsvorlage verwenden, um anzugeben, dass die Site-Suche/das Merchandising automatisch nach einem anderen Begriff sucht: </p> <p> <code>&nbsp;&lt;guided-if-suggestion-autosearch&gt;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Search&nbsp;for&nbsp;&lt;guided-param&nbsp;gsname="q"&nbsp;/&gt;&nbsp;instead&nbsp;of&nbsp;guided-suggestion-original-query&nbsp;/&gt;&nbsp;&lt;/guided-if-suggestion-autosearch&gt;</code> </p> <p>Hier können Sie auch weitere Vorschläge einblenden. </p> <p> <code>&nbsp;&lt;guided-if-suggestion-autosearch&gt;&nbsp;&nbsp;There&nbsp;was&nbsp;0&nbsp;matches&nbsp;for&nbsp;&lt;guided-suggestion-original-query&nbsp;/&gt;&nbsp;&nbsp;&nbsp;Did&nbsp;You&nbsp;Mean&nbsp;&lt;guided-param&nbsp;gsname="q"&gt;?&nbsp;Here&nbsp;are&nbsp;the&nbsp;results&nbsp;for&nbsp;that&nbsp;search.&nbsp;&nbsp;&nbsp;Or&nbsp;Did&nbsp;You&nbsp;Mean&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-suggestions&gt;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-suggestion-link&gt;&lt;guided-suggestion&nbsp;/&gt;&lt;/guided-suggestion-link&gt;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/guided-suggestions&gt;&nbsp;&lt;/guided-if-suggestion-autosearch&gt;</code> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Vorschläge aufgrund niedriger Ergebnisse erstellen </p> </td> 
      <td colname="col2"> <p>Wenn ein Kunde nach einem Begriff sucht, der weniger als zehn Ergebnisse liefert, prüft die Suchmaschine, ob ein Vorschlag vorliegt, der mehr als 100 Ergebnisse liefern kann. Wenn dies der Fall ist, können Sie die folgenden Tags verwenden, um dem Benutzer anzuzeigen, dass er während der Ergebnisse nach etwas Anderem suchen wollte: </p> <p> <code>&nbsp;&lt;guided-if-suggestion-low-results&gt; &nbsp;&nbsp;You&nbsp;have&nbsp;a&nbsp;low&nbsp;result&nbsp;count&nbsp;for&nbsp;&lt;Search&nbsp;for&nbsp;guided-param&nbsp;gsname="q"&gt;.&nbsp;&nbsp;Did&nbsp;you&nbsp;mean:&nbsp;&lt;guided-suggestion&gt;&lt;guided-suggestion-link&gt;&lt;guided-suggestion&nbsp;/&gt;&lt;/guided-suggestion-link&gt;&lt;guided-if-not-last&gt;,&nbsp;&lt;/guided-if-not-last&gt;&lt;/guided-suggestions&gt;&nbsp;&lt;/guided-if-suggestion-low-results&gt;</code> </p> <p> Im obigen Szenario wird die Anzahl der Vorschläge durch den Wert gesteuert, der unter <span class="uicontrol"> Standardanzahl der Vorschläge angegeben ist, die angezeigt werden sollen. </span> Der niedrige und der hohe Schwellenwert sind durch die folgenden Optionen konfigurierbar. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Vorschläge machen, wenn die ersten Ergebnisse geringer sind als </p> </td> 
      <td colname="col2"> <p>Steuert die Anzahl der Ergebnisse, wenn das System Angebot-Vorschläge Beginn. </p> <p>Diese Option wird nur angezeigt, wenn Sie <span class="uicontrol"> Vorschläge aufgrund niedriger Ergebnisse</span> aktivieren. </p> <p>Die Standardeinstellung ist „10“. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Ein Vorschlag muss mindestens so viele Ergebnisse generieren </p> </td> 
      <td colname="col2"> <p>Filter schlagen vor, die aufgrund der geringen Ergebnisse bei der Primärsuche nach der Ergebniszahl vorgenommen werden. </p> <p>Diese Option wird nur angezeigt, wenn Sie <span class="uicontrol"> Vorschläge aufgrund niedriger Ergebnisse</span> aktivieren. </p> <p>Die Standardeinstellung ist „100“. </p> </td> 
      </tr> 
    </tbody> 
    </table>

1. Klicken Sie auf **Änderungen speichern**.
1. (Optional) Führen Sie einen der folgenden Schritte aus:

   * Klicken Sie auf **[!UICONTROL History]**, um alle vorgenommenen Änderungen wiederherzustellen.

      Siehe [Verwenden der Option Verlauf](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Klicken **[!UICONTROL Live]**.

      Siehe [Live-Einstellungen anzeigen](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Klicken **[!UICONTROL Push Live]**.

      Siehe [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

