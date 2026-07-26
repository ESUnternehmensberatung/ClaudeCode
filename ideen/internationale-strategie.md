# Internationale Strategie: Hochzeitshomepage × 1.000 Verkäufe

_Gesammelt: 2026-07-26 · Aktualisiert: 2026-07-26_

---

## Kern-Idee

Das Produkt „Hochzeitshomepage" (aktuell 500 €) international über Pinterest vermarkten und 1.000 Mal verkaufen.

**Umsatzziel:** 1.000 × 500 € = 500.000 €

---

## Produktmodell (geklärt)

**Semi-automatisiertes Done-for-You:**

```
Kauf via Stripe
      ↓
Jotform-Briefing (Paar füllt Fragebogen aus)
      ↓
Eduard übergibt Briefing an Claude
      ↓
Claude erstellt Homepage nach Template
      ↓
Prüfung + Lieferung an das Paar
```

- Kein Self-Service – Eduard bleibt Übergabepunkt
- Flaschenhals: Briefings abarbeiten (geschätzt 20–40 Min./Sale inkl. Prüfung)
- Skalierbar bis ~50–100 Sales/Monat ohne Kapazitätsproblem
- Stripe übernimmt Steuer automatisch (kein Kleinunternehmerstatus)

**Template-Entwicklung:** Nach dem ersten echten Kauf wird gemeinsam mit Claude ein Template erarbeitet, das als Basis für alle Folge-Sales dient.

---

## Voraussetzungen (Stand nach Klärung)

| Thema | Status |
|---|---|
| Produktmodell | ✅ Geklärt: Claude-gestützt nach Template |
| Steuer/Stripe | ✅ Stripe Tax automatisch, kein Kleinunternehmer |
| Template | ⏳ Wird nach erstem Kauf entwickelt |
| Englische Landingpage | ⏳ Noch zu bauen |
| Automatisierter Checkout | ✅ Jotform + Stripe vorhanden |

---

## Warum Pinterest

- Hochzeiten sind die stärkste Nische auf Pinterest weltweit
- Zielgruppe: Frauen 25–40 mit konkretem Kaufinteresse (nicht nur Inspiration)
- Paid Pins sind im Vergleich zu Meta/Google günstig – Wettbewerb im Hochzeits-SaaS/Service noch gering
- Organische Reichweite (SEO auf Pinterest) bleibt langfristig
- Boards und Pins können in mehreren Sprachen angelegt werden (DE + EN parallel)

---

## Internationale Zahlungsabwicklung via Stripe

- Stripe verarbeitet 135+ Währungen automatisch
- Paare zahlen in ihrer Währung (USD, GBP, EUR, CHF, SEK, …)
- Stripe Tax übernimmt Steuerpflicht je Land (wichtig: B2C digital services → OSS-Verfahren DE)
- **Achtung Kleinunternehmerregelung:** § 19 UStG greift nur im Inland – bei ausländischen B2C-Umsätzen können Meldepflichten entstehen. Steuerberater befragen.

---

## Geoblocking / Geo-Routing

### Was ist möglich?

Ja, Nutzer können anhand ihres Landes auf unterschiedliche Seiten geleitet werden.

### Optionen (Aufwand aufsteigend)

| Option | Aufwand | Wie |
|---|---|---|
| **JS-Redirect mit IP-API** | Gering | `fetch("https://ipapi.co/json")` → redirect zu `/en/` oder Subdomain |
| **Cloudflare Workers** | Mittel | Kostenlos, serverseitig, kein JS nötig, zuverlässiger |
| **Vercel Edge Functions** | Mittel | Wenn von GitHub Pages zu Vercel migriert wird |
| **Separate Domains** | Höher | `wedding-homepage.com` (EN) + `zwischen-heide-und-herz.de` (DE) |

### Empfehlung für den Start

Zwei separate Landingpages auf derselben Domain:
- `/` → Deutsch (bestehende Seite)
- `/en/` → Englisch (neue Seite, gleicher Aufbau, lokalisierte Texte + Preise in USD/GBP)

Kein Hard-Geoblocking nötig – freie Sprachwahl per Navigation + optionaler Auto-Redirect.

---

## Mögliche Zielländer (Priorität)

| Markt | Warum |
|---|---|
| USA / Kanada | Größter Hochzeitsmarkt weltweit, Pinterest-Hauptmarkt |
| UK | Englischsprachig, starker Hochzeits-Content-Konsum auf Pinterest |
| Australien | Ähnliches Konsumverhalten, USD/AUD unkompliziert via Stripe |
| Niederlande / Belgien | Nah, teils deutschsprachig/englischsprachig affin |
| Schweiz / Österreich | Gleiche Sprache wie DE → keine Lokalisierung nötig |

---

## Prozess-Checkliste für den ersten Sale

- [ ] Template gemeinsam mit Claude entwickeln (nach erstem Kauf)
- [ ] Jotform-Briefing so strukturieren, dass Claude alle nötigen Infos bekommt
- [ ] Workflow dokumentieren: Briefing → Claude-Prompt → Output → Prüfung
- [ ] Lieferprozess definieren (wie bekommt das Paar die fertige Seite?)
- [ ] Stripe-Checkout für internationale Käufer testen

## Skalierungsüberlegungen

Bei wachsender Nachfrage:
- Briefing-Queue priorisieren (z.B. nach Hochzeitsdatum)
- Standard-Prompts für Claude optimieren (weniger Nacharbeit)
- Bei >20 Sales/Monat: Lieferzeiten klar kommunizieren (z.B. „fertig in 5 Werktagen")

---

## Nächste Schritte

1. **Ersten Sale generieren** (DE-Markt, bestehende Seite) → Template ableiten
2. **Template mit Claude entwickeln** → Briefing-to-Homepage-Workflow dokumentieren
3. **Pinterest-Account aufbauen:** Boards auf DE + EN, organischer Content als Fundament
4. **Englische Landingpage erstellen** (`/en/` oder neue Domain)
5. **Pilotlauf international:** Erste Pinterest Ads in EN-Märkten (UK/USA)

---

## Bewertung (Stand 2026-07-26)

| Dimension | Einschätzung |
|---|---|
| Marktpotenzial | ★★★★★ – Hochzeit ist global, Pinterest ist ideal |
| Technische Machbarkeit | ★★★★☆ – Geo-Routing einfach, Automatisierung etwas Aufwand |
| Skalierbarkeit | ★★★★☆ – Claude-gestützt, Eduard als Qualitätskontrolle; Flaschenhals bewusst |
| Risiko | Markenname „Zwischen Heide & Herz" sehr regional – für INT. Markt neue Marke? |
| Priorität | Nach Klärung des Produktmodells direkt umsetzbar |

---

_Letzte Aktualisierung: 2026-07-26_
