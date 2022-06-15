---
title: Unit-Database
description: 
published: true
date: 2022-06-15T09:45:22.683Z
tags: 
editor: markdown
dateCreated: 2021-12-24T23:47:16.475Z
---

Jede Statistik einer jeden Einheit in SC: FAF kann derzeit in 2 Einheiten-Datenbanken gefunden werden:
- [Spooky](https://spooky.github.io/unitdb/#/)
- [Offiziell](https://unitdb.faforever.com/)

## Wie man es benutzt
- Klicken Sie auf den Namen einer Einheit, um deren detaillierte Statistiken auf einer neuen Seite zu sehen
- Klicken Sie auf das Feld der Einheit und dann auf das Feld von bis zu 3 anderen Einheiten, um mehrere Einheiten auszuwählen
- Klicke auf die Schaltfläche "Einheiten vergleichen..." am unteren Rand, um diese Einheiten zu vergleichen

![unitdb.png](/unitdb.png)
## Spielzeit für eine Einheit
Um zu berechnen, wie lange es dauert, eine Einheit zu bauen, benötigen wir 2 Werte aus der Einheitendatenbank: Baurate und Bauzeit.
- Baurate - wie schnell eine Einheit gebaut werden kann
- Bauzeit - wie lange es dauert, eine Einheit zu bauen

Um den tatsächlichen Wert in Sekunden zu erhalten, verwenden wir diese Formel:
- Bauzeit / Baurate = Unser Wert in Sekunden
**Beispiel:**
T3-Energie baut Monkeylord:
15750 / 30 = 525 (Sekunden)
525 / 60 = 8 min 45 sec
![build_rate.png](/images/build_rate.png)
![build_time.png](/images/build_time.png)
{.is-info}