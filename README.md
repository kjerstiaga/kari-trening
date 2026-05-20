# Min trening 💙 — README

En enkel, tilgjengelig treningsapp for daglig bevegelse og styrketrening.
Laget som én HTML-fil som fungerer direkte i nettleseren — ingen installasjon nødvendig.

---

## Kom i gang

1. Last ned filen `min-trening-v3.html`
2. Åpne den i en nettleser (Chrome, Safari, Firefox)
3. For mobil: send filen til telefonen og åpne i nettleser, eller legg til som snarvei på hjemskjermen

> **Ingen internettforbindelse nødvendig** etter første åpning (fonter lastes fra Google Fonts ved oppstart).

---

## Funksjoner

| Fane | Innhold |
|------|---------|
| 🏠 Hjem | Oversikt og snarveger |
| 🧘 Daglig økt | 10–15 min med avkrysningsliste |
| 💪 Styrke | Styrkeprogram med sett og reps |
| 📋 Logg | Daglig sjekkliste + treningshistorikk |

- **Streak-teller** — viser antall sammenhengende treningsdager
- **Historikk** — lagrer de 20 siste øktene
- **Lokal lagring** — data lagres i nettleseren (ingen konto nødvendig)

---

## Tilgjengelighet — WCAG 2.2

Appen er bygget etter WCAG 2.2 på nivå AA. Her er en oversikt over hva som er ivaretatt:

### Perseptuelt (Principle 1)

| Krav | Tiltak |
|------|--------|
| **1.1.1** Tekstalternativ | `aria-hidden` på dekorative ikoner; meningsbærende tekst alltid tilgjengelig |
| **1.3.1** Informasjon og relasjoner | Ekte `<label>`, `<fieldset>`, `<legend>` for skjemaelement |
| **1.3.2** Meningsfull rekkefølge | Logisk DOM-rekkefølge, visuell og semantisk struktur er lik |
| **1.4.1** Bruk av farge | Aktiv fane markert med **linje** i tillegg til farge |
| **1.4.3** Kontrastforhold tekst | Alle tekstfarger ≥ 4.5:1 mot bakgrunn |
| **1.4.11** Kontrast for ikke-tekst | Knappar og avkryssingsboksar ≥ 3:1 mot bakgrunn |
| **1.4.12** Tekstforstand | Ingen hardkoda `line-height`, `letter-spacing` eller `word-spacing` som blokkerer overskriving |
| **1.4.10** Reflow | Layout fungerer ned til 320px bredde uten horisontal scrolling |

### Opererbar (Principle 2)

| Krav | Tiltak |
|------|--------|
| **2.1.1** Tastatur | Alle funksjoner nåes med Tab, Enter og Space |
| **2.4.1** Hopp over blokker | «Hopp til innhald»-lenke øverst på siden |
| **2.4.3** Fokusrekkefølge | Fokus flyttes til `<h1>` ved sideskifte |
| **2.4.11** Fokus ikke skjult | Fokusert element er alltid synlig |
| **2.4.12** Fokus utseende | Tydeleg fokusring: 3px hvit + 3px blå (dobbel) |
| **2.5.3** Label i navn | Knappetekst matcher visuell tekst |
| **2.5.5** Målstørrelse | Alle knappar og treffflater ≥ 44×44px |
| **2.5.8** Målstørrelse (forbedret) | Avkrysningselement ≥ 52px høyde |
| **2.3.3** Animasjon fra interaksjoner | Respekterer `prefers-reduced-motion` |

### Forståelig (Principle 3)

| Krav | Tiltak |
|------|--------|
| **3.1.1** Sidespråk | `<html lang="no">` |
| **3.3.2** Etiketter eller instruksjoner | Alle skjemafelt har synlig etikett |

### Robust (Principle 4)

| Krav | Tiltak |
|------|--------|
| **4.1.2** Navn, rolle, verdi | Native HTML-element (`<button>`, `<input>`, `<nav>`, `<main>`, `<section>`) gir korrekt rolle automatisk |
| **4.1.3** Statusmeldinger | `aria-live="polite"` varsler skjermlesere ved lagring og streak-oppdatering |

---

## Mobilvennlighet

- **`max-width: 500px`** — sentrert og lesbar på alle skjermstørrelser
- **`env(safe-area-inset-bottom)`** — tab-bar rykker ned på iPhone med hjemknapp-bar
- **`font-size: 18px`** som basis — lettere å lese, spesielt på mindre skjermar
- Ingen `maximum-scale` — brukere kan zoome fritt
- Touch-treffflater ≥ 44px på alle interaktive element

---

## Datalagring

Data lagres lokalt i nettleseren via `localStorage` under nøkkelen `treningslogg`.

```json
[
  { "dato": "20.5.2026", "type": "Daglig økt" },
  { "dato": "21.5.2026", "type": "Styrke" }
]
```

> Sletter du nettleserdata, slettes også treningsloggen.

---

## Filer

| Fil | Beskrivelse |
|-----|-------------|
| `min-trening-v3.html` | Selve appen (én fil, ingen avhengigheter) |
| `README-min-trening.md` | Denne filen |

---

## Teknisk stack

- **Ren HTML/CSS/JavaScript** — ingen rammeverk eller byggsteg
- **Google Fonts** — Nunito (lastes ved oppstart)
- **localStorage** — lokal datalagring
- Testet i Chrome, Safari og Firefox

---

*Laget med ❤️ for daglig bevegelse*
