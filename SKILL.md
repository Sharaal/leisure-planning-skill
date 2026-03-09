---
name: leisure-planning-skill
description: Finde lokale Freizeitaktivitäten für einen angegebenen Ort und optionale Kategoriefilter, einschließlich der Verfügbarkeit für einen bestimmten Tag und eine bestimmte Uhrzeit. Geeignet für strukturierte Empfehlungen zu Cafés, Spaziergängen, Restaurants, Aktivitäten und ähnlichen lokalen Angeboten mit praktischen Details wie Parkmöglichkeiten, Fußwegentfernung, Öffnungszeiten, Kosten, Adresse und Homepage.
---

# Leisure Planning Skill

Erstelle strukturierte Empfehlungen für Freizeitaktivitäten an einem angegebenen Ort.

## Erwartete Eingaben
Der Nutzer kann folgende Angaben machen:

### Pflichtangabe
- **Ort / Suchgebiet**
  - Beispiel: `Homburg`
  - Beispiel: `rund um Saarbrücken`
  - Beispiel: `Umkreis von 20 km um Homburg`

Ohne Ort nicht fortfahren. In diesem Fall gezielt nach dem Suchgebiet fragen.

### Optionale Angaben
- **Spezielle Kategorie**
  - Wenn nicht angegeben: **alle passenden Aktivitäten berücksichtigen**
  - Beispiele:
    - `Cafe`
    - `Spaziergang`
    - `Restaurant`
    - `Bar`
    - `Schwimmen`
    - `Brettspiele`
    - `Tanzen`
    - `Badminton`
    - `Natur`
    - `Kultur`

- **Tag und Uhrzeit**
  - Wenn nicht angegeben: **heute** als Referenz verwenden
  - Wenn nur ein Tag angegeben ist, aber keine Uhrzeit: auf typische Nutzbarkeit des Tages prüfen
  - Wenn Tag und Uhrzeit angegeben sind, immer bewerten, ob der Ort **zu diesem Zeitpunkt tatsächlich geöffnet bzw. sinnvoll nutzbar** ist

## Recherche-Regeln
Suche nach **realen, konkreten Orten oder Aktivitäten** für das angegebene Gebiet.

Bei jeder Empfehlung immer prüfen:
1. Ist die Aktivität / Location real und aktuell auffindbar?
2. Ist sie am angegebenen Tag / zur angegebenen Uhrzeit geöffnet oder nutzbar?
3. Ist sie praktisch erreichbar?
4. Gibt es sinnvolle Parkmöglichkeiten?
5. Wie lang ist der Fußweg vom sinnvollen Parkplatz oder Ankunftspunkt?
6. Welche Kosten fallen typischerweise an?

Wenn ein Ort zwar interessant ist, aber am gewünschten Zeitpunkt geschlossen ist, dann:
- klar als **nicht passend für den gewünschten Zeitpunkt** markieren
- nur dann aufnehmen, wenn es für den Nutzer trotzdem nützlich ist
- bevorzugt stattdessen passende Alternativen nennen

## Praktische Erreichbarkeit immer mitdenken
Bei allen Vorschlägen nicht nur die Aktivität selbst nennen, sondern immer auch die **praktische Nutzbarkeit vor Ort**.

Insbesondere berücksichtigen:
- nahegelegene Parkhäuser oder Parkplätze
- ob die Strecke vom Parkplatz aus kurz und angenehm ist
- ob es bergauf geht oder die Strecke anstrengender ist
- ob es eine sinnvollere Anfahrt direkt näher am Ziel gibt

Beispiel:
Nicht nur „Schlossberg“ nennen, sondern zusätzlich:
- guter Startpunkt / Parkplatz
- geschätzter Fußweg
- Hinweis auf Steigung
- ggf. Alternative mit kürzerem Aufstieg

## Ausgabeformat
Gib die Ergebnisse als übersichtliche Liste aus. Für **jede Aktivität** müssen diese Felder enthalten sein:

### 1. Titel
Kurzer, klarer Name der Aktivität oder Location.

### 2. Beschreibung
Kurz erklären:
- was man dort machen kann
- warum es zur Anfrage passt
- ob es eher entspannt, aktiv, sozial oder spontan geeignet ist

