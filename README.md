# OM Gesprekken — PWA

Kennismakingsgesprekken bijhouden, patronen analyseren en bevindingsnotities genereren voor OM Parket Den Haag.

## Installeren op GitHub Pages

### 1. Repository aanmaken
- Ga naar [github.com/new](https://github.com/new)
- Naam: `om-gesprekken` (of een naam naar keuze)
- Zet op **Public** (GitHub Pages vereist dit bij een gratis account)
- Klik **Create repository**

### 2. Bestanden uploaden
Upload de volgende bestanden naar de repository:
- `index.html`
- `sw.js`
- `manifest.json`
- `icon-192.png` *(optioneel — zie hieronder)*
- `icon-512.png` *(optioneel)*

Dit kan via de GitHub interface (Add file → Upload files) of via git:

```bash
git init
git add .
git commit -m "Initial commit"
git branch -M main
git remote add origin https://github.com/JOUWGEBRUIKERSNAAM/om-gesprekken.git
git push -u origin main
```

### 3. GitHub Pages aanzetten
- Ga naar **Settings** → **Pages**
- Bij **Source**: kies **Deploy from a branch**
- Branch: **main**, folder: **/ (root)**
- Klik **Save**

Na 1-2 minuten is de app beschikbaar op:
`https://JOUWGEBRUIKERSNAAM.github.io/om-gesprekken/`

### 4. App instellen
- Open de URL
- Voer je Anthropic API-sleutel in (via [console.anthropic.com](https://console.anthropic.com))
- De sleutel wordt lokaal opgeslagen in je browser

### 5. Op je telefoon installeren
- Open de URL in Safari (iOS) of Chrome (Android)
- Tik op **Delen** → **Voeg toe aan beginscherm**
- De app werkt daarna als een gewone app, ook offline

---

## Icons maken (optioneel)

Als je geen eigen icons hebt werkt de app gewoon, maar je kunt simpele placeholder icons aanmaken via [favicon.io](https://favicon.io) of [realfavicongenerator.net](https://realfavicongenerator.net).

---

## Gegevens

Alle gesprekken worden opgeslagen in de **lokale opslag van je browser** (localStorage). Ze verlaten je apparaat niet, tenzij je de AI-functies gebruikt — die sturen de gespreksinhoud naar de Anthropic API.

Wil je je gegevens op meerdere apparaten beschikbaar hebben, exporteer ze dan via kopiëren uit de patronenanalyse of notitie.

---

## API-sleutel beveiliging

De API-sleutel staat in je browser en is zichtbaar als iemand toegang heeft tot je apparaat. Voor een publieke omgeving is een serverless proxy (Cloudflare Worker, Vercel Function) veiliger. Voor persoonlijk gebruik is dit afdoende.
