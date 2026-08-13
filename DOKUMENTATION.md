# IT-Dokumentation: Praxis für Psychotherapie Jule Schröder

## 📋 Projektübersicht

**Projektname:** Praxis für Psychotherapie — Jule Schröder  
**Website:** https://psychotherapie-schroeder.com  
**Repository:** https://github.com/Julezz79/website  
**Deployment:** GitHub Pages  
**Letztes Update:** August 2026

---

## 📁 Dateistruktur

```
/Users/user/Desktop/Website/
├── index.html                 # Hauptseite (Startseite)
├── impressum.html             # Impressum (Rechtliche Informationen)
├── datenschutz.html           # Datenschutzerklärung (DSGVO)
├── DOKUMENTATION.md           # Diese Dokumentation
├── CNAME                       # Domain-Konfiguration für GitHub Pages
├── bilder/                    # Bildordner
│   ├── hero.jpg               # Hero-Bild (Jule auf Stuhl)
│   ├── praxisraum.jpg         # Praxisraum-Foto
│   └── ueber-mich.jpg         # Porträt (Über Mich Sektion)
└── .claude/
    └── launch.json            # Development Server Konfiguration
```

---

## 🌐 Deployment & Hosting

### GitHub Pages Setup
- **Provider:** GitHub Pages (kostenlos)
- **Repository:** Julezz79/website
- **Branch:** `main` (automatisches Deployment)
- **URL:** https://psychotherapie-schroeder.com (via Custom Domain)

### Custom Domain
- **Registrar:** INWX (inwx.de)
- **Domain:** psychotherapie-schroeder.com
- **DNS-Records:**
  - CNAME: `www.psychotherapie-schroeder.com` → `julezz79.github.io`
  - A-Records: Auf GitHub Pages IPs zeigen
- **CNAME-Datei:** Repository Root (GitHub Pages Anforderung)

### Deployment-Prozess
1. Code ändern lokal oder im Editor
2. `git add <datei>`
3. `git commit -m "Beschreibung der Änderung"`
4. `git push`
5. ✅ Live in ~30 Sekunden auf psychotherapie-schroeder.com

---

## 🎨 Responsive Design & Mobile-Optimierung

### Breakpoints
- **Desktop:** Alles über 760px (standard Layout)
- **Mobile/Tablet:** 760px und darunter

### Key Mobile-Optimierungen (760px Breakpoint)

#### Hero-Section (`.hero-shot-panel`)
```css
/* Mobile: Panel schwebt ÜBER dem Foto */
position: absolute;
bottom: 100%;              /* Über dem Bild */
width: 95%;
max-width: 95%;
min-height: 240px;         /* Große Box für Inhalt */
padding: 50px 24px 44px;   /* Großzügige Innenabstände */
display: flex;
flex-direction: column;
justify-content: center;    /* Inhalt vertikal zentriert */
```

**Besonderheit:** Das Panel wird auf Viewports unter 760px über dem Hero-Foto positioniert, nicht daneben. Dadurch nutzt die mobile Version die volle Breite optimal.

#### Green Badge (`.eyebrow`)
```css
/* Nur so breit wie der Text "psych." */
display: inline-flex !important;
width: auto !important;
margin: 0 auto 14px;
```

#### Bilder
- **Raumfoto (.band.mid):** Volle Viewport-Breite auf Mobile
  ```css
  width: 100vw;
  margin-left: calc(-50vw + 50%);  /* Breakout aus Container */
  ```

#### Navigation
- **Desktop:** Horizontal, immer sichtbar
- **Mobile:** Hamburger-Menu, versteckt bis angeklickt
  ```css
  position: fixed;
  inset: 70px 16px auto 16px;
  display: none;  /* Versteckt */
  ```
  Mit JS: `.nav.open` zeigt es an

#### Kontakt-Info
- **Email/Telefon:** `word-break: break-word; overflow-wrap: break-word;`
  → Bricht lange Nummern auf kleinen Displays um

---

## 🔧 Technische Details

