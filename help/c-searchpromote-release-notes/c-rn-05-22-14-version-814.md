---
description: Search&amp;Promote 8.14.0 Versionshinweise.
solution: Target
title: Search&amp;Promote 8.14.0 Versionshinweise (22.05.2014)
topic-legacy: Release Notes,Site search and merchandising
uuid: 308d84a9-ec38-4fec-b146-e8a353e65be4
exl-id: fcc00d85-128e-4015-aa82-7d31606cb076
translation-type: tm+mt
source-git-commit: 7559f5f7437d46e3510d4659772308666425ec96
workflow-type: tm+mt
source-wordcount: '96'
ht-degree: 67%

---

# Search&amp;Promote 8.14.0 Versionshinweise (22.05.2014){#search-promote-release-notes}

**Fehlerkorrekturen**

* Wenn [!DNL sqlite_open] fehlschlägt, wird die alte sqlite-Datenbank entfernt, und es wird eine vollständig neue Datenbank erstellt.
* Kernsuchergebnisse wurden inkonsistent, wenn dieselbe Suche wiederholt wurde.
* Leistungsverbesserung der Vorlagenverarbeitung, wenn pro Suchergebnis sehr viele Felder ausgegeben werden müssen.
* Hinweise zu **[!UICONTROL Business Rule History]** hinzugefügt.
* Die Leistung der ergebnisbasierten Trigger und der Regenerationsphase des Aktionsvorschauindex hat sich bei Indexierungsvorgängen im Laufe der Zeit ständig verschlechtert.
* Die Option **[!UICONTROL Reset SPIN cache]** wurde von &quot;boolean no/next-run&quot;in &quot;tri-state&quot;geändert: no/always/next-run.
