---
description: Search&amp;Promote 8.14.0 Versionshinweise.
solution: Target
title: Search&amp;Promote 8.14.0 Versionshinweise (22.05.2014)
topic: Release Notes,Site search and merchandising
uuid: 308d84a9-ec38-4fec-b146-e8a353e65be4
translation-type: tm+mt
source-git-commit: d015154efdccbb4c6a39a56907c0c337ec065c9f
workflow-type: tm+mt
source-wordcount: '102'
ht-degree: 63%

---


# Search&amp;Promote 8.14.0 Versionshinweise (22.05.2014){#search-promote-release-notes}

**Fehlerkorrekturen**

* Wenn [!DNL sqlite_open] fehlschlägt, wird die alte sqlite-Datenbank entfernt, und es wird eine vollständig neue Datenbank erstellt.
* Kernsuchergebnisse wurden inkonsistent, wenn dieselbe Suche wiederholt wurde.
* Leistungsverbesserung der Vorlagenverarbeitung, wenn pro Suchergebnis sehr viele Felder ausgegeben werden müssen.
* Hinweise zu **[!UICONTROL Business Rule History]** hinzugefügt.
* Die Leistung der ergebnisbasierten Trigger und der Regenerationsphase des Aktionsvorschauindex hat sich bei Indexierungsvorgängen im Laufe der Zeit ständig verschlechtert.
* Die Option **[!UICONTROL Reset SPIN cache]** wurde von &quot;boolean no/next-run&quot;in &quot;tri-state&quot;geändert: no/always/next-run.

