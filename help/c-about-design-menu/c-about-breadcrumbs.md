---
description: Breadcrumbs sind eine Navigationssteuerung, die Sie Ihrer Website hinzufügen können. Der Breadcrumb gibt Kunden Rückmeldungen darüber, wo sie sich in einem Suchergebnissatz befinden. Es hilft ihnen auch, schnell zu einem vorherigen Schritt zurückzukehren.
solution: Target
subtopic: Navigation
title: Info zu Breadcrumbs
topic-legacy: Design,Site search and merchandising
uuid: 3e630a72-a631-4f4f-8aa5-adf2882cdf1c
exl-id: e668d706-6899-4db9-968b-d98df9090ad9
translation-type: tm+mt
source-git-commit: 7559f5f7437d46e3510d4659772308666425ec96
workflow-type: tm+mt
source-wordcount: '750'
ht-degree: 1%

---

# Info zu Breadcrumbs{#about-breadcrumbs}

Breadcrumbs sind eine Navigationssteuerung, die Sie Ihrer Website hinzufügen können. Der Breadcrumb gibt Kunden Rückmeldungen darüber, wo sie sich in einem Suchergebnissatz befinden. Es hilft ihnen auch, schnell zu einem vorherigen Schritt zurückzukehren.

## Verwenden von Breadcrumbs {#concept_FB8A943C594A4A1593B118141DA61F03}

Die Breadcrumbs verfolgen den gesuchten Begriff und die nachfolgenden Facetten, die ausgewählt wurden, um die Ergebnismenge einzugrenzen.

Verwenden Sie die Breadcrumb-Einstellungen, um die Breadcrumb-Steuerung der Ebene Ihrer Suchpräsentation anzupassen. Wenn Ihre Präsentationsebene über mehrere Suchergebnisse verfügt, wirkt das Breadcrumb-Steuerelement auf die primäre Suche auf der Seite.

Sie können einen Breadcrumb bearbeiten, um das Standardverhalten, die maximale Wertebreite und die Werterweiterung zu ändern und festzulegen, ob der Begriff &quot;Abfrage&quot;einbezogen werden soll.

## Hinzufügen eines neuen Breadcrumbs {#task_2FFA94F82AE74F10BDDE7367CDCEAE8B}

Sie können eine Breadcrumb-Leiste hinzufügen, damit ein Kunde verfolgen kann, wo er sich auf Ihrer Website befindet.

<!-- 

t_adding_a_new_breadcrumb.xml

 -->

>[!NOTE]
>
>Verweisen Sie auf den Breadcrumb in Ihrer Präsentationsvorlage, damit er auf der Website angezeigt wird.

**So fügen Sie eine neue Breadcrumb hinzu**

1. Klicken Sie im Produktmenü auf **[!UICONTROL Design]** > **[!UICONTROL Navigation]** > **[!UICONTROL Breadcrumbs]**.
1. Klicken Sie auf der Seite [!DNL Breadcrumbs] auf **[!UICONTROL Add Breadcrumb]**.
1. Legen Sie auf der Seite [!DNL Add Breadcrumb] die gewünschten Optionen fest.

   Diese Einstellungen wirken sich sowohl auf das Verhalten als auch auf die Standarddarstellung eines Breadcrumbs aus. Sie können einige dieser Einstellungen mithilfe der Einstellungen der Präsentationsvorlage überschreiben.

   <!-- 
   
   r_breadcrumb_options.xml
    
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
      <td colname="col1"> <p>Breadcrumb-Name </p> </td> 
      <td colname="col2"> <p>Der Name des Breadcrumbs. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Verhalten </p> </td> 
      <td colname="col2"> <p>Legt eines der drei folgenden Breadcrumb-Verhalten fest: </p> <p> 
      <ul id="ul_7E66ACC1DA494B20BEC3B0B2CCAB103A"> 
        <li id="li_D81876660A8B48AFB70D3317063FBF6F"> <span class="uicontrol"> Goto  </span> <p>Goto entfernt alle Breadcrumbs nach dem angeklickten und Beginn eine neue Suche an diesem Punkt. </p> </li> 
        <li id="li_63AE06B544B64DCAA8C55031B3DFFFF7"> <span class="uicontrol"> Entfernen </span> <p>Entfernen Sie löscht den Pfad des Breadcrumbs, auf den der Kunde geklickt hat, und Beginn dann eine neue Suche. Dieses Verhalten ist nützlich, wenn Sie dem Kunden das Rückgängigmachen von Schritten beim Drilldown durch die Suche ermöglichen möchten. </p> </li> 
        <li id="li_EEC810D420FF41498ECE49EBAAB33BE5"> <span class="uicontrol"> Drop  </span> <p>Drop entfernt alle Breadcrumbs. </p> </li> 
      </ul> </p> <p> Angenommen, Sie haben einen Breadcrumb von 1 &gt; 2 &gt; 3 &gt; 4. Wenn ein Kunde auf "2"klickt, hat er je nach ausgewähltem Verhalten die folgenden Ergebnisse: </p> <p> 
      <ul id="ul_96FCD8E4C3704B45B59BC18A7A1AC52A"> 
        <li id="li_B880037088DF426F880788EAA3072180">Zu - 1 &gt; 2 </li> 
        <li id="li_D0F07A15DCD043EFA4563632ED33A9E2">Entfernen - 1 &gt; 3 &gt; 4 </li> 
        <li id="li_D848ED44B4E44538AA92010F9F186224"> Drop - Der gesamte Breadcrumb wird entfernt, sodass der Kunde zum Punkt zurückkehrt, bevor er mit dem Drilldown begonnen hat. </li> 
      </ul> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Breite des maximalen Werts </p> </td> 
      <td colname="col2"> <p>Gibt die Länge der einzelnen Werte im Breadcrumb-Pfad an. Sie geben die Einstellung als Anzahl von Zeichen an. </p> <p>Eine Einstellung von 6 bedeutet beispielsweise, dass der Breadcrumb-Pfad bis zu 6 Zeichen lang sein kann, einschließlich Leerzeichen. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Werterweiterung </p> </td> 
      <td colname="col2"> <p>Gibt die Ellipsen an, die verwendet werden sollen, wenn ein Breadcrumb abgeschnitten wird. </p> <p>Standardmäßig ein "..." (Ellipsen) verwendet. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Begriff Abfrage einschließen </p> </td> 
      <td colname="col2"> <p>Steuert das Vorhandensein von Abfragen in einem Breadcrumb. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Benutzerdefinierte Crumbs aktivieren </p> </td> 
      <td colname="col2"> <p>Aktivieren Sie diese Option, damit Sie die benutzerdefinierten Elemente in Breadcrumbs mit den Parametern <span class="codeph"> uX=[Name]&amp;[Name]=[Wert] </span> in der URL verwenden können. Sie können Verarbeitungsregeln verwenden, um diese Parameter wie gewünscht zu behandeln. </p> <p>Wenn diese Funktion beispielsweise aktiviert ist und Sie die URL <code> https://search.host.com/?1=category&amp;q1=Clothes&amp;u2= 
          type&amp;type=Men&amp;x3=kind&amp;q3=Sweater </code> haben, wenn Sie Facetten <span class="codeph"> <span class="varname"> Kategorie </span> </span> und <span class="codeph"> <span class="varname"> kind </span> </span> haben, sieht Ihr Breadcrumb wie <span class="codeph"> Kleidung &gt; Männer &gt; Pullover </span> aus.. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Benutzerdefinierte Crumb-Namen </p> </td> 
      <td colname="col2"> <p>Eine kommagetrennte Liste aller möglichen Namen von benutzerdefinierten Breadcrumb-Elementen. </p> <p>Diese Option ist nur verfügbar, wenn Sie <span class="uicontrol"> Benutzerdefinierte Crumbs aktivieren </span> aktivieren. </p> </td> 
      </tr> 
    </tbody> 
    </table>

