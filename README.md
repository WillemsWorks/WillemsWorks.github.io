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

## Procedure nieuw artikel (vaste regel sinds 11 november 2026)
1. **Concept als markdown.** Elk nieuw artikel begint als `.md` in het Claude-project (`claude/BLOG-[Titel]_concept_v0_x.md`, nieuwe versie = nieuw bestand). Paul krijgt het bestand en reviewt daar.
2. **Niets op de site tijdens de conceptfase.** Geen HTML-pagina, geen regel in `posts.json`, geen links vanuit andere artikelen. Reden: de titel kan nog veranderen, en de slug (URL) volgt de titel. Een URL die al geïndexeerd is en later verandert, kost vindbaarheid.
3. **Plaatsen pas na akkoord.** Pas als Paul zegt "plaats het artikel" wordt de titel definitief, de slug vastgelegd en de pagina gebouwd (stappen hieronder). Daarna verandert de slug niet meer.
4. Publicatiedatum: een woensdagavond (20:00). Geantedateerde planning (11 nov 2026): NS 15 jul · vakantie-artikelen 5 aug, 26 aug, 16 sep (drie weken ertussen; Goeierikken en slechterikken, De markt en de supermarkt, Titanic — volgorde nog te bevestigen) · Sanquin 7 okt · banaan 4 nov. Daarna (zelfde ritme, eerder in de tijd): 24 jun, 3 jun, 13 mei, 22 apr 2026 voor IKEA Museum, Het merk achter de CEO (Tesla), Matras/spijkerbroek en Vier jaar Hoomie — volgorde nog te bepalen; stevig bewerkt (eigen invalshoek + GOV-koppeling).
5. Links vanuit andere artikelen ("Lees ook") komen er pas bij het plaatsen bij.

## Nieuw artikel plaatsen
1. Kopieer `blog/_sjabloon.html` naar `blog/[slug].html` en vul alle [PLAATSHOUDERS] in
2. Voeg bovenaan `blog/posts.json` een regel toe
3. Het artikel op de site is de bron (canonical). Substack krijgt een kortere, afgeleide versie met link hierheen.

## Nog te doen vóór livegang
- `noindex`-regel verwijderen uit `index.html` en `blog/index.html`
- Fonts en beelden lokaal zetten in plaats van via framerusercontent.com (licentie PP Formula checken)
- `CNAME`-bestand met `www.willemsworks.nl` toevoegen en DNS omzetten

## Afspraken blog (8 november 2026)
- Nieuwe artikelen: volledig artikel op de site (canonical), Substack krijgt een kortere afgeleide versie met link hierheen, LinkedIn-posts zonder link.
- Eerste artikel: "Mijn tante en de banaan".
- Daarna de bestaande Substack-artikelen één voor één overzetten, **stevig bewerkt**: eigen invalshoek, koppeling met het GOV-doc erachter (expliciet of impliciet) en een korte terugblik. Daardoor is de site-versie een eigen stuk en mag hij de bron zijn. Elk overgezet artikel is meteen een toets of de GOV-koppeling klopt.
- Boekingen blijven via Bookable lopen (geen Calendly).

## Thumbnails in de bloglijst
`posts.json` heeft een optioneel veld `beeld` (pad naar een afbeelding in de repo, bijv. `/blog/img/slug.jpg`). Zonder beeld toont de kaart het WillemsWorks-logo op donkerpaars. Een Getty-embed kan niet als thumbnail dienen; alleen eigen of gelicenseerde beelden.

## Vaste regel: privacy van kinderen (11 november 2026)
Geen namen van Pauls kinderen op de site. In artikelen staat "mijn dochter" of "onze dochter". Het persoonlijke zit in de details, niet in de naam. Reden (Paul): "het gaat hier niet om mij maar om haar."

## Livegang (voorbereid 11 november 2026, branch `livegang`)
In deze branch staat alles klaar; `main` blijft preview tot de livegang.
- noindex verwijderd (behalve `_sjabloon.html` en `404.html`)
- `CNAME` (www.willemsworks.nl), `sitemap.xml`, `robots.txt`, `404.html`
- canonical/og-tags op home en blogoverzicht; BlogPosting-gegevens (JSON-LD) per artikel
Bij de livegang: `livegang` mergen naar `main`, daarna GitHub-domeininstelling, Hostnet-DNS (MX ongemoeid), Framer-domein loskoppelen, HTTPS aan, Search Console + sitemap indienen.
Nieuwe artikelen na de livegang: JSON-LD-blok meenemen en sitemap.xml bijwerken.
