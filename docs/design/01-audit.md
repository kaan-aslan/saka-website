# 01 – Design-Audit (Stand 09.11.2026)

Grundlage: echte Browser-Vorschau (Chromium/Playwright) mit 1440 × 900 (Desktop) und 390 × 844 (Mobil), Quelltextanalyse, Kontrastberechnung nach WCAG 2.x. Die App wurde über ihre Web-Ausgabe (Expo Web) im Browser geprüft; das native iPhone-Verhalten (Tab-Leiste, Tastatur) ist dort nur angenähert.

Screenshots: `screenshots/vorher_*`.

## Gesamturteil

Beide Oberflächen sind **funktional solide, sauber programmiert und datenschutzfreundlich** (Website ohne Tracking, ohne externe Skripte; App ohne Server). Gestalterisch bleiben sie unter dem Anspruch: Sie folgen erkennbar Standardmustern, die Website deutlich stärker als die App. Website und App wirken außerdem wie zwei verschiedene Marken.

## Website

### Architektur und Technik
- Eine statische Seite (`index.html`) plus drei Rechtsseiten, eine CSS-Datei, kein Framework, GitHub Pages. Gut wartbar, sehr schnell (≈150 KB inkl. Bilder).
- Keine Webschriften: Überschriften fallen auf Cambria/Georgia zurück, je nach Gerät also unterschiedlich. Die Marke hat damit keine eigene typografische Stimme.

### Branding
- Logo (Löwe mit Skyline-Krone, Gold) ist eigenständig und stark, wird aber nur klein im Kopf genutzt.
- Farbwelt Creme `#F4EFE4` + Bronze + braune Serifenschrift liegt sehr nah an der derzeit häufigsten KI-Website-Ästhetik (warmes Creme, kontrastreiche Serife, warmer Akzent). Sie hat keinen Bezug zum Logo-Gold auf Erdbraun, das die App nutzt.
- Startbild ist ein Stockfoto (Hausmodell). Generisch und lizenzrechtlich ungeklärt.

### Komposition und Hierarchie
- Fast jeder Abschnitt folgt demselben Schema: Überzeile in Versalien → Überschrift → Einleitung → Kartenraster. Insgesamt **9 Überzeilen**, 5 davon wiederholen nur die Überschrift („Häufige Fragen“ über „Häufige Fragen“).
- **13 gleichförmige Karten** in zwei Rastern (Leistungen, Vorteile). Gleiche Radien, gleiche Rahmen, keine Gewichtung.
- **Inhalte doppelt**: Der Abschnitt „Was Sie erwarten können“ und die FAQ enthalten wortgleiche Sätze. Unternehmensangaben (HRB, Sitz) stehen viermal auf einer Seite (Hero, Über uns, Kontakt, Fuß/Impressum).
- Die Formulierung „von der ersten Beratung bis zum Notartermin“ kommt sechsmal vor und verliert dadurch Wirkung.
- Im Hero stehen Registerdaten als „Fakten“. Sie schaffen dort kein Vertrauen, sondern wirken wie Füllmaterial.
- Positiv: Ablauf auf dunklem Grund ist der stärkste Abschnitt; die Person Kaan Aslan ist im Kontakt sichtbar.

### Navigation und Nutzerführung
- **Kritisch: Unter 900 px gibt es keine Navigation.** Das Menü wird ausgeblendet, unter 480 px auch der Kopf-Button. Mobile Besucher können nur scrollen.
- Vier gleichlautende Handlungsaufforderungen „Erstgespräch vereinbaren“, eine davon abweichend formuliert.
- Interne Links mit angehängtem „→“ (Standardmuster), externe mit „↗“.

### Responsives Verhalten
- Mobil: Hero mit Foto als Hintergrund funktioniert, danach wird das Desktop-Layout lediglich gestapelt (9.800 px Seitenlänge, Kartenstapel).

### Accessibility (WCAG 2.2 AA)
| Befund | Wert | Kriterium |
|---|---|---|
| Kleine Bronze-Schrift auf Creme (Überzeilen, Labels) | 4,38 : 1 | 1.4.3 verfehlt (4,5 : 1) |
| Copyright im Fuß, 50 % Weiß auf Braun | 4,22 : 1 | 1.4.3 verfehlt |
| Navigations- und Fußlinks kleiner als 24 px Höhe | 8 Links | 2.5.8 grenzwertig |
| Keine mobile Navigation | – | 2.4.5 / Bedienbarkeit |
| Fokusrahmen auf dunklem Grund kaum sichtbar | Bronze auf Braun | 2.4.11 / 1.4.11 |
| Positiv: Sprungmarke, Landmarken, eine H1, Alt-Texte, `prefers-reduced-motion` beim Scrollen | | |

### Performance und Auffindbarkeit
- Sehr gut: keine Skripte, kleine Seite. Verbesserbar: Startbild nur als JPEG, Logo-PNG 39 KB für 46 px Darstellung, keine Open-Graph-Angaben (Vorschau beim Teilen fehlt), keine strukturierten Daten.

## App ImmoPartner

### Architektur
- Expo / React Native, expo-router mit nativen Tabs, eigenes Komponentensystem (`src/components/ui.tsx`), Farbtokens hell/dunkel (`src/constants/theme.ts`), Schriften Bricolage Grotesque, Source Sans 3, IBM Plex Mono. Saubere Basis.

### Gestaltung
- Eigenständiger als die Website (Bricolage, dunkler Modus, Erdton), aber mit typischen Standardmustern: Versalien-Labels mit Sperrung über fast jedem Wert, Monospace-Schrift für alle Zahlen, nahezu jede Information in einer gleich aussehenden Karte.
- **Jede Hauptansicht beginnt gleich**: Objektleiste + großer orangefarbener Kasten „Du siehst gerade ein Beispiel“ + nummerierte Reiter. Der eigentliche Inhalt beginnt erst in der zweiten Bildschirmhälfte.
- Nummerierte Reiter („1 Profil, 2 Zahlen …“) als schwere Flächen. Die Nummerierung ist bei Kaufen und Verkaufen inhaltlich begründet (Abfolge), bei Verwalten nicht.
- Startseite ist eher Prospekt als Werkzeug: Nach „Meine Immobilien“ folgen drei große Bereichskarten mit Häkchenlisten, die erfahrene Nutzer nicht mehr brauchen.

### Accessibility
| Befund | Wert | Kriterium |
|---|---|---|
| Eingabefelder: Fläche und Rahmen kaum vom Hintergrund unterscheidbar | 1,1–1,3 : 1 | 1.4.11 verfehlt (3 : 1) |
| Akzent auf Akzent-Fläche (Pills „Kostenlos“, „Demnächst“) | 4,48 : 1 | 1.4.3 knapp verfehlt |
| Grün/Orange auf zarter Fläche (Hinweise, Status) | 4,30–4,34 : 1 | 1.4.3 knapp verfehlt |
| Auswahl-Chips 40 px hoch | | Apple HIG 44 pt |
| Positiv: Dunkelmodus 6–7 : 1, Rollen/Labels für Screenreader, ⓘ-Erklärungen, Tastaturleiste | | |

## Markenübergreifend
- Website: Serife, Creme, Bronze. App: Grotesk, Erdbraun, Gold. Zwei Identitäten für eine Marke.
- Fehlendes Bildmaterial: kein professionelles Porträt in ausreichender Auflösung (vorhanden 360 × 360 px), keine eigenen Objekt- oder Architekturfotos.
