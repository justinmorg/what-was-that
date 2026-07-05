# What was that?

Hear a plane go over? Open the site, press **Scan the sky**, and it identifies the
aircraft overhead at your location right now — with a compass telling you exactly
where in the sky to look.

## What it shows for each aircraft

- **Where to look** — bearing compass + elevation angle + distance (the signature feature)
- Callsign, registration, and ICAO hex code
- Aircraft type (e.g. Boeing 737-800)
- Altitude, ground speed, heading, and climb/descent rate
- Departure → destination route with airport names (when in the public route DB)
- A photo of the actual airframe, credited to the photographer via Planespotters.net

If nothing is within range: **"Nothing overhead!"**

## Data sources (all free, no API keys)

| Data | Source |
|---|---|
| Live aircraft positions | [adsb.lol](https://api.adsb.lol) community ADS-B network |
| Flight routes | adsb.lol route database (`/api/0/routeset`) |
| Aircraft photos | [Planespotters.net public API](https://www.planespotters.net) |

Notes:
- Routes are best-effort. Private, cargo-repositioning, and military flights often
  have no public route.
- Your location never touches this repo's code beyond being sent as a search point
  to the adsb.lol API. Nothing is stored.

## Running it

It's a single static `index.html` — no build step, no dependencies.

**Easiest: GitHub Pages**
1. Repo → Settings → Pages
2. Source: *Deploy from a branch*, branch `main`, folder `/ (root)`
3. Visit `https://<username>.github.io/what-was-that/`

(Geolocation requires HTTPS, which GitHub Pages provides. Opening the file
directly from disk also works in most browsers via `localhost`, e.g.
`python3 -m http.server`.)

## Range setting

- **5 nm** — right on top of you
- **10 nm** (default) — roughly anything you could hear or see clearly
- **25 nm** — the wider sky, including high-altitude cruisers