1. Klicken **[!UICONTROL Add]**.
1. (Optional) Führen Sie auf der Seite [!DNL Breadcrumbs] einen der folgenden Schritte aus:

   * Klicken Sie auf **[!UICONTROL History]**, um alle vorgenommenen Änderungen wiederherzustellen.

      Siehe [Verwenden der Option Verlauf](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Klicken **[!UICONTROL Live]**.

      Siehe [Live-Einstellungen anzeigen](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Klicken **[!UICONTROL Push Live]**.

      Siehe [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Bearbeiten eines Breadcrumbs {#task_583481D9A23E4E0F97AEB18E72CBE13F}

Sie können die Einstellungen aller hinzugefügten Breadcrumbs bearbeiten.

<!-- 

t_editing_a_breadcrumb.xml

 -->

>[!NOTE]
>
>Verweisen Sie auf den Breadcrumb in Ihrer Präsentationsvorlage, damit er auf der Website angezeigt wird.

**So bearbeiten Sie einen Breadcrumb**

1. Klicken Sie im Produktmenü auf **[!UICONTROL Design]** > **[!UICONTROL Navigation]** > **[!UICONTROL Breadcrumbs]**.
1. Klicken Sie auf der Seite [!DNL Breadcrumbs] auf **[!UICONTROL Edit]** ganz rechts neben einem Breadcrumb-Namen.
1. Legen Sie auf der Seite [!DNL Edit Breadcrumb] die gewünschten Optionen fest.

   Siehe die Tabelle der Optionen unter [Hinzufügen eines neuen Breadcrumbs](../c-about-design-menu/c-about-breadcrumbs.md#task_2FFA94F82AE74F10BDDE7367CDCEAE8B).
1. Klicken **[!UICONTROL Save Changes]**.
1. (Optional) Führen Sie auf der Seite **[!UICONTROL Breadcrumb]** einen der folgenden Schritte aus:

   * Klicken Sie auf **[!UICONTROL History]**, um alle vorgenommenen Änderungen wiederherzustellen.

      Siehe [Verwenden der Option Verlauf](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Klicken **[!UICONTROL Live]**.

      Siehe [Live-Einstellungen anzeigen](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Klicken **[!UICONTROL Push Live]**.

      Siehe [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Löschen eines Breadcrumbs {#task_401C6E481A744284906E15A29E04F757}

Sie können alle hinzugefügten Breadcrumbs löschen.

<!-- 

t_deleting_a_breadcrumb.xml

 -->

**So löschen Sie eine Breadcrumb**

1. Klicken Sie im Produktmenü auf **[!UICONTROL Design]** > **[!UICONTROL Navigation]** > **[!UICONTROL Breadcrumbs]**.
1. Klicken Sie auf der Seite [!DNL Breadcrumbs] auf **[!UICONTROL Delete]** ganz rechts neben einem Breadcrumb-Namen.
1. Klicken Sie im Dialogfeld [!DNL Confirmation] auf **[!UICONTROL OK]**.
1. (Optional) Führen Sie einen der folgenden Schritte aus:

   * Klicken Sie auf **[!UICONTROL History]**, um alle vorgenommenen Änderungen wiederherzustellen.

      Siehe [Verwenden der Option Verlauf](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Klicken **[!UICONTROL Live]**.

      Siehe [Live-Einstellungen anzeigen](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Klicken **[!UICONTROL Push Live]**.

      Siehe [Pushing stage settings live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).
