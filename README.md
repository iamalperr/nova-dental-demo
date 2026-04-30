# Nova Dental Clinic — Demo Website

A standalone, premium dental clinic demo website built for [ClinicBridge AI](https://clinicbridge-ai.com/).

## Stack

- Pure HTML + CSS + Vanilla JS (no framework)
- Vite as dev server
- Self-contained injectable AI widget (`clinicbridge-widget.js`)

## Getting Started

```bash
npm install
npm run dev
```

The site will open at [http://localhost:5500](http://localhost:5500).

## Project Structure

```
nova-dental-demo/
├── index.html              # Main page — all sections
├── style.css               # Design system & component styles
├── app.js                  # Navbar, form, i18n (EN/TR), scroll animations
├── clinicbridge-widget.js  # Injectable AI assistant widget
└── images/
    ├── hero.png            # Clinic hero image
    ├── doctor1.png         # Dr. Marcus Reid
    ├── doctor2.png         # Dr. Elena Vasquez
    └── doctor3.png         # Dr. James Holloway
```

## ClinicBridge AI Widget Integration

The widget is loaded as an external script — exactly how real clinics integrate it:

```html
<!-- Local development -->
<script src="clinicbridge-widget.js" data-clinic-id="nova-dental" data-lang="en"></script>

<!-- Production (future) -->
<script src="https://cdn.clinicbridge.ai/widget.js" data-clinic-id="nova-dental"></script>
```

### Widget Public API

```js
window.ClinicBridgeWidget.open()
window.ClinicBridgeWidget.close()
window.ClinicBridgeWidget.sendMessage("Hello")
window.ClinicBridgeWidget.setLang("tr") // switch to Turkish
```

### Configuration Attributes

| Attribute | Default | Description |
|---|---|---|
| `data-clinic-id` | `demo` | Clinic identifier |
| `data-lang` | `en` | Language (`en` or `tr`) |
| `data-disable-bubbles` | `false` | Disable suggestion bubbles |

## Features

- **Hero section** with full-screen clinic photo
- **6 Treatment cards** with hover animations
- **3 Doctor profiles** with portraits
- **6 Patient testimonials**
- **Appointment form** with success state
- **EN / TR language switcher** — updates all page content
- **ClinicBridge AI widget** — injectable, suggestion bubbles, typing indicator, quick replies
- **"Powered by ClinicBridge AI"** footer badge
- Fully responsive (mobile + desktop)

## Build for Production

```bash
npm run build    # outputs to dist/
npm run preview  # preview the production build
```
