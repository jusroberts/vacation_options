# Vacation Options – Project Plan

A GitHub Pages site comparing Air Canada non-stop Caribbean destinations for late April 2026.
Each destination gets a dedicated research page. An index page links to all destinations.

---

## 1. Repository Structure

```
vacation_options/
├── plan.md                          # This file
├── air_canada_caribbean_nonstop_late_april_2026.md  # Source todo list
├── _config.yml                      # Jekyll configuration
├── _layouts/
│   ├── default.html                 # Base layout (header, footer, nav)
│   └── location.html                # Location page layout (extends default)
├── _includes/
│   └── back_to_index.html           # Reusable "← Back to index" snippet
├── assets/
│   └── css/
│       └── style.css                # Custom styles (clean, readable)
├── index.md                         # Home page – destination index table
└── locations/
    ├── nassau-bahamas.md
    ├── great-exuma-bahamas.md
    ├── montego-bay-jamaica.md
    ├── kingston-jamaica.md
    ├── punta-cana-dominican-republic.md
    ├── varadero-cuba.md
    ├── cayo-coco-cuba.md
    ├── fort-de-france-martinique.md
    ├── pointe-a-pitre-guadeloupe.md
    ├── sint-maarten.md
    ├── antigua.md
    ├── st-kitts.md
    ├── st-lucia.md
    ├── barbados.md
    ├── grenada.md
    ├── aruba.md
    ├── curacao.md
    ├── grand-cayman.md
    ├── providenciales-turks-caicos.md
    └── san-juan-puerto-rico.md
```

---

## 2. GitHub Pages Setup (Jekyll)

GitHub Pages natively renders Jekyll sites — no external build step required.
Markdown files are automatically converted to HTML on push.

### Steps

1. **Create `_config.yml`** in repo root:
   ```yaml
   title: "Caribbean Vacation Options – April 2026"
   description: "Air Canada non-stop destinations compared for late April 2026"
   theme: minima
   url: "https://jusroberts.github.io"
   baseurl: "/vacation_options"
   collections:
     locations:
       output: true
       permalink: /locations/:name/
   ```

2. **Enable GitHub Pages** in the repo settings:
   - Settings → Pages → Source: Deploy from branch → `main` (or the feature branch once merged)
   - GitHub will automatically run Jekyll and publish the site

3. **Create `_layouts/default.html`** – wraps every page with consistent header/footer and a link back to the index.

4. **Create `_layouts/location.html`** – extends `default.html`; adds a structured sidebar or header block showing the destination name, country, and Air Canada route info.

5. **Create `assets/css/style.css`** – minimal custom styles on top of the minima theme (card layout for the index table, section anchors on location pages).

6. **Create `index.md`** with front matter `layout: default` and a Markdown table linking to all 20 destination pages.

---

## 3. Location Page Template

Every file in `locations/` follows this front-matter and section structure:

