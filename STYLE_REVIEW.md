# Portfolio Review

## Gefundene Punkte

- Das ursprüngliche Styling war fast vollständig in `src/style.css` hart verdrahtet. Dadurch kamen dunkler Hintergrund, helle Schrift, weiße Transparenz-Karten und lila/grüne Akzente nicht aus einem gemeinsamen Theme.
- Die Startseite hatte bereits einen soften grünen Ansatz, die restliche Seite blieb aber optisch im dunklen Stil. Ursache waren globale Farben wie `#0f1117`, `#f3f3ee`, `#d7d9e3` und transparente weiße Karten.
- Im Projekt lagen noch Template-Dateien von Vite/Vue: `HelloWorld.vue`, `ShowcaseSection.vue`, Vue/Vite-Assets, Vite-README und ein lila Vite-Favicon.
- `index.html` war noch auf `lang="en"` und `portfolio-inga` gesetzt.
- Der Build war nach dem Entpacken zuerst nicht ausführbar, weil `node_modules/.bin` keine Ausführungsrechte hatte und eine optionale native Abhängigkeit fehlte. Nach `npm install` lief `npm run build` erfolgreich.

## Umgesetzt

- Neues helles, einheitliches Soft-Green/Pastell-Theme mit CSS-Variablen.
- Einheitliche Farben für Body, Hero, Navigation, Cards, Buttons, Tags, Listen und Kontaktbereich.
- Bessere Hover- und Focus-States für Links und Buttons.
- Mobile Abstände und Scroll-Verhalten verbessert.
- Navigation mit `aria-label` ergänzt und Logo-Link auf `#top` geändert.
- `index.html` auf Deutsch gestellt, Seitentitel und Meta-Description angepasst.
- Unbenutzte Template-Komponenten und Assets entfernt.
- README durch ein echtes Projekt-README ersetzt.
- Neues grünes Favicon erstellt.

## Test

```bash
npm install
npm run build
```

Ergebnis: Build erfolgreich.
