# 04 – Prüfprotokoll (09.11.2026)

Werkzeug: Chromium über Playwright, Viewports 1440 × 900 und 390 × 844. App über Expo-Web-Export 393 × 852 und 1280 × 900. Screenshots unter `screenshots/`.

## Website

| Prüfung | Ergebnis |
|---|---|
| Visuell Desktop und Mobil, vorher/nachher | Layout unverändert bis auf beabsichtigte Änderungen. Kopfzeile mobil zunächst falsch ausgerichtet (Logo oben angeschnitten, wenn die Zeile umbricht). **Behoben** (`align-content`, eigene Abstände). |
| Mobile Navigation | Knopf sichtbar, `aria-expanded` wechselt false → true → false. Esc schließt und setzt den Fokus zurück auf den Knopf. Linkwahl schließt das Menü und springt zum Anker. Ein Fehler im Selektor (`.js .menue-offen` statt `.js.menue-offen`) machte das Menü unsichtbar. **Behoben** und erneut geprüft. |
| Ohne JavaScript | Navigation als umbrechende Linkliste sichtbar, Seite voll bedienbar. |
| Tastatur | Erster Tab: „Zum Inhalt springen“, danach Logo, dann Menü. Fokusrahmen sichtbar, auf dunklem Grund in hellem Messing. |
| Klickflächen | Automatische Messung: 0 Links/Schaltflächen unter 24 px (vorher 8). |
| Kontraste | Kleine Bronze-Schrift 5,41 : 1 (Creme) / 6,21 : 1 (Weiß), Fuß-Copyright 6,9 : 1, Buttons 6,2 : 1. |
| Struktur | Eine H1, alle Bilder mit `alt`, Landmarken `header/nav/main/footer`. |
| Performance | Startbild WebP 10 KB (mobil) / 20 KB (Desktop) statt 56 KB JPEG, Logo 18 KB statt 39 KB, ein kleines eigenes Skript (≈1 KB), keine externen Anfragen. |
| Rechtsseiten | Kopf mit neuem Logo und Favicon geprüft, Inhalte unverändert. |
| Konzept-Seite | Desktop und Mobil geprüft. Mobil zunächst verzerrtes Porträt und zu breiter Kopf-Button, **behoben**. Animation entfällt bei `prefers-reduced-motion`. |

## App

| Prüfung | Ergebnis |
|---|---|
| TypeScript | fehlerfrei |
| Rechentests | 7 von 7 bestanden (keine Rechenlogik verändert) |
| Visuell (Web-Export) | Eingabefelder, Auswahl-Chips und Objektleiste haben jetzt erkennbare Rahmen. Keine Layout-Verschiebungen. |
| Kontraste (berechnet) | Feldrahmen 3,0–3,3 : 1 hell, 3,1 : 1 dunkel; Akzent auf Akzentfläche 4,88 : 1; Grün 5,02 : 1, Orange 5,02 : 1 auf ihren Flächen; Weiß auf Akzent-Button 5,82 : 1. |
| Natives iPhone | Nicht geprüft: Die App-Änderungen liegen nur im Branch und erreichen kein Gerät, bis sie freigegeben und gebaut werden. |

## Nicht geprüft / Einschränkungen
- Kein Screenreader-Test mit VoiceOver auf echtem Gerät.
- Lighthouse nicht ausgeführt. Ladeverhalten nur über Dateigrößen und Anfragen beurteilt.
- Die Wirkung der Schriften im Konzept auf Windows-Geräten nicht gesondert geprüft.


## Prüfung Redesign A–D (09.11.2026, Branch)
- Website Desktop 1440 px und Mobil 390 px per Playwright: Menü öffnet/schließt (Esc, Linkwahl), aria-current folgt dem Scrollen, Maßkette zeichnet sich einmal, bei `prefers-reduced-motion` statisch.
- Kontraste neu berechnet: Erde auf Papier 18,2 : 1, Messing-Text #7A5C24 auf Papier 6,3 : 1, Leise #5A544C auf Sandstein ≥ 5,9 : 1. Werte bitte bei Bedarf mit einem eigenen Prüfwerkzeug gegenprüfen.
- Rechtsseiten (Impressum, Datenschutz, Datenschutz App) mit neuem Kopf geprüft, Inhalte unverändert.
- App: `npx tsc --noEmit` ohne Fehler, `npm test` 7/7 bestanden, Web-Ausgabe aller fünf Reiter visuell geprüft. Berechnungslogik nicht verändert (nur Darstellung). Natives iPhone-Verhalten muss im Vorschau-Build geprüft werden.
