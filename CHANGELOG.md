# Changelog

## v1.1.1 (2026-07-19)

- Gold-Markierung: doppelte Rahmenfärbung im Knoteninneren entfernt, nur noch durchgehendes Overlay und goldener Buchstabe

## v1.1.0 (2026-07-19)

- Kritischer Pfad wird nach vollständiger Lösung in Gold hervorgehoben (Knoten und Pfeile)
- Pfeilrouting: Knick in festem Abstand hinter dem Quellknoten, mehrere Ausgänge fächern in 20px-Schritten auf; Andockpunkte aufs Raster synchronisiert
- Highscore: stabile Sortierung (Fertige nach Zeit, Laufende alphabetisch), zweizeilige Einträge
- Multiplayer: Match-Ende-Meldung und alle Auswertungsausgaben zeilenweise
- Screenshot in der Dokumentation

## v1.0.0 (2026-07-19)

Erste stabile Version. Von beiden Testern im Multiplayer abgenommen.

Enthaltene Funktionsblöcke, in der Reihenfolge ihrer Entstehung:

**Prototyp "Netzplan-Trainer" (helles Design)**
- Aufgabengenerator für Vorgangsknotennetze mit Konsistenzprüfung (GP = SAZ − FAZ, 0 ≤ FP ≤ GP, kritische Pfade durchgehend pufferfrei)
- Zeichenfläche mit frei platzierbaren Knoten und klickbaren Verbindungen
- Getrennte Prüfung von Struktur und Werten mit Feld-Markierung
- Sidebar-Layout, an Fenstergröße angepasst

**Seeds, Statistik, Multiplayer**
- Deterministische Aufgaben-Codes (mulberry32/xmur3), Format L/M/S + 4 Zeichen
- Timer, Versuchs- und Fehlerzähler, lokaler Verlauf (localStorage, 15 Einträge)
- WebRTC-Multiplayer über Trystero: Raum, Aufgaben-Sync, Fortschritts-Broadcast

**Umbenennung in PUFFERZONE, Dark-Redesign**
- Kaltes Teal (#6fdcf7) als Primärakzent, Orange (#ff9028) strikt als Signalfarbe
- Neutrale Grau-Hintergründe, 1px-Linien, Mono-HUD-Labels, Glaspanels
- Abgeschrägte Ecken eingeführt und nach Subpixel-Problemen wieder entfernt

**IHK-konforme Knoten**
- Knotenlayout nach Prüfungsstandard: FAZ/FEZ oben an den Ecken, Nr + Bezeichnung, Dauer/GP/FP, SAZ/SEZ unten; Eckfelder halbhoch, linienbündig
- Quadratische Zellgeometrie, Raster-Snapping (20px), 30px-Randzone
- Freies, ungeprüftes Nr-Feld; Startknoten mit Cyan-Kante markiert
- Löschen per Drag-out statt Button, Verbindungs-Hitbox über den ganzen Knoten

**Orthogonale Kanten und Generator-Tuning**
- Pfeile verlassen Knoten rechts, treffen links, mit Knickwegen und Port-Auffächerung
- Kreuzungsarme Aufgaben: Vorgänger-Spannweite begrenzt (Leicht 2, Mittel 3, Schwer frei), Leicht mit seedgesteuerter Varianz
- Jede Aufgabe garantiert mindestens zwei Zusammenführungen und einen Vorgang mit FP < GP

**Multiplayer-Härtung**
- Wechsel von BitTorrent-Trackern auf Nostr-Relays, STUN-Server für Verbindungen über Netzgrenzen
- Relay-Diagnose in der Statuszeile
- Echtzeit-Highscore (zweizeilig) mit Siegzähler, Match-Erkennung und Siegermeldung
- Endzeit-Bug behoben (0:00 statt echter Zeit)

**Feinschliff**
- Header in Zonen: Steuerung bündig zur Arbeitsfläche, Prüfen/Lösung auf der Timer-Achse
- Projektwerte-Panel und Formeln-Cheatsheet als Overlays auf der Zeichenfläche
- Auswertung durchgängig zeilenweise mit Labels, ohne Dopplungen
- Branding mit verlinktem Copyright
