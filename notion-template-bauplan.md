# Zwischen Heide & Herz – Digitaler Hochzeitsplaner
## Notion Template Bauplan

---

## STRUKTUR (8 verlinkte Seiten)

### 1. 🏠 DASHBOARD (Startseite)
**Typ:** Normale Seite mit Callouts und verlinkten Datenbank-Ansichten

Inhalt:
- Großes Herzlich-Willkommen-Banner mit Logo
- Callout: "💍 Unser großer Tag: [Datum eintragen]"
- Callout: "📍 Location: [eintragen]"
- Callout: "👥 Gäste bestätigt: [verlinkte Zahl aus Gästeliste]"
- Callout: "💶 Budget verbraucht: [verlinkte Zahl aus Budget]"
- Schnelllinks zu allen 7 Bereichen
- Fortschrittsbalken der Gesamtplanung (verlinkt aus Checkliste)

---

### 2. 💶 BUDGETPLANER
**Typ:** Datenbank (Tabelle)

**Spalten:**
| Spalte | Typ | Beschreibung |
|--------|-----|--------------|
| Kategorie | Text | z.B. Location, Catering, Fotografie |
| Anbieter | Text | Name des Dienstleisters |
| Geplantes Budget | Number (€) | Was ihr einplant |
| Anzahlung | Number (€) | Bereits gezahlte Anzahlung |
| Restbetrag | Formula | `prop("Geplantes Budget") - prop("Anzahlung")` |
| Bezahlt | Checkbox | Vollständig bezahlt? |
| Fälligkeit | Date | Wann ist Zahlung fällig? |
| Notizen | Text | Vertragsnummer, Ansprechpartner |

**Formeln im Footer (Summary):**
- Geplantes Budget GESAMT: Sum aller "Geplantes Budget"
- Bereits bezahlt: Sum aller "Anzahlung"
- Noch offen: Sum aller "Restbetrag"

**Vorbefüllte Kategorien:**
- Location & Raummiete
- Catering & Getränke
- Hochzeitskuchen
- Fotografie
- Videografie
- Blumen & Dekoration
- Brautkleid & Accessoires
- Anzug / Outfit Partner
- Ringe
- Musik / DJ / Band
- Trauredner
- Einladungen & Papeterie
- Haare & Make-up
- Transport
- Flitterwochen
- Sonstiges

---

### 3. 👥 GÄSTELISTE
**Typ:** Datenbank (Tabelle)

**Spalten:**
| Spalte | Typ | Beschreibung |
|--------|-----|--------------|
| Name | Title | Vor- und Nachname |
| Seite | Select | Brautseite / Bräutigamseite / Gemeinsam |
| Kategorie | Select | Familie / Freunde / Arbeit / Bekannte |
| Status | Select | Eingeladen / Zugesagt / Abgesagt / Warteliste |
| Kinder | Number | Anzahl mitkommender Kinder |
| Menü | Select | Fleisch / Vegetarisch / Vegan / Kinder |
| Allergie | Text | Unverträglichkeiten |
| Tisch | Number | Tischnummer (verlinkt mit Sitzplan) |
| Adresse | Text | Für Einladungsversand |
| Einladung verschickt | Checkbox | |
| Dankeskarte | Checkbox | Nach der Hochzeit |

**Ansichten:**
- 📋 Alle Gäste (Tabelle)
- ✅ Zugesagt (gefiltert: Status = Zugesagt)
- ❌ Abgesagt (gefiltert: Status = Abgesagt)
- 🍽️ Menüübersicht (gruppiert nach Menü)
- 👨‍👩‍👧 Nach Tisch (gruppiert nach Tisch)

**Automatische Zählungen (Summary-Zeile):**
- Gesamt eingeladen: Count all
- Zugesagt: Count (Status = Zugesagt)
- Abgesagt: Count (Status = Abgesagt)
- Kinder gesamt: Sum "Kinder"
- Vegetarisch: Count (Menü = Vegetarisch)
- Vegan: Count (Menü = Vegan)

---

### 4. 🏢 DIENSTLEISTER
**Typ:** Datenbank (Tabelle)

**Spalten:**
| Spalte | Typ | Beschreibung |
|--------|-----|--------------|
| Dienstleister | Title | Name / Firma |
| Kategorie | Select | Fotograf / Caterer / Florist / DJ etc. |
| Status | Select | Recherche / Kontaktiert / Angebot / Gebucht / Abgesagt |
| Ansprechpartner | Text | |
| Telefon | Phone | |
| E-Mail | Email | |
| Website | URL | |
| Preis | Number (€) | |
| Vertrag | Checkbox | Vertrag unterschrieben? |
| Vertragsupload | Files | PDF des Vertrags |
| Notizen | Text | |

---

### 5. ✅ CHECKLISTE & ZEITPLAN
**Typ:** Datenbank (Tabelle)

