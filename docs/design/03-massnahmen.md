# 03 – Priorisierte Maßnahmen

Bewertung: Nutzerwirkung (W), Designgewinn (D), Risiko (R), Aufwand (A), jeweils niedrig / mittel / hoch.

## Umgesetzt im Branch `design/interactive-luxury` (kleine und mittlere Änderungen)

| # | Maßnahme | W | D | R | A | Status |
|---|---|---|---|---|---|---|
| 1 | **Website: Mobile Navigation.** Menü-Knopf mit `aria-expanded`, schließt mit Esc, nach Linkwahl und beim Wechsel auf Desktop-Breite. Ohne JavaScript bleibt die Navigation als Linkliste sichtbar. | hoch | mittel | niedrig | niedrig | umgesetzt, geprüft |
| 2 | **Website: Accessibility.** Bronze für kleine Schrift abgedunkelt (4,38 → 5,41 : 1 auf Creme), Copyright im Fuß 4,22 → 6,9 : 1, Klickflächen der Navigations- und Fußlinks ≥ 24 px, sichtbarer Fokus auch auf dunklem Grund, Sprungmarke gestaltet. | hoch | niedrig | niedrig | niedrig | umgesetzt, geprüft |
| 3 | **Website: Standardmuster abbauen, ohne Inhalte zu ändern.** Versalien-Überzeilen in normale Schreibweise, 5 doppelte Überzeilen entfernt, einheitliche Handlungsaufforderung „Erstgespräch vereinbaren“, „→“ an internen Links entfernt, Labels in Hero und Unternehmensangaben ohne Versalien. | mittel | mittel | niedrig | niedrig | umgesetzt |
| 4 | **Website: Technik und Auffindbarkeit.** Startbild als WebP in zwei Größen (640/1070 px, 10/20 KB statt 56 KB), Logo-PNG 39 → 18 KB, Open-Graph-Angaben für die Vorschau beim Teilen, strukturierte Daten (`RealEstateAgent`), `canonical`, `theme-color`, Apple-Touch-Icon. | mittel | niedrig | niedrig | niedrig | umgesetzt |
| 5 | **App: Accessibility-Tokens.** Neues Token `field` für Rahmen von Eingabefeldern, Auswahl-Chips, Sekundär-Buttons und Objektleiste (≥ 3 : 1, vorher 1,1–1,3 : 1). Akzent, Grün und Orange leicht abgedunkelt, damit Hinweise und Pills ≥ 4,5 : 1 erreichen. Chips und Bewertungsknöpfe auf 44 pt Mindesthöhe. | hoch | niedrig | niedrig | niedrig | umgesetzt, geprüft |

Punkte 1–5 sind seit Freigabe vom 09.11.2026 in `main` (Website live, App im Kanal `vorschau`).

## Größere Redesigns – freigegeben am 09.11.2026, umgesetzt im Branch, Merge noch nicht freigegeben

| # | Maßnahme | W | D | R | A | Status |
|---|---|---|---|---|---|---|
| A | **Neue Startseite „Maßstab“.** Typografischer Hero mit Kaan Aslan statt Stockfoto, Maßkette als Ablauf, Leistungen als redaktionelle Liste, Registerdaten aus dem Hero entfernen. | hoch | hoch | mittel | mittel | umgesetzt (`index.html`) |
| B | **Markensystem Website = App.** Bricolage Grotesque + Source Sans 3 selbst gehostet, Farben Erde/Messing/Papier/Sandstein/Schiefer statt Creme/Bronze, Buttons in Erde mit voller Rundung. | hoch | hoch | mittel | mittel | umgesetzt, inkl. Rechtsseiten |
| C | **Inhalte straffen.** Abschnitt „Was Sie erwarten können“ und FAQ zusammenführen (derzeit wortgleiche Sätze), Unternehmensangaben nur noch in Kontakt und Impressum, Wiederholung „bis zum Notartermin“ reduzieren. | mittel | mittel | niedrig | niedrig | umgesetzt (FAQ mit 7 Fragen) |
| D | **App: Startseite als persönliche Übersicht.** Beispiel-Hinweis als schmales Band in der Objektleiste statt großem Kasten auf jeder Seite, Bereichskarten kompakt, Zahlen in tabellarischen Ziffern statt Monospace, Labels ohne Versalien, Maßkette im Verkaufsfahrplan. | hoch | hoch | mittel | mittel | umgesetzt im App-Branch |
| E | **Bildmaterial.** Professionelles Porträt und eigene Architekturfotos (siehe Strategie, Bildbedarf). | hoch | hoch | niedrig | extern | offen: Bildauswahl durch Kaan |

| F | **Logo als Vektor.** Aus der hochaufgelösten App-Grafik neu vektorisiert (Innenformen der Krone erhalten), Varianten in `assets/brand/`: Bildmarke, Lockup quer hell/dunkel, Favicon. | mittel | hoch | niedrig | niedrig | umgesetzt; Feinschliff der Kronengeometrie optional |

Nächster Schritt: ausdrückliche Freigabe für den Merge. Website-Merge = sofort live. App-Änderungen gehen mit Version 1.1.0 in die Prüfung.
