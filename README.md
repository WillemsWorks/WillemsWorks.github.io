# willemsworks.nl

Website van Paul Willems (WillemsWorks). Statische site op GitHub Pages, onderhouden vanuit Claude.
Ontwerp: A Studio Called Quest (origineel in Framer), in november 2026 nagebouwd als HTML/CSS.

## Structuur
- `index.html` — de one-pager
- `assets/styles.css` — alle opmaak (kleuren, fonts, componenten)
- `blog/index.html` — overzicht van alle artikelen (leest `blog/posts.json`)
- `blog/posts.json` — lijst van artikelen, nieuwste eerst: `{slug, titel, datum, intro}`
- `blog/_sjabloon.html` — sjabloon voor een nieuw artikel
- De GOV Library (repo `gov-library`) verschijnt automatisch onder `/gov-library/`

## Nieuw artikel plaatsen
1. Kopieer `blog/_sjabloon.html` naar `blog/[slug].html` en vul alle [PLAATSHOUDERS] in
2. Voeg bovenaan `blog/posts.json` een regel toe
3. Het artikel op de site is de bron (canonical). Substack krijgt een kortere, afgeleide versie met link hierheen.

## Nog te doen vóór livegang
- `noindex`-regel verwijderen uit `index.html` en `blog/index.html`
- Fonts en beelden lokaal zetten in plaats van via framerusercontent.com (licentie PP Formula checken)
- `CNAME`-bestand met `www.willemsworks.nl` toevoegen en DNS omzetten