**Spalten:**
| Spalte | Typ | Beschreibung |
|--------|-----|--------------|
| Aufgabe | Title | Was muss erledigt werden |
| Zeitraum | Select | 12 Monate vor / 9 Monate / 6 Monate / 3 Monate / 1 Monat / 1 Woche / Am Tag |
| Kategorie | Select | Location / Catering / Kleidung / Papeterie / etc. |
| Erledigt | Checkbox | |
| Fälligkeit | Date | |
| Verantwortlich | Select | Braut / Bräutigam / Gemeinsam / Extern |
| Notizen | Text | |

**Ansichten:**
- 📅 Zeitstrahl (Timeline nach Fälligkeit)
- 📋 Nach Zeitraum (gruppiert)
- ✅ Erledigte Aufgaben
- ⏳ Offene Aufgaben (gefiltert: Erledigt = false)

**Vorbefüllte Aufgaben (Auszug):**

12 Monate vorher:
- [ ] Budget festlegen
- [ ] Gästeliste erstellen (grobe Version)
- [ ] Hochzeitsdatum festlegen
- [ ] Location besichtigen und buchen
- [ ] Trauredner buchen
- [ ] Fotograf buchen

9 Monate vorher:
- [ ] Brautkleid-Shopping beginnen
- [ ] Caterer anfragen
- [ ] Flitterwochen planen
- [ ] Hochzeitswebsite erstellen

6 Monate vorher:
- [ ] Einladungen gestalten
- [ ] Menü festlegen
- [ ] DJ / Band buchen
- [ ] Florist buchen
- [ ] Ringe aussuchen

3 Monate vorher:
- [ ] Einladungen verschicken
- [ ] Gästeliste finalisieren
- [ ] Sitzplan erstellen
- [ ] Brautkleid Anprobe

1 Monat vorher:
- [ ] Finale Gästezahlen an Caterer
- [ ] Ablaufplan erstellen
- [ ] Hochzeitsrede-Interview mit Trauredner
- [ ] Notfallkit packen

1 Woche vorher:
- [ ] Sitzplan final
- [ ] Umschläge mit Dankeskarten vorbereiten
- [ ] Alle Dienstleister bestätigen
- [ ] Ablaufplan an alle senden

Am Hochzeitstag:
- [ ] Notfallkit dabei?
- [ ] Ringe dabei?
- [ ] Trauzeugenbriefing

---

### 6. 🕐 ABLAUFPLAN HOCHZEITSTAG
**Typ:** Datenbank (Tabelle)

**Spalten:**
| Spalte | Typ | Beschreibung |
|--------|-----|--------------|
| Uhrzeit | Title | z.B. 10:00 Uhr |
| Programmpunkt | Text | Was passiert |
| Ort | Text | Wo findet es statt |
| Verantwortlich | Text | Wer kümmert sich |
| Notizen | Text | Details / Besonderheiten |

**Ansicht:** Sortiert nach Uhrzeit

---

### 7. 💒 ZEREMONIE-PLANER
**Typ:** Normale Seite mit Toggle-Blöcken

*(Eduards besonderer Beitrag — sein Know-how als Trauredner)*

Inhalt:
- Einführungstext von Eduard mit Tipps
- Toggle: "🎵 Einzugsmusik" → Felder: Lied, Künstler, Zeitpunkt
- Toggle: "📖 Begrüßung" → Notizfeld für Wünsche
- Toggle: "💌 Unsere Geschichte" → Fragebogen-Felder:
  - Wie habt ihr euch kennengelernt?
  - Was war euer erstes Date?
  - Wann wusstet ihr: Das ist der/die Richtige?
  - Wie war der Antrag?
  - Was macht euren Partner besonders?
  - Was wünscht ihr euch für die Zukunft?
- Toggle: "💍 Ringtausch" → Wünsche / Ringträger
- Toggle: "🌟 Rituale" → Checkboxen: Kerzenritual / Sandzeremonie / Handfasting / Baumkerze / Eigenes Ritual
- Toggle: "🎵 Auszugsmusik" → Felder: Lied, Künstler
- Toggle: "📝 Freie Notizen für den Trauredner"

---

### 8. 🪑 SITZPLAN
**Typ:** Normale Seite mit Tabellen pro Tisch

Aufbau:
- Übersichtstabelle: Tisch 1–X mit Anzahl Plätze
- Pro Tisch eine kleine Tabelle mit Namen (verknüpft aus Gästeliste)
- Notizfeld für Besonderheiten je Tisch

---

## DESIGN-HINWEISE FÜR NOTION

- **Cover:** Hochzeits-Foto oder Heide-Motiv (von Unsplash kostenlos)
- **Icon:** 💍 oder Herz-Emoji
- **Farbe der Datenbanken:** Alle in "Default" oder einheitlich rosa/beige
- **Schriftart:** Notion Standard reicht — wirkt clean und professionell
- **Erste Seite:** Dashboard immer als Startseite pinnen

---

## VERKAUF / LIEFERUNG

1. Template fertig erstellen
2. "Share" → "Share to web" → "Allow duplicate as template" aktivieren
3. Link kopieren → bei Digistore24 als Downloadlink hinterlegen
4. Käufer bekommt nach Kauf automatisch den Link per E-Mail

---

## PREISEMPFEHLUNG: 17 € (psychologisch besser als 19 €)