### Technologie-Stack
- **HTML:** Minified (Kompression für schnelleres Laden)
- **CSS:** Inline im `<style>` Tag (alles in einer Datei)
- **JavaScript:** Inline im `<script>` Tag (Hamburger-Menu Toggle)
- **Fonts:** Google Fonts (Fraunces, Poppins)
  - Fraunces: Serif-Schrift für Überschriften
  - Poppins: Sans-Serif für Körpertext und UI

### CSS-Variablen (Color Palette)
```css
:root {
  --lime: #c7dc3a;              /* Grünes Highlight-Badge */
  --lime-deep: #92a324;         /* Dunkleres Grün */
  --aubergine: #2d1730;         /* Dunkles Lila/Aubergine */
  --aubergine-soft: #4a2d4d;    /* Helleres Lila */
  --cream: #faf6ee;             /* Creme/Off-White */
  --sand: #f0e9d8;              /* Sandfarbe (Hintergründe) */
  --paper: #fffdf8;             /* Papier-Weiß */
  --ink: #2d1730;               /* Haupttext-Farbe */
  --ink-soft: #5b4b5e;          /* Grauer Text */
  --maxw: 880px;                /* Max Content-Width */
}
```

### JavaScript-Funktionalität
**Hamburger Menu (Mobile Navigation)**
```javascript
const toggle = document.getElementById('menuToggle');
const nav = document.getElementById('nav');

toggle.addEventListener('click', () => nav.classList.toggle('open'));

/* Schließt Menu wenn Link geklickt wird */
nav.querySelectorAll('a').forEach(a => 
  a.addEventListener('click', () => nav.classList.remove('open'))
);
```

---

## 📄 Seiten-Beschreibungen

### 1. index.html (Startseite)
**Inhalt:**
- Hero Section mit Foto + Info-Panel
- Behandlungsangebot
- Über Mich (mit Foto + Qualifikationen)
- Ablauf & Kosten
- Kontakt (mit Karte + Kontaktdaten)

**Key Sections:**
- `#behandlung`: Behandlungsschwerpunkte mit Chips
- `#uebermich`: Portrait + Qualifikationen Grid
- `#ablauf`: Ablauf & Kostenboxen
- `#kontakt`: Kontaktformular & Karte

### 2. impressum.html (Rechtliches)
**Inhalt:**
- Geschäftsinhaber (M.Sc. Psych. Jule Schröder)
- Berufsbezeichnung + Approbation
- Berufshaftpflichtversicherung
- Zuständige Behörden
- Haftungsausschlüsse
- Urheberrecht

### 3. datenschutz.html (DSGVO-Compliance)
**Inhalt:**
- Datenschutzerklärung (vollständig DSGVO-konform)
- Hosting-Information
- Kontaktdaten-Verarbeitung
- SSL/TLS-Verschlüsselung
- Benutzerrechte (Auskunft, Löschung, etc.)
- Beschwerdeverfahren

---

## 🖼️ Bildverwaltung

### Bildformat & Optimierung
- **Format:** JPG (komprimiert)
- **Speicherort:** `/bilder/` Ordner
- **Verwendung:**

| Datei | Zweck | Größe (ungefähr) |
|-------|-------|-----------------|
| `hero.jpg` | Hero-Section (Jule auf Stuhl) | 100-150 KB |
| `praxisraum.jpg` | Praxisraum-Foto (band.mid) | 100-150 KB |
| `ueber-mich.jpg` | Portrait in Über-Mich Section | 80-100 KB |

### Bildoptimierungsrichtlinien
- JPG-Qualität: 80-85% (guter Trade-off zwischen Qualität & Größe)
- Maximale Breite: 1200px
- Responsive: CSS `max-width: 100%` sorgt für Skalierung

---

## 🔄 Development & Testing

### Lokale Entwicklung
```bash
# 1. In Projektordner navigieren
cd /Users/user/Desktop/Website

# 2. HTTP-Server starten (Port 8000)
npm install -g http-server
http-server

# 3. Browser öffnen
http://localhost:8000
```

### Testing-Checklist (vor Push)
- [ ] Desktop: Alle Seiten anschauen
- [ ] Tablet (768px): Responsive Check
- [ ] Mobile (375px): Hamburger-Menu, Panel, Bilder
- [ ] Links funktionieren (Kontakt, Email, Telefon)
- [ ] Formulare testen
- [ ] Performance: Schnelles Laden?
- [ ] SSL/HTTPS funktioniert