### 3. Parkmöglichkeiten
So konkret wie möglich:
- empfohlener Parkplatz / Parkhaus
- ob dieser nah dran ist
- falls relevant: alternative Parkmöglichkeit
- falls Parken schwierig ist: klar sagen

### 4. Laufwege
Immer als praktische Einschätzung angeben:
- geschätzte Gehzeit
- ob der Weg flach oder anstrengend ist
- ob der Weg alltagstauglich ist
- ob es eine nähere Anfahrtsmöglichkeit gibt

### 5. Öffnungszeiten
Immer bezogen auf den **angegebenen Tag und die angegebene Uhrzeit** ausgeben:
- ob geöffnet / geschlossen / unklar
- relevante Öffnungszeit an diesem Tag
- **Link zu den Öffnungszeiten**
- wenn möglich zusätzlich kurz erwähnen, ob die Aktivität zu dieser Uhrzeit sinnvoll ist

Beispiel:
- „Sonntag geöffnet ab 18:00 Uhr – daher für 15:00 Uhr nicht geeignet.“
- „Heute von 11:30 bis 22:00 Uhr geöffnet.“
- „Öffnungszeiten konnten nicht zuverlässig bestätigt werden.“

### 6. Kosten
So konkret wie möglich:
- kostenlos / Eintritt / typisches Preisniveau
- bei Restaurants: grobe Preisspanne
- bei Freizeitorten: Eintritt, Kursgebühr oder kostenloser Zugang

Wenn keine verlässlichen Angaben auffindbar sind, transparent sagen:
- „Kosten online nicht klar ersichtlich“

### 7. Adresse und Homepage
Immer beide Punkte nennen:
- vollständige oder bestmögliche Adresse
- offizielle Homepage oder die beste verfügbare offizielle Seite

## Sortierung
Wenn mehrere Ergebnisse vorhanden sind, sortiere nach praktischer Relevanz:
1. passt zur gewünschten Kategorie
2. ist zum gewünschten Zeitpunkt nutzbar
3. ist gut erreichbar
4. hat sinnvolle Park- und Laufwegsituation
5. ist insgesamt attraktiv für die geschilderte Situation

## Qualitätsregeln
- Keine Fantasie-Orte
- Keine allgemeinen Ideen ohne konkrete Location
- Keine Planung vorschlagen, die an Öffnungszeiten scheitert
- Keine langen Wege verschweigen
- Bei Unsicherheit transparent sein
- Lieber weniger, aber praktisch brauchbare Vorschläge als viele ungeprüfte Nennungen

## Umgang mit fehlenden Angaben
Wenn der Nutzer etwas nicht angegeben hat:

### Kein Ort angegeben
Nach dem Ort oder Suchgebiet fragen.

### Keine Kategorie angegeben
Breit suchen und gemischte Optionen liefern.

### Kein Tag / keine Uhrzeit angegeben
Mit **heute** arbeiten und das klar so behandeln.

## Empfohlene Struktur der Antwort
Verwende nach Möglichkeit dieses Format:

## Vorschläge für [Ort]  
**Kategorie:** [alle / Cafe / Spaziergang / ...]  
**Zeitbezug:** [heute / konkreter Tag + Uhrzeit]

### 1. [Titel]
- **Beschreibung:** ...
- **Parkmöglichkeiten:** ...
- **Laufwege:** ...
- **Öffnungszeiten:** ...
- **Kosten:** ...
- **Adresse:** ...
- **Homepage:** ...

### 2. [Titel]
- **Beschreibung:** ...
- **Parkmöglichkeiten:** ...
- **Laufwege:** ...
- **Öffnungszeiten:** ...
- **Kosten:** ...
- **Adresse:** ...
- **Homepage:** ...

## Sonderfall: Kombinationen
Wenn die Anfrage eine Kombination sinnvoll macht, dürfen auch kurze Routen vorgeschlagen werden, z. B.:
- Cafe → Spaziergang
- Restaurant → Aussichtspunkt
- Parken → kurze Aktivität → Essen

Aber auch dann müssen für jede einzelne Station die Pflichtangaben vorhanden sein.

## Ziel
Der Nutzer soll eine **realistisch machbare, zeitlich passende und vor Ort praktische** Empfehlung erhalten, nicht nur eine theoretisch schöne Idee.