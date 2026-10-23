# Løft og løp

Et 12-ukers program for sterkere bein og setemuskler som tar hensyn til løpingen, med qi gong, pust og daglige rutiner for bekkenbunn, skulder og nakke. Appen har tidtaker, figurer som viser bevegelsene, forslag til vekt og en logg over det du har gjort.

Hele appen er én HTML-fil. Den kan installeres på telefonen og virker uten nett.

---

## Installer på telefonen

Appen må ligge på en nettadresse med https, for eksempel GitHub Pages. Se [Publisering](#publisering).

**iPhone (Safari):** åpne adressen, trykk Del-knappen og velg **Legg til på Hjem-skjerm**.

**Android (Chrome):** åpne adressen, trykk menyen ⋮ og velg **Installer app** eller **Legg til på startskjermen**.

Etter første åpning starter appen også uten nett. Fontene lagres første gang de lastes.

---

## Innhold

| Fane | Innhold |
|------|---------|
| **Økt** | Dagens økt etter ukeplanen, eller en annen du velger. Tidtaker, hvile, sett og reps, vekt med forslag, lyd og vibrasjon. Skjermen holdes våken under økta. |
| **Uke** | 12-ukers plan i tre faser (Grunnlag, Tung, Hypertrofi) og en vanlig uke. |
| **Logg** | Nakke- og skulderminutter mot ukemålet, daglige rutiner, manuell registrering, siste økter, progresjon på hovedløftene og sikkerhetskopi. |
| **Grunnlag** | Hva programmet bygger på, med kilder. |

Øktene er Styrke A, Styrke B, Kondisjon (rolig eller terskel), Qi gong (Baduanjin), Høst-qi gong, Vagus-pust, Skulder og nakke, og Bekkenbunn.

Uke 1 startet mandag 19. oktober 2026. Startdatoen står i funksjonen `curWeek()` i `index.html`.

---

## Data og sikkerhetskopi

Loggen lagres i nettleseren på enheten (`localStorage`, nøkkel `loft-og-lop`). Den trenger ingen konto, men følger ikke med til andre enheter.

- **Last ned logg** under Logg → Sikkerhetskopi lagrer alt som en JSON-fil.
- **Hent inn logg** slår en fil sammen med det som allerede ligger der. Ingenting blir overskrevet, og samme fil kan hentes inn flere ganger uten at økter dobles.
- Appen ber nettleseren om varig lagring, så loggen ikke ryddes bort når det blir lite plass.
- Sletter du nettstedsdata for adressen, forsvinner loggen. Ta en sikkerhetskopi først.

Åpnes appen som artifact på claude.ai, lagres loggen også i kontoen der. Den loggen flyttes ikke automatisk til en installert versjon.

---

## Tilgjengelighet (WCAG 2.2 AA)

Appen er testet med axe-core (regler for WCAG 2.0, 2.1 og 2.2, nivå A og AA) i alle fire faner og under en pågående økt, i lyst og mørkt tema. Resultatet var ingen brudd. Verktøy finner ikke alt, så det viktigste er også sjekket for hånd:

| Krav | Slik er det løst |
|------|------------------|
| **1.1.1** Ikke-tekstlig innhold | Hver figur har en tekstbeskrivelse av bevegelsen. Ukegrafen og dagsprikkene har tekst for skjermleser. |
| **1.3.1** Informasjon og relasjoner | Overskrifter, lister, tabeller med `scope` og `caption`, og ekte `<label>` på alle felt. |
| **1.4.3** Kontrast for tekst | All tekst har minst 4.5:1 i begge tema, også tempo-teksten i figurene. |
| **1.4.10** Reflow | Ingen sidelengs scrolling ned til 320 px bredde. |
| **1.4.11** Kontrast for ikke-tekst | Kanten rundt skjemafelt og tomme dagsprikker har minst 3:1. |
| **2.1.1** Tastatur | Alt kan brukes med Tab, Enter og mellomrom. |
| **2.3.3** Animasjon | `prefers-reduced-motion` stopper figuranimasjonene og viser en stillestående versjon. |
| **2.4.1** Hopp over blokker | Lenken «Hopp til innhold» kommer først. |
| **2.4.3** Fokusrekkefølge | Fokus blir på samme knapp når visningen tegnes på nytt, og flyttes til hovedknappen ved nytt steg i økta. |
| **2.4.7 / 2.4.11** Synlig fokus | Tydelig fokusring på alt som kan fokuseres, også den skjulte filvelgeren. Fokus skjules ikke bak den faste knapperaden. |
| **2.5.8** Målstørrelse | Knapper og felt er minst 44–48 px høye. |
| **3.1.1** Språk | `<html lang="nb">`. |
| **3.2.5** Endring på forespørsel | Lenker som åpner ny fane sier fra om det til skjermleser. |
| **4.1.2** Navn, rolle, verdi | Valgknapper bruker `aria-pressed`, aktiv fane bruker `aria-current`, og pluss/minus sier hvilket felt de endrer («Vekt (kg) pluss 2,5»). |
| **4.1.3** Statusmeldinger | Nytt steg, pause, lagring og import leses opp via `aria-live`. |

Brukeren kan zoome fritt, fordi `maximum-scale` ikke er satt.

---

## Publisering

Appen trenger ikke noe byggesteg. Med **GitHub Pages**:

1. Gå til repoets **Settings → Pages**.
2. Velg **Deploy from a branch**, grenen `main` og mappen `/ (root)`.
3. Etter et par minutter ligger appen på `https://kjerstiaga.github.io/kari-trening/`.

Åpnes `index.html` rett fra disken (`file://`), virker appen, men den kan ikke installeres eller brukes uten nett.

**Ny versjon:** når `index.html` eller ikonene endres, øk `VERSION` i `sw.js`. Appen henter alltid nyeste versjon når den er på nett, og versjonsnummeret rydder bort gammelt lager.

---

## Filer

| Fil | Hva den er |
|-----|------------|
| `index.html` | Hele appen: HTML, CSS og JavaScript. |
| `manifest.webmanifest` | Navn, farger og ikoner for installasjon. |
| `sw.js` | Service worker som gjør at appen virker uten nett. |
| `icons/` | App-ikon som SVG og PNG (192, 512, maskerbar 512 og 180 for iPhone). |

## Teknisk

- Ren HTML, CSS og JavaScript, uten rammeverk eller byggesteg.
- Fonter: Playfair Display, DM Sans og DM Mono fra Google Fonts.
- Lyst og mørkt tema følger innstillingen på enheten.
