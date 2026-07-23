# GTA V Style Map — New England

A personal navigation web app that renders real-world New England in the style of the *Grand Theft Auto V* pause-menu map — and works like a real nav app. Built as a single self-contained HTML page, entirely on free and open services, with no API keys and no accounts.

**Live map:** https://jfalcone456.github.io/GTA-V-MAP/

Open it on a phone and use *Share → Add to Home Screen* to run it full-screen like a native app.

## Features

- GTA V pause-menu cartography: charcoal land, near-black water with a soft coastal shelf, white-to-gray road hierarchy, film grain and vignette
- 20 toggleable blip categories (police, gas, food, hotels, barbers, and more) drawn from OpenStreetMap data, with a GTA-style legend — tap a category to find the nearest ones, hold to hide it
- Tap any blip for a place card: live open/closed status, address, hours, phone, website, and distance
- Waypoints with real turn-by-turn routing, route bar with distance/time/live ETA, and a directions list — route line in five selectable colors with a matching compass waypoint marker
- Live GPS tracking with an HD re-creation of the player arrow, heading rotation, speed readout, and automatic re-routing as you move
- Search that understands both addresses and nearby chain stores, biased around your start point
- Safehouse system: set any location as home, route from it by default, drop points of interest with a long press
- Current-area name in the corner (neighborhood, town, or city depending on zoom) with the state abbreviation, gameplay-style

## The native iOS app

This map also exists as a real iPhone app: same GTA cartography and blips, plus voice turn-by-turn navigation and TomTom live traffic. It's built on MapLibre Native and the MapLibre Navigation SDK, sideloaded with a free Apple ID. The app source lives in a separate private repo (it carries an API key). See ROADMAP.md for where the project is headed next.

## Built with

This project stands on free, open infrastructure. Credit and thanks to:

- **[OpenStreetMap](https://www.openstreetmap.org/copyright)** contributors — all map data, place data, and business details (© OpenStreetMap contributors, ODbL)
- **[OpenFreeMap](https://openfreemap.org/)** — free vector tile hosting of OpenStreetMap data
- **[MapLibre GL JS](https://maplibre.org/)** — open-source map rendering engine (BSD-3-Clause)
- **[OSRM](https://project-osrm.org/)** (Open Source Routing Machine) — turn-by-turn route calculation via its public demo server
- **[Nominatim](https://nominatim.org/)** — geocoding, reverse geocoding, and address lookups
- **[Overpass API](https://overpass-api.de/)** — nearby-place and place-detail queries (with the [Kumi Systems](https://overpass.kumi.systems/) mirror as fallback)
- **[Photon](https://photon.komoot.io/)** by Komoot — fuzzy, location-biased search-as-you-type
- **[TomTom](https://developer.tomtom.com/)** — live traffic tiles in the iOS app (free developer tier)
- **[MapLibre Navigation iOS](https://github.com/maplibre/maplibre-navigation-ios)** — turn-by-turn navigation in the iOS app
- **[Oswald](https://fonts.google.com/specimen/Oswald)** and **[Kaushan Script](https://fonts.google.com/specimen/Kaushan+Script)** — fonts via Google Fonts (Open Font License), standing in for the game's Chalet and House Script typefaces

## Disclaimer

This is a non-commercial fan project for personal use. It is not affiliated with, endorsed by, or connected to Rockstar Games or Take-Two Interactive. *Grand Theft Auto* and its visual style are the property of Rockstar Games; all map icons and artwork in this project are original re-creations inspired by the game's UI. Map style aside, all geographic data comes from OpenStreetMap and its contributors.

## How it works

Everything lives in one `index.html`: a custom MapLibre style sheet recolors OpenStreetMap vector tiles into the GTA palette, SVG blip icons are generated inline, and routing/search/place details are fetched on demand from OSRM, Nominatim, and Overpass. There is no build step, no backend, and nothing to install — GitHub Pages serves the file as-is.