---

## 🚀 Häufige Updates & Maintenance

### Content-Updates
**Wo:** Direkt in `index.html` im entsprechenden `<section>` Tag
- Behandlungsangebot ändern? → `#behandlung` Section
- Text in "Über Mich"? → `#uebermich` Section
- Kontaktdaten? → `#kontakt` Section

### Design-Änderungen
**Wo:** `<style>` Tag in `<head>`
- Farben: CSS-Variablen `:root { --variable }`
- Layout: Flexbox/Grid Regeln in jeweiligen `.klassen`
- Mobile: `@media (max-width:760px)` Media Query

### Bilder austauschen
1. Neue Bild in `/bilder/` speichern
2. In HTML `src="bilder/dateiname.jpg"` anpassen
3. `git add`, `git commit`, `git push`

---

## 📞 Kontakt & Support

**Praxis:**
- Adresse: Haus Fortwängler, Stadtstraße 43, 79104 Freiburg im Breisgau
- Telefon: 0157 53739595
- E-Mail: psychotherapie.schroeder@posteo.de

**Website-Administration:**
- GitHub-Account: Julezz79
- Repository: github.com/Julezz79/website

---

## 🔒 Sicherheit & DSGVO

### SSL/TLS
✅ Aktiviert (GitHub Pages + Custom Domain = automatisches HTTPS)

### Datenschutz
✅ Datenschutzerklärung vorhanden (datenschutz.html)
✅ DSGVO-konform (Privacy Policy, Auskunftsrechte, etc.)
✅ Keine Cookies (außer ggf. Google Fonts)

### Impressum
✅ Vorhanden (impressum.html)
✅ Berufliche Informationen vollständig
✅ Haftungsausschlüsse enthalten

---

## 📊 Analytics & Performance

### Aktuelle Setup
- Kein Google Analytics/Tracking aktiv
- Könnte hinzugefügt werden (beachte: DSGVO-Consent notwendig)

### Ladezeit
- ~1-2 Sekunden (abhängig von Internetverbindung)
- Minified HTML hilft bei schnellerem Laden
- Bilder sollten regelmäßig optimiert werden

---

## 🔄 Git & Versionskontrolle

### Commit-Workflow
```bash
git status                    # Welche Dateien ändern?
git add index.html           # Datei zum Commit hinzufügen
git commit -m "Beschreibung" # Commit mit Nachricht
git push                     # Zu GitHub pushen (= Live!)
```

### Wichtige Commits (letzter Stand)
```
c96bdf6 - Make band.mid image full viewport width on mobile
9b6ef10 - Remove margin-bottom from hero-shot on mobile
e2a2372 - Force eyebrow badge to fit content
...
```

---

## ⚙️ Konfigurationsdateien

### CNAME
```
psychotherapie-schroeder.com
```
→ Sagt GitHub Pages, welche Domain verwendet wird

### .claude/launch.json
```json
{
  "version": "0.0.1",
  "configurations": [{
    "name": "website",
    "runtimeExecutable": "npm",
    "runtimeArgs": ["install", "-g", "http-server"],
    "port": 8000
  }]
}
```
→ Konfiguration für lokalen Development Server

---

## 📈 Zukünftige Verbesserungen (Optional)

- [ ] Terminbuchungssystem integrieren
- [ ] Kontaktformular mit Validierung
- [ ] Bilderoptimierung (WebP Format)
- [ ] Dark Mode Toggle
- [ ] Mehrsprachigkeit (Englisch)
- [ ] Blog-Bereich für Therapie-Tipps
- [ ] Newsletter-Anmeldung

---

## 📝 Versionsverlauf

| Version | Datum | Änderungen |
|---------|-------|-----------|
| 1.0 | Aug 2026 | Initiales Launch, Responsive Design, Mobile-Optimierung |
| 1.1 | Aug 2026 | Hero Panel über Foto, Badge-Größe angepasst, White Space entfernt |

---

**Zuletzt aktualisiert:** 13. August 2026  
**Dokumentation erstellt mit:** Claude Code Assistant
