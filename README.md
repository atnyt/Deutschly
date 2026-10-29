# German Pronunciation Verifier

A responsive, mobile-friendly German pronunciation lookup page.

## Features
- Looks up a typed word in structured Wiktionary-derived data through Wiktapi
- Filters results to German entries
- Displays IPA only when the source provides it
- Attempts the dedicated pronunciation endpoint for additional IPA/audio data
- Plays a recorded audio file when a direct audio URL is supplied
- Offers browser/device German text-to-speech as a clearly labelled synthesized fallback
- Shows available glosses, source links, and honest error/no-data messages
- Responsive layout for mobile devices

## Data source and limitations
- Primary API: [Wiktapi quickstart and endpoint docs](https://wiktapi.dev/quickstart)
- Dictionary data is derived from Wiktionary processing. Entries and audio availability vary by word.
- Device speech synthesis is not a native recording and depends on installed voices and browser support.
- This is a learning aid, not a certified pronunciation assessment.

## Run locally
Open `index.html` through a web server or deploy it as a static site. Live lookup requires an internet connection and browser access to `api.wiktapi.dev`.

## Publish with GitHub Pages
1. Open this repository's **Settings → Pages**.
2. Under build/deployment, choose **Deploy from a branch**.
3. Select branch `main` and folder `/(root)`, then save.
4. Wait for the Pages deployment to complete. GitHub will show the published URL in the Pages settings.

If the API blocks browser requests or is temporarily unavailable, the app will show an error instead of fabricating results.