```markdown
---
layout: location
title: "Nassau, Bahamas"
country: Bahamas
iata: NAS
air_canada_routes:
  - "Toronto (YYZ) – up to 12x weekly"
  - "Ottawa (YOW) – 1x weekly (through April 2026)"
  - "Halifax (YHZ) – 1x weekly (through April 2026)"
last_researched: YYYY-MM-DD
---

## Flights

### Round-Trip Cost (2 passengers, late April 2026)
- **Estimated price range:** $XXX–$XXX CAD per person (economy)
- **Source:** [Google Flights](https://...), [Air Canada](https://...)
- **Notes:** Prices for Mon Apr 20 – Fri Apr 25, 2026 departure window

---

## Hotels & Resorts

> 5-night stay (Monday–Friday), 2 adults

| Hotel | Star Rating | Price/Night (CAD) | Total (5 nights) | Highlights |
|---|---|---|---|---|
| [Hotel Name](https://...) | ⭐⭐⭐⭐ | ~$XXX | ~$X,XXX | All-inclusive, beachfront |
| [Hotel Name](https://...) | ⭐⭐⭐ | ~$XXX | ~$X,XXX | Adults-only, pool bar |

---

## Dining Near Hotels

- [Restaurant Name](https://...) – description, cuisine type, price range
- [Restaurant Name](https://...) – description, cuisine type, price range
- *(For all-inclusive resorts, note what's included vs. extra)*

---

## Transportation

| Option | Cost (estimated) | Notes |
|---|---|---|
| Car rental (economy, 5 days) | ~$XXX CAD | [Rental agency](https://...) |
| Public transit | $X/ride or day pass | Bus/ferry routes |
| Hotel shuttle | Free / $XX | From airport |
| Taxi airport → hotel | ~$XX | Fixed rate or metered |

---

## Beaches

- [Beach Name](https://...) – description, distance from hotel zone, facilities
- [Beach Name](https://...) – description

---

## Attractions

- [Attraction Name](https://...) – description, entry cost
- [Attraction Name](https://...) – description, entry cost

---

## Community Insights

- **Reddit:** [r/Bahamas](https://www.reddit.com/r/Bahamas/) – summary of relevant tips
- **Wikivoyage:** [Nassau](https://en.wikivoyage.org/wiki/Nassau) – key excerpts

---

*[← Back to all destinations]({{ site.baseurl }}/)*
```

---

## 4. Index Page Template (`index.md`)

```markdown
---
layout: default
title: "Caribbean Vacation Options – April 2026"
---

# Caribbean Vacation Options
### Air Canada Non-Stop Destinations – Late April 2026

| Destination | Country | Est. Flight Cost (2 pax) | Est. Hotel/Week | Page |
|---|---|---|---|---|
| Nassau | Bahamas | $X,XXX CAD | $X,XXX CAD | [View →]({{ site.baseurl }}/locations/nassau-bahamas/) |
| ... | ... | ... | ... | ... |

*Prices are estimates based on research conducted in March 2026. Verify before booking.*
```

---

## 5. Research Tasks (per destination)

