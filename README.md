# Wimmelton Website

Een moderne, professionele website voor Wimmelton - gespecialiseerd in data analyses en visualisaties.

## 🚀 Features

- **Moderne Vue.js 3** met Composition API
- **Responsive design** voor alle apparaten
- **Zwart/wit huisstijl** - professioneel en elegant
- **Volledig functionele pagina's**: Home, Diensten, Portfolio, Contact
- **Interactieve elementen** zoals portfolio filters en FAQ accordions
- **Contact formulier** met validatie
- **SEO-vriendelijk** met proper routing

## 🛠️ Technische Stack

- **Frontend**: Vue.js 3 + TypeScript
- **Styling**: CSS3 met moderne features (Grid, Flexbox, Animations)
- **Build Tool**: Vite
- **Deployment**: Netlify-ready

## 📱 Pagina's

### Home
- Hero sectie met data visualisatie animaties
- Feature highlights
- Proces uitleg
- Call-to-action

### Diensten
- Uitgebreide service beschrijvingen
- Werkwijze uitleg
- Prijzen en pakketten
- Contact CTA

### Portfolio
- Project showcase met filters
- Case studies
- Klanten testimonials
- Interactieve project details

### Contact
- Contact formulier
- Contact informatie
- FAQ sectie
- Kantooruren

## 🎨 Design Features

- **Kleurpalet**: Zwart (#0a0a0a), Wit (#ffffff), Grijs (#cccccc)
- **Typografie**: Inter font family voor moderne uitstraling
- **Animaties**: Smooth transitions en hover effects
- **Gradients**: Subtiele witte gradients voor accenten
- **Cards**: Glasmorphism effect met transparantie

## 🚀 Lokale Ontwikkeling

```bash
# Installeer dependencies
npm install

# Start development server
npm run dev

# Build voor productie
npm run build

# Preview productie build
npm run preview
```

## 🌐 Deployment naar Netlify

1. **Push naar GitHub**:
   ```bash
   git add .
   git commit -m "Initial commit"
   git push origin main
   ```

2. **Netlify Setup**:
   - Ga naar [netlify.com](https://netlify.com)
   - Klik "New site from Git"
   - Verbind met je GitHub repository
   - Build command: `npm run build`
   - Publish directory: `dist`

3. **Automatische Deploy**:
   - Elke push naar main branch triggert automatische deploy
   - Netlify.toml zorgt voor proper configuratie

## 📁 Project Structuur

```
src/
├── views/           # Pagina componenten
│   ├── Home.vue
│   ├── Diensten.vue
│   ├── Portfolio.vue
│   └── Contact.vue
├── router/          # Vue Router configuratie
│   └── index.js
├── App.vue          # Hoofdcomponent
└── main.js          # App entry point
```

## 🎯 Customisatie

### Logo Aanpassen
- Vervang de "W" in de logo-icon div in `App.vue`
- Pas kleuren aan in de CSS variabelen

### Kleuren Wijzigen
- Zoek naar `#0a0a0a`, `#ffffff`, `#cccccc` in de CSS
- Vervang met je gewenste kleuren

### Content Bijwerken
- Alle tekst staat in de Vue componenten
- Pas de data arrays aan in Portfolio.vue voor projecten
- Update contact informatie in Contact.vue

## 📧 Contact

Voor vragen over de website of customisatie:
- **E-mail**: info@wimmelton.nl
- **Telefoon**: +31 6 12345678

## 📄 Licentie

Dit project is gemaakt voor Wimmelton. Alle rechten voorbehouden.

---

**Wimmelton** - Data analyses en visualisaties die resultaten leveren
