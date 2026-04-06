# Taxipoint - Taxi Service Website

A modern, responsive landing page for **Taxipoint**, a taxi service operating 24/7 across the Netherlands. Built with vanilla HTML, CSS, and JavaScript — optimized for GitHub Pages deployment.

![License](https://img.shields.io/badge/license-MIT-blue.svg)
![GitHub Pages](https://img.shields.io/badge/deploy-GitHub%20Pages-brightgreen)

## 🚕 Live Demo

**[View Live Site](https://robinslevel.github.io/getataxi/)**

---

## ✨ Features

### Core Functionality
- **Multi-language Support** — Dutch (NL), English (EN), and Spanish (ES) with instant language switching
- **Dark/Light Theme** — Toggleable theme with system preference detection and localStorage persistence
- **Responsive Design** — Mobile-first layout with hamburger menu for smaller screens
- **Booking Form** — Contact form with car preference pre-selection from vehicle cards

### Performance & SEO
- **Zero Dependencies** — Pure HTML, CSS, and vanilla JavaScript
- **Optimized Loading** — Minimal assets, no external frameworks
- **SEO Ready** — Complete meta tags, Open Graph, Twitter Cards, and JSON-LD structured data
- **Accessible** — Semantic HTML, ARIA labels, and reduced-motion support

### User Experience
- **Sticky Header** — Navigation stays visible with blur effect
- **Smooth Interactions** — CSS transitions for theme changes and hover states
- **Print Styles** — Optimized layout for printing contact information
- **Custom 404 Page** — Branded error page for GitHub Pages

---

## 📁 Project Structure

```
getataxi/
├── index.html          # Main landing page
├── 404.html            # Custom 404 error page
├── README.md           # Project documentation
├── script/
│   └── script.js       # Language switching, theme toggle, form handling
└── style/
    └── styles.css      # All styles including dark theme and print styles
```

---

## 🛠️ Tech Stack

| Technology | Purpose |
|------------|---------|
| HTML5 | Semantic markup |
| CSS3 | Styling, CSS variables, Grid, Flexbox |
| JavaScript (ES6+) | Interactivity, i18n, theme management |
| GitHub Pages | Hosting |

---

## 🚀 Getting Started

### Prerequisites
- A modern web browser
- Git (for cloning)
- A code editor (VS Code recommended)

### Local Development

1. **Clone the repository**
   ```bash
   git clone https://github.com/robinslevel/getataxi.git
   cd getataxi
   ```

2. **Open in browser**
   
   Simply open `index.html` in your browser, or use a local server:
   
   ```bash
   # Using Python
   python -m http.server 8000
   
   # Using Node.js (npx)
   npx serve
   
   # Using VS Code
   # Install "Live Server" extension and click "Go Live"
   ```

3. **View the site**
   
   Navigate to `http://localhost:8000` (or the port shown)

---

## 🌐 Deploying to GitHub Pages

### Option 1: From GitHub Settings (Recommended)

1. Push your code to GitHub
2. Go to your repository → **Settings** → **Pages**
3. Under "Source", select **Deploy from a branch**
4. Choose `main` branch and `/ (root)` folder
5. Click **Save**
6. Your site will be live at `https://<username>.github.io/getataxi/`

### Option 2: Using GitHub Actions

The site works out of the box with GitHub Pages. No build step required.

---

## 🎨 Customization

### Changing Colors

Edit the CSS variables in `style/styles.css`:

```css
:root {
  --primary: #2563eb;      /* Main brand color */
  --primary2: #22c55e;     /* Secondary/accent color */
  --bg: #f6f7fb;           /* Light theme background */
  --surface: #ffffff;      /* Card backgrounds */
  --text: #0f172a;         /* Main text color */
}

:root[data-theme="dark"] {
  --bg: #0b1220;           /* Dark theme background */
  --surface: #0f1a30;      /* Dark card backgrounds */
  --text: #e5e7eb;         /* Dark theme text */
}
```

### Adding/Editing Translations

Edit the `translations` object in `script/script.js`:

```javascript
const translations = {
  nl: {
    hero_title: "Taxi in Nederland",
    // ... add more keys
  },
  en: {
    hero_title: "Taxi in the Netherlands",
    // ... add more keys
  },
  // Add new language
  de: {
    hero_title: "Taxi in den Niederlanden",
    // ...
  }
};
```

Then add the language button in `index.html`:
```html
<button class="lang__btn" type="button" data-lang="de" aria-label="Deutsch">DE</button>
```

### Updating Contact Information

Search and replace these values in `index.html`:
- Phone: `+31203586204`
- Email: `info@taxipoint.nl`
- WhatsApp: `wa.me/31203586204`

Also update the JSON-LD structured data in the `<head>` section.

### Adding Hero Image

Replace the placeholder in the hero section:

```html
<!-- Before -->
<div class="media-card" role="img" aria-label="Taxi afbeelding placeholder">
  <p>Jouw hero afbeelding komt hier</p>
</div>

<!-- After -->
<img 
  src="images/hero.jpg" 
  alt="Taxipoint taxi service" 
  class="hero__image"
  loading="lazy"
/>
```

---

## 📱 Browser Support

| Browser | Supported |
|---------|-----------|
| Chrome | ✅ Latest 2 versions |
| Firefox | ✅ Latest 2 versions |
| Safari | ✅ Latest 2 versions |
| Edge | ✅ Latest 2 versions |
| IE11 | ❌ Not supported |

---

## ♿ Accessibility

This site follows WCAG 2.1 guidelines:

- Semantic HTML structure
- ARIA labels on interactive elements
- Keyboard navigation support
- Focus visible indicators
- Reduced motion support (`prefers-reduced-motion`)
- Sufficient color contrast ratios
- Skip links and logical heading hierarchy

---

## 📄 File Descriptions

### `index.html`
Main landing page containing:
- Top bar with contact info and language switcher
- Sticky header with navigation
- Hero section with CTAs
- Service cards
- Vehicle showcase
- Popular routes
- FAQ accordion
- Contact form with direct contact card
- Footer

### `404.html`
Custom error page for GitHub Pages with:
- Branded design matching main site
- Dark mode support via CSS media query
- Quick links to contact options

### `script/script.js`
JavaScript functionality:
- `translations` object — All UI strings in NL/EN/ES
- `applyLanguage()` — Switches language and updates DOM
- Theme toggle with localStorage persistence
- Mobile menu toggle
- Car pre-selection for booking form
- Form submission handler (placeholder)

### `style/styles.css`
Complete styling including:
- CSS custom properties (variables) for theming
- Light and dark theme definitions
- Component styles (cards, buttons, forms)
- Responsive breakpoints
- Print stylesheet
- Accessibility enhancements

---

## 🔧 Form Integration

The booking form currently shows an alert on submission. To integrate with a backend:

### Option A: Formspree (No backend needed)
```html
<form action="https://formspree.io/f/YOUR_FORM_ID" method="POST">
```

### Option B: WhatsApp Direct
```javascript
bookingForm.addEventListener("submit", (e) => {
  e.preventDefault();
  const data = new FormData(bookingForm);
  const text = `Nieuwe aanvraag:\nNaam: ${data.get('name')}\nTel: ${data.get('phone')}\nVan: ${data.get('pickup')}\nNaar: ${data.get('destination')}\nDatum: ${data.get('date')} ${data.get('time')}`;
  window.open(`https://wa.me/31203586204?text=${encodeURIComponent(text)}`);
});
```

### Option C: Email via Mailto
```javascript
bookingForm.addEventListener("submit", (e) => {
  e.preventDefault();
  const data = new FormData(bookingForm);
  const subject = `Taxi aanvraag - ${data.get('name')}`;
  const body = `Van: ${data.get('pickup')}\nNaar: ${data.get('destination')}\nDatum: ${data.get('date')} om ${data.get('time')}`;
  window.location.href = `mailto:info@taxipoint.nl?subject=${encodeURIComponent(subject)}&body=${encodeURIComponent(body)}`;
});
```

---

## 📝 License

This project is licensed under the MIT License — see the [LICENSE](LICENSE) file for details.

---

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

---

## 📞 Contact

**Taxipoint**
- 📞 Phone: +31 20 358 6204
- 💬 WhatsApp: [wa.me/31203586204](https://wa.me/31203586204)
- ✉️ Email: info@taxipoint.nl

---

Made with ❤️ for reliable taxi service in the Netherlands