# 02 – Designstrategie „Maßstab“

## Leitidee

SAKA verkauft keine Träume, sondern **nachvollziehbare Entscheidungen** mit einem Menschen, der bleibt. Die Gestaltung übernimmt deshalb die Sprache der Architektenzeichnung: präzise Linien, Bemaßung, Raster, Grundriss. Sie ist ruhig, genau und souverän. Luxus entsteht durch Präzision und Weißraum, nicht durch Gold-Effekte.

Ein wiederkehrendes, inhaltlich begründetes Element trägt die Marke: die **Maßkette**, also die Bemaßungslinie mit 45°-Strichen aus Bauplänen.
- Auf der Website stellt sie den **Ablauf** dar (Erstgespräch → Objekt und Berechnung → Kauf und Notar → Danach).
- In der App stellt sie **Fortschritt und Zahlenbereiche** dar, zum Beispiel den Verkaufsfahrplan, Gesamtkosten aus Kaufpreis plus Nebenkosten oder die Restschuld über die Zeit.
- Sie wird nie als Dekoration eingesetzt.

Das zweite Merkmal ist die **Person statt Stockfoto**: Kaan Aslan als erkennbarer Ansprechpartner im ersten Bildschirm.

## Farben (aus dem Logo abgeleitet)

| Name | Hex | Rolle |
|---|---|---|
| Erde | `#17120C` | Grund des App-Symbols. Primäre Buttons, dunkle Flächen, Überschriften |
| Messing | `#A9813E` | Nur Linien, Maßketten, Logo. Nie große Flächen |
| Messing-Text | `#7A5C24` | Kleine Akzentschrift (6,2 : 1 auf Weiß) |
| Papier | `#FFFFFF` | Lesefläche. Ersetzt das bisherige Creme |
| Sandstein | `#ECE7DD` | Eine ruhige Fläche zum Gliedern, sparsam |
| Schiefer | `#4B555E` | Kühler Gegenton für Anmerkungen und Annahmen |

Begründung: Weg vom Creme-Bronze-Standard, hin zu Weiß mit Erde und Messing. Das ist die Farbwelt des Logos und der App. Der kühle Schiefer setzt einen bewussten Gegenpol zu den warmen Tönen.

## Schrift

- **Bricolage Grotesque**: Display und Überschriften. Light (300) für große Aussagen, SemiBold (600) für die Betonung ganzer Sätze, nie einzelner Wörter. Dieselbe Familie wie in der App, damit Website und App eine Stimme haben.
- **Source Sans 3**: Fließtext und Bedienelemente, mit **tabellarischen Ziffern** für Zahlen. In der App ersetzt sie die Monospace-Zahlen.
- Beide selbst gehostet (SIL Open Font License), auf Latein reduziert (je ≈25 KB). Keine Anfragen an Google, die Website bleibt datenschutzneutral.
- Typografische Skala Website: 18 / 20 / 26 / 40 / 56–90 px. Zeilenlänge Fließtext höchstens 70 Zeichen.
- Keine Überzeilen in Versalien. Labels in normaler Schreibweise, nur wo sie Information tragen.

## Layout

- 12-Spalten-Raster, linksbündig, asymmetrisch. Überschriften über 8 bis 9 Spalten, Text über 6 Spalten, Nebeninformationen rechts.
- Wechsel zwischen großzügigen Abschnitten mit Aussage und kompakten Abschnitten mit Information.
- Leistungen als **redaktionelle Liste** mit Linien statt Kartenraster.
- Mobil eigene Kompositionen: Maßkette vertikal, Porträt als Zeile, Buttons in voller Breite.

```
Desktop-Hero
┌──────────────────────────────────────────────┐
│ Logo SAKA            Navigation   [Erstgespr.]│
├──────────────────────────────────────────────┤
│ Wohnimmobilien als                 ┌───────┐ │
│ Kapitalanlage.                     │ Porträt│ │
│ Mit einem Ansprechpartner,         │ Kaan   │ │
│ der bleibt.                        └───────┘ │
│ Unterzeile (6 Spalten)             Name, §34c │
│ [Erstgespräch] (Angebote)                     │
├─/───────────/───────────/───────────/────────/┤  ← Maßkette = Ablauf
│ Erstgespräch  Objekt+Rechn.  Kauf+Notar  Danach│
└──────────────────────────────────────────────┘
```

## Bewegung

- **Ein einziger orchestrierter Moment** pro Seite: Die Maßkette zeichnet sich beim ersten Erscheinen von links nach rechts (1,4 s), die Teilstriche folgen.
- Sonst nur Rückmeldung auf Handlungen: Menü öffnen, Aufklappen, Bestätigen.
- Kein Einblenden jedes Abschnitts, kein Parallax-Dauerlauf. Bei `prefers-reduced-motion` keine Animation.

## App: dieselbe Sprache, produktorientiert

- Startseite wird **persönliche Übersicht** statt Prospekt: zuerst Meine Immobilien mit dem Wichtigsten (Cashflow, nächste Frist), dann Aufgaben. Die Bereichskarten werden kompakt.
- Beispiel-Hinweis wird ein schmales, ruhiges Band in der Objektleiste statt eines großen orangefarbenen Kastens auf jeder Seite.
- Labels in normaler Schreibweise, Zahlen in Source Sans mit tabellarischen Ziffern, Karten nur dort, wo Inhalte wirklich zusammengehören.
- Maßkette für Fortschritt (Verkaufsfahrplan) und Zusammensetzungen (Gesamtkosten).

## Prüfung gegen Standardmuster

| Standardmuster | Entscheidung |
|---|---|
| Creme + Serife + warmer Akzent | Ersetzt durch Weiß, Erde, Messing, Schiefer und eine Grotesk-Schrift |
| Versalien-Überzeilen überall | Entfernt, Labels nur mit Information |
| Kartenraster | Redaktionelle Listen, Karten nur in der App für echte Einheiten |
| Nummerierung 01/02/03 | Nur beim echten Ablauf, als Maßkette statt Ziffern |
| Monospace für Zahlen | Tabellarische Ziffern der Textschrift |
| Gold-Schwarz ohne Bezug | Gold nur als feine Linie, abgeleitet aus Logo und App-Symbol |
| Stockfoto | Person und eigenes Bildmaterial (Bedarf siehe Maßnahmen) |

## Bildbedarf (Empfehlung)

1. **Professionelles Porträt** von Kaan Aslan, mindestens 2000 px, in ruhigem Tageslicht vor Architekturhintergrund in Augsburg. Hochformat 4 : 5 und ein Querformat.
2. **Architekturfotografie** echter vermittelter Objekte, sobald freigegeben. Klare Linien, Tageslicht, keine Weitwinkel-Verzerrung.
3. Bis dahin: lieber kein Bild als ein generisches Stockbild.
