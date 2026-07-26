# Internationale Strategie: Hochzeitshomepage × 1.000 Verkäufe

_Gesammelt: 2026-07-26_

---

## Kern-Idee

Das Produkt „Hochzeitshomepage" (aktuell 500 €) international über Pinterest vermarkten und 1.000 Mal verkaufen.

**Umsatzziel:** 1.000 × 500 € = 500.000 €

---

## Voraussetzungen (vor der Strategie klären)

| Frage | Antwort bestimmt alles |
|---|---|
| Ist die Homepage ein Template/Baukasten? | → skalierbar, 1.000× realistisch |
| Oder wird jede Seite manuell gebaut? | → Kapazitätsgrenze, 1.000× nicht umsetzbar |
| Welche Sprachen soll das Produkt abdecken? | EN für Start, dann FR/ES/NL? |
| Gibt es einen Self-Service-Checkout? | Stripe + automatische Lieferung/Onboarding |

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

## Produktvoraussetzungen für 1.000 Verkäufe

Damit das Modell skaliert, muss der Kaufprozess vollständig automatisiert sein:

- [ ] Stripe-Checkout ohne manuelle Intervention
- [ ] Automatische Lieferung nach Kauf (Zugang zu Template, Formular, Onboarding-PDF)
- [ ] Self-Service-Onboarding (Brautpaar füllt Fragebogen aus → automatisierter Output)
- [ ] Kein oder minimaler Kundensupport pro Sale
- [ ] Klare Produktbeschreibung in EN auf Landingpage

---

## Offene Fragen / Nächste Schritte

1. **Produktmodell klären:** Template, Generator, oder Done-for-You?
2. **Pinterest-Account aufbauen:** Boards auf DE + EN, organischer Content als Fundament
3. **Englische Landingpage erstellen** (`/en/` oder neue Domain)
4. **Automatisierungs-Stack festlegen:** Stripe → Zapier/Make → Lieferung
5. **Steuerberater:** Umsatzsteuer bei internationalen B2C-Digitalleistungen
6. **Pilotlauf:** 10 Sales manuell testen, dann automatisieren

---

## Bewertung (Stand 2026-07-26)

| Dimension | Einschätzung |
|---|---|
| Marktpotenzial | ★★★★★ – Hochzeit ist global, Pinterest ist ideal |
| Technische Machbarkeit | ★★★★☆ – Geo-Routing einfach, Automatisierung etwas Aufwand |
| Skalierbarkeit | ★★★☆☆ – Abhängig vom Produktmodell (Template vs. manuell) |
| Risiko | Steuerliche Komplexität bei Auslandsverkäufen; Markenname sehr regional |
| Priorität | Nach Klärung des Produktmodells direkt umsetzbar |

---

_Letzte Aktualisierung: 2026-07-26_
