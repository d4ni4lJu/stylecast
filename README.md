# Stylecast

Outfit suggestions for your weather, season and local style, plus clothing and accessory shops near you.

**Live app:** https://d4ni4lju.github.io/stylecast/

On iPhone, open it in Safari, then tap Share → Add to Home Screen.

## Run it
Location access only works on `https://` or `localhost`, so serve the folder rather than double-clicking the file:

    cd stylecast
    python3 -m http.server 8000
    # then open http://localhost:8000

To put it online for free (it's a single static file), use GitHub Pages, Netlify Drop or Vercel.
On a phone, open the hosted link and choose "Add to Home Screen" to use it like an app.

## What it does
- **Location:** GPS ("Use my location") or a city search
- **Weather and season:** live weather and a 7-day forecast from Open-Meteo. It knows which hemisphere you're in, uses wet/dry seasons in the tropics, and detects Harmattan in West Africa
- **Outfits:** 3 looks based on feels-like temperature, rain, UV and wind, plus what you wear, the occasion and your vibe
- **Local style:** dress-code notes and traditional pieces for 30+ countries (the "Traditional" vibe builds a look around one)
- **My wardrobe:** photograph your clothes (the phone camera works) and tag them in a few taps. The main colour is detected automatically. The first outfit card is then built from your own clothes to suit the weather and occasion: it matches colours, skips things you wore in the last two days, and marks missing pieces. A "Missing for today" line lists gaps. Photos stay in your browser (IndexedDB); use Back up / Restore to move them to another device
- **Brand finder:** pick or type any brand (UNIQLO, GU, Zara, H&M, MUJI…) to find its nearest stores. Names in local scripts, like ユニクロ, are matched too, and when a brand is missing from the map data you get a Google Maps search instead
- **Check stock:** every brand store has a link to that store's own page (when the map data has one) or the brand's official site, where an item page lets you check in-store availability
- **Shops nearby:** clothing, shoes, bags, jewellery, tailors, thrift stores, malls and markets from OpenStreetMap, shown on a map with directions
- **Saved looks:** stored on your device
- **AI stylist chat (optional):** ask Claude what to wear, how to style a piece, what to pack, or send a photo of an outfit for feedback. It automatically sees your weather, season, location, preferences, wardrobe and nearby stores. In the wardrobe, **✦ Auto-tag with AI** fills in an item's name, type, warmth, style and colour from its photo

Everything except the AI features works with no API keys or accounts, using free, open data sources.

## Setting up the AI stylist
1. Create an API key at https://console.anthropic.com/settings/keys and add a little credit. Set a monthly spend limit there.
2. In Stylecast, open **Ask your stylist → ⚿ Key**, paste the key and tap **Save key**.

The key is stored only in your browser and sent only to Anthropic (the app calls Claude directly from your device). You pay Anthropic for what you use: roughly a cent or two per chat message, and less for auto-tagging. Don't save your key on a shared computer, and don't publish the app with a key built in.
