# German Pronunciation Verifier

A mobile-friendly German word lookup workspace designed for careful, source-based pronunciation study.

## Current features

- Looks up a typed German word using Wiktapi's structured, Wiktionary-derived data.
- Filters the response to German entries.
- Displays IPA only when it is actually present in the returned data.
- Queries Wiktapi's dedicated pronunciation endpoint as an additional field source.
- Plays recorded audio only when the API supplies a usable direct audio URL.
- Offers browser/device text-to-speech as a clearly labelled synthetic alternative.
- Shows dictionary glosses when present, source links, clear loading/error states, and no-result guidance.
- Includes example words, recent searches stored locally in the browser, copy-IPA, mobile-responsive layout, keyboard-friendly controls, and reduced-motion support.
- Never fabricates missing IPA or claims synthesized speech is a native recording.

## Data source and limitations

- Primary structured data API: [Wiktapi quickstart and endpoint documentation](https://wiktapi.dev/quickstart).
- Wiktapi data is derived from Wiktionary processing. Coverage, IPA and recorded audio availability vary by word.
- The linked Wiktionary page is a reference for checking the entry; the current app does **not** claim that Wiktionary is being queried as a second independent live API.
- Device speech synthesis depends on browser support and installed German voices. It is not a substitute for recorded native-speaker audio.
- This is a study aid, not a certified pronunciation assessment or speech-scoring system.
- Live lookups require internet access and browser access to `api.wiktapi.dev`. If the service or connection fails, the app reports the problem rather than inventing a result.

## Run locally

Open `index.html` through a local web server or deploy it as a static site. No build step or API key is required for the current client-side version.

## Publish with GitHub Pages

This repository includes `.github/workflows/deploy-pages.yml`, which deploys the root directory with GitHub Actions.

1. Open **Settings → Pages** for this repository.
2. Under **Build and deployment → Source**, select **GitHub Actions** and save.
3. Open the **Actions** tab and wait for **Deploy German Pronunciation Verifier to GitHub Pages** to finish successfully.
4. Confirm the published URL in **Settings → Pages** before sharing it.

Repository: https://github.com/pallobhasan62-hue/German-Pronunciation-Verifier-