For each of the 20 destinations, gather the following. Prioritize public sources:
[Wikivoyage](https://en.wikivoyage.org), [Reddit](https://www.reddit.com),
[Google Flights](https://www.google.com/travel/flights),
[Booking.com](https://www.booking.com), [TripAdvisor](https://www.tripadvisor.com).

### 5a. Flights
- Search Air Canada or Google Flights for round-trip fares for 2 passengers,
  departing Mon Apr 20 and returning Fri Apr 25, 2026 (or nearest available dates)
- Note economy vs. premium economy price difference

### 5b. Hotels & Resorts
- Find 2–4 representative options per destination (budget, mid-range, luxury)
- Record nightly rate for the 5-night window above
- Note meal plan (all-inclusive, B&B, room only)
- Note key amenities: beach access, pool, spa, kids/adults-only, etc.

### 5c. Dining
- Identify 3–5 notable restaurants near the main hotel zone
- Note cuisine, price range ($ to $$$$), and any links to menus or reviews

### 5d. Transportation
- Car rental: check local agencies and aggregators (Kayak, Rentalcars.com)
- Public transit: bus, ferry, route taxi options with fares
- Airport transfers: hotel shuttle availability, taxi fixed rates, rideshare availability

### 5e. Beaches & Attractions
- 2–4 notable beaches with descriptions, facilities, and access info
- 2–4 notable non-beach attractions (historical sites, nature, snorkeling, etc.)
- Entry costs where applicable

### 5f. Community Tips
- Check r/[destination] subreddits and travel subreddits for practical tips
- Check Wikivoyage for "Stay safe", "Get around", and "Eat" sections

---

## 6. Implementation Order

### Phase 1 – Site Scaffolding
1. Create `_config.yml`
2. Create `_layouts/default.html`
3. Create `_layouts/location.html`
4. Create `_includes/back_to_index.html`
5. Create `assets/css/style.css`
6. Create `index.md` (skeleton, to be filled as locations are researched)

### Phase 2 – Research & Content (per location, in batches)
Work through all 20 destinations. Suggested grouping by proximity/similarity:

- **Batch A** (Bahamas): Nassau, Great Exuma
- **Batch B** (Jamaica + DR): Montego Bay, Kingston, Punta Cana
- **Batch C** (Cuba): Varadero, Cayo Coco
- **Batch D** (French Antilles): Fort-de-France (Martinique), Pointe-à-Pitre (Guadeloupe)
- **Batch E** (Dutch/French Caribbean): Sint Maarten, Aruba, Curaçao
- **Batch F** (Eastern Caribbean): Antigua, St. Kitts, St. Lucia, Barbados, Grenada
- **Batch G** (Other)**: Grand Cayman, Providenciales (Turks & Caicos), San Juan (Puerto Rico)

For each location:
1. Research all 5 facets (flights, hotels, dining, transport, beaches/attractions)
2. Create `locations/<slug>.md` using the template above
3. Update the index table in `index.md` with estimated costs

### Phase 3 – Polish
1. Verify all links in location pages are live
2. Add estimated cost summary to `index.md` table
3. Final review of formatting and navigation

---

## 7. Markdown → HTML Conversion Notes

GitHub Pages uses **Jekyll with Kramdown** (the default markdown renderer).
The workflow is:

```
push markdown files → GitHub Pages runs Jekyll → HTML served at <username>.github.io/<repo>
```

**No local build step is strictly required**, but you can preview locally with:
```bash
gem install bundler jekyll
bundle init
# Add to Gemfile: gem "github-pages", group: :jekyll_plugins
bundle install
bundle exec jekyll serve
# Visit http://localhost:4000
```

### Front Matter Requirements
Every `.md` file that should be rendered as HTML must have YAML front matter at the top:
```yaml
---
layout: default   # or "location" for destination pages
title: "Page Title"
---
```

Files without front matter are served as raw markdown by GitHub Pages.

---

## 8. Destination List Reference

| # | Destination | Country | Slug | Air Canada Hub(s) |
|---|---|---|---|---|
| 1 | Nassau | Bahamas | `nassau-bahamas` | YYZ, YOW, YHZ |
| 2 | Great Exuma | Bahamas | `great-exuma-bahamas` | YYZ |
| 3 | Montego Bay | Jamaica | `montego-bay-jamaica` | YYZ, YUL, YOW, YHZ |
| 4 | Kingston | Jamaica | `kingston-jamaica` | YYZ |
| 5 | Punta Cana | Dominican Republic | `punta-cana-dominican-republic` | YUL, YYZ |
| 6 | Varadero | Cuba | `varadero-cuba` | YYZ, YUL |
| 7 | Cayo Coco/Guillermo | Cuba | `cayo-coco-cuba` | YYZ, YUL |
| 8 | Fort-de-France | Martinique | `fort-de-france-martinique` | YUL, YQB, YYZ |
| 9 | Pointe-à-Pitre | Guadeloupe | `pointe-a-pitre-guadeloupe` | YYZ |
| 10 | Sint Maarten | Sint Maarten | `sint-maarten` | YYZ, YUL |
| 11 | Antigua | Antigua & Barbuda | `antigua` | YYZ |
| 12 | St. Kitts | St. Kitts & Nevis | `st-kitts` | YYZ |
| 13 | St. Lucia | St. Lucia | `st-lucia` | YYZ |
| 14 | Barbados | Barbados | `barbados` | YYZ |
| 15 | Grenada | Grenada | `grenada` | YYZ |
| 16 | Aruba | Aruba | `aruba` | YYZ, YUL |
| 17 | Curaçao | Curaçao | `curacao` | YYZ |
| 18 | Grand Cayman | Cayman Islands | `grand-cayman` | YYZ |
| 19 | Providenciales | Turks & Caicos | `providenciales-turks-caicos` | YYZ |
| 20 | San Juan | Puerto Rico | `san-juan-puerto-rico` | YYZ, YUL |
