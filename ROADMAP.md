# GTA V Nav - What's Next

The project as it stands: the web map is live at jfalcone456.github.io/GTA-V-MAP, and the native app is on the iPhone with all the core features working. This is the pile of ideas for whenever we pick it back up, roughly ordered by how much they'd actually matter day to day.

## Near-term (quick wins)

1. Test voice guidance. Run a route with the ringer on and volume up. If it stays silent, that's the first debugging session of the next round.
2. Wire up re-routing. Right now if you miss a turn, the app keeps showing the old route. Pointing the SDK's re-router at our free routing server fixes that, and it matters before any real road trip.
3. One more pass on blip density. Some downtown areas get crowded. Could hide the busiest categories (food, coffee) by default like the web does, or thin them out at mid zoom.

## Medium effort

4. GTA-themed navigation banners. The turn-by-turn screen still uses the SDK's stock look. Its Style system lets us recolor the banners, fonts, and route line to match the rest of the app.
5. Voice that names streets better. The instruction text we generate is decent but could sound more natural ("take the second exit" instead of "take the roundabout").
6. POI drop on the phone. The web map lets you hold to drop a point of interest. The app's long-press is taken by waypoints, so this needs a different gesture or a button.
7. Route options. Avoid highways, shortest vs fastest. Our routing server supports some of this already.

## Big swings (someday)

8. CarPlay. The SDK supports it, but Apple requires a special entitlement for navigation apps that takes an application and usually a paid developer account. Worth a look if the app becomes a daily driver.
9. Traffic-aware ETAs. TomTom's routing API factors live traffic into the route itself, not just the overlay colors. Needs a converter between their format and the SDK's.
10. Offline maps. MapLibre can cache tiles for offline use. Handy for dead zones in northern New England.
11. Share the app. TestFlight for friends requires the $99 Apple developer account. The web map link works for anyone right now, so this is only if people want the native version.

## Maintenance (already handled, just don't forget)

- The app re-signs every 7 days. Sunday push reminder is set. AltStore automates it if the weekly Xcode run gets old (steps in SETUP.md).
- The web map updates by pushing index.html to the GitHub repo. Phone picks it up on refresh.
- TomTom key lives in Config.swift. Free tier, no card, thousands of requests a day.
